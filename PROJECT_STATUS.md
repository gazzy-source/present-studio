# Project Status

**Project:** Present Studio — Creative Intelligence Operating System
**Version:** MVP v1.0
**Updated:** 2026-08-01
**Phase:** MVP Foundation Freeze. Architecture stable. Implementation blocked.

Working backlog lives in [ROADMAP.md](ROADMAP.md). This file is state; ROADMAP is
the task list.

---

## Blockers

Two blockers sit at the front of the critical path. Both need the founder.

### 1. `foundation/` and `contracts/` are empty

The Foundation Freeze brief treats these as complete. They are not — both are
empty directories holding only a boundary README. Nothing has been authored.

This matters because `CLAUDE.md` requires contracts before content, and forbids
inventing document classes. Brand Voice, Collection DNA and Visual Identity have
no schemas to conform to, so authoring them now would mean inventing their shape.

The Lead Engineer role explicitly may not modify Foundation or Contracts.
**Authorization required** to author them. They are brand-agnostic and need no
Present Clothing input — one approval unblocks Phase 1 and Phase 3.

### 2. No Present Clothing brand inputs exist

The repository contains no information about Present Clothing: category,
positioning, price tier, audience, aesthetic, collection detail. A premium
brand's voice and DNA cannot be fabricated from an empty context.

**Founder input required.** This blocks Phase 2 regardless of blocker 1.

---

## Current state

The repository has been rebuilt from scratch as a framework. The previous
structure — thirteen flat folders organized around agency workflow — has been
removed.

What exists today is **architecture, not capability**. Every folder is present
and its boundary is documented. No engines, contracts, adapters, or brand
documents have been authored yet.

Structure verified 2026-08-01 against the approved design: 14 directories and 15
files, no unexpected entries. Committed as the repository's architecture baseline.

---

## Built

| Item | State |
|---|---|
| Framework architecture | Defined and enforced by the dependency rule |
| Directory structure | Complete |
| `README.md` | System overview and repository map — for humans |
| `CLAUDE.md` | Conventions, workflow rules, Founder Preference — for Claude Code |
| `AGENTS.md` | Agent scopes, definition schema and roster (roster empty) |
| `ROADMAP.md` | Engineering backlog and critical path |
| `PROJECT_STATUS.md` | This file |
| Folder boundary READMEs | One per system folder |
| `brandpacks/present-clothing/` | Scaffold + empty manifest. No brand content. |

---

## Empty by design

| Folder | Awaiting |
|---|---|
| `foundation/` | Principles, quality bar, taxonomy |
| `contracts/` | Artifact schemas, starting with `brand-pack` |
| `engines/` | First engine |
| `adapters/` | First adapter |
| `campaigns/` | Campaign archetypes |
| `production-blueprints/` | Output specifications |
| `docs/` | Human-facing documentation |
| `archive/` | Nothing superseded yet |

---

## Explicitly deferred past MVP v1.0

- `pipelines/` — engine composition and orchestration
- `evals/` — automated contract-conformance testing
- `.claude/` — agent automation and repo-level tooling
- Additional brand packs beyond Present Clothing
- An addressable `agents/` folder. Agent scopes and the definition schema are
  specified in `AGENTS.md`; the roster is empty. Promoting agents to first-class
  components is a separate decision, not an assumed next step.

All attach at root without disturbing existing structure.

---

## Next steps

Build one thin vertical slice end to end rather than partially filling all four
core layers.

1. **`foundation/`** — author the invariants. Everything downstream reads them,
   so nothing else can be correct until these are fixed.
2. **`contracts/`** — define `brand-pack`, then the two or three schemas the
   first engine actually needs.
3. **`engines/`** — one complete engine, with declared input and output contracts.
4. **`adapters/`** — one complete adapter consuming that engine's output.
5. **`brandpacks/present-clothing/`** — first real run through the slice. This is
   the point at which brand documents get generated, and the point at which the
   isolation boundary is genuinely tested.

---

## Open decisions

- Which engine is the first slice.
- Whether campaign archetypes are authored before or after the first brand run.

---

## Architectural constraints in force

- Dependencies point one way. Core never depends on a brand pack.
- Root is brand-agnostic. Brand-specific work lives only in `brandpacks/`.
- Campaign and production **instances** belong to brand packs; only reusable
  archetypes and blueprints live at root.
- The schema is the template. No parallel template files alongside contracts.
