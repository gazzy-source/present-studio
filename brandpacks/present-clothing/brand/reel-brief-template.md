# Present Clothing — Reel Brief Template

```yaml
document: reel-brief-template
version: 1.1.0
status: active
layer: 3
derives_from: campaign-system.md
```

> **A brief without a named reward (K4) or a named discovery (D1) is not
> producible.** Both are required before production, not after.
>
> Constants C1–C8 hold in every brief and are not restated per brief. A brief
> does not declare them; it is rejected if it breaks one.

---

## Fields

| Field | Source | Required |
|---|---|---|
| `reel_id` | sequential, permanent | ✅ |
| `subject` | named person | ✅ |
| `practice` | open dimension — specific, never generic | ✅ |
| `practice_class` | closed (7) | ✅ |
| `subject_stage` | closed (4) | ✅ |
| `emotional_temperature` | closed (12) | ✅ |
| `hour` | closed (6) | ✅ |
| `weather` | closed (6) | ✅ |
| `location_class` | closed (9) | ✅ |
| `location_id` | open — named, reusable | ✅ |
| `sound_world` | 2–3 layers from ambience / body / material | ✅ |
| `motif_primary` | closed (6), exactly one | ✅ |
| `structure` | 3-beat · 5-beat · 7-beat · single take | ✅ |
| `entry_point` | closed (5) | ✅ |
| `proximity_arc` | closed (4) | ✅ |
| `garment_role` | closed (4) | ✅ |
| `reward` | one sentence — what the second viewing yields | ✅ |
| `discovery_element` | the one new reusable element | ✅ |
| `discovery_type` | practice · location ID · city · object · ritual · material · sound · maker · subject | ✅ |
| `recurrence_ref` | prior reel_id satisfying K5, where applicable | — |
| `exceptions` | layer, rule, reason. Empty list permitted | ✅ |
| `owner` | named human | ✅ |
| `status` | `draft` · `accepted` | ✅ |

---

## Shape

```yaml
reel_id:
subject:
practice:
practice_class:
subject_stage:
emotional_temperature:
hour:
weather:
location_class:
location_id:
sound_world: []
motif_primary:
structure:
entry_point:
proximity_arc:
garment_role:
reward:
discovery_element:
discovery_type:
recurrence_ref:
exceptions: []
owner:
status: draft
```

---

## Pre-production checks

Run against `campaign-memory.md` before the brief leaves `draft`.

- [ ] K1 — all eight constants hold
- [ ] K2 — exactly one primary motif
- [ ] K3 — no 3+ match with any prior reel on {hour, location class, weather, motif}
- [ ] K4 — `reward` named in one sentence
- [ ] K5 — recurrence satisfied at least 1 in 4
- [ ] K6 — ≤ 2 of any 8 consecutive share `practice_class`
- [ ] K7 — ≥ 1 in 6 depicts an unphotogenic practice
- [ ] K8 — ≤ 3 of any 8 consecutive share `subject_stage`
- [ ] K9 — ≤ 2 of any 8 consecutive share `emotional_temperature`
- [ ] D1 — discovery named
- [ ] D5 — ≤ 2 consecutive share `discovery_type`
- [ ] D6 — ≤ 1 new city per 8
- [ ] All cooldowns in `campaign-memory.md` respected

---

## Acceptance

- [ ] Felt-distinctness test run against the three nearest prior reels
- [ ] Critic evaluation complete — self-certification is not acceptance
- [ ] `owner` names a human
- [ ] Entry appended to `campaign-memory.md`, including discovery ledger

---

## Anti-patterns

| Anti-pattern | Rule |
|---|---|
| Reward stated as a second fact rather than a second reading | K4 · P3 |
| Discovery used as the subject of the reel | D3 · L3 |
| Generic practice — "training", "creating", "working" | §2 Practice |
| Emotional temperature naming a feeling rather than a treatment | §2.1 · L4 |
| Music specified in `sound_world` | `visual-identity.md` Sound |
| Brief passing constraint arithmetic but feeling identical to a prior reel | Felt-distinctness test |
| Brief marked `accepted` without Critic evaluation | Acceptance |
