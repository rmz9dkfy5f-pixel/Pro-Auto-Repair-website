# CHANGELOG

All notable changes to this project are documented here.
Format follows [Keep a Changelog](https://keepachangelog.com).
Versioning follows the rules in [Documents/01 Reference Documents/VERSIONING.md](Documents/01%20Reference%20Documents/VERSIONING.md).

---

## [Unreleased]

---

## [v1.2.1] — 2026-05-09

### Added
- `Documents/` folder: AI-assisted project scaffolding system
  - `00 Core Documents/`: 11 sequential setup prompts (start with `00_RUN_FIRST.md`)
  - `01 Reference Documents/`: full project-planning-stack-template (ROADMAP, ARCHITECTURE, RULES, TESTING, SECURITY, ACCESSIBILITY, PERFORMANCE, WIREFRAMES, IA, API, FLOWS, DATA_MODEL, DECISIONS, STATE_MODEL, CHANGELOG, ADRs)
  - `03 Optional Documents/`: Codex + Claude Code implementation bridge guide
  - `# Snapshot Info.md`: snapshot tracking template stamped to this release
- `.gitignore`: excludes macOS metadata (`.DS_Store`, `._*`)

---

## [v2] — 2026-04-21

### Added
- GitHub Pages design hub — root `index.html` selector linking all versioned demos
- `v2.0.0/index.html` and `v2.0.0/styles.css`: conversion-focused homepage (642 lines)
  - Top utility bar: service area label + hours strip
  - Sticky header with persistent call CTA
  - Hero with trust strip and dual CTAs; right panel is a real hours/address card
  - Proof bar: rating, makes served, estimate promise, address
  - 8 symptom-labeled service cards linking to v1.0.0 service pages
  - Why Choose Us: 4 numbered trust points + typical-visit callout
  - How It Works: 3-step numbered process
  - 3 Google-attributed customer review cards
  - $25 first-visit offer band with call CTA
  - Native `<details>` FAQ accordion (5 questions)
  - Contact/hours/map block with Google Maps iframe
  - Footer with dynamic copyright year

### Changed
- Hero right panel replaced fake live dashboard with real shop hours/address card
- Service cards switched to symptom-first labels (over generic capability titles)
- CTA strategy unified: `tel:` link as primary throughout; no non-functional booking anchor

### Removed
- Unverified claims: fake dashboard widget, unsourced star rating, pricing anchors, warranty claims, placeholder address

---

## [v1] — 2026-02-11

### Added
- `v1.0.0/` and `v2.0.0/` versioned folders for GitHub Pages deployment
- Root selector `index.html` to navigate between site versions
- Preserves original full site in `v2.0.0/` alongside a minimal version in `v1.0.0/`

---

## [v0.0.1] — 2026-02-01

### Added
- Initial mechanic website HTML/CSS foundation (`6ce8b52`)
- Real site files uploaded and iterated over (`8218dd8`, `95faafa`)
- Initial deployment to `main` branch (`d824dc3`)
