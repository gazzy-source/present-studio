# Handoff

Session continuity. Read this first; it is faster than re-reading the repository.

Updated at the end of every work session.

---

## Last Updated

2026-08-01 · post Creative Director phase · pack `v0.3.0`

*No commit hash recorded here — it necessarily lags by one, since committing this
file changes it. Use `git log -1 -- docs/HANDOFF.md` for the true position.*

---

## Completed

**System core — brand-agnostic, stable, unchanged this session**

- Repository architecture v1.0 · Foundation v1.0 · Contracts v1.0 (7 schemas)
- Engines v1.0 (3) · Archetypes v1.0 (5) · Blueprints v1.0 (2) · Adapters v1.0 (1)

**Present Clothing pack — `status: partial`, v0.3.0**

Creative Director documents received and verified. Not rewritten.

| Document | Layer | Version | Status |
|---|---|---|---|
| `brand-laws.md` | 1 | permanent | active |
| `creative-principles.md` | 2 | permanent | active |
| `brand-bible.md` | 1–4 | tiers 1–3 frozen | active |
| `product-philosophy.md` | 4 | — | active |
| `campaign-system.md` | 3 | 1.1.0 | active |
| `reel-brief-template.md` | 3 | 1.1.0 | active |
| `escalation-ledger.md` | 3 | 1.0.0 | active, empty |
| `brand-voice.md` | 3 | 0.2.0 | active, conformant |
| `visual-identity.md` | 3 | 0.2.0 | active, conformant |
| `campaign-memory.md` | — | 0.2.0 | active, conformant, empty |
| `collection-dna.md` | — | 0.1.0 | **non-conformant** |
| `audience.md` | 4 | 0.1.0 | proposed, predates CD phase |

---

## Current Decisions

**Architecture — settled, do not revisit**

- Dependencies point one way; core never depends on a brand pack
- Contracts before content; the schema is the template
- Campaign and production *instances* live in brand packs
- `campaign-system.md` holds brand-specific sets and quotas only; root
  `campaign-engine` logic is not duplicated

**Brand — Creative Director output, now authoritative**

- **Tier 1 Belief:** the future is built in the present *(permanent, never copy)*
- **Tier 2 Territory:** **The Middle** — not the decision, not the arrival, the interval
- **Tier 3 Tension:** the work that builds you is rarely visible while it is happening
- **Tier 3 Promise:** you stop needing to explain yourself
- **Tier 4:** every product carries physical evidence it was made to be used
  repeatedly. Weight is a route, not the principle
- **The One Test:** does this want something from the viewer? If yes, it fails
- **Laws L1–L5** permanent, never bent · **Principles P1–P5** derive from them
- **Constants C1–C8** hold in every campaign · **Constraints K1–K9** are hard gates
- **Discovery:** exactly one new reusable element per campaign (D1–D6)
- **Category:** premium streetwear, gym and street — `unverified`
- **Tagline:** unfrozen. Three candidates held, none deployed

**Derivation chain — enforced**

```
brand-laws → creative-principles → visual-identity / brand-voice → campaigns
```

An orphan rule is deleted, not grandfathered.

---

## Next Creative Decision Needed

**Collection DNA — verified product facts.** Unchanged and now the sole blocker.

Four pieces (Coat, Overshirt, Trouser, Knit) at `status: concept`, all facts
`[unverified]`, no maker's detail on any piece. The file also predates the
Creative Director phase and still frames weight as the thesis, which
`product-philosophy.md` has since superseded.

Required per piece: materials with fibre percentages, weight, construction,
sizing, price with currency, and the maker's detail. Plus mill and factory
names, or an explicit decision to make no origin claims.

**Second decision — base city.** `campaign-system.md` §7.5 records all location
IDs as provisional until fixed. This blocks K3 collision checking and D6 city
rationing from operating on real values.

**Third — import the ten briefs.** `campaign-memory.md` records R-001 to R-010
as existing and pending Critic evaluation. No brief files are in the repository.
Either commit them to `brandpacks/present-clothing/campaigns/` or correct the
memory note.

---

## Known open issues

Recorded by the Creative Director in `campaign-system.md` §7. Not resolved here.

1. K6 / Mechanism 1 contradiction — briefs proceeded on 4 practice classes
2. Location class breadth may be too narrow in year 1
3. `Restless` temperature and `Oscillating` proximity may duplicate
4. Engine placement — extend `campaign-engine` or add one (Architect decision)
5. Geography unset

---

## Update rule

Rewrite this file at the end of every session. Keep it short — it is a handoff,
not a log. Supersede rather than append; history lives in git.
