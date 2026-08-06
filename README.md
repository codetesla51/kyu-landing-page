# Kyu Landing Page

Marketing site for [Kyu](https://github.com/codetesla51/kyu), a Postgres-backed job queue for Go.

## Design

Vercel-inspired system:
- Near-black ink on warm white/soft-gray canvas (`#171717` / `#fafafa`) with a 4-step gray ladder for depth
- Geist + Geist Mono (Google Fonts), sentence-case headlines with aggressive negative tracking
- Single decorative system: the brand mesh gradient (blue → teal → violet → magenta → coral), used at hero scale only
- 100px-pill marketing CTAs, 6px-radius nav buttons, 8/12px card radius
- Stacked hairline + soft-shadow elevation, one polarity-flipped dark band for benchmarks
- No shadows in hero; the mesh gradient is the atmospheric depth cue

## Structure

1. **Hero** — text-only, problem-led copy ("Stop losing jobs when Redis flushes."), centered, no dashboard image
2. **The trade-off** — fast-but-not-durable / durable-but-slow / reliable-but-heavy cards, Kyu as the fix
3. **See it in action** — the Kyu dashboard screenshot (`screenshot-2026-08-05_18-11-32`) in dark browser chrome
4. **Features** — six marketing-first cards
5. **Quick start** — install / quick start / enqueue tabs with highlighted Go + Bash (highlight.js)
6. **Benchmarks** — dark polarity-flip band with measured numbers + link to the full Barrage report
7. **Compare** — Kyu vs asynq / river / machinery matrix
8. **CTA + footer**

## Assets

- `dashboard.png` — Kyu dashboard screenshot (copied from `/home/uthman/Pictures/screenshot-2026-08-05_18-11-32.png`)

## Responsiveness

Tested with a headless-chromium overflow harness at 375 / 768 / 1024 / 1440 px — zero horizontal overflow at every breakpoint. Nav collapses to a hamburger menu below 900px.

## Run locally

```bash
node server.js   # serves on http://localhost:3000
```

Or open `index.html` directly — it's a single static file. Geist/Geist Mono fonts and highlight.js load from CDNs.
