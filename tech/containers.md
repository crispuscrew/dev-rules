# Containers — everyone

- **Run code in a container, not on the host** — the whole pipeline runs inside: build, test, lint, run. Nothing touches the host toolchain. Reproducible and disposable.
- **Rootless Podman first**, Docker as automatic fallback when Podman isn't installed — detect the engine (in the Makefile, see `tech/make.md`), don't hardcode one. Same flags where they overlap.
- **Small, pinned images** — Alpine or distroless where applicable, exact tag or digest, never `:latest`.
- **Least privilege** — non-root user, dropped capabilities, read-only rootfs where possible; no `--privileged`, no host network unless required.
- **Minimal mounts** — bind only the paths a step needs, read-only by default; no broad host or `$HOME` binds.
- **DNS gotcha** — rootless Podman can fail name resolution behind a VPN with DNS-leak protection; workaround `--dns=1.1.1.1` (or your trusted resolver). Stopgap, not a fix — revisit when a cleaner option exists.
