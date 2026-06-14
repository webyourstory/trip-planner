# Departure — Trip Planner

A single-file, zero-dependency trip planning app. Build a day-by-day itinerary,
watch the 2-week forecast for your destination, and route between every stop —
all from one `index.html` with no build step and no API keys.

## Features

- **Forecast** — 14-day weather for your destination (highs, lows, rain chance),
  split into *This week* / *Next week*, with a °F/°C toggle. Each day's forecast
  also appears on its itinerary card when the date is in range.
- **Itinerary** — days auto-generated from your trip dates, one card each.
- **Typed stops** — Flight, Stay, Restaurant, Activity, Ticket, Transit, Note,
  Resource. Each has title, time, location, cost, confirmation/reference, link,
  and notes.
- **Routing** — Drive / Transit / Walk links between consecutive stops, plus a
  map link on any location. Opens directions directly in Google Maps.
- **Ideas bucket** — park stops before assigning them to a day.
- **Multiple trips** — switch between trips from the top bar.
- **Autosave** — everything persists locally; no account needed.

## Run it

It's static. Either open `index.html` directly, or serve it:

```bash
# Python
python3 -m http.server 8000
# or Node
npx serve .
```

Then visit `http://localhost:8000`.

## Deploy free with GitHub Pages

1. Push this repo to GitHub (see below).
2. Repo → **Settings → Pages**.
3. Source: **Deploy from a branch**, branch `main`, folder `/ (root)`.
4. Your site goes live at `https://<username>.github.io/<repo>/`.

## Tech notes

- **Weather:** [Open-Meteo](https://open-meteo.com) forecast + geocoding APIs —
  free and keyless.
- **Maps:** Google Maps *deep links* (no billed API key). To embed a live
  in-page map instead, swap the route links for the Google Maps JavaScript +
  Directions API and add your key.
- **Storage:** uses the host's `window.storage` when present, otherwise falls
  back to `localStorage`, so data persists whether hosted here or elsewhere.
- **Icons:** [Lucide](https://lucide.dev) via CDN (degrades gracefully offline).
- **Fonts:** Archivo, Fraunces, JetBrains Mono via Google Fonts.

## License

MIT — do whatever you like.
