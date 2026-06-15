# Variant: strict / NDA

Closed, regulated, or NDA work. **Layers on `team`.** Tightest defaults; assume everything is audited. Commit & history hygiene → `tech/git.md`.

## Data egress — the NDA boundary
Internal content (source, docs, mail, tickets, customer data) must not reach a third-party AI provider unless the user consciously allows it. Before any tool call reading an internal service (wiki, mail, tracker, repo) via MCP/API, the agent emits:

> **NDA EGRESS WARNING** — Content from `<service>` will be transmitted to the AI provider. Confirm the NDA permits this before continuing.

- First access per service per session, **every** access to strict-tagged data (no suppression), and before any bulk pull.
- Wait for explicit confirmation. Don't soften it or suggest a bypass. Absence of a warning is not permission.
