# TapIQ

**Test your tap. Find your filter.**

Landing page for TapIQ — a local San Diego drinking-water screening and filter
guidance service for renters, families, and bottled-water users.

## Pages

- **`index.html`** — the marketing landing page
- **`report.html`** — the example water analysis report (the customer deliverable).
  Switch package tiers with the tabs, or deep-link a tier:
  `report.html?tier=starter` · `report.html?tier=kit` · `report.html?tier=advanced`

## Running it

Standalone files, no build step. Just open them:

```
index.html
```

Double-click the file, or drag it into any browser tab.

(Optional) Serve it locally over HTTP:

```bash
npx serve .
# or
python -m http.server 5174
```

## Editing

Common things to update are flagged with `UPDATE ... HERE` comments in `index.html`:

- **Contact info** — email and phone in the footer
- **Package prices** — in the Packages section

## Sections

Hero · Problem · Service (Clean Water Starter Kit) · Packages · How It Works ·
Why TapIQ · FAQ · Lead form · Footer

The hero features a custom canvas-rendered globe: people-nodes light up green as
connections complete, then the cycle smoothly resets and repeats.
