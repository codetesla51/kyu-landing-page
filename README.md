# Kyu Landing Page

Marketing site for [Kyu](https://github.com/codetesla51/kyu), a Go job queue where Postgres is the durable ledger and Redis is the fast dispatch lane.

## Design

Grafana-dark developer-tool aesthetic — dark only, no light bands, no SaaS treatment:

- Always-dark canvas (`#101214`) with a surface/elevation ladder (`#14171A` → `#1B1E22` → `#22262B`), hairline borders, and an amber accent (`#E8A84C`)
- Inter + JetBrains Mono (Google Fonts), mono labels and stat figures
- Single icon system: Phosphor (`@phosphor-icons/web`), no other icon set
- No Kyu logo or wordmark anywhere in nav or footer — navigation links and actions only, no logos at all
- No "Get started" CTA; the hero's only action is the `go get` install command with a copy button and a "Read the code" GitHub link
- Text-only, centered, problem-led hero — the dashboard screenshot lives in a section far down the page

## Structure

1. **Hero** — centered problem-led copy ("Jobs survive a Redis flush. Dispatch stays fast.") above a full-width pipeline schematic that loops continuously (GSAP DrawSVG: connectors draw in, labels fade, boxes pulse, flow rests — paused off-screen); install box + GitHub button + proof tags below the copy
2. **Stats strip** — Redis throughput 1,250/s · Postgres 749.9/s · 100% delivery · 52ns dispatch overhead
3. **01 Architecture** — GSAP DrawSVG pipeline animation: the app → Postgres/Redis → worker connectors draw themselves (blue lane first, red lane offset 0.3s), labels fade in as each path completes, destination boxes pulse on arrival; plays on scroll into view + six subsystem panels
4. **02 Lifecycle** — animated state-machine SVG (pending → running → completed / failed / re-queued / dead) + status table
5. **03 Features** — thirteen cards (durability, priorities, scheduling, retries, DLQ, locking, middleware, batch, Prometheus, RunOnce, inspect APIs, webhooks, scope boundaries)
6. **04 Quick start** — install / quick start / enqueue tabs with statically-rendered Go + Bash code (highlight.js) — content is in the markup, never empty — plus CLI / docker-compose / queue-isolation panels
7. **05 Dashboard** — `dashboard.png` screenshot in browser chrome + metrics table
8. **06 Benchmarks** — dispatch table (52ns register / 950ns execute) + Barrage load table (251.5/s HTTP, 749.9/s Postgres, 1250/s Redis, 100% success) + investigation-log link
9. **07 Why Kyu** — positioning spectrum (Redis-only → Postgres-only → Kyu) + comparison matrix vs Asynq / River / Machinery / BullMQ

## Assets

- `dashboard.png` — Kyu dashboard screenshot (copied from `/home/uthman/Pictures/screenshot-2026-08-05_18-11-32.png`), used only in the dashboard section

## Responsiveness

Tested with a headless-chromium overflow harness at 375 / 768 / 1024 / 1440 px — zero horizontal overflow at every breakpoint (`html,body{overflow-x:clip}`). Nav collapses to a hamburger menu below 920px; feature/bench grids collapse to one column below 560px.

## Run locally

```bash
node server.js   # serves on http://localhost:3000
```

Or open `index.html` directly — it's a single static file. Phosphor icons, highlight.js, GSAP 3.13 (core + DrawSVGPlugin + ScrollTrigger), and IBM Plex fonts load from CDNs.
