# Present Studio

**A Creative Intelligence Operating System for building premium brands.**

This repository is the source code of the operating system itself — not a client
workspace, not a folder of brand documents. It is a framework: reusable system
components at the core, brand implementations isolated at the edge.

---

## Architecture

```
foundation  →  contracts  →  engines  →  adapters
                                             ↑
                                        brandpacks
```

**Dependencies point one way.** Nothing in the core knows a brand pack exists.

Delete every brand pack and the system still stands. Add a brand pack and no
core file changes. Isolation is an enforced property of the architecture, not a
naming convention.

---

## Repository map

### Core system

| Folder | Role |
|---|---|
| `foundation/` | Invariants. What "premium" means operationally, the quality bar, shared taxonomy. Everything reads it; it reads nothing. |
| `contracts/` | The type system. One schema per artifact. Engines declare their input and output contracts. Makes output verifiable instead of vibes-checked. |
| `engines/` | The logic. Each engine consumes contract-conformant input, applies a defined process, emits contract-conformant output. |
| `adapters/` | The I/O boundary. Renders artifacts into a target channel. Keeps channel formatting out of brand reasoning. |

### System-level libraries

| Folder | Role |
|---|---|
| `campaigns/` | Campaign **archetypes** — brand-agnostic, reusable. Instances live in brand packs. |
| `production-blueprints/` | Reusable output specifications. Rendered output lives in brand packs. |

### Implementations

| Folder | Role |
|---|---|
| `brandpacks/` | Brand implementations. Configuration and instance data, never core logic. |

### Support

| Folder | Role |
|---|---|
| `docs/` | Human-facing documentation. |
| `archive/` | Superseded material, kept out of the live tree. |

---

## Anatomy of a brand pack

```
brandpacks/<brand>/
├── pack.yaml       manifest: identity, version, engines enabled, adapter config
├── brand/          resolved brand artifacts (contract instances)
├── campaigns/      instances of root campaign archetypes
├── production/     output rendered from production blueprints
└── assets/         binaries owned by this brand
```

A pack is configuration plus instance data. There is no pack template — the
schema *is* the template. `contracts/` defines what a valid pack is; two sources
of truth would drift.

---

## Extending the system

| Adding | Costs |
|---|---|
| A new process | one file in `engines/` |
| A new channel | one file in `adapters/` |
| A new brand | one directory in `brandpacks/` |
| A new artifact type | one schema in `contracts/` |

No restructuring required in any case.

---

## Onboarding path

| File | Audience | Contents |
|---|---|---|
| `README.md` | Humans | What the system is and how it is arranged — start here |
| `CLAUDE.md` | Claude Code | Conventions, constraints and workflow rules |
| `AGENTS.md` | Both | Agent definitions, scopes and responsibilities |
| `PROJECT_STATUS.md` | Both | Current build state, deferrals and next steps |

---

## Status

MVP v1.0 — structural scaffold. Architecture is complete; no system content has
been authored. See [PROJECT_STATUS.md](PROJECT_STATUS.md) for what is built, what
is deferred, and what comes next.
