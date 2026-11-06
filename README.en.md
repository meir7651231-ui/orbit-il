<p align="right"><b>English</b> · <a href="README.md">עברית</a></p>

<p align="center"><img src="assets/hero.svg" alt="Orbit · orbit-il.com — the repo that builds and serves the live site" width="100%"></p>

<p align="center">
<a href="https://github.com/meir7651231-ui/orbit-il/actions/workflows/deploy.yml"><img src="https://github.com/meir7651231-ui/orbit-il/actions/workflows/deploy.yml/badge.svg?branch=main" alt="Build Orbit from maor-system"></a>
<a href="https://orbit-il.com"><img src="https://img.shields.io/badge/live-orbit--il.com-2fd4a4?style=flat-square&labelColor=0d1120" alt="live: orbit-il.com"></a>
<img src="https://img.shields.io/badge/build-daily%2003%3A00%20UTC-4f7dff?style=flat-square&labelColor=0d1120" alt="build: daily 03:00 UTC">
<img src="https://img.shields.io/badge/host-GitHub%20Pages-8a7dff?style=flat-square&labelColor=0d1120" alt="host: GitHub Pages">
</p>

<h3 align="center">No product code here. One path only: from <code>maor-system@main</code> to live, at orbit-il.com.</h3>

<p align="center"><a href="#what-it-does"><b>What it does</b></a> · <a href="#when-it-runs">When it runs</a> · <a href="#run-it-manually">Run manually</a> · <a href="#verify">Verify</a> · <a href="#layout">Layout</a> · <a href="#do-not-touch">Do not touch</a></p>

---

## What it does

This repo **builds and serves the live site [orbit-il.com](https://orbit-il.com)**. The application code lives in `meir7651231-ui/maor-system`; this repo holds only the deploy path:

<p align="center"><img src="assets/deploy-flow.svg" alt="Deploy flow: trigger, checkout maor-system@main, build on Node 22, push to gh-pages, GitHub Pages serves orbit-il.com" width="100%"></p>

1. **Trigger** — one of the three sources below starts the `Build Orbit from maor-system` workflow.
2. **Checkout** — `actions/checkout` pulls `maor-system` at `main`.
3. **Build** — Node 22, `npm ci`, `npm run build` → `dist/`.
4. **Publish** — `CNAME` (`orbit-il.com`) and `.nojekyll` are written, and `dist/` is force-pushed to this repo's `gh-pages` branch.
5. **Live** — GitHub Pages serves `gh-pages` at orbit-il.com.

## When it runs

| Trigger | When | Note |
|---|---|---|
| ⏰ `schedule` | daily at **03:00 UTC** | ships whatever was merged to `maor-system@main` |
| 📌 `push` | every push to `main` **in this repo** | the "deploy now" path: add an entry to [`DEPLOY-LOG.md`](DEPLOY-LOG.md) and push |
| ▶️ `workflow_dispatch` | manually, from the Actions tab | see below |

> ⚠️ Every merge to `main` here — **documentation changes included** — rebuilds and redeploys the live site from the current `maor-system@main`.

## Run it manually

1. Open [**Actions → Build Orbit from maor-system**](https://github.com/meir7651231-ui/orbit-il/actions/workflows/deploy.yml).
2. Click **Run workflow** → branch `main` → **Run workflow**.
3. Wait for the green check (about a minute), then for the `pages build and deployment` run (another minute).

## Verify

```bash
curl -s https://orbit-il.com/version.json
# {"id":"2026-11-06T10:02:48.801Z"}  ← time of the last build (UTC)
```

If the time in `version.json` is later than the run's start, the live site is up to date. You can also compare it with the latest run in [Actions](https://github.com/meir7651231-ui/orbit-il/actions).

## Layout

```
orbit-il/
├── .github/workflows/deploy.yml   ← the build & deploy path (owner approval to change)
├── DEPLOY-LOG.md                  ← manual-deploy log; entry + push = deploy now
├── README.md / README.en.md       ← this document
├── CHANGELOG.md                   ← repo history by month
├── SECURITY.md                    ← permissions, secrets, reporting
└── assets/                        ← hero.svg, deploy-flow.svg
```

`gh-pages` is recreated on every run (force push) — never edit it by hand.

## Do not touch

- `.github/workflows/` — a change can take the live site down.
- The `gh-pages` branch and `CNAME` — written automatically; hand edits are overwritten, and a CNAME change detaches the domain.
- `DEPLOY-LOG.md` — a historical log; append only.
- Direct pushes to `main` — they deploy. Work on a branch + PR.

The pre-October trigger lines that used to live in this README are kept, unchanged, at the bottom of the [Hebrew README](README.md).

---

<p align="center"><sub><a href="CHANGELOG.md">CHANGELOG</a> · <a href="SECURITY.md">SECURITY</a> · <a href="DEPLOY-LOG.md">DEPLOY-LOG</a></sub></p>
