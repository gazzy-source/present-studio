# Handoff

Session continuity. Read this first; it is faster than re-reading the repository.

Updated at the end of every work session.

---

## Last Updated

2026-08-02 · `HEAD` at commit `39c9648`

---

## Completed

**System core — brand-agnostic, stable**

- Repository architecture v1.0 — 9 folders, one-way dependency rule
- Foundation v1.0 — principles, premium, quality-bar, taxonomy
- Contracts v1.0 — 7 schemas
- Engines v1.0 — narrative, cinematic-language, campaign
- Archetypes v1.0 — collection-launch, single-piece, manifesto, process, world-building
- Blueprints v1.0 — short-form-reel, still-series
- Adapters v1.0 — social-vertical

**Present Clothing pack — `status: partial`**

- Brand Bible v0.1 — *proposed*
- Brand Voice v0.1 — *proposed*, contract-conformant
- Audience v0.1 — *proposed*
- Product Philosophy v0.1 — *proposed*
- Visual Identity v0.1 — *proposed*, contract-conformant
- Campaign Memory v0.1 — conformant, empty, ready to log
- Collection DNA v0.1 — structurally complete, **non-conformant, zero verified facts**

---

## Current Decisions

**Architecture — settled, do not revisit**

- Dependencies point one way; core never depends on a brand pack
- Contracts before content; the schema is the template
- Campaign and production *instances* live in brand packs; only archetypes and
  blueprints live at root
- Agents defined in `AGENTS.md` by scope, not as an `agents/` folder

**Brand — proposed, awaiting founder confirmation**

- **Concept:** *present* = attending · *presence* = physical weight · a coat with
  presence and a person who is present are the same word
- **Thesis:** garments with enough physical presence to keep the wearer in the present
- **Tension:** substance disappears; lightness demands attention
- **Stance:** clothing should return you to the present, not perform for the future
- **Range logic:** small, definitive, revised rather than replaced
- **Voice:** numbers over adjectives; `effortless` / `elevated` / `curated` /
  `timeless` forbidden with reasons
- **Visual:** overcast northern light, 50mm home lens, away-gaze default,
  no slow motion, no golden hour
- **Commercial:** no urgency, no scarcity mechanics, no hashtags

---

## Next Creative Decision Needed

**Collection DNA — verified product facts.**

All four pieces (Coat, Overshirt, Trouser, Knit) are `status: concept` with
`[unverified]` materials, weights, construction and prices, and **no maker's
detail on any piece**.

Required per piece:

- Materials with fibre percentages
- Weight (oz / gsm)
- Construction techniques
- Sizing range and fit intent
- Price with currency
- **The maker's detail** — the decision that was genuinely difficult

Plus: mill and factory names, or an explicit decision to make no origin claims.

**Why this blocks everything:** concept pieces are never campaigned (`campaign`
contract, rule 2) and unverified facts never reach output (gate G1). Any engine
asked to generate a campaign will report the gap and refuse. Phase 5 — the 100
reels — cannot start until this file carries real data.

**Second decision, cheaper now than later:** confirm or replace the brand concept
above. Every downstream artifact inherits from it.

---

## Update rule

Rewrite this file at the end of every session. Keep it short — it is a handoff,
not a log. Supersede rather than append; history lives in git.
