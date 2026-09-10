# Context

Use this file for durable project context that agents need across sessions.

## Project-Specific Facts

- Pure static HTML/CSS site — no JavaScript framework, no build tool, no backend, no package
  manager. `docs/governance/REPOSITORY_HANDOFF_CONFIG.md`'s Validation Contract confirms no
  install/test/lint/build commands exist.
- Deployed via GitHub Pages, auto-built from `main` branch root on every push — no CI pipeline, no
  manual deploy step. See the Deployment Contract in `docs/governance/REPOSITORY_HANDOFF_CONFIG.md`.
- Three versioned demo folders (`v0.0.1/`, `v1.0.0/`, `v2.0.0/`) are historical/current design
  iterations, linked from the root `index.html` design hub. `v0.0.1/` and `v1.0.0/` are read-only
  history; `v2.0.0/` is the current best design.
- `v2.0.0/` shop data (hours, address, reviews, `$25` offer) is explicitly fictional/placeholder —
  never present it as production-ready without owner verification.
- `Documents/` is a separate, historical 11-prompt scaffolding system that predates this kit and is
  unrelated to it — preserved unmodified, marked historical in its own `00_RUN_FIRST.md`. Do not
  confuse it with this kit's own governance docs.
- Snapshot/backup destination for this machine (Anthony's MacBook Pro):
  `/Users/ant/WorkSync/Projects/RepoBackups/Pro Auto Repair` — but that folder also contains
  unrelated, non-authoritative extra content (a generic `v3.0.0/` template for a different
  business, mostly-empty scaffolding stubs); see the warning in
  `docs/governance/REPOSITORY_HANDOFF_CONFIG.md`'s Snapshot Contract before trusting anything in
  it beyond `v0.0.1/`/`v1.0.0/`/`v2.0.0/`/root `index.html`.

## Known Constraints

- Do not introduce a JavaScript framework or build toolchain (`docs/project/DECISION_LOG.md`,
  2026-02-01 decision).
- Do not modify `v0.0.1/` or `v1.0.0/` — historical, read-only.
- Do not add unverified claims (fake hours, ratings, prices, warranties) to `v2.0.0/`.
- A push to `main` is itself the deploy (GitHub Pages auto-builds) — treat push authorization as
  deploy authorization; there is no separate deploy step to gate.

## Repeated Corrections

- None yet.
