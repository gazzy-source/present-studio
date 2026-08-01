# Contract: visual-identity

```yaml
id: visual-identity
version: 1.0.0
status: stable
```

## Purpose

Defines how the brand looks and how it is framed — precisely enough that a
single frame is identifiable without a logo.

This is a **direction** contract, not a style guide. It specifies what a camera
does, where light comes from, and what recurs. Its output is instructions a
photographer, director or image model can execute without interpretation.

---

## Required fields

| Field | Type | Rule |
|---|---|---|
| `palette` | spec | Colours with names, values, and role (dominant / support / accent) |
| `light` | spec | Quality, direction, hour, source. The most identity-carrying field |
| `lens` | spec | Focal lengths, depth, distance-to-subject |
| `composition` | rules | Framing, negative space, subject placement, horizon policy |
| `motion` | spec | Camera movement, pace, cut rhythm. Required for time-based work |
| `grade` | spec | Contrast, black level, saturation, cast |
| `motifs` | 3–7 | Recurring elements that accrue recognition |
| `environments` | list | Where work is set, and where it is never set |
| `subject_direction` | spec | Posture, gaze, expression, hands, movement |
| `typography` | spec | Faces, weights, case, spacing, alignment |
| `prohibitions` | list | Absolute visual rules. Any occurrence fails gate G5 |

---

## Field detail

### `light`

The strongest identity signal in image-making, and the most under-specified.

Required: quality (hard/soft/diffuse), direction (relative to subject), hour
(named, e.g. "the twenty minutes after sunrise"), source (natural/practical/
artificial), and shadow behaviour.

"Natural light" is not a specification. "Low side light forty minutes before
sunset, long shadows, no fill, subject's face half in shadow" is.

### `lens`

Focal length choice is a point of view. Wide close is intimate and distorting;
long is observational and detached. Specify the range and what it means, so the
choice is reasoned rather than defaulted.

### `motifs`

Recurring elements — a colour that always appears once, a gesture, an object, an
hour, a type of surface. Motifs are declared here and **never improvised**
(principle 7). Campaign Memory tracks which have been spent.

Three to seven. Fewer and nothing accumulates; more and nothing is distinctive.

### `environments`

Both halves are required. Where the brand is *never* set is as defining as where
it is — it is the negative space of the visual world.

### `subject_direction`

How people are, not who they are. Casting sits in Collection DNA and campaign
briefs. This field covers posture, gaze policy (to camera or away), expression
range, what hands do, stillness versus movement.

Gaze policy alone separates most premium apparel imagery from most mass-market
imagery.

---

## Validation rules

1. **Executability** — every field is actionable by a photographer without
   interpretation. Adjectival description is non-conformant.
2. **Light specificity** — quality, direction, hour, source and shadow all present.
3. **Palette closure** — values given, roles assigned. Colours match Collection
   DNA palette names where they overlap.
4. **Motif count** — 3–7, each concretely described.
5. **Environment exclusions** — the "never" list is non-empty.
6. **Substitution** — replacing the brand name must break the document.
7. **No claims** — visual identity governs appearance, not product fact.

---

## Conformance checklist

- [ ] All eleven required fields present
- [ ] `light` fully specified across five sub-properties
- [ ] `lens` gives focal range and the reasoning
- [ ] 3–7 motifs, each concrete
- [ ] `environments` includes explicit exclusions
- [ ] `subject_direction` states gaze policy
- [ ] `motion` present (required once time-based work exists)
- [ ] Every field executable without interpretation
- [ ] Document breaks under substitution
- [ ] No product claims present

---

## How engines use this

The Cinematic Language Engine reads this to produce shot-level direction.
Production Blueprints reference it for output specification. Adapters must not
override it — a channel's conventions never outrank the brand's visual identity.
