# Meridian No. 7 — Field Station Panel

A single-page, self-contained frontend demo: an analog-instrument-style
dashboard (temperature dial, humidity/wind/pressure gauges, a live
observation log) driven by simulated sensor data. No backend, no build
step — just static HTML/CSS/JS served by nginx.

## Run it with Docker (option A — docker compose)

```bash
docker compose up --build
```

Then open **http://localhost:8080**

## Run it with Docker (option B — plain docker)

```bash
docker build -t meridian-app .
docker run --rm -p 8080:80 meridian-app
```

Then open **http://localhost:8080**

## Stopping it

```bash
docker compose down
# or, for plain docker, Ctrl+C in the terminal running it
```

## Files

- `index.html` — the entire app (markup, styles, and script in one file)
- `Dockerfile` — nginx:alpine serving the static file
- `docker-compose.yml` — one-command build & run, mapped to port 8080

## Notes

- All sensor readings are randomly simulated client-side — nothing is
  fetched from a real API, so it works fully offline once loaded.
- The dashboard is responsive down to mobile widths and respects
  `prefers-reduced-motion`.
