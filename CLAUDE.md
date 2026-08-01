# CLAUDE.md

Project-wide instructions for Claude Code working in this repository.

Present Studio is a **Creative Intelligence Operating System** — a framework for
building premium brands. This repository is the source code of the system, not a
client workspace.

---

## The one hard constraint

```
foundation  →  contracts  →  engines  →  adapters  ←  brandpacks
```

**Dependencies point one way. Core never depends on a brand pack.**

- Work inside `brandpacks/<brand>/` may read the entire core.
- Work inside `brandpacks/<brand>/` must **never** write to `foundation/`,
  `contracts/`, `engines/`, `adapters/`, `campaigns/` or `production-blueprints/`.
- If brand work reveals a needed core change, stop and raise it. Never inline a
  brand-specific exception into a core file.

Violating this silently converts the framework back into an agency folder
structure. It is the failure mode this repository was rebuilt to prevent.

---

## Where things go

| Root (brand-agnostic) | Brand pack (instance) |
|---|---|
| Campaign archetypes | Campaign instances |
| Production blueprints | Rendered production output |
| Engine definitions | Engine configuration (`pack.yaml`) |
| Contracts | Contract instances |

**If it names a brand, it does not belong at root.**

Brand output is written only under `brandpacks/<brand>/`.

---

## Working order

Never start from a blank context. Load in this order:

1. `foundation/` — the invariants
2. `contracts/` — the schema for what you are about to produce
3. The relevant `engines/` definition
4. Only then, the brand pack

Producing an artifact without first reading its contract is invalid work.

---

## Conventions

- **Markdown for system content**, YAML for manifests. No other formats without
  reason.
- **One engine per file. One adapter per file. One contract per artifact.**
- **Lowercase kebab-case** for all file and folder names.
- **Contracts before content.** Define the schema before authoring anything that
  must conform to it.
- **The schema is the template.** Never create a template file that duplicates a
  contract — two sources of truth drift.
- Every artifact declares which engine produced it.
- Every system folder has a `README.md` stating its role, dependencies, and what
  does not belong in it. Keep it accurate when the folder's role changes.

---

## Workflow rules

- **Do not invent system components.** If an engine, contract or adapter needed
  for a task does not exist, report the gap. Do not fabricate one to finish.
- **An empty folder is scaffold, not a feature.** Check `PROJECT_STATUS.md`
  before treating any layer as available.
- **Archive, don't delete.** Superseded material moves to `archive/`, preserving
  its original path (`archive/engines/positioning-v1.md`).
- **Update `PROJECT_STATUS.md`** whenever a layer gains or loses capability. It
  is the working state of the build.
- **Ask before generating brand documents.** Content generation is a separate
  decision from system construction.

---

## Scope discipline

Current phase is **MVP v1.0**. Optimize for a two-day build, not enterprise
completeness.

Build one thin vertical slice end to end — foundation → contracts → one engine →
one adapter → one brand run — rather than partially filling all four core layers.

Deferred past v1.0 and **not to be built** without an explicit decision:
`pipelines/`, `evals/`, `.claude/`, additional brand packs, an agent-persona
folder.

---

## Documentation map

| File | Audience |
|---|---|
| `README.md` | Humans — what the system is and how it is arranged |
| `CLAUDE.md` | Claude Code — conventions and workflow rules (this file) |
| `AGENTS.md` | Agent definitions and responsibilities |
| `PROJECT_STATUS.md` | Current build state |
