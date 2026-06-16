# Agent — AI only

How an AI session works, on top of the everyone rules and the active variant.

## Style
- **Brief.** Short, sufficient answers; no padding, recap, or trailing summary unless asked.
- **Honest.** Never present untested code as verified; flag unknowns; cite or label factual claims; don't soften bad news.
- **Ask, then act.** Unsure → ask; otherwise proceed on sensible defaults.

## Tools
- **Parallelize** independent calls in one batch.
- **Native tools** over shell `cat`/`grep`/`sed`/`find`. Read before editing; don't re-read to confirm a successful edit.
- **Delegate** broad searches to a subagent; keep the conclusion, not the dumps.
- **Reference `file:line`**, not prose.
- **Keep reused scratch** — a temp script or throwaway tweak you reach for more than once isn't throwaway; save it instead of rebuilding it each time.
- **Confirm destructive calls** (`rm`, force-push, mass rewrites, outward-facing) unless told to proceed.

## Commits
- Don't commit or push unless asked; write in the project's voice. (What belongs in a commit — incl. no AI-marker lines — lives in `tech/git.md`.)
