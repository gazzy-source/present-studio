# Contract: collection-dna

```yaml
id: collection-dna
version: 1.0.0
status: stable
```

## Purpose

The single source of truth for what exists and what may be said about it.

**Every claim in every artifact traces here.** If a fact is not in Collection
DNA, no engine may assert it. This contract is what makes quality-bar gate **G1**
enforceable, and what keeps the system from fabricating material, provenance or
process — which in apparel is a factual and legal failure, not a stylistic one.

---

## Required fields

### Collection level

| Field | Type | Rule |
|---|---|---|
| `collection` | string | Name of the collection or drop |
| `season` | string | e.g. `AW26`. Used in campaign instance naming |
| `thesis` | 1–2 sentences | Why this collection exists. Not a description of what is in it |
| `tension` | 1 sentence | The productive contradiction the collection holds |
| `palette` | list | Colours with names as the brand refers to them |
| `provenance` | spec | Where made, by whom, under what conditions — only if verified |
| `drop_structure` | spec | How and when it releases |

### Piece level — repeated per piece

| Field | Type | Rule |
|---|---|---|
| `name` | string | As sold |
| `category` | string | Garment type |
| `materials` | list | Fibre content with percentages, as verified |
| `weight` | measure | Fabric weight (gsm/oz) where applicable |
| `construction` | list | Named techniques, seams, finishing |
| `colourways` | list | Must be drawn from collection `palette` |
| `sizing` | spec | Range and fit intent |
| `price` | number | Currency explicit |
| `detail` | 1+ items | A fact only the maker would know. Required |
| `status` | enum | `concept` · `sampling` · `production` · `available` · `archived` |

---

## The `detail` field

Every piece carries at least one **maker's detail** — the decision someone
agonised over. The bar tacked to reduce roll. The button spacing changed twice.
The dye lot that shifts across the batch.

This field is the craft evidence in `premium.md`. Without it, product writing
falls back on adjectives, which fail gate S1. It is the highest-leverage input
in the entire pack and the one most often left thin.

---

## Verification levels

Every fact carries a verification level. Engines treat these differently.

| Level | Meaning | Engine behaviour |
|---|---|---|
| `verified` | Confirmed by founder or supplier documentation | May state plainly |
| `provisional` | Believed true, unconfirmed | May state, must not emphasise |
| `unverified` | Assumed | **May not be asserted.** Report the gap |

Unverified facts are permitted in the DNA as placeholders. They are never
permitted in output.

---

## Validation rules

1. **Closure** — nothing asserted anywhere in the pack lacks an entry here.
2. **No marketing language** — DNA records fact. Adjectival or persuasive
   phrasing belongs in generated output, never in the source of truth.
3. **Palette closure** — every colourway resolves to a named collection colour.
4. **Detail presence** — every piece has ≥1 maker's detail.
5. **Verification completeness** — every material, provenance and process claim
   carries a level.
6. **Status honesty** — `available` means purchasable now. Concept pieces are
   never marked available.
7. **Price currency** — always explicit. Never a bare number.

---

## Conformance checklist

- [ ] All seven collection-level fields present
- [ ] `thesis` states why, not what
- [ ] `tension` nameable in one sentence
- [ ] Every piece has all eleven piece-level fields
- [ ] Every piece has ≥1 maker's detail
- [ ] Every colourway maps to the collection palette
- [ ] Every material/provenance/process fact carries a verification level
- [ ] No `unverified` fact is relied on by any existing artifact
- [ ] No marketing language anywhere in the document

---

## Failure modes

| Symptom | Cause | Resolution |
|---|---|---|
| Output describes fabric in generic adjectives | `detail` and `materials` too thin | Enrich DNA. Do not fix in copy |
| Two pieces read identically | Insufficient per-piece differentiation | Add distinguishing detail |
| Engine reports a gap mid-campaign | A needed fact is `unverified` | Founder verifies. Never promote a level to satisfy an engine |
