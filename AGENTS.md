# Global Working Agreements

- Treat the repository as shared operating memory for humans and AI agents.
- Prefer durable repo docs over chat memory for anything that should matter later.
- Distinguish scratch working memory, durable project memory, canonical historical record, and derived views.
- Do not rewrite canonical history to simplify the story; corrections should be additive and traceable.
- At startup, read the repo `README.md`, then the repo agent README, then the repo current-focus doc.
- When terminology, architecture, workflow, or protocol changes in a way that should matter later, record it durably in the repo.
- If an expected local tool is missing, say so explicitly instead of silently substituting a weaker workaround.
- Prefer visible repo-governed instruction surfaces over hidden one-off prompt memory.

--- project-doc ---

# Repository Instructions

This repository is the canonical-history and derived-working-data home for `NEXUS-EventStore`.

Read in this order before substantial work:

1. [`README.md`](README.md)
2. [`docs/agent-readme.md`](docs/agent-readme.md)
3. [`docs/current-focus.md`](docs/current-focus.md)
4. the relevant docs, manifests, events, projections, and working batches

Working rules:

- do not rely on chat memory alone for project understanding
- when a task depends on an external package or tool library, check the package's official docs entry point, onboarding docs, and examples before inferring behavior from local outputs or implementation details
- keep canonical history, durable docs, and derived working data distinct
- treat committed event-store files as durable historical record unless a documented policy says otherwise
- keep derived local SQLite indexes untracked
- when operational expectations change, update the durable docs and runbooks
- never guess the current store shape when it can be inspected directly
- prefer `main` as the steady-state branch unless a temporary side branch truly needs an independent cadence
- inherit the NEXUS-wide package-guidance rule by default and add or update a local note under [`docs/reference/packages/README.md`](docs/reference/packages/README.md) only when this repo has stronger package-specific operational behavior

Primary references:

- [`docs/agent-readme.md`](docs/agent-readme.md)
- [`docs/current-focus.md`](docs/current-focus.md)
- [`docs/reference/packages/README.md`](docs/reference/packages/README.md)
- [`docs/v0-layout-and-toml.md`](docs/v0-layout-and-toml.md)
