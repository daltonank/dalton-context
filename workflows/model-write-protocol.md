# Model Write Protocol

Three write modes. Default posture: **READ freely, PROPOSE conservatively, WRITE intentionally.**

## READ

No modification. Default for normal tasks — the vast majority of interactions with this repository should be read-only.

## PROPOSE

The model identifies a context change worth making and produces a proposed patch, summary, or PR rather than committing directly. Use PROPOSE when:

- the change appears durable but Dalton did not explicitly request a canonical modification,
- the change is interpretive (the model is inferring something rather than recording something Dalton stated),
- the change affects major plans (graduate study, career direction, project architecture),
- the change contains sensitive information, or
- multiple existing entries may need reconciliation (e.g. a change in one project file implies a decision-register update).

Use `templates/context-update-template.md` to draft a PROPOSE-mode change before Dalton approves it.

## WRITE

Canonical modification, committed directly. Permitted only when:

- Dalton explicitly requests a context sync (`Context sync.` — see `workflows/context-sync.md`),
- Dalton explicitly requests repository maintenance, or
- a dedicated, approved context-maintenance task is running.

### Mechanics for a WRITE

1. Inspect the existing relevant file first.
2. Modify only the sections that actually need to change.
3. Preserve unrelated context in that file.
4. Update `Last updated` / `Last verified` dates on anything touched.
5. Update the context state if it changed (e.g. `TENTATIVE` → `ACTIVE`).
6. Update `CHANGELOG.md` when the change is consequential.
7. Update `decisions/decisions.md` if a durable decision was made, changed, or reversed.
8. Avoid duplicate entries — search related files first.
9. Review the resulting diff (`git diff`) before finishing.

For large or multi-file WRITE-mode changes, use a branch and PR rather than committing straight to `main` — see `README.md`.
