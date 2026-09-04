# Security & Privacy

This repository must remain **private**. It is a personal cross-model context store for Dalton Ankenbrand, not a public artifact.

## Never Store

Regardless of how the request is framed, never commit any of the following to this repository:

- Passwords, authentication secrets, API keys, tokens, cookies, private keys
- Social Security numbers or other government ID numbers
- Bank account or payment card numbers
- Full medical documents or records
- Confidential third-party records (anything about another person they haven't consented to being recorded here)
- Unnecessary intimate or highly sensitive personal detail that has no plausible future usefulness

## Labels Are Not Access Control

Markdown labels such as `PRIVATE` or `SENSITIVE` (as used on `context/personal.md`) are **model-handling instructions** — a signal to any AI reading this repository to be conservative about surfacing that content. They are not real access controls. The actual security boundary is that this is a private repository with a limited set of collaborators. Do not rely on an in-file label to do the work an access control would do.

## Guiding Principle

> Store the least-sensitive representation that preserves future usefulness.

Concretely: don't store an entire emotional conversation. Prefer a durable abstraction that captures what a future AI interaction would actually need, e.g. "Dalton is actively developing strategies for emotional regulation under uncertainty" rather than the conversation that produced that observation.

Only include personal information here when it is expected to materially improve future work. If it wouldn't change what an AI recommends or how it responds, it doesn't belong here.

## If Something Sensitive Is Already Present

If a review (see the quarterly audit in `README.md`) finds something that violates the rules above, remove it — don't archive it. `archive/` is for information that is no longer current but still safe and useful to keep; it is not a place to relocate things that should never have been stored.
