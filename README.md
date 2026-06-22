# Financial Analysis Dashboard

An interactive financial dashboard for analysing any company's financials. Upload a P&L and Balance Sheet — as an Excel file or CSV exports — and instantly get charts, KPI cards, margin trends, and a plain-English reading guide. Built for finance professionals, analysts, and anyone who wants to understand a company's numbers without specialist software.

**[→ Open Live Dashboard](https://finacial-dashboard-sme.netlify.app/)**

> Everything runs in your browser. No login required. No data is sent anywhere.

---

## Who this is for

- **Finance teams** who want a quick visual read of their own or a competitor's accounts
- **SME owners** who receive statutory accounts and want to understand what the numbers mean
- **Students and analysts** learning to read financial statements
- **Investors and advisors** doing preliminary due diligence on a company

---

## What it shows

| Section | Content |
|---|---|
| **Overview** | Revenue, gross margin, net result, total assets, equity ratio — with year-on-year trends |
| **P&L** | Full income statement table, revenue vs gross profit, cost breakdown, interest analysis |
| **Balance Sheet** | Asset composition, funding structure, full balance sheet table |
| **Reading Guide** | Every metric explained in plain English, illustrated with the uploaded company's actual numbers |

---

## How to use

### Option A — Excel workbook

Upload any `.xlsx` file with two sheets:

| Sheet name | Contents |
|---|---|
| `P&L` | Income statement — years as column headers, line items as rows |
| `Balance Sheet` | Balance sheet — same structure |

**Format:**
```
Row 1:  Company name
Row 2:  Column headers  →  [blank] | 2022 | % Rev | 2023 | % Rev | 2024 | % Rev
Row 3+: Line item label in column B, values in year columns
```

### Option B — Two CSV files

Upload two separate CSV files using the two pickers on the upload screen:

| Picker | Upload |
|---|---|
| Left box | Income statement / P&L CSV |
| Right box | Balance sheet CSV |

**Format:**
```
Row 1:  Company name  (e.g. "Acme Ltd, London, UK")
Row 2:  Blank
Row 3:  Date headers  →  [blank] | 31/12/2022 | 31/12/2023 | 31/12/2024
Row 4+: Label in column A, values in columns B, C, D...
```

Values can be formatted as quoted strings with commas (e.g. `"1,250,000.00"`) — the parser handles this automatically.

---

## Where to get the data

| Source | Steps |
|---|---|
| **Northdata** (Germany) | Search company → Download CSVs → upload via Option B |
| **Bundesanzeiger** (Germany) | Find filing → export → upload via Option B |
| **Companies House** (UK) | Download filing → restructure to two-file format → Option B |
| **Your own accounts** | Export from accounting software (Xero, DATEV, SAP) → Option A or B |
| **Annual report** | Copy P&L and balance sheet into Excel template → Option A |

---

## Supported labels

The dashboard matches line items by keyword — exact naming is not required. It recognises standard English and German (HGB) accounting terms:

| Line item | Recognised keywords |
|---|---|
| Revenue | revenue, turnover, net sales, umsatz |
| Cost of sales | materials, cost of goods, cogs, wareneinsatz |
| Personnel costs | personnel, wages, salaries, staff costs, personalaufwand |
| Depreciation | depreciation, amortisation, abschreibung |
| Other operating expenses | other operating expenses, sonstige betriebliche aufwendungen |
| Net result | net income, net loss, net profit, jahresfehlbetrag, jahresüberschuss |
| Fixed assets | fixed assets, anlagevermögen |
| Cash | cash on hand, cash equivalents, kassenbestand |
| Receivables | receivables, forderungen |
| Equity | equity, eigenkapital |
| Liabilities | accounts payable, verbindlichkeiten |

Unmatched lines show as `—` without breaking the rest of the dashboard.

---

## Key ratios explained

| Ratio | Formula | What it tells you |
|---|---|---|
| Gross Margin | Gross Profit ÷ Revenue | Profitability after direct costs. Varies by industry: software 70%+, manufacturing 20–40%, retail 25–50% |
| EBITDA Margin | EBITDA ÷ Revenue | Operating cash generation before depreciation and financing |
| Equity Ratio | Equity ÷ Total Assets | How much is funded by owners vs creditors. Below 10% = highly leveraged |
| Interest Coverage | EBIT ÷ Interest Expense | Can operations cover the interest bill? Below 1.5× = risk |
| Revenue Growth | (Revenue − Prior) ÷ Prior | Top-line momentum year on year |

---

## Deploying your own copy

This is a single static HTML file — no build step, no backend, no dependencies to install.

**GitHub Pages**
1. Create a new public repo
2. Upload `index.html` (rename from `Financial_Dashboard.html`)
3. Settings → Pages → Deploy from branch → main → / (root) → Save
4. Live at `https://yourusername.github.io/your-repo-name`

**Netlify**
1. Go to [netlify.com](https://netlify.com)
2. Drag and drop `index.html` onto the dashboard
3. Live instantly — rename the site under Site configuration → Site details

**Vercel**
1. Go to [vercel.com](https://vercel.com)
2. Import or drag and drop the file
3. Live at a `*.vercel.app` URL

---

## Updating the dashboard

To deploy a new version, simply drag the updated `index.html` file onto the Netlify or GitHub repo. No commands needed.

---

## Privacy

All file processing happens entirely in your browser using:
- [SheetJS](https://sheetjs.com) — Excel and CSV parsing
- [Chart.js](https://chartjs.org) — Charts and visualisations

No data is transmitted to any server. No analytics. No cookies. Safe to use with confidential company financials.

---

## Tech stack

| Component | Library / Tool |
|---|---|
| Charts | Chart.js 4.4.1 |
| Excel / CSV parsing | SheetJS (xlsx) 0.18.5 |
| Fonts | DM Sans + DM Mono via Google Fonts |
| Hosting | Netlify / GitHub Pages / Vercel |
| Framework | None — plain HTML, CSS, JavaScript |

---

## Limitations

- Designed for companies filing under HGB (Germany) or similar structured formats — IFRS filings with more complex structures may need minor reformatting
- Values are displayed in millions (€M) — very small companies may want to adjust the display unit
- Multi-currency consolidations are not supported — values should be in a single currency before upload
- The dashboard reads up to 10 years of data; beyond that, chart readability degrades

---

## Built by

**Kaviya Gopal**
MSc Financial Engineering & Management · Karlsruhe Institute of Technology (KIT)
Previously: Middle Office Analyst, JPMorgan Chase CIB · Data Analytics, TUI Group

[LinkedIn]([https://www.linkedin.com/in/kaviya-gopal-a9a6361a0/]) · [GitHub]([https://github.com/Kaviya04]) · [Live Dashboard](https://finacial-dashboard-sme.netlify.app/)
