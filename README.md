# Kyu Landing Page

Marketing site for [Kyu](https://github.com/codetesla51/kyu), a postgres-backed job queue for Go.

## Design

Grafana-dark dashboard aesthetic: near-black layered surfaces, amber accent, Inter + JetBrains Mono. Content is written to reflect Kyu's current state (engines, lifecycle, CLI, config, metrics, and the Barrage load-test benchmark results).

## Sections

- Hero — live dashboard screenshot inside a browser frame, animated ticker, stats strip
- Architecture — animated SVG pipeline (particles along the queue paths)
- Lifecycle — animated SVG state machine (ok / retry / dead routes)
- Features — 13 feature cards
- Quick start — install / quick start / enqueue code tabs (highlight.js)
- Dashboard — metrics panel screenshot + Prometheus metric table
- Benchmarks — dispatch overhead + Barrage load-test results
- Why Kyu — spectrum comparison vs asynq, river, machinery, bullmq

## Responsiveness

Fully responsive, tested with a headless-chromium overflow harness at 375 / 768 / 1024 / 1440 px (zero horizontal overflow at every breakpoint). Nav collapses to a hamburger menu below 920 px.

## Run locally

```bash
node server.js   # serves on http://localhost:3000
```

Or open `index.html` directly — it's a single static file. Icons, fonts, anime.js and highlight.js load from CDNs, so an internet connection is expected.

## Animations

All anime.js motion respects `prefers-reduced-motion`, and every block has a CDN-failure fallback so content is never left invisible.
