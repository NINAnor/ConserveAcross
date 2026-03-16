# TBCA Governance Tool Prototype

A minimal Quarto + GitHub Pages prototype for the Excel-based TBCA management effectiveness and governance tool.

## What is included

- `index.qmd` — static questionnaire prototype
- `questions.json` — structured questions and scoring options
- `about.qmd` — rationale for the Quarto/GitHub Pages architecture
- `_quarto.yml` — Quarto website configuration

## Why this is realistic

This version is designed for **GitHub Pages**, which is a static host. That makes it ideal for:

- transparent versioning
- easy publishing
- cross-country workshop access
- reproducible releases

It does **not** yet provide a central database or live multi-user editing.


## Suggested next steps

1. Convert the full workbook into structured JSON/CSV.
2. Reproduce the report logic from the Excel workbook.
3. Add facilitator mode and workshop export.
4. Decide whether collaborative persistence should use GitHub or an external backend.
