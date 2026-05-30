# dev-rules

Development rules for humans to read and AI to follow. Short by design: minutes to read, cheap on context. One topic per file — import only what a project uses.

## Files

**Everyone (humans + AI):**
- `principles.md` — values: integrity, security, stability, approval, verify
- `tech/git.md` — branches & commits
- `tech/containers.md` — Podman, images, least privilege

**AI only:**
- `agent.md` — response style, tool use, commit hygiene

**Variants** (pick one):

| Variant | For | Adds |
|---|---|---|
| `solo` | one dev, prod level | lighter flow, fewer confirmations |
| `team` | production service | promotion flow, review gates, approval-first |
| `strict` | NDA / regulated | team + NDA data-egress alerts |

`strict` layers on `team`. Don't mix `solo` with `team`.

## Use in a project

Vendor this repo as `dev-rules/`, then in the project's `CLAUDE.md` import the topics you use + one variant:

```
@dev-rules/principles.md
@dev-rules/tech/git.md
@dev-rules/tech/containers.md
@dev-rules/agent.md
@dev-rules/variants/team.md
```

Humans read the everyone topics + their variant; skip `agent.md`. Drop any topic you don't use (no containers → omit `tech/containers.md`). Claude Code resolves `@`-imports relative to the file; `~/…` and absolute paths work, nested to 5 levels. No import support → concatenate by hand.

Strict project: don't commit `CLAUDE.md` (it's an AI marker) — put the imports in `~/.claude/CLAUDE.md`.

## Editing

- One topic per file; fix a rule once, every importer follows.
- Variants and `agent.md` hold only the delta — never repeat an everyone rule.
- Keep it terse. If a rule needs a paragraph, it's too long.
