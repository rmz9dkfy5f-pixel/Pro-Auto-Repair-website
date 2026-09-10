# Decision Log

Brief table for this repo's own kit-governed record. Full rationale for each decision lives in the
AntBrainOS vault's `03_PROJECTS/Backlog/Pro_Auto_Repair_Website/DECISION_LOG.md` — this table
points to it rather than duplicating it.

| Date | Decision | Reason | Alternatives Considered | Status |
|---|---|---|---|---|
| 2026-02-01 | Pure HTML/CSS, no JS framework | Zero-dependency static demo, no build step needed | Astro/Eleventy; vanilla JS for interactivity | Accepted |
| 2026-02-11 | Multi-version folder structure on GitHub Pages | Compare design iterations side by side without destroying history | Separate branches/repos per version | Accepted |
| 2026-04-21 | Remove all unverified claims from v2.0.0 | Demo integrity — no fake "real" data | Fake data with a demo disclaimer badge | Accepted |
| 2026-04-21 | Symptom-first service card labels | Conversion-oriented UX, matches customer intent | Generic capability titles; icon-only cards | Accepted |
| 2026-05-09 | Add `Documents/` reusable AI scaffolding system | Capture the project's own planning workflow as a reusable template | Separate repo; document in CLAUDE.md only | Accepted |
| 2026-09-09 | Adopt AntBrainOS Project Starter Kit v3.10.0; `Documents/` becomes historical | Standardize on the vault's general project-governance tool; `Documents/` predates it and is unrelated | Delete `Documents/`; merge its content into the kit's docs | Accepted |
| 2026-09-10 | Reject promoting a `v3.0.0` backup-folder template to main version | Investigation showed it's a generic, unrelated "Atlas Auto Repair" template, not project history | Promote it as requested; ignore the mismatch | Accepted |
