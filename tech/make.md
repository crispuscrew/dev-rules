# Make — everyone

The Makefile is the project's front door: one command name per task, run the same way by humans and AI, wrapping the container so nobody memorises raw `podman`/`docker` flags. Recipes follow `tech/containers.md` — they run *in* the container.

- **`make help` is the default target and self-documenting** — it parses target docs out of the Makefile, never a hardcoded list, so help can't drift from what exists. Document a target with a trailing `## …` and it appears automatically:
  ```make
  .DEFAULT_GOAL := help
  help:  ## Show available targets
  	@grep -E '^[a-zA-Z_-]+:.*?## ' $(MAKEFILE_LIST) \
  	  | awk 'BEGIN{FS=":.*?## "}{printf "  %-14s %s\n", $$1, $$2}'
  ```
- **Detect the engine once** — prefer Podman, fall back to Docker; every recipe uses the variable, not a literal:
  ```make
  ENGINE := $(shell command -v podman 2>/dev/null || command -v docker 2>/dev/null)
  ```
- **Standard targets, all in the container:** `build`, `run`, `test`, `lint`. `make run` is a build → run sequence — it always builds first, so a fresh checkout runs with one command.
- **No host-only escape hatch** — if a target needs the toolchain, it runs inside the container, not on the host.
