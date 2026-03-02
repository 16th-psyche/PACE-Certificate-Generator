# PACE Certificate Generator

**Live app:** [https://16th-psyche.github.io/PACE-Certificate-Generator/](https://16th-psyche.github.io/PACE-Certificate-Generator/)

A lightweight, browser-based tool to bulk-generate personalised PDF certificates for the **Business P.A.C.E Program**.

No installation, no server, no dependencies to install — just open and use.

---

## How It Works

1. Open `index.html` in **Safari or Chrome** on your Mac
2. Upload a **CSV file** with participant names
3. Click **Generate Certificates**
4. Click **Download ZIP** — get all PDFs instantly

---

## CSV Format

The CSV must have a single column with the header `Name`:

```csv
Name
Krishna Sagar
Priya Sharma
Rahul Mehta
```

A sample file [`sample_names.csv`](sample_names.csv) is included for testing.

---

## Output

Each certificate is saved as a PDF named with a zero-padded serial number followed by the participant's name:

```
001_Krishna Sagar.pdf
002_Priya Sharma.pdf
003_Rahul Mehta.pdf
...
```

All files are packaged into a single `PACE_Certificates.zip` download.

---

## File Structure

```
PACE Certificate/
├── index.html           # Certificate generator app (self-contained)
├── PACE certificate.svg # Original SVG template (reference only)
├── sample_names.csv     # Sample CSV for testing
└── README.md
```

> The SVG template is hardcoded inside `index.html` — the original `.svg` file is kept as a reference but is not required to run the tool.

---

## Technical Details

| Detail | Value |
|---|---|
| Output format | PDF (A4 Landscape) |
| PDF resolution | ~144 DPI (2× render scale) |
| Certificate font | Savoye LET (macOS system font) |
| Naming convention | `001_Name.pdf`, `002_Name.pdf`, … |
| Internet required | First load only (CDN libraries) |

**Libraries used (via CDN):**
- [PapaParse](https://www.papaparse.com/) — CSV parsing
- [jsPDF](https://github.com/parallax/jsPDF) — PDF generation
- [JSZip](https://stuk.github.io/jszip/) — ZIP packaging
- [FileSaver.js](https://github.com/eligrey/FileSaver.js/) — file download

---

## Requirements

- macOS (the certificate uses **Savoye LET**, a macOS system font)
- Safari or Chrome browser
- Internet connection on first use (to load CDN libraries)
