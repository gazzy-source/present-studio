# Present Studio MVP

Engineering backlog. Not documentation.

**Milestone:** a working Creative Intelligence System capable of generating
premium campaigns for Present Clothing.

**Legend:** `[x]` done · `[ ]` open · 🚧 in progress · ⛔ blocked
**Owner:** `ENG` = implementable now · `FOUNDER` = needs founder input or decision

---

## Phase 1 — System core ✅

The gate for everything downstream. Authored under founder authorization
2026-08-01.

- [x] Repository architecture — `ENG`
- [x] Root documents (README, CLAUDE, AGENTS, PROJECT_STATUS, ROADMAP) — `ENG`
- [x] **Foundation** — `ENG`
  - [x] `principles` — nine reasoning rules with precedence order
  - [x] `premium` — five signals, nine anti-signals, substitution test
  - [x] `quality-bar` — 5 hard gates, 6 soft gates, scoring, revision rule
  - [x] `taxonomy` — shared vocabulary and naming conventions
- [x] **Contracts** — `ENG`
  - [x] `brand-pack` — what a valid pack is
  - [x] `brand-voice`
  - [x] `collection-dna`
  - [x] `visual-identity`
  - [x] `campaign`
  - [x] `campaign-memory` — added; `brand-pack` requires it as a fourth artifact
  - [x] `production-blueprint`

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

## Phase 3 — Engines ✅

Brand-agnostic. Complete.

- [x] Narrative Engine — tension → spine → turn → beats → copy
- [x] Cinematic Language Engine — beats → light → lens → frame → motion
- [x] Campaign Engine — orchestrator; gates and writes memory

---

## Phase 4 — Output layer ✅

Brand-agnostic. Complete.

- [x] Campaign Archetypes — `ENG`
  - [x] `collection-launch` — 7 beats, late turn
  - [x] `single-piece` — 5 beats, highest volume
  - [x] `manifesto` — 6 beats, used rarely
  - [x] `process` — 5 beats, most claim-dense
  - [x] `world-building` — 4 beats, motif accumulation
- [x] Production Blueprints — `ENG`
  - [x] `short-form-reel` — 9:16, 8–15s, with archetype compression table
  - [x] `still-series` — 3–8 frames
- [x] Adapters — `ENG`
  - [x] `social-vertical` — feed and story, caption rules
- [ ] `campaign-film` blueprint — deferred; not required for the reel milestone

---

## Phase 5 — Generation

The success metric. Everything above is scaffolding for this.

- [ ] First campaign for Present Clothing, end to end
- [ ] Generate 100 launch-ready reels

---

## Critical path

```
Foundation ✅ → Contracts ✅ → Engines ✅ → Blueprints ✅ → Campaign → Reels
                        ↘ Brand Pack ⛔ (needs founder inputs) ↗
```

**The entire brand-agnostic system is built.** Everything that can be
implemented without knowing what Present Clothing is, is done.

One blocker remains, and it is the only one: **Present Clothing brand inputs**.
Phase 2 gates Phase 5 — the machine is complete and has nothing to run on.

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
