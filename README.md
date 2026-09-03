# Trainer Calendar Dashboard

A GitHub Pages-ready L&D trainer calendar dashboard.

## Features

- Trainer dropdown: All Trainers or an individual trainer.
- Month dropdown populated from the calendar data.
- KPI cards change for the selected trainer/month.
- Calendar filters to the selected trainer.
- All Trainers shows aggregate totals.
- Participants column is supported.
- Download PDF creates a trainer/month PDF.
- Local `data.csv` is included as the starting dataset.
- A Google Sheet CSV can be connected with one configuration change.

## Google Sheet connection

Use one Google Sheet with these columns in row 1:

`trainer,trainingName,topics,date,time,day,mode,department,participants,month`

For recurring dates, a row can contain comma-separated day numbers such as `3,7,10,14` and the `month` column should contain `September 2026`.

To connect the live sheet:

1. In Google Sheets, use File → Share → Publish to web.
2. Publish the required sheet as CSV.
3. Copy the generated CSV URL.
4. In `index.html`, replace the empty `GOOGLE_SHEET_CSV_URL` value with that URL.
5. Commit the change once.
6. After that, maintain the calendar in Google Sheets rather than editing the dashboard code.

When the month/date data in the Google Sheet changes, the dashboard rebuilds its month list and calendar from the sheet data.

Do not put confidential participant information in a publicly published Google Sheet.

## GitHub Pages

This repository is designed for GitHub Pages. Enable it under repository Settings → Pages and deploy the `main` branch from the repository root.

The PDF export uses the `html2pdf.js` browser library from a CDN.

## Current data

`data.csv` contains the starting data converted from the September 2026 trainer calendar workbook supplied for this project. Participants are intentionally blank and can be filled in later.
