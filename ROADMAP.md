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

## Phase 2 — Present Clothing Brand Pack 🚧

Creative Director phase complete. Twelve documents, four-layer derivation chain.
Pack `v0.3.0`, `status: partial`.

**Layer 1 — permanent**
- [x] `brand-laws.md` — The One Test, L1–L5, no exception path

**Layer 2 — long-lived**
- [x] `creative-principles.md` — P1–P5, each citing its parent law

**Tier structure**
- [x] `brand-bible.md` — Belief, Territory (The Middle), Tension, Promise; tiers 1–3 frozen
- [x] `product-philosophy.md` — evidence of repeated use; weight is a route, not the principle

**Layer 3 — versions freely**
- [x] `campaign-system.md` v1.1.0 — C1–C8, 14 dimensions, K1–K9, discovery D1–D6
- [x] `reel-brief-template.md` v1.1.0 — 23 fields, pre-production checks
- [x] `escalation-ledger.md` v1.0.0 — empty; era changes, one rule per era
- [x] `brand-voice.md` v0.2.0 — conformant; 3 registers, 27 owned words, 11 prohibitions
- [x] `visual-identity.md` v0.2.0 — conformant; 6 motifs, sound, 24fps

**Contract artifacts**
- [x] `campaign-memory.md` v0.2.0 — conformant; discovery ledger, cooldowns, drift
- [x] `pack.yaml` v0.3.0 — all 12 documents referenced, blockers declared
- [ ] ⛔ `collection-dna.md` v0.1.0 — **non-conformant, zero verified facts**
- [ ] `audience.md` v0.1.0 — predates CD phase, still `proposed`

**Blocker:** four pieces at `status: concept`, all facts `[unverified]`, no
maker's detail. Concept pieces are never campaigned and unverified facts never
reach output (G1), so production is blocked at engine level.

**Secondary:** base city unset (`campaign-system.md` §7.5); briefs R-001 to R-010
recorded in memory but absent from the repository.

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
                        ↘ Brand Pack 🚧 (11 of 12 done) ↗
```

**System and brand direction are both built.** The Creative Director phase closed
the strategy gap: laws, principles, voice, visual language, campaign system and
brief template are all authoritative.

**One blocker remains: verified product facts in `collection-dna.md`.** Nothing
else gates production.

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
- **ADR:** engine placement for campaign sampling and memory-query logic — extend
  root `campaign-engine` or add a new engine. Raised in `campaign-system.md` §7.4;
  standing recommendation is extend, add nothing. Architect decision.
- **ADR:** K6 / Mechanism 1 contradiction — `campaign-system.md` §7.1. Briefs
  proceeded on 4 practice classes; formal resolution outstanding.
- **TODO:** import briefs R-001 to R-010 into `brandpacks/present-clothing/campaigns/`,
  or correct the note in `campaign-memory.md` that records them as existing.
- **TODO:** `audience.md` predates the Creative Director phase and still carries
  the superseded weight-as-thesis framing. Supersede or retire; archive if retired.
- **TODO:** `execution-rules.md` is deliberately absent (`creative-principles.md`
  Layer 3 note). Create only if multiple photographers or agencies appear.
