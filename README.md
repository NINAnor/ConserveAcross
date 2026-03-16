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

## Deploy to GitHub Pages

### Option 1 — easiest

1. Create a GitHub repository.
2. Add these files.
3. Render locally with Quarto:

```bash
quarto render
```

4. Commit the generated `docs/` folder.
5. In GitHub: **Settings -> Pages -> Deploy from a branch**.
6. Choose the `main` branch and `/docs` folder.

### Option 2 — with GitHub Actions

Use the workflow below.

```yaml
name: Publish Quarto site

on:
  push:
    branches: [main]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: true

jobs:
  build-deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: quarto-dev/quarto-actions/setup@v2
      - uses: actions/configure-pages@v5
      - run: quarto render
      - uses: actions/upload-pages-artifact@v3
        with:
          path: docs
      - uses: actions/deploy-pages@v4
```

## Suggested next steps

1. Convert the full workbook into structured JSON/CSV.
2. Reproduce the report logic from the Excel workbook.
3. Add facilitator mode and workshop export.
4. Decide whether collaborative persistence should use GitHub or an external backend.
