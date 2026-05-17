# Felt Heat — interactive story

A single-page interactive story about how felt heat (UTCI) diverges from
air temperature (T2M) across four Indian cities, 2000–2025.

## Files

- `index.html` — the whole story. All scripts, styles, and chart data
  are inline. D3.js v7 is pulled from the CDN.
- `delhi-daily-2000-2025.csv`
- `mumbai-daily-2000-2025.csv`
- `chennai-daily-2000-2025.csv`
- `kolkata-daily-2000-2025.csv`

The daily CSVs are loaded at runtime via `fetch()` to drive the calendar
view in Insight 03. The page falls back to a simulated distribution if
the files aren't reachable.

## Running locally

`fetch()` needs the page to be served over HTTP — opening `index.html`
directly via `file://` will silently skip the daily-CSV load.

```bash
cd feels-like-story-site
python3 -m http.server 8000
# then open http://localhost:8000
```

## Publishing on GitHub Pages

1. Push this directory to a GitHub repo.
2. In repo Settings → Pages, point Pages at the `main` branch / root.
3. The story will be live at `https://<user>.github.io/<repo>/`.

The CSV fetches will work out of the box on Pages — no extra config.
