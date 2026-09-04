# CLAUDE.md — Operating Contract for This Repository

This file is read automatically by Claude Code when working inside `dalton-context`. It governs how Claude reads and writes this repository. It does not apply to other repositories.

Context modification here is a **high-trust action**. This repository is Dalton's canonical cross-model memory, not a scratch space. Treat it accordingly.

## Before History-Dependent Work

1. Read `context.md`.
2. Decide whether deeper context is *materially* relevant to the current task. If not, stop here.
3. Read only the relevant linked file(s) — see `workflows/model-read-protocol.md` for the three read levels and worked examples.
4. Check each fact's state (`STABLE` / `ACTIVE` / `TENTATIVE` / `HISTORICAL` / `SUPERSEDED`) and, for `ACTIVE` facts, its `Last verified` date.
5. Check `decisions/decisions.md` for any decision that bears on the task.
6. Prefer Dalton's current direct statement over anything in the repository — the repository is context, not a constraint on what he says right now.
7. Do not pull in unrelated personal context just because it's available.

## Before Modifying Context

Classify the proposed change as exactly one of:

- **ADD** — new durable information with no existing entry
- **CHANGE** — an existing entry needs updating (state, date, detail)
- **SUPERSEDE** — new information replaces old information; the old information is kept and marked `SUPERSEDED`, not deleted
- **REMOVE** — the information should no longer exist in canonical context (privacy, no longer true, requested deletion)
- **ARCHIVE** — no longer current, but worth keeping for historical explanation; move to `archive/`

Then check all of:

- Is it durable (will plausibly matter again), not one-off chat exhaust?
- Is it material (would change a future response or recommendation)?
- Is it sufficiently certain (or should it be filed as `TENTATIVE`)?
- Is it scoped to the right file (see `README.md` for the file map)?
- Is it safe to store (see `SECURITY.md` — never secrets, never more sensitive than necessary)?

## Critical Write Guardrail

**New information appearing in conversation does not automatically become durable memory.** Default behavior:

> READ freely. PROPOSE conservatively. WRITE intentionally.

Direct writes to canonical context (`context/`, `projects/`, `decisions/decisions.md`, `context.md`) are permitted only when Dalton:

- explicitly requests a context sync (`Context sync.` or a scoped form — see `workflows/context-sync.md`),
- explicitly asks for the context repository to be updated,
- gives an equivalent unambiguous instruction, or
- is running a documented workflow whose purpose includes context maintenance.

If the change is consequential, ambiguous, sensitive, or interpretive, prefer a reviewable branch/PR over a direct commit to `main` — even if a write is otherwise permitted. When in doubt, use `templates/context-update-template.md` to draft the change and show Dalton the diff before committing.

## Context Quality Rule

Before storing anything, ask:

1. Is this likely to matter again?
2. Would future AI work materially improve by preserving it?
3. Is it still true?
4. Is the confidence level sufficient to state it as fact rather than `TENTATIVE`?
5. Can it be represented with less sensitive detail and still be useful?
6. Does another file already contain this? (Don't duplicate — cross-reference with `[[relative/path.md]]`-style links instead.)
7. Is this current state, history, or merely conversation residue that doesn't belong here at all?

Do not store low-value chat exhaust: passing moods, one-off logistics, anything that expires on its own.

## Mechanics for Direct Writes

1. Inspect the existing relevant file before editing it.
2. Modify only the sections that actually need to change.
3. Preserve unrelated context in the same file verbatim.
4. Update the `Last updated` / `Last verified` date on anything touched.
5. Update the context state if the fact's status changed (e.g. `TENTATIVE` → `ACTIVE` on confirmation).
6. Update `CHANGELOG.md` for any consequential change.
7. Update `decisions/decisions.md` if a durable decision was made or reversed.
8. Avoid duplicate entries — search before adding.
9. Run `git diff` and review it before finishing. Never bulk-rewrite a file when a targeted edit will do.

Never invent missing facts to fill a template section — leave it absent or write "not yet established" rather than guessing. Never "improve" a stated fact stylistically in a way that changes its meaning. Never touch files unrelated to the change at hand.

For large or multi-file changes, use a branch and open a PR rather than committing directly to `main`.

## Privacy

Do not surface unrelated personal information merely because it exists in the repository. Use the minimum relevant context necessary for the current task. `context/personal.md` is classified `PRIVATE` — read it only when the task materially depends on it.
