# Present Clothing — Campaign Memory

```yaml
contract: campaign-memory
version: 0.2.0
status: active
```

Append-only record of what has been made. Consulted at brief time, written on
produce. Entries are never edited or deleted.

**No campaigns have been produced.** Ten briefs (R-001 to R-010) exist and are
pending Critic evaluation; none has been accepted, so all sections below remain
empty and conformant.

---

## Entry schema

Every accepted campaign records:

```
reel_id · subject · practice · practice_class · stage ·
emotional_temperature · hour · weather · location_class · location_id ·
sound_world (list) · motif_primary · structure · entry · proximity_arc ·
garment_role · reward · discovery_element · discovery_type ·
exceptions · accepted_by
```

`reward` states, in one sentence, what a second viewing yields (K4).
`exceptions` records layer, rule, reason and piece. Empty list permitted.
`accepted_by` names a human. Engine self-certification is not acceptance.

---

## Campaigns

| reel_id | subject | practice | class | stage | temperature | hour | weather | location_id | motif | reward | discovery | accepted_by |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| — | — | — | — | — | — | — | — | — | — | — | — | — |

*Empty. Entries are appended when a campaign reaches `produced`.*

---

## Motifs

Motifs resolve to `visual-identity.md`. State is derived from `uses`:
`establishing` 1–2 · `established` 3–6 · `saturated` 7+.

| motif | uses | last_used | state |
|---|---|---|---|
| Weather arriving | 0 | — | unused |
| The hand on the seam | 0 | — | unused |
| The empty garment | 0 | — | unused |
| Wet stone | 0 | — | unused |
| The turned back | 0 | — | unused |
| The same place, again | 0 | — | unused |

*All six available. None saturated.*

---

## Discovery ledger

Every element introduced to the world, its origin, and its reuse count. Elements
become eligible for reuse after 3 campaigns (D4). Never deleted.

| element | type | origin_reel | reuse_count | eligible |
|---|---|---|---|---|
| — | — | — | — | — |

*Empty. No campaign has been produced.*

---

## Cooldowns

Checked at brief time. A brief violating a cooldown is re-sampled, not accepted
with an exception.

| Dimension | Cooldown |
|---|---|
| Motif | 6 campaigns |
| Location ID | 4 campaigns |
| Hour + weather pair | 10 campaigns |
| Emotional temperature | 8 campaigns |
| Discovery type | 2 consecutive |
| New city | 8 campaigns |

---

## Distribution and drift

Rolling window: last 24 accepted campaigns. Any single value exceeding 25% of
the window raises a drift flag.

| Axis | Window share | Flag |
|---|---|---|
| Practice class | — | — |
| Subject stage | — | — |
| Emotional temperature | — | — |
| Hour | — | — |
| Location class | — | — |
| Discovery type | — | — |

*Empty. Window opens at the first accepted campaign.*

**Drift is reported, never auto-corrected.** A human decides.

---

## Felt-distinctness test

Run before acceptance. Play the candidate against the three nearest prior
campaigns by field overlap. If a viewer who does not know the brief cannot tell
them apart, they collided regardless of field values.

| reel_id | compared against | verdict | constraint added |
|---|---|---|---|
| — | — | — | — |

*Empty.*

---

## Exceptions log

Layer, rule, reason, piece. Laws are never bent and never appear here.

| reel_id | layer | rule | reason | accepted_by |
|---|---|---|---|---|
| — | — | — | — | — |

*Empty. An unlogged exception is a failure, not a judgment call.*

---

## Spent

Reuse requires deliberate, declared variation.

### Tensions

*None spent.* The brand tension — "the work that builds you is rarely visible
while it is happening" — is internal and never deployed as copy. It anchors
briefs, not lines.

### Lines

*None.* No copy has shipped. Tagline remains unfrozen; three candidates held.

### Environments

*None.* Full `visual-identity.md` environment list available.

### Openings

*None.* No campaign has established an opening pattern.

---

## Notes for the first campaign

1. **The first campaign sets the opening pattern.** Whatever beat 1 does becomes
   the thing subsequent campaigns must vary from. Choose deliberately.
2. **Log verbatim.** Paraphrased rewards and discoveries defeat repetition
   detection.
3. **Discovery is cumulative and irreversible.** An element logged is in the
   world permanently. Introduce nothing the brand would not want in year ten.
4. **K5 recurrence cannot be satisfied before campaign 4.** The first three
   campaigns are exempt by arithmetic, not by exception.

---

## Conformance

- [x] All required sections present
- [x] Entry schema states all 21 fields
- [x] Every produced campaign has an entry — none produced
- [x] Every motif resolves to `visual-identity.md`
- [x] Motif `state` matches `uses` count
- [x] No entry edited or removed
- [x] Discovery ledger present and append-only
- [x] Cooldowns, drift thresholds and felt-distinctness test recorded
- [x] Exceptions log present; no law-level entry possible
- [x] Spent lists cover tensions, lines, environments and openings
