# Contract: production-blueprint

```yaml
id: production-blueprint
version: 1.0.0
status: stable
```

## Purpose

Defines how a class of deliverable is produced: its inputs, its structure, its
technical specification, and the standard it must meet.

A blueprint is **brand-agnostic** and lives at root in `production-blueprints/`.
It is the reusable specification; the rendered result lives in a Brand Pack's
`production/`.

A blueprint is executable by a producer, editor or generation model without
further creative interpretation.

---

## Required fields

| Field | Type | Rule |
|---|---|---|
| `id` | string | kebab-case, names the deliverable class |
| `deliverable` | string | What this produces, in one line |
| `inputs` | list | Required artifacts by contract id |
| `structure` | spec | Beat or section shape, with counts and durations |
| `technical` | spec | Format, ratio, resolution, duration, frame rate, audio |
| `visual_source` | string | `visual-identity` — never restated inline |
| `copy_source` | string | `brand-voice` — never restated inline |
| `constraints` | list | Hard production limits |
| `acceptance` | checklist | How a finished deliverable is judged |
| `adapter` | string | Adapter id that renders this |

---

## Field detail

### `inputs`

Named by contract id, never by brand. A blueprint requiring
`present-clothing/brand-voice.md` is non-conformant — it requires `brand-voice`,
and the pack supplies the instance.

This is the isolation boundary. A blueprint that names a brand has leaked.

### `structure`

Quantified. Beat count, duration per beat, section order, where the turn falls.
"Short and punchy" is not a structure; "6 beats, 1.5–3s each, turn at beat 4" is.

### `technical`

Complete enough to hand to an editor: aspect ratio, resolution, frame rate,
duration tolerance, audio spec, safe areas, text placement bounds, export format.

### `visual_source` / `copy_source`

Blueprints **reference** the brand's identity and voice; they never restate them.
Restating creates a second source of truth that silently drifts. This is the most
common way a framework degrades into a document folder.

### `acceptance`

A pass/fail list a producer can run without the brand team present. Distinct from
the quality bar — the quality bar judges the artifact, acceptance judges the
production.

---

## Validation rules

1. **Brand-agnostic** — no brand named anywhere. Automatic non-conformance.
2. **Input by contract** — inputs named by contract id only.
3. **No restatement** — visual and copy direction referenced, never inlined.
4. **Quantified structure** — counts and durations, not adjectives.
5. **Complete technical spec** — sufficient to produce without follow-up.
6. **Executable acceptance** — every criterion objectively checkable.
7. **Adapter named** — every blueprint names its rendering adapter.

---

## Conformance checklist

- [ ] All ten required fields present
- [ ] No brand named anywhere in the document
- [ ] Inputs given as contract ids
- [ ] `structure` quantified with counts and durations
- [ ] `technical` complete: ratio, resolution, duration, frame rate, audio
- [ ] Visual and copy direction referenced, not restated
- [ ] `acceptance` criteria objectively checkable
- [ ] `adapter` names an existing adapter

---

## Failure modes

| Symptom | Cause | Resolution |
|---|---|---|
| Output drifts from brand identity | Blueprint restated visual direction inline | Delete the inline copy; reference the source |
| Blueprint only works for one brand | Brand-specific assumptions embedded | Extract to the Brand Pack; generalise the blueprint |
| Producer returns with questions | `technical` or `structure` under-specified | Quantify. A blueprint needing clarification is incomplete |
