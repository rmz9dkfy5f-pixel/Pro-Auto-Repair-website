# Commit Notes

## Suggested Commit Template

```text
<type>: <short summary>

- What changed:
- Why:
- Validation:
- Risks:
```

## Commit Types

- feat
- fix
- docs
- refactor
- test
- chore
- security
- perf

## Session 2026-09-10 — Starter Kit v3.10.0 Adoption Closeout

```text
docs: session-end closeout for Starter Kit v3.10.0 adoption

- What changed: filled in the kit's own docs/project/ and
  docs/governance/AGENT_RUN_LOG.md continuity files (previously
  placeholder TBD content left by the migration); this push will be
  tagged v1.3.0, applied in Section 7 of the session-end super prompt.
- Why: closes out the session that adopted the Starter Kit
  (web_application profile), confirmed its release-blocking facts
  with the repository owner, and documented a real snapshot
  destination — see MIGRATION_REPORT.md and
  docs/governance/REPOSITORY_HANDOFF_CONFIG.md for full detail.
- Validation: validate PASS, validate --release PASS (re-run after
  these edits).
- Risks: none — no runtime/demo files touched
  (v0.0.1/, v1.0.0/, v2.0.0/, assets/, index.html unchanged).
```
