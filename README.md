# Macro Tracker

Mobile-first calorie & macro logger. The database is a spreadsheet: every entry is a row in
[`data/log.xlsx`](data/log.xlsx), committed to this repo through the GitHub API. Open the xlsx
anytime — it's the single source of truth.

## Columns

| Date | Time | Name | Calories | Protein | Carbs | Fats |
|------|------|------|----------|---------|-------|------|

Dates are `YYYY-MM-DD` (device-local). The app groups rows by date and shows daily totals.

## Deploy (Vercel)

1. vercel.com → Add New Project → import `Marwan997/macro-tracker`
2. Framework preset: **Other** (it's a static `index.html`, no build step)
3. Deploy, then open the URL on your phone and "Add to Home Screen"

## First launch

The app asks for a GitHub token (stored only in your browser's localStorage — never committed).
Use a **fine-grained token scoped to this repo only** with `Contents: read & write`:
github.com → Settings → Developer settings → Fine-grained tokens.

## Notes

- Every add/delete commits the updated xlsx, so your commit history doubles as an edit log.
- If a save fails (e.g. edited from two devices at once), the app re-pulls the latest xlsx — just re-add the entry.
