# EfficientToolKit

## "Officially featured by ICAI under the CA PRACTO — Practice Tools Support Initiative"

**One offline Windows app. 30+ tools. Zero data leakage.**

EfficientToolKit is a **free, offline Windows desktop application** built for Chartered Accountants, tax consultants, and accounting professionals. It brings together 30+ productivity tools — File Management, Excel & CSV Processing, PDF Utilities, GST Tools, and GSTR Reconciliation — into a single, easy-to-use app.

> This repository hosts **only the compiled release (.exe) and supporting documentation** — not the application source code. See [Why no source code?](#why-no-source-code) below.

---

## Why this exists

Most professionals reach for free online tools — iLovePDF, SmallPDF, online Excel mergers — to merge a PDF or convert a file. Every time you do that, you upload a client's bank statement, GST return, or PAN details to a server you don't control.

Under India's **Digital Personal Data Protection (DPDP) Act, 2023**, that client data is "personal data," and your firm — not the website — is the **Data Fiduciary** responsible for it. Penalties under the Act run up to ₹250 crore.

**EfficientToolKit never uploads anything, anywhere.** It has no network calls, no telemetry, no cloud dependency. Every file is processed entirely in memory, on your own machine. This is a technical fact, not a privacy policy promise — the app simply has no code path that sends a file anywhere.

| | Online Tool (iLovePDF, etc.) | EfficientToolKit |
|---|---|---|
| Where files are processed | Unknown remote server | Your own laptop |
| Internet required | Yes | **No** |
| File ever leaves your PC | Yes | **Never** |
| DPDP consent/liability risk | Yes | **None — no third party involved** |
| Cost | "Free" (you pay with data) | **Free, for life — no subscription, no login** |

---

## What's inside (30+ tools across 5 categories)

1. **File Explorer** — Folder Walker, Bulk Create Folders, Bulk Rename Files, Auto Sort Files, Duplicate File Finder
2. **Excel & CSV** — Combine CSV/Excel, CSV ↔ XLSX, XLS → XLSX, Split Excel by Column, Mail Merge, Combine Text Files
3. **PDF Tools** — Split (5 modes), Combine, Encrypt/Decrypt, Sort/Reverse, Word → PDF
4. **GST Tools** — GSTR1 / GSTR2B JSON → Excel, Combine GSTR2A / GSTR2B Excel exports
5. **Reconciliation** — GSTR2A vs Purchase Register (5-stage automated matching)
6. **Other Formats** — Merge DOCX Files

Full tool-by-tool documentation: **[MANUAL_GUIDE.md](MANUAL_GUIDE.md)**

---

## Download

Go to the **[Releases](../../releases)** page on this repository and download the latest `EfficientToolKit.exe` from the topmost release.

- No installer, no setup wizard — just double-click the EXE
- Windows may show a SmartScreen warning on first run (the EXE isn't signed with a paid certificate) — click **More info → Run anyway**
- No login, no account, no licence key, ever

> ⚠️ **Download only from this repository's official Releases page.** No other website, link, or shared file is an authorized source for this Software — see [LICENSE.md](LICENSE.md) for full terms. If you want to share EfficientToolKit with a colleague, send them this repository's link — never the file itself.

**System requirements:** Windows 10/11 (64-bit). LibreOffice is required only for the Word → PDF tool — every other tool works without it.

---

## Our promise

- **EfficientToolKit will remain free for life for the entire CA fraternity** — practising Chartered Accountants, CA students, and articleship trainees alike. No paywall, no "free trial," no premium tier, ever
- The toolkit will **keep growing**. Today's 30+ tools are a starting point, not a ceiling
- We will only add features that can run **fully offline**. If a feature requires the internet, it doesn't belong in this app — see [FEATURE_REQUESTS.md](FEATURE_REQUESTS.md)
- The Software must always be obtained from this repository's official Releases page — see [LICENSE.md](LICENSE.md) for the full distribution terms

---

## Got a feature idea or found a bug?

This is a **living app**, and it's built around your feedback. Open an issue, tell us what's missing, and track its progress right here on GitHub.

See **[FEATURE_REQUESTS.md](FEATURE_REQUESTS.md)** for:
- How to submit a request or bug report
- What we will and won't build (offline-only rule)
- Our response-time commitment
- How to get **notified** the moment a new release ships (GitHub Watch, or email)

---

## Why no source code?

This repository intentionally contains **only the compiled release and documentation**, not the application's source code. The "100% offline" guarantee doesn't depend on the source being public — you can verify it yourself with any network monitor (e.g. Windows Firewall logs, Wireshark, Resource Monitor) and you'll see EfficientToolKit makes zero outbound connections. Keeping the source private lets the developer maintain and support the app long-term while still being fully transparent about what it does and doesn't do with your data.

---

## License

Free for personal and professional use by the CA fraternity — Chartered Accountants, CA students, and articleship trainees. No redistribution, re-uploading, or resale is permitted. Must always be downloaded from this repository's official Releases page only. Full terms: **[LICENSE.md](LICENSE.md)**.

---

## Contact

- **Developer:** CA Pranav P Tulshyan
- **Email:** PPtulshyan@gmail.com
- **Mobile / WhatsApp:** +91-7464098001

For feature requests and bug reports, please use [GitHub Issues](../../issues) on this repo instead of email — it keeps requests visible and trackable for everyone.

---

*EfficientToolKit is developed and maintained by CA Pranav P Tulshyan. All file processing happens locally on your machine. No client data is ever transmitted, stored, or shared with any external party.*
