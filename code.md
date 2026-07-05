# Code — everyone

Language-agnostic rules for any code, human- or AI-written. Per-language style lives elsewhere; these hold everywhere.

## Naming
- **At least 3 characters, a meaningful word or well-known abbreviation** — `str` not `s`, `count` not `c`, `iter` not `i` for loop counters. No one- or two-letter names; `_` only for a deliberately unused binding.
- **Name for intent** — the role is clear from the name alone (`userCount`, not `n` or `tmp`).
- **One word per concept** — don't alias `user`/`account`/`member` for the same thing.

## Clarity
- **Readable over clever** — obvious beats terse; optimise only with a measured reason.
- **One job per function** — split when it takes on a second.
- **Cap file length** — ~150 lines recommended, 200 max when truly needed; past that, split by responsibility.
- **Name constants** — `MAX_RETRIES = 3`, never a bare literal.
- **Prefer clear code to comments** — a good name or structure beats a comment; comment only the non-obvious *why*. Docs and comments: the bare minimum that's still sufficient, never restating the code.
- **No dead code** — delete the unused and the commented-out; git remembers it.
- **No ASCII trees or art in docs** — no ASCII-drawn directory trees, diagrams, or banners in READMEs and docs; describe the structure in prose or a list.
- **Match surrounding style** — consistency within a file beats personal taste.

## Correctness
- **Handle errors explicitly** — never silently swallow; fail loud or handle it.
- **No surprise side effects** — name and signature should predict what a function touches.
