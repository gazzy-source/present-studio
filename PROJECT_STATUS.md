# Project Status

**Project:** Present Studio — Creative Intelligence Operating System
**Version:** MVP v1.0
**Updated:** 2026-08-01
**Phase:** MVP Foundation Freeze. Architecture stable. Implementation blocked.

Working backlog lives in [ROADMAP.md](ROADMAP.md). This file is state; ROADMAP is
the task list.

---

## Blocker

One blocker remains, and it is the only thing standing between the system and
its first output.

### No verified Present Clothing product facts exist

The Creative Director phase has landed. Eleven brand documents are in place, with
a four-layer derivation chain enforced from permanent laws down to execution.

`collection-dna.md` is the sole non-conformant artifact. It holds **zero verified
facts**: four pieces at `status: concept`, `[unverified]` materials, weights,
construction and prices, and no maker's detail on any piece. It also predates the
Creative Director phase and still frames weight as the thesis, which
`product-philosophy.md` has since superseded — weight is now one route to
evidence, not the principle.

**This blocks production structurally, not by convention.** Concept pieces are
never campaigned (`campaign` contract, rule 2) and unverified facts never reach
output (gate G1), so any engine asked to generate a campaign reports the gap and
refuses.

**Founder input required:** per piece — materials with fibre percentages, weight,
construction, sizing, price, and the maker's detail. Plus mill and factory names,
or an explicit decision to make no origin claims.

### Secondary blockers

- **Base city unset.** `campaign-system.md` §7.5 records all location IDs as
  provisional. K3 collision checking and D6 city rationing cannot operate on real
  values until fixed.
- **Ten briefs referenced but absent.** `campaign-memory.md` records R-001 to
  R-010 as existing and pending Critic evaluation. No brief files exist under
  `brandpacks/present-clothing/campaigns/`. Recorded in `pack.yaml` as
  `pending_import`.

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

## Layer state

| Folder | State |
|---|---|
| `foundation/` | ✅ 4 documents — principles, premium, quality bar, taxonomy |
| `contracts/` | ✅ 7 schemas |
| `engines/` | ✅ 3 engines |
| `campaigns/` | ✅ 5 archetypes |
| `production-blueprints/` | ✅ 2 blueprints |
| `adapters/` | ✅ 1 adapter (`social-vertical`) |
| `brandpacks/present-clothing/` | 🚧 `partial` v0.3.0 — 12 documents; `collection-dna` non-conformant |
| `docs/` | Empty — no human-facing docs needed yet |
| `archive/` | Empty — nothing superseded |

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
