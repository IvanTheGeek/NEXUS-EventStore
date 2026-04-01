# NEXUS-EventStore

`NEXUS-EventStore` is the canonical append-only history and derived working-data repo for NEXUS.

It holds:

- canonical event files
- import manifests
- normalized import snapshots
- projections
- graph assertions
- graph working batches and catalogs
- commit-checkpoint manifests

Git is the durable history mechanism for this layer.

## Bootstrap Origin

This repo was bootstrapped as a curated extraction from `NEXUS-EMERGING` rather than a history rewrite.

- source repo: `NEXUS-EMERGING`
- source commit: `0d547e6fc2893a4c99a25370fed5c47e742c46b6`
- extraction date: `2026-04-01`
- provenance file: [`bootstrap-source.toml`](bootstrap-source.toml)

## Layout

The first storage shape is stream-oriented:

- `events/conversations/<conversation-id>/`
- `events/artifacts/<artifact-id>/`
- `events/imports/<import-id>/`
- `imports/`
- `snapshots/`
- `projections/`
- `graph/`
- `work-batches/`

See [`docs/v0-layout-and-toml.md`](docs/v0-layout-and-toml.md) for the current layout and TOML schema draft.

## Derived Local Indexes

The working SQLite index under `graph/working/index/` is treated as derived local state.

- it may exist on a machine for faster reporting/query flows
- it is rebuildable
- it should not be committed to Git

The root `.gitignore` already keeps those SQLite files local.

## External Package Guidance

This repo inherits the broader NEXUS rule:

- check official package docs and examples first
- then use local package-reference notes for repo-specific operational workflows and gotchas
- add or update a local note under [`docs/reference/packages/README.md`](docs/reference/packages/README.md) only when this repo develops stronger local package behavior
