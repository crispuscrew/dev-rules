# Containers — everyone

- **Run code in a container, not on the host** — anything you build, run, or test. Reproducible and disposable.
- **Rootless Podman** over Docker; Docker only when explicitly required.
- **Small, pinned images** — Alpine or distroless, exact tag or digest, never `:latest`.
- **Least privilege** — non-root user, dropped capabilities, read-only rootfs where possible; no `--privileged`, no host network unless required.
