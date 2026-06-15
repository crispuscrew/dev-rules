# Variant: team

Team-developed production service. Strict gates. Git flow → `tech/git.md`.

- **Upgrades are deliberate** — no silent dependency or image bumps; they go through review like any change.
- **Approval-first** for schema/data migrations, new exposed ports/services, topology/infra, destructive ops.
- **Verify beyond unit** — integration checks pass and are shown in review.
