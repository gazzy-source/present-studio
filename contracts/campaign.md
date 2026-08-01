# Contract: campaign

```yaml
id: campaign
version: 1.0.0
status: stable
```

## Purpose

Defines a campaign: a bounded piece of creative work with one tension, one
narrative spine, and a set of beats that render into deliverables.

Applies to campaign **instances** inside a Brand Pack. Brand-agnostic campaign
shapes are governed by their archetype and live at root.

---

## Required fields

| Field | Type | Rule |
|---|---|---|
| `id` | string | kebab-case, `<season>-<name>`, e.g. `aw26-first-light` |
| `archetype` | string | Root archetype id this instantiates |
| `season` | string | Matches Collection DNA `season` |
| `tension` | 1 sentence | The productive contradiction. Required, nameable |
| `thesis` | 1–2 sentences | What this campaign asserts. Not a summary of content |
| `pieces` | list | Collection DNA piece names featured. Must resolve |
| `register` | string | Brand Voice register selected, with justification |
| `beats` | list | Ordered. See beat structure below |
| `motifs_used` | list | Visual Identity motifs drawn on. Logged to Campaign Memory |
| `deliverables` | list | What this renders into, with adapter and blueprint ids |
| `status` | enum | `brief` · `drafted` · `approved` · `produced` · `archived` |

---

## Beat structure

A beat is one unit of time-based narrative — one shot, one moment, one line.

| Field | Type | Rule |
|---|---|---|
| `n` | integer | Position in sequence |
| `function` | enum | `establish` · `escalate` · `turn` · `rest` · `close` |
| `frame` | spec | What the camera sees, per Visual Identity |
| `copy` | string / null | Line spoken or shown. Null is valid and often correct |
| `piece` | string / null | Piece featured, if any. Must resolve to Collection DNA |
| `duration` | measure | Seconds, for time-based work |

**Beat rules:**

- Every campaign has exactly one `turn`. A campaign without a turn is a montage.
- At least one `rest` beat in any sequence over four beats. Unrelieved escalation
  reads as advertising.
- `close` never restates `establish`. If it does, nothing happened.
- Not every beat carries copy. Silence is a beat function (principle 3).

---

## Validation rules

1. **Tension present** — one sentence, nameable. Blocking if absent (S4).
2. **Piece resolution** — every referenced piece exists in Collection DNA with
   status `production` or `available`. Concept pieces are never campaigned.
3. **Claim closure** — every claim in every beat traces to Collection DNA (G1).
4. **Voice conformance** — all copy obeys the selected register and every Brand
   Voice prohibition (G5).
5. **Visual conformance** — every `frame` obeys Visual Identity, including its
   prohibitions.
6. **Archetype conformance** — beat structure satisfies the named archetype's
   required shape.
7. **Single turn** — exactly one beat with function `turn`.
8. **Motif logging** — `motifs_used` is written to Campaign Memory on reaching
   status `produced`.
9. **Non-repetition** — the tension and spine are checked against Campaign
   Memory. Reusing a spent tension requires deliberate variation, not accident.

---

## Conformance checklist

- [ ] All eleven required fields present
- [ ] `id` follows `<season>-<name>`
- [ ] `archetype` resolves to a root archetype
- [ ] `tension` is one sentence and genuinely contradictory
- [ ] Every piece resolves and is `production` or `available`
- [ ] Exactly one `turn` beat
- [ ] ≥1 `rest` beat if over four beats
- [ ] `close` does not restate `establish`
- [ ] Every claim traces to Collection DNA
- [ ] All copy passes voice conformance
- [ ] All frames pass visual conformance
- [ ] Campaign Memory checked for repetition
- [ ] Every deliverable names an adapter and a blueprint

---

## Failure modes

| Symptom | Cause | Resolution |
|---|---|---|
| Campaign reads as a product montage | No `turn` beat | Restructure. Do not fix with copy |
| Every beat feels the same weight | No `rest` beats | Insert silence |
| Feels like the last campaign | Spent tension or motif reused | Check Campaign Memory before briefing, not after |
| Copy is strong but generic | Register selected but voice applied as post-filter | Regenerate with voice loaded first |
