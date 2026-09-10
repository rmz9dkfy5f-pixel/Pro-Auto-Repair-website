# v3.10.0 Migration Report

Run `python3 scripts/starter_kit.py --target <this repo> adopt-audit` before filling this in — it produces the
Git State, Role Mapping, and Agent-Neutral Handoff Gap sections below automatically. See
`ADOPTION_POLICY.md` for the rules governing this migration.

## Status

Completed for the initial v3.10.0 install/migration slice. `validate` (structural): PASS.
`validate --release`: BLOCKED, pending owner-supplied facts (see Risks/Next Action) — expected for
a first migration, not a defect in the migration itself.

## Git State

- Branch: `starter-kit-migration`
- Matches expected default branch: no — dedicated migration branch, run with
  `--allow-non-default-branch` per `release/MIGRATION_GUIDE.md` step 1
- Working tree clean: yes, before apply (the session's own `.claude/settings.json` was gitignored
  first so the dirty-tree gate could pass cleanly, not bypassed)

## Existing Instructions Found

- No `AGENTS.md`, `CLAUDE.md`, or `HANDOFF_TO_CLAUDE.md` existed at repo root before this migration
  (`adopt-audit` reported `legacy_continuity_files: []`).
- `README.md`, `CHANGELOG.md`, `RELEASE_NOTES.md` exist at root with real content — none were
  targeted for replacement by the plan (0 conflicts).
- `Documents/` — a separate, pre-existing 11-prompt Markdown scaffolding system unrelated to any
  version of this kit (added in commit `110d062`, tagged `v1.2.1`, 2026-05-09). Not a legacy
  continuity file in the kit's sense; see Suggested Merges below for its disposition.

## Legacy Continuity File Role Mapping

| Legacy file found | Nearest v3.10.0 equivalent | Decision |
|---|---|---|
| None (`adopt-audit` found no prior-kit continuity files) | N/A | No legacy role mapping needed — this project never ran any prior version of this kit |

## Agent-Neutral Handoff Gap

- No root `HANDOFF_TO_CLAUDE.md` existed, so no agent-neutral handoff gap was found at repo root.
  (This project's continuity records live in the AntBrainOS vault project folder,
  `03_PROJECTS/Backlog/Pro_Auto_Repair_Website/`, not in the repo itself — unaffected by this
  migration; update separately.)

## Compatibility Aliases To Preserve

- None from a prior local install. The kit's own v3.4 compatibility aliases
  (`.agents/skills/v34-*/SKILL.md`, `ai/prompts/V34_AGENT_TASK_PROMPT.md`) were installed as
  standard kit files, not preserved from anything pre-existing.

## Files Installed

66 creates, 0 replacements, 0 conflicts (plan `91fbf065a5ab0b69bd742310d859d850dcb1a75068c739ac856f46f149c06fa7`,
run `7823236a-cea6-407a-8a3d-b0521a5989ab`):

- `.agents/skills/` — 12 skill files (8 starter-kit, 4 v3.4 compatibility aliases)
- Root governance: `AGENTS.md`, `MODEL_SELECTION_GATE.md`, `PROMPT_MODEL_SELECTION_GATE.md`
- `ai/` — 4 files (agent review gates, subagent roles, migration/task-intake prompts)
- `docs/governance/` — 18 files (release gate, security baseline, project classification, etc.)
- `docs/project/` — 9 files (`PROJECT_BRIEF.md`, `ARCHITECTURE.md`, `STATUS.md`, `ROADMAP.md`,
  `CONTEXT.md`, `DECISION_LOG.md`, `CHANGELOG.md`, `COMMIT_NOTES.md`, `RELEASE_NOTES.md`)
- Migration docs: `00_MIGRATION_KICKOFF.md`, `ADOPTION_POLICY.md`, `MIGRATION_REPORT.md` (this file)
- `.starter-kit/` — 16 generated governance/state JSON files (manifest, profile, validation
  contract, SBOM, provenance, threat model, etc.)

Verified untouched: `v0.0.1/`, `v1.0.0/`, `v2.0.0/`, `assets/`, `index.html`
(`git diff --stat main` against each is empty).

## Conflicts Preserved In Transaction Evidence

- None — 0 conflicts. Journal: `.starter-kit/migrations/7823236a-cea6-407a-8a3d-b0521a5989ab/journal.json`.

## Suggested Merges

Three `shadowed_document` warnings from `plan-migration`, each reviewed and decided explicitly
(never accepted as a side effect of applying the plan):

1. `docs/project/ARCHITECTURE.md` shadows `Documents/01 Reference Documents/project-planning-stack-template/ARCHITECTURE.md`
   (a never-filled-in blank skeleton). **Decision: keep both.** `docs/project/ARCHITECTURE.md` is
   now the active, kit-governed architecture doc; the `Documents/` skeleton stays purely historical
   per the note added to `Documents/00 Core Documents/00_RUN_FIRST.md`.
2. `docs/project/ROADMAP.md` shadows `Documents/01 Reference Documents/project-planning-stack-template/ROADMAP.md`
   (same situation). **Decision: keep both**, same reasoning.
3. `docs/project/RELEASE_NOTES.md` shadows the root `RELEASE_NOTES.md` (real, populated content
   covering v0.0.1–v1.2.1). **Decision: keep both.** Root `RELEASE_NOTES.md` remains the historical
   pre-Starter-Kit release record; `docs/project/RELEASE_NOTES.md` becomes the active,
   kit-governed release notes file for this migration onward.

## Risks

- This is a governance/scaffolding migration only — confirmed no website runtime/demo files
  changed (see Files Installed).
- `validate --release` is currently `BLOCKED` on five facts that require explicit owner
  confirmation, not a defect: `public_exposure`, `data_sensitivity`, `risk_level`
  (`.starter-kit/project-profile.json`), an unresolved snapshot/backup destination
  (`docs/governance/REPOSITORY_HANDOFF_CONFIG.md`), and privacy classification
  (`.starter-kit/privacy-classification.json`). Likely answers given this is a public GitHub Pages
  demo site with only fictional/placeholder shop data — `public_exposure: true`,
  `data_sensitivity: none`, `risk_level: low` — but these are recorded here as a recommendation,
  not filled in unilaterally.

## Next Action

- Owner to confirm the five release-blocking facts above, then re-run `validate --release`.
- Review the full `starter-kit-migration` branch diff against `main`, merge when satisfied.
- Update the vault's `03_PROJECTS/Backlog/Pro_Auto_Repair_Website/` continuity files to record this
  migration.
