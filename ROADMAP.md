# Present Studio MVP

Engineering backlog. Not documentation.

**Milestone:** a working Creative Intelligence System capable of generating
premium campaigns for Present Clothing.

**Legend:** `[x]` done · `[ ]` open · 🚧 in progress · ⛔ blocked
**Owner:** `ENG` = implementable now · `FOUNDER` = needs founder input or decision

---

## Phase 1 — System core 🚧

The gate for everything downstream. Nothing in Phase 2+ can be authored
correctly until contracts exist to constrain it.

- [x] Repository architecture — `ENG`
- [x] Root documents (README, CLAUDE, AGENTS, PROJECT_STATUS, ROADMAP) — `ENG`
- [ ] ⛔ **Foundation** — invariants, definition of premium, quality bar, taxonomy — `FOUNDER`
- [ ] ⛔ **Contracts** — artifact schemas — `FOUNDER`
  - [ ] `brand-pack` — what a valid pack is
  - [ ] `brand-voice`
  - [ ] `collection-dna`
  - [ ] `visual-identity`
  - [ ] `campaign`
  - [ ] `production-blueprint`

**Blocker:** `foundation/` and `contracts/` are empty directories. Authoring them
is prohibited to the Lead Engineer role without founder authorization. See
PROJECT_STATUS.md → Blockers.

---

## Phase 2 — Present Clothing Brand Pack ⛔

Blocked by Phase 1 (no contracts to conform to) **and** by missing brand inputs.

- [ ] Brand Pack manifest — promote `pack.yaml` from scaffold to conformant — `ENG`
- [ ] Brand Voice — `FOUNDER` input required
- [ ] Collection DNA — `FOUNDER` input required
- [ ] Visual Identity — `FOUNDER` input required
- [ ] Campaign Memory — `ENG` once the above land

**Blocker:** no information about Present Clothing exists in this repository.
Category, positioning, price tier, audience, aesthetic and collection detail are
all unknown. These cannot be invented — they are the founder's raw material.

---

## Phase 3 — Engines

Brand-agnostic. Buildable once contracts exist; does **not** need brand inputs.

- [ ] Narrative Engine — `ENG`
- [ ] Cinematic Language Engine — `ENG`
- [ ] Campaign Engine — `ENG`

Each declares an input contract and an output contract. One engine per file.

---

## Phase 4 — Output layer

- [ ] Production Blueprints — reusable output specifications — `ENG`
- [ ] Campaign Archetypes — brand-agnostic campaign shapes — `ENG`
- [ ] Adapters — at least one, to render artifacts to a channel — `ENG`

---

## Phase 5 — Generation

The success metric. Everything above is scaffolding for this.

- [ ] First campaign for Present Clothing, end to end
- [ ] Generate 100 launch-ready reels

---

## Critical path

```
Foundation → Contracts → Engines → Blueprints → Campaign → Reels
                  ↘ Brand Pack (also needs founder inputs) ↗
```

Two independent blockers sit at the front: **authorization** to author the system
core, and **brand inputs** for Present Clothing. Engines (Phase 3) unblock with
the first alone.

---

## TODO / ADR candidates

Recorded, not acted on. Do not interrupt implementation for these.

- **ADR:** promote agents to an addressable `agents/` folder, or keep them as
  definitions in `AGENTS.md`? Deferred at MVP.
- **ADR:** `pipelines/` for engine composition once more than two engines chain.
- **ADR:** `evals/` for automated contract-conformance testing.
- **TODO:** move `presentclothing/present-studio` to be the canonical remote if
  that org becomes the project home. Currently `origin` is `gazzy-source`.
- **TODO:** `LICENSE` was removed in the architecture rebuild. Decide whether the
  project ships with one.
- **TODO:** second brand pack, to prove the isolation boundary genuinely holds.
