# AGENTS.md

Agent definitions and responsibilities.

An **engine** is a process. An **agent** is an executor that runs engines within a
declared scope. This file is the registry of those executors.

Repository-wide conventions and workflow rules live in
[CLAUDE.md](CLAUDE.md) — not here.

---

## Agent scopes

Every agent operates in exactly one scope. Scope determines write permissions and
is the mechanism that enforces the system's one-way dependency rule.

### Core-scoped

Builds and maintains the operating system itself.

- **May write:** `foundation/`, `contracts/`, `engines/`, `adapters/`,
  `campaigns/`, `production-blueprints/`
- **May not write:** any brand pack
- **Responsibility:** the components stay brand-agnostic. A core-scoped agent
  that finds itself naming a brand has left its scope.

### Pack-scoped

Produces brand work by running existing system components.

- **May write:** `brandpacks/<brand>/` only
- **May read:** the entire core
- **May not write:** anything at root
- **Responsibility:** conform to contracts. A pack-scoped agent that needs a core
  change raises it rather than making it.

No agent holds both scopes in a single unit of work.

---

## What an agent definition must specify

Each agent in this registry declares:

| Field | Meaning |
|---|---|
| `name` | Identifier, lowercase kebab-case |
| `scope` | `core` or `pack` |
| `responsibility` | The single outcome it owns |
| `reads` | Which folders and contracts it consumes |
| `writes` | Which paths it may produce, bounded by scope |
| `engines` | Which engines it runs |
| `boundaries` | What it must escalate rather than decide |

An agent that cannot state its scope and boundaries is not ready to run.

---

## Roster

**No agents authored yet.**

The agent layer is deferred past MVP v1.0. Until it exists, work is performed
directly against `engines/` under the scope rules above, following
[CLAUDE.md](CLAUDE.md).

Agents are registered here as definitions. Promoting them to an addressable
`agents/` folder is a separate decision, not an assumed next step — see
[PROJECT_STATUS.md](PROJECT_STATUS.md).

| Agent | Scope | Responsibility | Status |
|---|---|---|---|
| — | — | — | none defined |
