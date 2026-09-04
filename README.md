# dalton-context

A private, version-controlled context layer that lets multiple AI systems (Claude, ChatGPT, and others Dalton uses) work from the same understanding of his identity, education, career, active projects, decisions, and working preferences — instead of each system holding its own partial, drifting picture.

This is **not** a diary, a transcript archive, a generic notes folder, or a prompt dump. It is a structured, user-owned knowledge system with the auditability of Git and the readability of Markdown.

## Purpose

Both ChatGPT and Claude should be able to consult this repository before doing work that depends on Dalton's history, current projects, preferences, or prior decisions — rather than re-deriving that context from scratch each session, or worse, silently guessing at it.

GitHub is the canonical datastore. The AI providers' own native memory features are supplementary. When this repository holds newer, explicitly verified information, it takes priority over what a given assistant's native memory happens to recall.

**`context.md` is the canonical entry point, but not necessarily the only relevant file.** It is a short briefing, not a substitute for the deeper files it links to.

**This repository does not replace original project source repositories.** It stores project *context* — state, decisions, history, cross-session continuity — not source code, build artifacts, or the projects themselves.

## Architecture

```
dalton-context/
├── README.md                    this file
├── CLAUDE.md                    operating contract for Claude Code specifically
├── context.md                   canonical entry point / briefing
├── CHANGELOG.md                 reverse-chronological log of meaningful changes
├── SECURITY.md                  privacy rules and what must never be stored
│
├── context/                     durable facts about Dalton, by domain
│   ├── identity.md
│   ├── education.md
│   ├── career.md
│   ├── preferences.md
│   ├── technical-environment.md
│   ├── languages.md
│   └── personal.md              PRIVATE — read only when materially relevant
│
├── projects/                    active/ongoing project context (not source code)
│   ├── README.md
│   ├── ielts-study-app.md
│   ├── cybersecurity-projects.md
│   ├── university.md
│   └── ankenwerks.md
│
├── decisions/
│   └── decisions.md             durable decision register, DEC-YYYY-MM-DD-NNN
│
├── workflows/                   how models should read and write this repo
│   ├── context-sync.md
│   ├── model-read-protocol.md
│   └── model-write-protocol.md
│
├── templates/                   reusable templates for new entries
│   ├── project-context-template.md
│   ├── decision-template.md
│   └── context-update-template.md
│
└── archive/                     superseded/stale detail kept for historical explanation
    └── README.md
```

## Context States

Every durable statement in this repository carries one of five states:

| State | Meaning |
|---|---|
| `STABLE` | Expected to remain valid until Dalton explicitly changes it (e.g. long-term professional direction, broad learning preferences). |
| `ACTIVE` | Current, time-sensitive — circumstances, commitments, project state. Must carry a `Last verified: YYYY-MM-DD` date. |
| `TENTATIVE` | An idea, possibility, or unconfirmed interpretation. **Never** treated as established fact. |
| `HISTORICAL` | Useful for understanding past work or decisions; not current, not a basis for present recommendations. |
| `SUPERSEDED` | Explicitly replaced by newer context. Kept for the record; must not influence current recommendations except when explaining history. |

A statement like "Dalton has considered Germany as a future residence" (`TENTATIVE`/`ACTIVE`-planning) must never silently become "Dalton is moving permanently to Germany." A statement like "this project may eventually use X" must never silently become "the project architecture uses X." Context retains its epistemic status — that is the whole point of the state model.

## Authority Hierarchy

When information conflicts, resolve in this order (highest first):

1. Dalton's current direct statement
2. Newer, explicitly verified `ACTIVE` repository context
3. `STABLE` repository context
4. Explicit recorded decisions (`decisions/decisions.md`)
5. `HISTORICAL` information
6. `TENTATIVE` information
7. Model inference

Older repository content never overrides a newer direct statement from Dalton. A model's own inference never overwrites an explicit fact. When a material conflict cannot be safely resolved by this order, the model should surface the conflict to Dalton rather than guess.

## Update Philosophy

Small, auditable changes over bulk rewrites. Explicit state and explicit uncertainty over confident-sounding prose. Dated information, with current state kept separate from history. Least-context access — read only what the task needs. Resistance to context drift: no fact sits `ACTIVE` forever without being re-verified; no model interpretation quietly becomes fact; no `TENTATIVE` plan quietly becomes established.

Default write posture: **read freely, propose conservatively, write intentionally.** See `workflows/model-write-protocol.md`.

## Privacy Principle

`SECURITY.md` and `context/personal.md` both apply the same rule: store the least-sensitive representation that preserves future usefulness. Labels like `PRIVATE` or `SENSITIVE` in this repository are model-handling instructions, not real access controls — the repository's actual privacy control is that it is a **private** GitHub repository. Keep it that way.

## How ChatGPT and Claude Should Consume This

- **Claude Code** reads `CLAUDE.md` automatically when working inside this repository; it encodes the read/write protocol as an operating contract.
- **Claude Projects**: add this repository via Project Knowledge (see the setup steps Dalton has on file) and re-sync when repository state changes materially — GitHub knowledge in a Claude Project does not update continuously on its own.
- **ChatGPT** (or any other assistant): point it at `context.md` as the entry point and give it the same read/write protocol described in `workflows/`. A ChatGPT-specific instructions file can be added later if needed; it is not required for v1.

Canonical context files (`context.md`, everything under `context/`, `projects/`, `decisions/`) intentionally avoid Claude-specific syntax so any model, or a human, can read them directly. Claude-specific operational behavior lives only in `CLAUDE.md`.

## How Changes Should Be Reviewed

- Small, explicit, user-requested context maintenance may be committed directly to `main`.
- Prefer a branch + PR for: major personal-context changes, architectural changes to this repository, mass cleanup, model-generated reinterpretations, multi-file deletions, migrations, and large project-state updates.
- Recommended (not enforced) branch protection: `main` is canonical; consequential AI-generated changes go through a PR that Dalton reviews before merge. See `CHANGELOG.md` and the final setup notes for what's actually configured versus recommended.

## Maintenance Cadence

See `README` section reproduced in each workflow file for detail, but in short: update event-driven (when something durable changes), review weekly (priorities, active projects, blockers), compact monthly (remove duplication and stale `ACTIVE` entries), audit quarterly (privacy, contradictions, superseded information, whether the current project list and educational/career direction are still right). The standing question for anything under consideration for removal: *would preserving this help an AI make a materially better decision three months from now?* If not, archive or remove it.
