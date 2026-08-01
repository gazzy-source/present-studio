# Contract: brand-voice

```yaml
id: brand-voice
version: 1.0.0
status: stable
```

## Purpose

Defines how a brand speaks, precisely enough that generated copy is
indistinguishable from founder-written copy — and precisely enough that a
competitor's voice would fail against it.

A voice that could describe several brands is not a voice. It is a category
description.

---

## Required fields

| Field | Type | Rule |
|---|---|---|
| `stance` | 1 sentence | What the brand believes that others in its category do not. Must be arguable — a stance nobody could reject is not one |
| `registers` | 2–4 named | Each with a name, when it is used, and a two-line example |
| `cadence` | spec | Sentence length distribution, rhythm, paragraph shape |
| `vocabulary.owned` | 10–25 words | Words this brand uses that its category does not |
| `vocabulary.forbidden` | 10–25 words | Words that would break the voice, with reasons |
| `syntax` | rules | Person, tense, contractions, punctuation, capitalisation |
| `claim_posture` | spec | How strongly claims are stated; how craft is referenced |
| `prohibitions` | list | Absolute rules. Any occurrence is a hard-gate failure |
| `calibration` | 3+ pairs | Matched "in voice" / "out of voice" pairs on the same idea |

---

## Field detail

### `registers`

A register is a setting of the voice, not a different voice. All registers share
stance, vocabulary and syntax; they differ in density and warmth.

Typical set: one for campaign narrative, one for product detail, one for direct
address. Each declares **when** it applies — an engine selects register from
context, so an unspecified trigger makes the field unusable.

### `cadence`

Must be quantified, not described. "Short, punchy sentences" is not a cadence.

Required: target sentence-length range, permitted maximum, fragment policy,
paragraph length in sentences, and rhythm rule (e.g. "long, long, short — the
short line carries the weight").

### `vocabulary.owned`

The differentiators. Generic positives (`quality`, `crafted`, `timeless`) are not
owned words; every brand in the category uses them. Owned words come from the
brand's actual world: its materials, its references, its geography, its trade.

### `vocabulary.forbidden`

Each entry carries a reason. Reasons make the rule generalisable to words not on
the list — an engine can extrapolate from "no words that rank the customer"
but not from a bare list.

### `calibration`

The highest-value field. Each pair expresses the **same idea** twice: once in
voice, once in a plausible near-miss. Near-misses must be genuinely plausible —
contrasting against obviously bad writing teaches nothing.

---

## Validation rules

1. **Substitution** — replacing the brand name must break the document. A voice
   that survives substitution is a category description.
2. **Specificity** — `vocabulary.owned` contains no generic category positives.
3. **Quantified cadence** — cadence is numeric, not adjectival.
4. **Register triggers** — every register declares when it applies.
5. **Reasoned prohibitions** — every forbidden word carries a reason.
6. **Calibration realism** — out-of-voice examples are plausible, not strawmen.
7. **No claims** — voice governs *how* things are said. *What* may be said is
   Collection DNA. A voice document asserting product facts is non-conformant.

---

## Conformance checklist

- [ ] All nine required fields present
- [ ] `stance` is arguable, one sentence
- [ ] 2–4 registers, each with trigger and example
- [ ] Cadence quantified
- [ ] 10–25 owned words, none generic
- [ ] 10–25 forbidden words, each reasoned
- [ ] 3+ calibration pairs on matched ideas
- [ ] Document survives the substitution test (i.e. breaks when substituted)
- [ ] No product claims present

---

## How engines use this

Engines load voice **before** generating, not as a post-filter. Voice as
post-processing produces generic copy with vocabulary swapped in — the failure
mode this contract exists to prevent.

`prohibitions` map to quality-bar gate **G5**. Any occurrence blocks emission.
