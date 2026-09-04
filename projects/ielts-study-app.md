# Project: IELTS Academic UA+EN Study Webapp

## Metadata

Status: ACTIVE
Priority: HIGH
Last updated: 2026-09-04

## Objective

Build a complete, mobile-first, bilingual Ukrainian/English IELTS Academic preparation system targeting approximately Band 7.0–8.0 / C1 performance.

## Why It Exists

IELTS Academic preparation requires coordinated coverage across reading, writing, listening, speaking, vocabulary, and grammar, with bilingual (UA/EN) explanation so the material is usable in both languages rather than English-only. No off-the-shelf tool covers this the way Dalton wants it structured.

## Current State — `ACTIVE`, last verified 2026-09-04

**Current build phase:** G3 Reading Curriculum is the current major implementation phase.

**Architecture/deployment decision:** the build stays local HTML until the local implementation is complete and validated. See `decisions/decisions.md` — `DEC-2026-09-04-002`. Do not prematurely reconcile or deploy the public version.

## Scope — Capabilities

- IELTS test structure
- Bilingual UA+EN explanations throughout
- Reading, Writing, Listening, Speaking modules
- Vocabulary, including C1 vocabulary and selected C2 vocabulary
- Grammar and sentence structure
- Graph and data interpretation (Academic Writing Task 1 style)
- Diagnostics and practice banks
- Mastery tracking and spaced review
- Error analysis
- Mock testing
- Adaptive recommendations

## Product Principle

Preserve the useful original study-guide material and the bilingual design while expanding it into a deeper, structured curriculum — this is an extension of existing work, not a from-scratch replacement of it.

## Validation Principle

A feature or phase is not complete merely because it exists visually. It must pass its defined benchmarks and validation criteria before being considered done. (Per-phase validation criteria live with the build itself, not duplicated here — this file tracks project-level state, not a running test log.)

## Constraints

- Stays local-HTML until the local build is validated (see decision above).
- Bilingual UA/EN coverage is a hard requirement, not a nice-to-have layered on later.

## Open Questions

- Exact validation benchmarks per phase (reading, writing, etc.) — not yet consolidated into this file.
- Timeline for reconciling the local build with a deployed public version.

## Related Resources

- `context/languages.md` — Ukrainian language context (this project has its own bilingual scope distinct from general Ukrainian study)
- `decisions/decisions.md` — `DEC-2026-09-04-002`

## History

- 2026-09-04 — Project context seeded into `dalton-context`. Current phase recorded as G3 Reading Curriculum, local-HTML build stage.
