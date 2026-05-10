# Release Notes — Pro Auto Repair Website

---

## v1.2.1 — Project Scaffolding System
**Released:** 2026-05-09
**Commits:** `110d062` → `be32423`
**Tag:** `v1.2.1`

Introduces a `Documents/` folder containing a structured, AI-assisted setup
system designed to guide Claude Code and Codex through methodical project
planning before implementation. The system is organized into three tiers:

- **00 Core Documents/** — 11 sequential prompts that walk through repo
  planning, scaffolding, strategy, architecture, versioning, and first-task
  planning. Begin with `00_RUN_FIRST.md`.
- **01 Reference Documents/** — a complete `project-planning-stack-template/`
  covering ROADMAP, FLOWS, DATA_MODEL, ARCHITECTURE, RULES, SECURITY, TESTING,
  ACCESSIBILITY, PERFORMANCE, WIREFRAMES, IA, API, DECISIONS, STATE_MODEL,
  CHANGELOG, and ADRs. Also includes `VERSIONING.md` (semver reference).
- **03 Optional Documents/** — implementation bridge guide for parallel
  Codex + Claude Code workflows.

Also adds `.gitignore` to exclude macOS-generated metadata (`.DS_Store`, `._*`)
from future commits.

---

## v2 — Conversion-Focused Homepage & Design Hub
**Released:** 2026-04-21
**Commits:** `681e062` → `74dc53b` → `53343dc`
**Tag:** `v2`

A full redesign of the homepage (`v2.0.0/`) built around conversion goals. Key
improvements over the v1 foundation:

- **Design hub** — root `index.html` links all versioned demos from one page
- **Sticky header** with persistent call CTA visible at every scroll position
- **Hero** featuring Option C headline, trust strip, and dual CTAs; the
  previously fake "live dashboard" right panel was replaced with a real
  hours/address card
- **Proof bar** — rating, makes served, free-estimate promise, address
- **Symptom-first service cards** — 8 cards labeled by what the customer
  notices, not shop capability names
- **3-step How It Works** process (call → inspect → approve/fix)
- **FAQ accordion** using native `<details>` — 5 common questions
- **Customer reviews** — 3 cards attributed to Google
- **$25 first-visit offer** band with direct call CTA
- **Full contact block** with Google Maps iframe embed

Unverified claims from earlier versions were removed: fake dashboard widget,
unsourced star rating, pricing anchors, warranty claims, and placeholder address.

> This is a pilot/demo version. Production deployment requires verifying
> hours, email, review attribution, and offer terms with the shop owner.

---

## v1 — GitHub Pages Versioned Structure
**Released:** 2026-02-11
**Commits:** `e9daf7d` → `9b9d3fb`
**Tag:** `v1`

Restructured the repository for GitHub Pages deployment with separate versioned
folders (`v1.0.0/`, `v2.0.0/`) and a root selector page. The original full
site was preserved in `v2.0.0/` while a minimal version lives in `v1.0.0/`,
allowing both to be served and compared from a single GitHub Pages site.

---

## v0.0.1 — Foundation
**Released:** 2026-02-01
**Commits:** `6ce8b52` → `8a30270` → `8218dd8` → `95faafa` → `d824dc3`
**Tag:** *(pre-release, untagged)*

Initial mechanic website scaffold: HTML/CSS foundation created, real site files
uploaded and iterated, first deployment pushed to the `main` branch. This
version established the baseline design tokens and page structure that later
versions build on.
