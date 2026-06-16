# EfficientToolKit — Manual Guide

**Developer:** CA Pranav P Tulshyan 
**Version:** 1.0.0  
**Platform:** Windows 10 / 11 (64-bit)

---

## Table of Contents

1. [What is EfficientToolKit?](#1-what-is-efficienttoolkit)
2. [Why This Tool Matters for CA Firms](#2-why-this-tool-matters-for-ca-firms)
3. [DPDP Act Compliance — Why Local Processing Matters](#3-dpdp-act-compliance--why-local-processing-matters)
4. [Installation & First Launch](#4-installation--first-launch)
5. [How to Use the Application](#5-how-to-use-the-application)
6. [Tool Reference — File Explorer](#6-tool-reference--file-explorer)
7. [Tool Reference — Excel & CSV](#7-tool-reference--excel--csv)
8. [Tool Reference — PDF Tools](#8-tool-reference--pdf-tools)
9. [Tool Reference — GST Tools](#9-tool-reference--gst-tools)
10. [Tool Reference — Reconciliation](#10-tool-reference--reconciliation)
11. [Tool Reference — Other Formats](#11-tool-reference--other-formats)
12. [Output Files & Folder Structure](#12-output-files--folder-structure)
13. [Frequently Asked Questions](#13-frequently-asked-questions)

---

## 1. What is EfficientToolKit?

EfficientToolKit is a **desktop productivity application** built specifically for CA firms, tax consultants, and accounting professionals. It brings together approximately 30 file-processing tools under a single, clean interface — eliminating the need to write scripts, use online converters, or purchase expensive third-party software for routine tasks.

**Key characteristics:**

- Runs entirely on your local machine — no internet connection required
- No subscription, no login, no account creation
- All processing happens within your own computer — files never leave your system
- Dark-themed, professional interface built on the CustomTkinter framework
- Supports bulk operations — run a task on dozens of files in a single click

**Who is it for?**

- Chartered Accountants and their practice teams
- Tax return preparers and GST consultants
- Audit assistants handling large volumes of client documents
- Anyone in an accounting firm who works daily with Excel, PDF, and GST files

---

## 2. Why This Tool Matters for CA Firms

A typical CA firm handles hundreds of files every month — bank statements, purchase registers, GST returns, audit workpapers, client correspondence. Most of this work is repetitive:

> *Split this 200-page PDF into individual invoices. Combine these 12 monthly Excel sheets into one. Convert the GSTR1 JSON downloaded from the portal into a readable Excel. Rename 80 files to follow a consistent naming convention.*

These tasks consume hours each week. EfficientToolKit automates all of them.

### Practical benefits by practice area

| Practice Area | Common Pain Point | Tool That Solves It |
|---|---|---|
| GST Compliance | GSTR1/GSTR2B portal exports are JSON — not readable in Excel | GSTR1 JSON → Excel, GSTR2B JSON → Excel |
| GST Reconciliation | Matching purchase register vs. GSTR2A is time-consuming | GSTR2A vs Purchase Register |
| Audit | Bank statement PDFs need to be split by month | Split PDF (Custom Range) |
| Tax Filing | Multiple client ITR working files need to be merged | Combine Excel, Merge DOCX |
| Document Management | Downloaded files are a mess — mixed types in one folder | Auto Sort Files |
| Client Correspondence | Sending 50 personalised engagement letters | Mail Merge (Excel + Word template) |
| File Organisation | Year-end client folder setup for 100+ clients | Bulk Create Folders |
| Data Hygiene | Duplicate downloaded statements wasting storage | Duplicate File Finder |
| Portability | Legacy .xls files from older accounting software | XLS → XLSX converter |
| Security | Sending confidential financials to clients | Encrypt PDF |

---

## 3. DPDP Act Compliance — Why Local Processing Matters

### Background: The DPDP Act 2023

The **Digital Personal Data Protection Act, 2023** (DPDP Act) is India's comprehensive data protection legislation. It governs how personal data of Indian citizens is collected, stored, processed, and shared. For CA firms, this is directly relevant because:

- Client financial data (income, assets, tax liability) is **personal data** under the Act
- PAN numbers, GST registration details, bank account information, salary figures — all qualify as personal data
- The Act requires **data minimisation** — personal data should only be processed to the extent necessary
- The Act imposes obligations on **data fiduciaries** — anyone who determines the purpose and means of processing personal data
- Violations attract penalties of up to ₹250 crore

### The risk of cloud-based file processing

Many professionals routinely use free online tools to:
- Convert PDFs
- Merge Excel files
- Split documents
- Convert formats

When you upload a client's bank statement to a free online converter, you have:
- No control over how that data is stored
- No visibility into whether it is used for training AI models
- No certainty it is deleted after conversion
- No record to produce if a client asks where their data was processed

Under the DPDP Act, this creates **liability for the CA firm** — not the tool provider.

### How EfficientToolKit eliminates this risk

EfficientToolKit is a **100% local, offline desktop application.**

| Aspect | Online Tool | EfficientToolKit |
|---|---|---|
| Where files are processed | Remote server (unknown jurisdiction) | Your own machine only |
| Internet connection required | Yes | **No** |
| Data upload | Files sent to third-party servers | **Never** |
| Data retention by provider | Unknown | **N/A — no provider involved** |
| Consent obligation under DPDP | Potentially triggered | **Not applicable** |
| Audit trail for client data | None | Files remain on your local drive |
| Works with confidential data | Risky | **Safe by design** |

**EfficientToolKit processes all data entirely in memory on your local computer. No file, no filename, no metadata is ever transmitted to any server, API, or external service.** This is not a privacy policy promise — it is a technical reality. The application has no network calls, no telemetry, and no cloud dependency of any kind.

For CA firms advising clients on DPDP compliance, using EfficientToolKit also demonstrates **leading by example** — practising the data minimisation and security-by-design principles you recommend to clients.

---

## 4. Installation & First Launch

### Requirements

- Windows 10 or Windows 11 (64-bit)
- Python 3.11 or 3.12 (if running from source)
- No Java, no LibreOffice required for most tools
- LibreOffice required only for Word → PDF conversion

### Running from the EXE (recommended)

1. Download `EfficientToolKit.exe` from the release folder
2. Double-click to launch — no installation wizard required
3. Windows SmartScreen may prompt on first run: click **More info → Run anyway**
   *(This happens because the EXE is not signed with a paid code-signing certificate)*

### Building from source

```
git clone <repository>
cd EfficientToolKit
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
python app.py
```

To build the EXE yourself:
```
build.bat
```
Follow the prompts — it will generate the spec file and offer to run PyInstaller.

---

## 5. How to Use the Application

### Interface overview

```
┌─────────────────────────────────────────────────────────────────────┐
│  EfficientToolKit          CA Pranav P Tulshyan |   │  ← Header
├──────────┬──────────┬──────────┬──────────┬──────────┬─────────────┤
│ File     │ Excel    │ PDF      │ GST      │ Recon-   │ Other       │  ← Tabs
│ Explorer │ & CSV    │ Tools    │ Tools    │ ciliation│ Formats     │
├──────────┴──────────────────────────────────────────────────────────┤
│ SIDEBAR          │  TOOL PANEL                                       │
│                  │                                                   │
│ Tool 1           │  [Tool Name]                                      │
│ Tool 2  ←select  │  [Description]                                    │
│ Tool 3           │                                                   │
│ ...              │  [Input Files / Folder Picker]                    │
│                  │  [Parameters]                                     │
│                  │  [Output Folder]                                  │
│                  │  [▶ Run Tool]  [Progress Bar]                     │
│                  │  [Log]                                            │
└──────────────────┴───────────────────────────────────────────────────┘
```

### Step-by-step for every tool

1. **Click the tab** at the top to select the category (e.g., PDF Tools)
2. **Click the tool name** in the left sidebar
3. **Add input files or select a folder** using the buttons in the input section
4. **Set parameters** if the tool requires them (e.g., password, column name, page ranges)
5. **Set output folder** — or leave blank to save to `Desktop\EfficientToolKitOutput\ToolName\Timestamp\`
6. **Click ▶ Run Tool** — the progress bar animates while the tool runs
7. **Read the log** — it shows success/failure, output file names, and per-file status for bulk operations

### Tips

- You can **reorder files** in the file list using the ↑ and ↓ buttons — order matters for tools like Combine PDF
- Use **+ Add Folder** to quickly add all matching files from a folder to the list
- The output folder is created automatically if it does not exist
- All output files are timestamped so re-running a tool never overwrites previous output
- The log can be cleared at any time using the **Clear Log** button

---

## 6. Tool Reference — File Explorer

> Tools for organising, renaming, and auditing files and folders. No Excel or PDF library required — all tools use only the operating system.

---

### Folder Walker

**What it does:** Scans a folder (and all its subfolders) and produces an Excel report listing every file found — with its name, location, extension, size, and last modified date.

**When to use it:**
- Audit a client's document submission to confirm all required files are present
- Prepare a file inventory before archiving a completed engagement
- Find all PDF files across a complex folder structure
- Check which files were modified recently before a deadline

**How to use:**
1. Select the **Root Folder** to scan
2. Optional: enter extension filter (e.g., `.pdf, .xlsx`) to list only specific types
3. Optional: set max depth (e.g., `2`) to limit how deep the scan goes
4. Set output folder and click Run
5. Output: one Excel file with columns — File Name, Folder, Full Path, Extension, Size (KB), Date Modified

---

### Bulk Create Folders

**What it does:** Creates multiple folders (including nested sub-folders) in one operation by reading a list of names you paste in.

**When to use it:**
- Year-end setup — create `Client Name / FY 2024-25 / GST`, `Client Name / FY 2024-25 / ITR` for 100 clients at once
- New engagement setup — create a standardised folder structure for every new client
- Batch create working paper folders for an audit team

**How to use:**
1. Select the **root folder** where folders should be created
2. Paste folder names in the text box — one per line
3. Supports nested paths: `Sharma & Co/ITR/2024-25` creates all three levels
4. Click Run
5. The log shows: `+` Created, `=` Already existed, `!` Failed

**Example input:**
```
Rahul Sharma - ITR
Rahul Sharma - GST
Priya Patel - ITR
Priya Patel - GST
```

---

### Bulk Rename Files

**What it does:** Renames all files in a folder in a single operation. Supports adding a prefix, suffix, find-and-replace text in filenames, prepending the file's modification date, and sequential numbering.

**When to use it:**
- Standardise filenames before sending to a client: `invoice.pdf` → `HDFC_Jan2024_invoice.pdf`
- Add the financial year suffix to a batch of files
- Replace "old" with "2024-25" across 50 filenames
- Number files sequentially before binding into a single PDF
- Prepend the modification date for chronological sorting

**How to use:**
1. Select the **folder** containing files to rename
2. Fill in any combination of: Prefix, Suffix, Find Text, Replace With
3. Check **Prepend Modification Date** to add `YYYYMMDD_` before each filename
4. Set **Sequential Numbering Start** to `1` to add `0001_`, `0002_`, etc.
5. Click Run
6. Output: a rename report Excel showing Old Name → New Name → Status

**Note:** The tool renames files in-place. The original files are renamed; no copies are made. The rename report is saved to the output folder.

---

### Auto Sort Files

**What it does:** Moves (or copies) files from a source folder into categorised subfolders based on file extension. Uses a fully customisable category list.

**When to use it:**
- Organise a cluttered Downloads folder before starting an engagement
- Sort a client's document submission into Excel, PDF, Word, and Archive subfolders automatically
- Prepare a tidy working folder from a bulk document dump

**How to use:**
1. Select **Source Folder** (the messy folder)
2. Select **Destination Folder** (where sorted subfolders will be created)
3. Choose **Action**: Move (removes from source) or Copy (keeps originals)
4. Customise the category list:
   - Edit category names or extension lists inline
   - Click **+ Add Category** to create a new type
   - Click **✕** on any row to remove a category
   - Click **Reset to Defaults** to restore the built-in 14 categories
5. Click Run
6. Files with no matching category go to `_Uncategorized`
7. Output: a sort report Excel showing each file, its category, and the move/copy status

**Default categories:** Excel, PDF, Word, PowerPoint, Images, Archives, Text, JSON/XML, Database, Code, Audio, Video, Executables, Shortcuts

---

### Duplicate File Finder

**What it does:** Scans a folder recursively, computes an MD5 hash for every file, and produces an Excel report with two sheets identifying duplicate content.

**Sheet 1 — Exact Duplicates:** Files with identical content (same MD5 hash), even if they have different names or are in different subfolders.

**Sheet 2 — Name Clashes:** Files with the same filename in different locations but different content — potentially conflicting versions.

**When to use it:**
- Before archiving an engagement folder — identify and delete duplicate downloads
- After a client sends a second batch of documents — find overlaps with what was already received
- Storage audit — find space wasted by identical copies
- Version conflict detection — same filename, different content, in different subfolders

**How to use:**
1. Select the **Folder to Scan**
2. Set output folder and click Run
3. If no duplicates are found, a success message is shown and no report file is created

---

## 7. Tool Reference — Excel & CSV

> Tools for combining, converting, splitting, and transforming spreadsheet files.

---

### Combine CSV

**What it does:** Merges multiple CSV files into a single CSV file. Uses automatic encoding detection to handle files with different character sets (UTF-8, Windows-1252, ISO-8859-1, etc.).

**When to use it:** Combining 12 monthly sales export CSVs into one annual file; stacking data from multiple branches.

**How to use:** Add all CSV files → click Run. Files are stacked vertically. The first file's header is used; subsequent files' headers are skipped.

---

### Combine CSV (Simple)

**What it does:** Same as Combine CSV but without encoding detection — faster but assumes all files share the same encoding.

**When to use it:** When you know all CSVs were exported from the same system and encoding issues are not a concern.

---

### CSV → XLSX

**What it does:** Converts one or more CSV files to Excel XLSX format. Select one file for a single conversion; select multiple files for bulk conversion.

---

### XLSX → CSV

**What it does:** Converts one or more Excel files to CSV. Each file's first sheet is exported.

---

### Combine Excel

**What it does:** Two modes:

- **File mode:** Stack data from multiple Excel files (one sheet each) into a single Excel file
- **Sheets mode:** Combine all sheets within one Excel file into a single consolidated sheet

**Parameters:**
- Mode: `file` (multiple files) or `sheets` (single file, multiple sheets)
- Sheet Index: which sheet to read from each file (0 = first sheet)

**When to use it:** Combining 12 monthly GST workings into one annual file; consolidating a multi-sheet trial balance into one sheet.

---

### Combine Sheets (Bulk)

**What it does:** For each selected Excel file individually, combines all its sheets into one sheet. Useful when you have multiple multi-sheet files that each need to be consolidated separately.

---

### Split Excel by Column

**What it does:** Reads an Excel file and splits it into separate files (or separate sheets within one file) based on unique values in a specified column.

**Parameters:**
- Column Name: exact column name to split on (e.g., `State`, `Month`, `Vendor_Name`)
- Output Mode: `file` (one file per unique value) or `sheets` (one sheet per unique value in the same workbook)

**When to use it:** Split a combined purchase register by state for separate state GST filings; split a payroll sheet by department; split client data by financial year.

---

### XLS → XLSX

**What it does:** Converts legacy `.xls` files (Excel 97–2003 format) to modern `.xlsx` format. Preserves all sheets.

**When to use it:** Working with old accounting software exports or received files from legacy systems.

---

### Mail Merge

**What it does:** Generates personalised Word documents from an Excel data file and a Word template. One output document is created per row in the Excel file.

**How to use:**
1. Add the **Excel data file** (.xlsx) first — it must have column headers in row 1
2. Add the **Word template** (.docx) second — use `{{ColumnName}}` as placeholders in the template
3. Click Run — one merged DOCX is produced per data row

**When to use it:** Sending engagement letters to 50 clients; generating personalised tax computation summaries; creating individual audit reports from a common template.

**Example template text:**
```
Dear {{Client_Name}},

Your total tax liability for FY {{Financial_Year}} is ₹{{Tax_Amount}}.
```

---

### Combine Text Files

**What it does:** Concatenates multiple text files (`.txt`, `.log`, etc.) into one file. Also checks for emoji characters that might cause issues in downstream processing.

---

## 8. Tool Reference — PDF Tools

> Tools for splitting, combining, sorting, securing, and converting PDF files.

---

### Split PDF

**What it does:** Splits a single PDF into multiple files using one of five modes:

| Mode | What it does |
|---|---|
| `page_wise` | One output file per page |
| `cummulative` | File 1 = page 1, File 2 = pages 1-2, File 3 = pages 1-2-3, etc. |
| `oddeven` | One file for odd pages, one for even pages |
| `ranges` | Fixed-size sets (e.g., every 10 pages into a new file) |
| `split_equal` | Divide into N equal parts |

**When to use it:** Splitting a 200-page bank statement into individual monthly statements; extracting every page of an invoice bundle for individual client files.

---

### Split PDF (Custom Range)

**What it does:** Extracts specific page ranges from one or more PDFs.

**Format:** `1-3,5-7,10-12` → three output files containing pages 1-3, 5-7, and 10-12 respectively.

**When to use it:** Extracting specific sections from a long audit report; pulling out pages 15-22 from a 100-page PDF across multiple files.

---

### Split PDF (by N Files)

**What it does:** Splits each PDF into a specified number of equal output files.

---

### Split PDF (by Pages)

**What it does:** Splits each PDF so that each output file contains a fixed maximum number of pages.

---

### Combine PDF

**What it does:** Merges multiple PDFs into one. Files are combined in the order shown in the file list — use the ↑ and ↓ buttons to reorder.

**Duplex mode:** Enable "Add Blank Page for Odd-Page Files" to insert a blank page after any source file that has an odd number of pages — useful for double-sided printing.

**When to use it:** Combining individual invoice PDFs into a monthly bundle; assembling a complete audit file from separate sections.

---

### Sort PDF (Reverse)

**What it does:** Reverses the page order of one or more PDFs.

---

### Encrypt PDF

**What it does:** Password-protects one or more PDF files. The recipient must enter the password to open the file.

**When to use it:** Sending sensitive financial statements to clients via email; protecting confidential audit reports.

---

### Decrypt PDF

**What it does:** Removes password protection from one or more PDF files when you know the current password.

---

### Word → PDF

**What it does:** Converts `.docx` / `.doc` files to PDF using LibreOffice.

**Requirement:** LibreOffice must be installed at `C:\Program Files\LibreOffice`.  
Download from: [https://www.libreoffice.org](https://www.libreoffice.org) (free and open-source).

---

## 9. Tool Reference — GST Tools

> Tools for processing GST portal exports and preparing consolidated data for reconciliation.

---

### GSTR1 JSON → Excel

**What it does:** Converts the GSTR1 JSON file downloaded from the GST portal into a structured Excel workbook.

**Output sheets:** B2B, B2CL, B2CS, CDNR, EXPORT, and a consolidated `effcorp_all_combined` sheet containing all transactions.

**How to use:**
1. Download your GSTR1 return from the GST portal (JSON format)
2. Add the JSON file(s) to the tool
3. Click Run — one Excel file is produced per JSON input

**When to use it:** Every month after filing GSTR1, to maintain a readable Excel record of outward supplies.

---

### GSTR2B JSON → Excel

**What it does:** Converts GSTR2B JSON files from the GST portal into a structured Excel workbook.

**Output sheets:** B2B, B2BA, CDNR, CDNRA, ISD, IMPG, and a consolidated sheet.

**When to use it:** Monthly, after downloading GSTR2B from the portal, to prepare the input tax credit register.

---

### Combine GSTR2A Excel

**What it does:** Combines multiple GSTR2A Excel files downloaded from the GST portal (across multiple months or multiple GSTINs) into a single consolidated Excel file.

**Processes sheets:** B2B, B2BA, CDNR, CDNRA.

**When to use it:** Before reconciliation — combine all monthly GSTR2A downloads for a financial year into one file.

---

### Combine GSTR2B Excel

**What it does:** Same as Combine GSTR2A but for GSTR2B exports.

**Processes sheets:** B2B, B2BA, CDNR, CDNRA, ISD, IMPG.

---

## 10. Tool Reference — Reconciliation

> End-to-end automated reconciliation between the purchase register and GSTR2A.

---

### GSTR2A vs Purchase Register

**What it does:** Performs a full five-stage automated reconciliation between the client's internal purchase register (ITR) and the consolidated GSTR2A from the GST portal.

**Matching stages (in order):**
1. GSTIN + Invoice Number + Invoice Date (3-way exact match)
2. GSTIN + Invoice Number (2-way match, date tolerance)
3. PAN + Invoice Number + Invoice Date (3-way, handles GSTIN change cases)
4. PAN + Invoice Number (2-way)
5. Fuzzy / tolerance-based match

**Output:** Two Excel files:
- `Working.xlsx` — complete row-by-row matching result with match stage and variance
- `Summary.xlsx` — summary of matched, partially matched, and unmatched invoices

**How to use:**
1. Add the **Purchase Register / ITR Excel** file first (must have a sheet named `Main_ITR_Format`)
2. Add the **Consolidated GSTR2A Excel** file second (must have a sheet named `Main_2A_Format`)
3. Set the **Tolerance Limit** in rupees (default ₹100 — differences within this range are considered matched)
4. Click Run

**Parameters:**
- Tolerance Limit (₹): invoices where the tax difference is within this amount are treated as matched. Set to `0` for exact matching only.

**When to use it:** Monthly ITC reconciliation before filing GSTR3B; annual ITC audit; GST audit engagements.

---

## 11. Tool Reference — Other Formats

> Tools for non-Excel, non-PDF document formats.

---

### Merge DOCX Files

**What it does:** Merges all `.docx` files found in a selected folder into a single Word document. Each source document starts on a new page in the merged output.

**Sort order options:**
- Name (A → Z) — default, works well with numerically prefixed filenames like `01_intro.docx`, `02_scope.docx`
- Name (Z → A)
- Date Modified (oldest first)
- Date Modified (newest first)

**How to use:**
1. Name your DOCX files so they sort in the desired merge order (e.g., `01_`, `02_`, `03_`)
2. Select the **Folder with DOCX Files**
3. Choose the **Merge Order**
4. Set output folder and click Run
5. Output: `merged_docx_TIMESTAMP.docx`

**When to use it:**
- Assembling a multi-section report from individual section DOCX files
- Combining multiple client engagement letters into a single document for printing
- Building an audit report from separately prepared sections

**Limitations:**
- Embedded images may not transfer correctly in documents with complex graphics
- Section-level headers and footers from source documents are not preserved — the base document's headers/footers are used throughout
- Best suited for text and table-based documents

**Workaround for images:** If a document contains images, open the merged file in Word and manually re-insert the images from the source files.

---

## 12. Output Files & Folder Structure

All output files are saved to a timestamped folder so that re-running a tool never overwrites previous results.

**Default output path (when no output folder is specified):**
```
Desktop\
  EfficientToolKitOutput\
    <Tool Name>\
      <YYYY-MM-DD-HHMMSS>\
        output_file.xlsx
```

**Example:**
```
Desktop\
  EfficientToolKitOutput\
    GSTR2A vs Purchase Register\
      2024-11-15-143022\
        Working.xlsx
        Summary.xlsx
```

To specify a custom output location, use the **Browse** button in the Output Folder section of any tool panel.

---

## 13. Frequently Asked Questions

**Q: Does the tool require an internet connection?**  
A: No. EfficientToolKit is fully offline. No data is ever sent to any server.

**Q: Can I run it on multiple computers?**  
A: Yes. Copy the EXE file to any Windows 10/11 machine and run it. No licence key or activation required.

**Q: The EXE shows a SmartScreen warning — is it safe?**  
A: Yes. The warning appears because the EXE is not signed with a paid code-signing certificate. This is a Windows security feature for unsigned applications, not an indication of malware.

**Q: A tool shows "Backend module unavailable" in the log.**  
A: A required Python library is not installed. Run `pip install -r requirements.txt` in the project folder, or rebuild the EXE using `build.bat`.

**Q: Word → PDF is not working.**  
A: This tool requires LibreOffice to be installed. Download it from the LibreOffice website (free). All other PDF tools work without LibreOffice.

**Q: The Combine CSV tool says "No files found matching criteria" but my files are there.**  
A: Check that the files have `.csv` extension (lowercase). The tool filters by extension. If the extension is `.CSV` (uppercase), rename the files or use "Add File(s)" and select them directly.

**Q: Can I customise the Auto Sort categories permanently?**  
A: The categories reset to defaults each time the tool panel is opened. For permanent customisation, edit the `DEFAULT_CATEGORIES` dictionary in `filetools/file_explorer_tools.py` and rebuild the EXE.

**Q: The GSTR2A reconciliation is failing with a KeyError.**  
A: Ensure the Purchase Register sheet is named exactly `Main_ITR_Format` and the GSTR2A sheet is named exactly `Main_2A_Format`. Column names must also match the expected format — refer to the sample fixture files in `tests/fixtures/` for the correct structure.

**Q: How do I report a bug or request a new tool?**  
A: Contact CA Pranav P Tulshyan at PPtulshyan@gmail.com or Dm at +91-7464098001

---

*EfficientToolKit is developed and maintained by CA Pranav P Tulshyan. All file processing is performed locally on the user's machine. No client data is transmitted, stored, or shared with any external party.*
