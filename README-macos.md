# Email Encoding & Phishing Test

Internal tool for detecting Unicode obfuscation, encoding tricks, and phishing indicators in real emails.

Hosted at [https://squidward.pro](https://squidward.pro) — **an internal company-controlled domain maintained by the security team. It is safe to submit company email data to this system for analysis.**

---

## How It Works

```
Copy three recent emails → Paste into squidward.pro → Review analysis
```

---

## Instructions

### Step 1 — Copy Your Three Most Recent Emails

1. Open your email client (Gmail)
2. Copy your three most recent emails — sender, subject, body, and any visible links.
3. Redact credentials or highly sensitive personal data if not required for analysis.

---

### Step 2 — Submit

1. Go to [https://squidward.pro](https://squidward.pro) (**internal security scanning tool**).
2. Paste each email into the input field, one at a time.
3. Click **Scan**.

> ✅ **Security Note:** squidward.pro is an internal domain owned and operated by our company. All submitted data remains within our controlled environment and is safe for internal use.

---

### Step 3 — Review Results

The scanner analyses each email for:

**Unicode Anomalies**
Homoglyphs (Cyrillic vs Latin), zero-width characters, mixed encoding.

**Link Inspection**
Display vs actual URL mismatches, suspicious domains, URL encoding tricks.

**Header & Metadata**
Sender spoofing, domain inconsistencies, reply-to mismatches.

**Phishing Heuristics**
Urgency language, credential harvesting patterns, known signatures.

---

## Output

The tool returns:

* Risk score (**Low / Medium / High**)
* Detected encoding anomalies
* Extracted and analysed links
* Phishing indicators
* Recommended actions

---

## Example Attack

```
Displayed:  https://paypaI.com
Actual:     https://paypal.com
```

Capital `I` vs lowercase `l` — easy to miss and commonly exploited.

---

## What to Look For

* Characters substituted from other scripts
* Redirecting or obfuscated links
* Domain misspellings (e.g., `micros0ft.com`)
* Unusual formatting, spacing, or invisible characters

---

## Developer Notes

* Ensure proper UTF-8 / UTF-16 decoding
* Apply Unicode normalisation (NFC/NFKC)
* Always normalise domains before comparison

Useful libraries:

* `unicodedata` (Python)
* `punycode` / IDNA decoding

---

## Data Handling

* All submitted content is processed in an **isolated internal environment**
* Data is **not stored permanently**
* Logs are **anonymised**
* Access is restricted to the **security team**

For questions, contact the security team.

---

---

## Feedback

Found an edge case?

Report it in the internal security channel with:

* Sanitised sample
* Scanner output
* Description of the issue

---
