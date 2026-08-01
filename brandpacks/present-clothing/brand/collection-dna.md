# Present Clothing — Collection DNA

```yaml
contract: collection-dna
version: 0.1.0
status: proposed
```

> **⛔ NO VERIFIED FACTS EXIST IN THIS DOCUMENT.**
>
> No product, material, supplier or pricing information was supplied. Every
> piece below is a **proposed structure**, not a record of anything that exists.
>
> All pieces are `status: concept` and all facts are `unverified`. Per the
> `campaign` contract, concept pieces are never campaigned, and per gate G1 no
> `unverified` fact may appear in output.
>
> **This is deliberate.** The blocker now lives in the system rather than in a
> conversation: any engine asked to generate a campaign will report the gap and
> refuse. Replace the `[unverified]` values with real data and the pack becomes
> live.

---

## Collection

| Field | Value | Verification |
|---|---|---|
| `collection` | Foundation | `unverified` — name proposed |
| `season` | AW26 | `unverified` |
| `thesis` | Four garments for ordinary weather, made to a weight that outlasts interest in them. | `unverified` |
| `tension` | Substance disappears; lightness demands attention. | Inherited from `brand-bible.md` |

**Thesis note:** states why the collection exists, not what is in it, per contract.

---

## Palette

Colourways resolve to these names. Values in `visual-identity.md`.

| Name | Verification |
|---|---|
| Raw | `unverified` |
| Wet concrete | `unverified` |
| Dry black | `unverified` |
| Dye lot | `unverified` — proposed as a limited seasonal accent |

---

## Provenance

| Field | Value | Verification |
|---|---|---|
| Mill | `[unverified]` | **Blocking** |
| Manufacture | `[unverified]` | **Blocking** |
| Conditions | `[unverified]` | **Blocking** |

**Rule from `product-philosophy.md`:** if the mill and factory cannot be named
publicly, no origin claim is made at all. Until these are filled, all campaigns
run with zero provenance claims.

---

## Drop structure

| Field | Value | Verification |
|---|---|---|
| Model | Continuous. Pieces return revised rather than retiring | `unverified` |
| Cadence | Two revision cycles per year | `unverified` |
| Scarcity mechanics | None. No limited drops, no countdowns | Confirmed by stance |

---

## Pieces

All `status: concept`. None may be campaigned.

### 1. The Coat

| Field | Value | Verification |
|---|---|---|
| `category` | Outerwear, mid-thigh, unlined | `unverified` |
| `materials` | `[unverified]` — proposed heavyweight cotton | **Blocking** |
| `weight` | `[unverified]` oz | **Blocking** |
| `construction` | `[unverified]` — proposed: bar-tacked pocket mouths, felled side seams, no fusible interlining | **Blocking** |
| `colourways` | Raw, Wet concrete | `unverified` |
| `sizing` | `[unverified]`. One fit intent: room for a layer, no more | `unverified` |
| `price` | `[unverified]` | **Blocking** |
| `detail` | ⛔ **MISSING** — founder must supply | **Blocking** |
| `status` | `concept` | |

### 2. The Overshirt

| Field | Value | Verification |
|---|---|---|
| `category` | Mid-layer, hip length | `unverified` |
| `materials` | `[unverified]` | **Blocking** |
| `weight` | `[unverified]` oz | **Blocking** |
| `construction` | `[unverified]` | **Blocking** |
| `colourways` | Raw, Dry black | `unverified` |
| `sizing` | `[unverified]` | `unverified` |
| `price` | `[unverified]` | **Blocking** |
| `detail` | ⛔ **MISSING** | **Blocking** |
| `status` | `concept` | |

### 3. The Trouser

| Field | Value | Verification |
|---|---|---|
| `category` | Trouser, straight, full break | `unverified` |
| `materials` | `[unverified]` | **Blocking** |
| `weight` | `[unverified]` oz | **Blocking** |
| `construction` | `[unverified]` | **Blocking** |
| `colourways` | Wet concrete, Dry black | `unverified` |
| `sizing` | `[unverified]` | `unverified` |
| `price` | `[unverified]` | **Blocking** |
| `detail` | ⛔ **MISSING** | **Blocking** |
| `status` | `concept` | |

### 4. The Knit

| Field | Value | Verification |
|---|---|---|
| `category` | Crew neck, heavy gauge | `unverified` |
| `materials` | `[unverified]` | **Blocking** |
| `weight` | `[unverified]` gsm | **Blocking** |
| `construction` | `[unverified]` | **Blocking** |
| `colourways` | Raw, Dye lot | `unverified` |
| `sizing` | `[unverified]` | `unverified` |
| `price` | `[unverified]` | **Blocking** |
| `detail` | ⛔ **MISSING** | **Blocking** |
| `status` | `concept` | |

---

## Conformance

- [x] All seven collection-level fields present
- [x] `thesis` states why, not what
- [x] `tension` nameable in one sentence
- [x] Every piece has all ten piece-level fields
- [ ] ⛔ **Every piece has ≥1 maker's detail** — all four missing
- [x] Every colourway maps to the collection palette
- [x] Every fact carries a verification level
- [x] No `unverified` fact is relied on by any existing artifact — no campaigns exist
- [x] No marketing language present

**Non-conformant.** Fails the maker's-detail rule on all four pieces. This is the
correct state given zero founder input, and it is what blocks Phase 5.

---

## To make this pack live

Per piece: materials with fibre percentages, weight, construction techniques,
sizing range, price with currency, and **the maker's detail** — the decision that
was genuinely difficult.

Plus: mill and factory names, or an explicit decision to make no origin claims.

Fill these and set `status: production`. Everything downstream then runs.
