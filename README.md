# Obrazec 8.204 — PDF Form Filler

Fill the Slovenian medical form **"Napotnica za predhodni preventivni zdravstveni pregled"** (Obrazec 8.204) digitally — no need to fill it in by hand.

The original PDF has no interactive form fields. This project renders the PDF in the browser with editable input fields on top.

## Usage

Serve the files with any static HTTP server and open in a browser:

```bash
npx serve
# or
python3 -m http.server 8000
```

Or deploy to GitHub Pages, Netlify, or any static hosting.

Features:
- PDF rendered as background with editable input fields on top
- Per-character spacing for fields like tax number, EMSO, postal code
- Auto-saves to `localStorage`
- Export/import data as JSON
- Print-ready A4 layout

## Data Format

Key fields:

| Field | Description |
|---|---|
| `employer_name` | Employer name and address |
| `tax_number` | Tax number (davčna številka) |
| `economic_activity` | Economic activity + `activity_code` |
| `surname_name` | Full name |
| `emso` | EMŠO (13 digits) |
| `address`, `postal_code` | Address and postal code |
| `education`, `education_level` | Education and level (1–9) |
| `profession`, `profession_code` | Profession and SKP code |
| `position`, `position_code` | Job position and code |
| `risk_assessment_date` | Risk assessment date (ddmmyyyy) |
| `work_process` | Work process description |
| `work_equipment` | Work equipment |
| `work_objects` | Work objects |
| `risk_exposure` | Risk exposure |
| `measures` | Protective measures |
| `ppe` | Personal protective equipment |
| `health_requirements` | Health requirements |
| `unsuitable_for` | Unsuitable conditions |
| `employer_remarks` | Employer remarks |

## Field Definitions

`fields.json` contains field positions (in PDF points from top-left of page 1). Fields with `charSpacing` render each character in a separate cell.

## License

MIT
