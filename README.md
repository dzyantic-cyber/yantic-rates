# yantic-rates

Public data file read by the Sarf Yantic app to show the parallel-market
("square") EUR/USD rate against the Algerian dinar.

## Format

`rates.json`:

```json
{ "eur": 277.17, "usd": 237.67, "updated": "2026-09-20" }
```

- `eur` / `usd`: dinars for 1 euro / 1 US dollar (numbers).
- `updated`: date of the observation, for humans (the app currently ignores it).

## Daily update

Edit `rates.json` on the hosting site's web editor, change the two numbers
and the date, commit. The app picks it up on its next refresh — no app
release needed.

Indicative rates only, informal market — not an official quotation.
