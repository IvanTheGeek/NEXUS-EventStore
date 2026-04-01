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

If work spans both repos:

- treat `NEXUS-EMERGING` as the doctrine/code/tooling repo
- treat `NEXUS-EventStore` as the data/history repo
- make cross-repo assumptions explicit in docs and examples
