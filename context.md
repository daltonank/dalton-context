# context.md — Canonical Briefing

```
schema_version: 1.0
last_updated: 2026-09-04
context_owner: Dalton Ankenbrand
purpose: Cross-model context briefing for AI systems (Claude, ChatGPT, others)
          working with Dalton on projects, planning, or personal-context-dependent tasks.
```

This is the entry point for this repository, not the whole of it. Read this file first. Read a deeper linked file only when the current task actually depends on it — see `workflows/model-read-protocol.md` for the three read levels.

## Interpretation Rules

**Context states.** Every durable fact in this repository carries one of five states: `STABLE` (holds until Dalton changes it), `ACTIVE` (current, time-sensitive, carries a `Last verified` date), `TENTATIVE` (an idea or possibility — never treat as decided), `HISTORICAL` (useful past context, not current), `SUPERSEDED` (explicitly replaced — kept for the record, not for current recommendations). Full definitions: `README.md`.

**Authority order**, highest first:
1. Dalton's current direct statement (this conversation, right now)
2. Newer, explicitly verified `ACTIVE` repository context
3. `STABLE` repository context
4. Explicit recorded decisions (`decisions/decisions.md`)
5. `HISTORICAL` information
6. `TENTATIVE` information
7. Model inference

Older repository content never overrides a newer direct statement from Dalton. A model's inference never overrides an explicit fact. If a conflict can't be resolved by this order, say so — don't guess.

**Privacy.** Use only the personal context that is materially relevant to the current task. See `SECURITY.md` and `context/personal.md`.

## Identity Summary

Dalton Ankenbrand, based in the St. Louis, MO area. Working toward a B.S. in Cybersecurity (minors: Computer Science, Management Information Systems) at Maryville University, aimed at defensive cybersecurity, cloud/infrastructure security, and technically-informed IT leadership. Full detail: `context/identity.md`.

## Education Summary

B.S. Cybersecurity at Maryville University, expected graduation May 2027 (subject to final scheduling), cumulative GPA 3.465. Longer-term interest in graduate study in Europe, with University of Koblenz's M.Sc. E-Government as a current target — this is a direction, not a confirmed admission. Full detail: `context/education.md`.

## Career Summary

Currently an IT Intern at Russell Construction (St. Louis). Previously a full-time air ramp supervisor at UPS. Professional direction: defensive cybersecurity, cyber threat intelligence, security engineering, technically-oriented IT work. Full detail: `context/career.md`.

## Current Priorities

1. Complete the Cybersecurity B.S. (target: May 2027) while building a portfolio that supports the defensive-security direction.
2. Russell Construction internship — deliver value, build toward a possible IT/security role.
3. Germany/Koblenz preparation — German language study, M.Sc. E-Government research, funding.
4. Active technical projects (IELTS study app, cybersecurity portfolio work, Ankenwerks).

*(Last verified: 2026-09-04. See `decisions/decisions.md` and each project file for detail — this list is intentionally short.)*

## Active Projects

| Project | Status | Phase | Detail |
|---|---|---|---|
| IELTS Academic UA+EN Study Webapp | ACTIVE, HIGH priority | G3 Reading Curriculum build phase; local HTML build (not yet deployed) | `projects/ielts-study-app.md` |
| Cybersecurity portfolio (CTI feed, etc.) | ACTIVE | CTI feed functional locally; enrichment sources TENTATIVE | `projects/cybersecurity-projects.md` |
| University / degree completion | ACTIVE | Coursework in progress, incl. ISYS-481 Cloud Computing & Virtualization | `projects/university.md` |
| Ankenwerks | ACTIVE / EVOLVING | Umbrella identity for technical/security/automation work | `projects/ankenwerks.md` |

## Working Preferences

Learns best through hands-on implementation, conceptual decomposition, and connecting theory to real systems — not answers without mechanism. Prefers computational framing (inputs/outputs/states/rules) for abstractions. Writing preference: academic-but-practical, evidence-based, precise, no generic corporate prose, no em dashes. Full detail: `context/preferences.md`.

## Decision Register

See `decisions/decisions.md` for all recorded architectural and project decisions, each with an ID, rationale, and status.

## Recently Changed

- **2026-09-04** — Repository created. Initial context system stood up (identity, education, career, preferences, technical environment, languages, personal; IELTS app, cybersecurity projects, university, Ankenwerks; decision register seeded with 3 decisions). See `CHANGELOG.md`.

*(This section holds only recent, consequential changes — not a running history. Older entries move to `CHANGELOG.md` and, where no longer relevant to current state, `archive/`.)*
