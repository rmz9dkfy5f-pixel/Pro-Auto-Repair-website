# Repository Handoff Configuration

Project-local handoff/closeout configuration. Fill in only real, confirmed values — never
placeholder paths or commands presented as facts. For any section that does not apply given this
repository's `PROJECT_CLASSIFICATION.md` entry, write `N/A — <reason>` instead of deleting the
section or inventing a value.

Store operational coordinates here, never credentials. If this repository already has equivalent
configuration in `AGENTS.md`, deployment docs, or another canonical file, reference it rather than
duplicate it.

## Repository Identity

- Project name: Pro Auto Repair Website
- Repository root: `/Users/ant/Projects/GitHub/Pro-Auto-Repair-website`
- Canonical remote: `https://github.com/rmz9dkfy5f-pixel/Pro-Auto-Repair-website.git`
- Default branch: `main`
- Canonical handoff file: `docs/governance/AGENT_RUN_LOG.md`

## Validation Contract

Discover these from the real toolchain (`package.json`, `pyproject.toml`, `Makefile`, CI config,
etc.) — do not invent commands that were not actually found.

- Install command: N/A — static HTML repo; no package manager or dependency manifest found.
- Focused test commands: N/A — no automated test suite found.
- Full test command: N/A — no automated test suite found.
- Lint/type-check commands: N/A — no lint or type-check toolchain found.
- Production build command: N/A — static HTML repo; no build step. GitHub Pages serves the
  repository root directly.
- Runtime smoke test: Open root `index.html` (design hub) and each version folder's `index.html`
  (`v0.0.1/`, `v1.0.0/`, `v2.0.0/`) locally and confirm they render and link correctly.
- Manual or device checks: For UI changes, inspect desktop and mobile layouts manually; confirm no
  unverified claims (fake hours, ratings, prices, warranties) were newly published to `v2.0.0/`,
  per this project's own Non-Negotiables.

## Snapshot Contract

Applies to Git-backed classifications (see `PROJECT_CLASSIFICATION.md`). Write `N/A — not
Git-backed` if this repository is Vault-only or Local non-Git.

- Snapshot required: no — Git history and the GitHub remote (`origin`) are this repository's only
  backup/snapshot mechanism; no separate snapshot process exists.
- Naming rule: N/A — no snapshot file exists. Version history is tracked via Git tags (`v0.0.1`,
  `v1`, `v2`, `v1.2.1`) and `CHANGELOG.md`/`RELEASE_NOTES.md`.
  `Documents/# Snapshot Info.md` is a one-off historical stamp from the v1.2.1 release, not an
  ongoing snapshot process.
- Exclusions: N/A — no snapshot process exists.
- Verification method: N/A — no snapshot process exists.
- Checksum requirement: N/A — no snapshot process exists.
- Retention policy: N/A — Git history retention is unbounded by default; no separate policy exists.
- Restore/rollback procedure: Use Git to check out or revert to the desired committed version or
  tag (`git checkout <tag>`, `git revert`, or `git reset` on a dedicated branch).

### Snapshot Destination by Machine

Only relevant if snapshots are machine-path-dependent (e.g. an external backup drive). Detect the
current machine before resolving a destination:

```bash
scutil --get ComputerName 2>/dev/null || hostname
```

| Machine | Detection | Snapshot destination | Notes |
|---|---|---|---|
| N/A | N/A | N/A | No machine-path-dependent snapshot destination is used for this repository; Git plus the GitHub remote is the sole backup/restore mechanism. |

If the current machine does not match any row above, or more than one row could plausibly match,
stop and ask before picking a destination — do not guess or infer a path pattern.

## Deployment Contract

Applies to the "Git-backed with deployment" classification (repository classified
`git_backed_with_deployment` by `starter_kit.py inspect`; confirmed via `gh api
repos/rmz9dkfy5f-pixel/Pro-Auto-Repair-website/pages`: `status: built`, `source: {branch: main,
path: /}`, `public: true`, `https_enforced: true`).

- Deployment in scope: yes — static GitHub Pages deploy only. No build step, no server-side
  process, no container.
- VPS/server alias: N/A — GitHub Pages hosted; no VPS or server under this project's control.
- Deployment root: N/A — GitHub Pages serves the repository root directly; no separate deployment
  directory.
- Deployment branch or artifact: `main` branch root (`/`), auto-built and deployed by GitHub Pages
  on every push — no manual build/deploy step and no CI pipeline.
- Service/container names: N/A — GitHub-managed static hosting, no app process.
- Read-only health checks: `curl -fsSI https://rmz9dkfy5f-pixel.github.io/Pro-Auto-Repair-website/`
  — expect `200`.
- Log locations: N/A — GitHub Pages does not expose server logs to the repository owner.
- Rollback target: revert or reset the offending commit on `main` and push; GitHub Pages
  redeploys automatically from the new `main` HEAD.
- Actions requiring approval: any push to `main` requires explicit user authorization — GitHub
  Pages redeploys automatically on push, so a push to `main` is itself the deploy action with no
  separate confirmation step.

## Safety Boundaries

- Protected paths: `v0.0.1/`, `v1.0.0/`, `v2.0.0/` (historical demo versions, read-only per this
  project's own Non-Negotiables — see `docs/project/PROJECT_BRIEF.md`); `assets/`.
- Secret-bearing files: none identified — static site, no credentials, API keys, tokens, or `.env`
  files exist in this repository.
- Prohibited actions: do not introduce a JavaScript framework or build toolchain (per
  `docs/project/DECISION_LOG.md`, 2026-02-01 entry); do not modify `v0.0.1/` or `v1.0.0/`; do not
  add unverified claims (fake hours, ratings, prices, warranties) to `v2.0.0/` without owner
  verification.
- Commit/push authorization rule: commit freely for reviewed work; push to `main` only when
  explicitly requested, since a push auto-deploys via GitHub Pages.
- Tag/release authorization rule: tag or mark releases only when explicitly requested or when
  following an approved release plan.
- Deploy/merge authorization rule: no separate deploy step exists — pushing to `main` is the
  deploy. Treat the push-to-`main` authorization rule above as the deploy authorization rule.
