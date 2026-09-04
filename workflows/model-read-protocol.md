# Model Read Protocol

Defines how much of this repository a model should read for a given request. Read only what the task needs — this is the "least-context access" principle from `README.md`.

## Level 0 — No Repository Read Needed

Use when the request is general knowledge, a standalone explanation, a trivial transformation, or otherwise independent of Dalton's history. Do not read personal context just because it's available.

*Example:* "Explain how TLS handshakes work." No repository read needed.

## Level 1 — Root Context Read

Read `context.md` when the request depends on user preferences, broad priorities, education, career trajectory, known projects, or established working style, but doesn't need deep detail.

*Example:* "Should I take on a side project right now given everything going on?" → read `context.md` for current priorities and active projects.

## Level 2 — Targeted Deep Read

Read `context.md` plus the relevant deeper file(s) when the request involves continuing or modifying an existing project, prior technical decisions, academic or career planning, detailed personal context, established architecture, project milestones, or previously unresolved questions.

Worked examples:

| Task | Read |
|---|---|
| IELTS app work | `context.md` + `projects/ielts-study-app.md` |
| University/degree planning | `context.md` + `context/education.md` + `projects/university.md` |
| Writing-preference-sensitive work | `context.md` + `context/preferences.md` |
| Career/internship planning | `context.md` + `context/career.md` + `decisions/decisions.md` (relevant entries) |
| Cybersecurity portfolio work | `context.md` + `projects/cybersecurity-projects.md` + `context/technical-environment.md` |
| Germany/graduate-study planning | `context.md` + `context/education.md` + `context/languages.md` |

## Rule

Do not read every file for every request. If a request touches multiple domains, read only the specific files each domain maps to above — not the whole repository.
