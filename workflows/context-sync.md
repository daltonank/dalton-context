# Context Sync

Defines the explicit command: **`Context sync.`**

## Interpretation

When Dalton says `Context sync.` (or a scoped form — see below), the model should:

1. Review meaningful new developments supplied in the current work context (this conversation, recent files, recent decisions Dalton has stated).
2. Compare them against canonical repository state.
3. Identify durable deltas — information that has actually changed, not conversational noise.
4. Classify each delta as one of: **ADD**, **CHANGE**, **SUPERSEDE**, **REMOVE**, **ARCHIVE** (see `CLAUDE.md` for definitions).
5. Ignore transient conversational material that doesn't meet the context-quality bar in `CLAUDE.md`.
6. Update only the relevant files.
7. Preserve unrelated context in every file touched.
8. Update dates (`Last updated` / `Last verified`) on anything changed.
9. Update `CHANGELOG.md`.
10. Update `decisions/decisions.md` where a durable decision was made or changed.
11. Review the final diff for accidental context loss before finishing — a sync should never silently drop information that's still valid.

## Scoped Forms

Support scoped syncs that limit the sweep to one domain:

- `Context sync: IELTS`
- `Context sync: university`
- `Context sync: career`
- `Context sync: preferences`
- `Context sync: personal`

A scoped sync must not edit files outside its named domain, except where strictly necessary to maintain an explicit cross-reference (e.g. a career change that also requires updating a decision it's linked from). When that happens, note it explicitly in the sync's summary and in `CHANGELOG.md` rather than doing it silently.

## Output of a Sync

A sync should end with a short summary Dalton can review: what changed, in which files, and why — not a silent commit. Use `templates/context-update-template.md` as the working scratchpad for drafting the sync before committing it.
