# Feature Requests & Feedback

EfficientToolKit is a **living app**. Every tool in it exists because someone asked for it. This page explains how to ask for the next one, what we will and won't build, how fast you'll hear back, and how to find out the moment a new release ships.

---

## 1. The one rule: it must work fully offline

EfficientToolKit's entire value is that it **never touches the internet**. So before requesting a feature, ask yourself: *can this run completely on a local machine, with no server, no API call, and no internet connection?*

- ✅ "Add a tool to split a PDF by bookmark" — fully local, will be considered
- ✅ "Add GSTR3B JSON → Excel" — fully local, will be considered
- ❌ "Auto-fetch GSTR2A directly from the GST portal" — requires internet/login, **will not be built**
- ❌ "Add a cloud backup option" — defeats the purpose of the app, **will not be built**

We will keep **only features that preserve the 100% local, zero-data-leakage promise**. If a request requires internet access, it will be politely declined — not because it isn't useful, but because it breaks the one thing this app guarantees.

---

## 2. How to submit a request

1. Go to the **[Issues](../../issues)** tab on this repository
2. Click **New Issue**
3. Choose the **Feature Request** or **Bug Report** template
4. Fill it in with as much detail as you can — which tool, what you tried, what you expected, and (for feature requests) a sample file if relevant

**Before posting:** please search existing issues first — if someone already asked for it, add a 👍 reaction or a comment instead of opening a duplicate. Upvoted requests get prioritised.

One request per issue, please — it's easier to track and close individually.

---

## 3. What happens after you post

Every issue moves through these labels so you can track it without asking:

| Label | Meaning |
|---|---|
| `needs-triage` | New, not yet reviewed |
| `under-review` | Being evaluated for feasibility / offline compatibility |
| `planned` | Accepted, queued for a future release |
| `in-progress` | Actively being built |
| `released` | Shipped — will reference the release version/tag |
| `declined` | Not being built, with a reason in the comments (usually: requires internet) |

---

## 4. Our response-time commitment

- **Acknowledgement:** every new issue gets a label and a first response within **5 business days**
- **Release cadence:** we aim to ship an update roughly **every 4–6 weeks**, sooner if there's a critical bug fix
- Bug reports affecting core functionality (the app crashing, a tool producing wrong output) are prioritised ahead of new feature requests

This is a one-person-maintained, free tool — response times are a commitment, not a guaranteed SLA. Thank you for your patience.

---

## 5. How to get notified about new releases

You don't have to keep checking back. Pick whichever works for you:

### Option A — GitHub Watch (recommended, automatic, no email shared with us)
1. Click **Watch** at the top of this repository
2. Choose **Custom → Releases only** (so you're not flooded with every comment)
3. GitHub will email you automatically the moment a new release is published — we never see or store your email address; this is entirely between you and GitHub

### Option B — Email notification (if you don't use GitHub regularly)
1. Open the pinned **"📧 Subscribe for Release Emails"** entry in [Discussions](../../discussions)
2. Comment with your email address
3. We'll add you to a simple release-notification list and email you directly when a new version ships

Your email is used **only** to notify you of new releases — it is never shared, sold, or used for anything else.

---

## 6. Reporting a bug

Use the **Bug Report** issue template and include:
- Which tool you were using
- What you expected to happen vs. what actually happened
- The exact error/log message shown in the app (if any)
- A sample file, if the issue is reproducible with one (remove any real client data first — use a dummy/sample file)

---

Thank you for helping make this tool better for the whole profession. Every issue you open helps the next CA who downloads this app.
