# Decision Register

Durable decisions, one entry per decision, IDs in `DEC-YYYY-MM-DD-NNN` format (NNN resets per day). New decisions use `templates/decision-template.md`. Allowed statuses: `ACTIVE`, `SUPERSEDED`, `REVERSED`, `HISTORICAL`.

---

## DEC-2026-09-04-001 — GitHub as Canonical Cross-Model Context Store

**Date:** 2026-09-04
**Status:** ACTIVE
**Related project:** repository-level (this repository)

### Decision

Use the private `dalton-context` GitHub repository as the authoritative shared context store between Claude and ChatGPT.

### Rationale

Both assistants need a common, durable, auditable source of truth about Dalton's identity, projects, preferences, and decisions that survives across sessions and isn't locked into either provider's native memory format.

### Implications

Native provider memory (Claude's memory, ChatGPT's memory) is supplementary. When this repository holds newer, explicitly verified information, it takes priority over what a provider's native memory recalls. See the authority hierarchy in `README.md` and `context.md`.

### Supersedes

None.

---

## DEC-2026-09-04-002 — IELTS App: Local Build Sequence Before Deployment

**Date:** 2026-09-04
**Status:** ACTIVE
**Related project:** `projects/ielts-study-app.md`

### Decision

Keep the IELTS Academic UA+EN Study Webapp as a local HTML implementation until the local build is complete and validated, then reconcile and deploy the public version.

### Rationale

Avoids prematurely locking in a deployed architecture before the curriculum build (currently at the G3 Reading Curriculum phase) and its validation criteria are settled.

### Implications

Any AI-assisted work on this project should not push toward public deployment or hosting decisions until Dalton explicitly signals the local build is validated and ready to reconcile.

### Supersedes

None.

---

## DEC-2026-09-04-003 — Undergraduate Direction: Cybersecurity B.S.

**Date:** 2026-09-04
**Status:** ACTIVE
**Related project:** `projects/university.md`, `context/education.md`

### Decision

Current undergraduate direction is a B.S. in Cybersecurity, with minors in Computer Science and Management Information Systems, at Maryville University.

### Rationale

Aligns coursework with the stated long-term professional direction (defensive cybersecurity, cloud/infrastructure security, technically-informed IT leadership — see `context/career.md`).

### Implications

Academic planning, portfolio-building advice, and career-direction discussions should treat this as the settled undergraduate direction unless Dalton states a change directly.

### Supersedes

None.

---

*(Add new decisions above this line using `templates/decision-template.md`. Never delete a decision — mark it `SUPERSEDED`, `REVERSED`, or `HISTORICAL` and note what replaced it.)*
