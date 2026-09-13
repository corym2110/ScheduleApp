# 2110 Fitness — scheduling browser

Design prototypes for the studio's operations console. Eight screens: dashboard, schedule,
classes, members, POS, reports, settings, and per-coach preferences.

These are **static HTML files with no build step.** There is no framework to install, no
bundler and no backend. `package.json` exists only to provide a one-command local server.

## Running it

Open `2110 Scheduling Dashboard.dc.html` in a browser, or serve the folder:

```
npm start
```

Then visit http://localhost:4000 — a static server avoids the occasional `file://`
restriction and makes the cross-page links behave exactly as they would deployed.

## Structure

Keep the files flat at the repo root. The pages link to each other by filename and load
`support.js` and `_ds/…` by relative path, so moving them into subfolders breaks navigation.

| Path | What it is |
| --- | --- |
| `2110 *.dc.html` | One file per screen |
| `support.js` | Prototype runtime — required for the pages to render |
| `_ds/nocturne-…/` | The Nocturne design system: tokens, stylesheet, guide |
| `design_handoff_2110_scheduling/` | Implementation handoff package (see its README) |

## State

All data is mock and hardcoded in each page. The only persistence is `localStorage`, under
keys namespaced `2110-` (theme, attendance, waitlists, coach availability, shared accounts).
Clearing site data resets everything to the seeded state.

## Implementing this for real

Read `design_handoff_2110_scheduling/README.md`. It documents every screen, the shared app
shell, session types and durations, the exact design tokens, the state shapes, and what is
not yet designed.
