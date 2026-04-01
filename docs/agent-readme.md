# Agent Readme

This repo is the active canonical-history/data home for `NEXUS-EventStore`.

Use it for:

- canonical event files
- import manifests
- normalized import snapshots
- projections
- graph assertions
- graph working batches and catalogs
- commit-checkpoint manifests

Do not use it for:

- hidden one-off chat memory
- derived local SQLite indexes that can be rebuilt
- broad NEXUS doctrine that belongs in `NEXUS-EMERGING`

Working guidance:

- inspect the actual store shape before proposing or changing anything
- preserve append-only historical meaning whenever possible
- when a correction is needed, prefer additive and traceable follow-up over silent rewrite
- document any new operational rule that later agents would otherwise have to rediscover
- keep local machine-only paths and secrets out of commits
- when a task depends on an external package or tool library, check the package's official docs entry point, onboarding docs, and examples before inferring behavior from local outputs or implementation details
- inherit the broader NEXUS package-guidance rule first, and add a local note under [`reference/packages/README.md`](reference/packages/README.md) only when this repo has stronger package-specific operational behavior

If work spans both repos:

- treat `NEXUS-EMERGING` as the doctrine/code/tooling repo
- treat `NEXUS-EventStore` as the data/history repo
- make cross-repo assumptions explicit in docs and examples

Related:

- [`reference/packages/README.md`](reference/packages/README.md)
