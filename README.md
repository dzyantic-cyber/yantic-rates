# yantic-rates

Public data file read by the Sarf Yantic app to show the parallel-market
("square") EUR/USD rate against the Algerian dinar.

## Format

`rates.json`:

```json
{ "eur": 277.17, "usd": 237.67, "updated": "2026-09-20" }
```

- `eur` / `usd`: dinars for 1 euro / 1 US dollar (numbers).
- `updated`: date of the observation, `YYYY-MM-DD` (or `YYYY-MM-DD HH:MM`).
  The app shows this as the "last updated" date, so keep it accurate — if it
  can't be parsed, the app falls back to the time it fetched the file.

## Optional: history (fills the chart for every user)

```json
{
  "eur": 277.17, "usd": 237.67, "updated": "2026-09-20",
  "history": [
    { "date": "2026-09-19", "eur": 276.80, "usd": 237.40 },
    { "date": "2026-09-18", "eur": 276.10, "usd": 236.90 }
  ]
}
```

List **real** past days you actually observed (up to ~15 is enough). The app
merges them into the parallel chart, one point per day; rows with a bad
date or a missing number are skipped. Each day, add the previous day's values
to `history` and update the top-level numbers. Don't invent values — the
chart shows min/max/average and % change as fact.

## Daily update

Edit `rates.json` on the hosting site's web editor, change the two numbers
and the date, commit. The app picks it up on its next refresh — no app
release needed.

Indicative rates only, informal market — not an official quotation.
