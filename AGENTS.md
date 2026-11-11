# AGENTS.md - MKRBOX Notes for Coding Agents

## Self-Improvement Directive
Update this file whenever you learn something important about the project.
Capture both wins and misses, plus collaborator preferences. Be concrete.

## Project Overview
MKRBOX is a "factory-in-a-box" simulator + game with a public-facing site.
The site is static HTML right now, while the sim/game stack will evolve into
an Omniverse/Kit-based simulator with a streamed web client.

Key ideas:
- Modular Kinematic Replicator (MKRBOX), 1 m2 footprint, ~1 m3 reach envelope.
- Sim-first: run levels, debug workflows, then build hardware.
- Operator-in-the-loop handoffs (input/output bays).

## Current Repo Structure
- `index.html` - landing page
- `join/`, `concept/`, `play/` - route folders with `index.html`
- `SPEC.md`, `MODULES.md`, `LEVELS.md`, `SIM.md` - draft docs
- `SIM_QUICKSTART.md` - sim/app client flow
- `ARCHITECTURE.md`, `TODO.md` - product vision + roadmap
- `CNAME` - domain config

## Build & Run Commands
No build system yet for the static site.
- Open `index.html` directly or serve with any static server.
- `./run-app.sh` runs the React game app (expects `./app` with a `package.json`).

## Coding & Content Conventions
- Keep copy grounded: avoid "build anything" claims.
- Always state the footprint/reach as: "1 m2 footprint, ~1 m3 reach".
- Avoid implying redistribution of Omniverse Kit; note dependency download + EULA.
- Mention that full sim streams to the browser; in-browser is a lightweight preview.
- Use MKRBOX spelling (box, not bx).

## Known Pitfalls
- CTAs must point to real routes (e.g. `/join/`, `/concept/`, `/play/`).
- Don't promise bundling NVIDIA/Omniverse components in the repo.
- Keep simulator language explicit about RTX/GPU streaming requirements.

## Agent Tips
- For new routes: create a folder with `index.html` (static host friendly).
- If push fails due to remote updates, use `git pull --rebase` first.
- Prefer ASCII content; keep formatting simple and scannable.
- Save useful third-party docs into `docs/third_party/` and record source URLs + retrieval date in `docs/README.md`.

## Rapport & Collaboration Cues
- User prefers direct, action-first responses.
- Always commit and push after every edit.
- When asked to commit/push, do it immediately and report results.
- If blocked by git conflicts, ask for a clear next action.

## Reflection Notes
If this file grows too long, consolidate repeated guidance into short bullets
and move long how-tos into dedicated docs.

## Cross-repository work tracking

For work on this repository for Jack, maintain the private [jhacksman knowledge wiki](https://github.com/jhacksman/jhacksman-knowledge-wiki). Read its `AGENTS.md`, `_index.md`, and `_schema.md` before updating it; re-check task-critical facts at their sources.

- At task start, when blocked, at handoff, and at completion, create or update the task's single `work/items/<id>.json` record. Reuse its stable ID rather than creating duplicate records.
- Follow the existing schema: `id`, `title`, `repos`, `status`, `owner`, `updated_on`, `next_step`, and `evidence`. Include this repository in `repos`, identify the project in `title`, and use `active`, `blocked`, `paused`, or `done` accurately.
- In the existing optional `notes` field, record the execution machine (and any separate target machine) and decisions needed from Jack, explicitly saying `none` when there are none. Use `blocker` for the exact obstacle when blocked. At handoff, record the recipient and concrete next action; at completion, link the result and set `next_step` to `none`.
- Support the record with dated, direct evidence links. A push or open PR alone does not establish that a task is active. Keep secrets and unnecessary personal data out of the wiki and public repository.
- From the wiki root run `python3 scripts/sync_github.py --offline`, then `python3 scripts/sync_github.py --offline --check`. Commit the work record and generated views together. Use a branch and PR for concurrent wiki edits; reconcile generated-view conflicts by rerunning the renderer after merging records.
- If wiki access or publication is blocked, report the exact failure and retain the pending update in the task's working artifacts for handoff. Do not claim the wiki was updated, invent a parallel tracking schema, or let the tracking failure stop independent authorized work.

Keep repository-specific instructions in effect alongside this tracking requirement.
