# Present Clothing — Campaign System

```yaml
document: campaign-system
version: 1.1.0
status: active
layer: 3
derives_from: creative-principles.md
```

> **Status: ACTIVE.** The generative system that produces campaigns. Distinct
> from the root `campaign-engine`, whose logic is not duplicated here. This
> document holds brand-specific sets, quotas and constraints only.
>
> **Design principle.** Recognition comes from repeating *how* work is shown,
> never *what* is shown. The constants are formal. The subject is the most
> variable element in the system.
>
> **Known failure mode.** The risk is not repetition — it is sameness of
> feeling. Two campaigns can sample entirely different values and land
> identically. Combinatorics do not guarantee distinctness. Constraints and the
> felt-distinctness test do.

---

## 1. Constants

Never sampled. Hold in every campaign, forever.

| # | Constant | Serves |
|---|---|---|
| C1 | Nothing is asked of the viewer. No hook, no CTA, no question | L1 |
| C2 | Opens mid-action, closes before completion | L2 · P1 |
| C3 | No outcome, reveal, or before-and-after | L3 |
| C4 | Away-gaze throughout. One late look to lens permitted, once, never in the opening three seconds | P4 |
| C5 | Nothing is explained. Copy is fact or absent | L4 · P2 |
| C6 | Real time. No retiming. Cuts land on stillness | P4 |
| C7 | One person, one practice | L2 |
| C8 | Something is present that only a second viewing finds | P3 |

C8 is the only constant requiring an idea rather than compliance, and is
therefore the one most likely to be skipped.

---

## 2. Creative Dimensions

Sampled every campaign. Fourteen dimensions. Four open, ten closed.

**A dimension is not a list.** Every closed set must *span* — the extremes must
be genuinely different and no midpoint redundant. A value that does not occupy a
distinct position on the range is removed.

| Dimension | Type | Values |
|---|---|---|
| **Practice** | open | Any real, specific discipline. Never generic |
| **Practice class** | closed (7) | Physical · Craft · Cognitive · Performative · Care · Commercial · Maintenance |
| **Subject stage** | closed (4) | Month 1–6 · Year 1–2 · Year 3–7 · Year 8+ |
| **Emotional temperature** | closed (12) | See §2.1 |
| **Hour** | closed (6) | Before dawn · First light · Mid-morning grey · Flat afternoon · Dusk before dark · The hour before rain |
| **Weather** | closed (6) | Overcast dry · Raining · After rain · Wind · Cold still · Fog |
| **Location class** | closed (9) | Training room · Stairwell · Car park · Workshop · Kitchen · Studio · Street · Transport · Domestic |
| **Location ID** | open | A specific place, named and reusable |
| **Sound world** | closed (19) | Sampled as 2–3 layers. See §2.2 |
| **Motif** | closed (6) | The six in `visual-identity.md` |
| **Structure** | closed (4) | 3-beat · 5-beat · 7-beat · Single take |
| **Entry point** | closed (5) | Mid-action · Mid-rest · Mid-transit · Mid-repair · Aftermath |
| **Proximity arc** | closed (4) | Static · Closing · Receding · Oscillating |
| **Garment role** | closed (4) | Worn unremarked · Worn with detail found · Empty garment · Absent but implied |

### 2.1 — Emotional temperature

Temperature, not emotion. It is the dimension that operates *across* subject: a
boxer and a ceramicist can share **Heavy** while sharing nothing else.

**A temperature that cannot be expressed as camera, pace or light is not a valid
value.** Naming a feeling fails L4.

| Temperature | Executable as |
|---|---|
| Still | Locked camera, long beats, no subject transit |
| Heavy | Low angle, weight-bearing action, slow settle, dense frame |
| Quiet | Sparse sound world, wide negative space, minimal cutting |
| Tense | Shorter beats, tighter proximity, held breath in sound |
| Patient | Rest beats to 4.0s, repeated identical action |
| Restless | Oscillating proximity, incomplete actions, transit |
| Resolute | Static frame, unbroken action, no cut mid-effort |
| Fragile | Shallow handling, small gestures, precarious objects |
| Cold | Breath visible, hands stiff, grade cast pushed cool |
| Tender | Hands on material, close proximity, soft light |
| Exhausted | Post-effort stillness, seated, slack posture |
| Focused | Single unbroken task, no environmental cutaway |

**Excluded and not to be reinstated:** *Warm* contradicts the grade. *Hopeful*
is not executable and implies an outcome.

### 2.2 — Sound world

Sampled as two to three layers. Full rules in `visual-identity.md` §Sound.

| Layer | Values |
|---|---|
| Ambience | Room tone · Street · Rain · Wind · Traffic distant · Extraction fan · Silence |
| Body | Breathing · Footsteps · Hands on material · Clothing movement |
| Material | Metal · Wood · Fabric · Water · Chalk · Paper · Glass · Machine |

No music. Diegetic only. Silence is recorded room tone, never a stripped track.

---

## 3. Constraints

Hard gates. A campaign failing any of these is not produced.

| # | Constraint | Test |
|---|---|---|
| K1 | All eight constants hold | Checked before production, not after |
| K2 | Exactly one primary motif | A second may appear; never centred |
| K3 | Collision rule | No campaign matches a prior one on 3+ of {hour, location class, weather, motif}. Two permitted |
| K4 | The reward is named | One sentence stating what the second viewing yields. **If it cannot be named, the campaign is not made** |
| K5 | Recurrence quota | At least 1 in 4 reuses a prior location ID, subject, or garment |
| K6 | Practice distribution | No more than 2 of any 8 consecutive share a practice class |
| K7 | Unphotogenic quota | At least 1 in 6 depicts a practice with no visual drama — revision, admin, waiting, correspondence, cleaning up, the second attempt |
| K8 | Stage distribution | No more than 3 of any 8 consecutive share a subject stage |
| K9 | Temperature distribution | No more than 2 of any 8 consecutive share an emotional temperature |

**K7 exists because the system's most likely drift is toward the most
photogenic practice.** Without a quota, sampling gravitates to boxing and
ceramics until the brand becomes a boxing-and-ceramics brand.

---

## 4. Memory

`campaign-memory.md` is an operational index, not an archive. Three functions:

**Collision prevention.** Cooldowns: motif 6 · location ID 4 · hour+weather pair
10 · temperature 8 · discovery type 2 consecutive · city 8.

**Recurrence enablement.** Memory is queried to *find* what should return, not
only what to avoid. K5 is satisfied by reading it.

**Drift detection.** Rolling distribution across the last 24 campaigns per
practice class, stage, hour, location class and temperature. Any class exceeding
25% is a drift flag — reported, never auto-corrected. A human decides.

**The felt-distinctness test.** Before acceptance, play the candidate against
the three nearest prior campaigns by field overlap. If a viewer who does not
know the brief cannot tell them apart, they collided regardless of field values.
Log the finding and add a constraint.

This is the only check that catches sameness the fields cannot see, and it is
why a human sits at acceptance.

---

## 5. Escalation

Changes permitted range and accumulated depth. **Never touches a constant.**

**Mechanism 1 — Unlocking.** Variable sets widen as the body of work earns them.
Year 1 runs on 4 practice classes and 4 location classes; by year 3 all 7 and
all 9 are live. Restraint early is how the form becomes legible before it
becomes broad.

**Mechanism 2 — The recurrence dividend.** The same subject revisited at year 1,
year 3, year 7. The same location, unchanged, across a decade. This compounds
and cannot be bought, faked, or copied by a competitor with a larger budget. It
is the only genuine moat the system produces.

**Mechanism 3 — Era marking.** Roughly every two years, exactly one execution
rule in `visual-identity.md` or `brand-voice.md` is deliberately revised — a
lens length, a grade cast, a beat duration. Layer 3 versions freely, so identity
is untouched, but the archive gains visible strata.

Rules: one rule per era · never a constant · logged in `escalation-ledger.md`
with its parent principle intact. A proposed era change that cannot complete
law → principle → execution is a preference and does not ship.

---

## 6. Discovery

**Every campaign contributes exactly one new reusable element to the world.**

Exactly one. Zero and the world closes — around campaign 300 the audience stops
discovering and starts recognising. Two and the campaign becomes a tour, with
novelty competing against the practice for attention.

**Element types:** practice · location ID · city · object · ritual · material ·
sound · maker · subject

| # | Rule |
|---|---|
| D1 | Every campaign names its discovery in the brief, before production. Unnamed discovery does not count |
| D2 | The element is logged to `campaign-memory.md` as `discovery_element` and `discovery_type`, and enters the reusable world |
| D3 | Discovery is never the campaign's subject. It appears within the frame; the practice remains the subject. A discovery announced is an outcome, failing L3 |
| D4 | A discovered element becomes eligible for reuse after 3 campaigns. Reuse satisfies K5 |
| D5 | No more than 2 consecutive campaigns discover the same type |
| D6 | Cities are rationed — 1 new city per 8 campaigns maximum |

**D6 exists because** a world expanding geographically too fast reads as travel
content. The brand's world is characterised by returning to unremarkable places,
not by finding remarkable ones.

The **discovery ledger** in `campaign-memory.md` records every element, its
type, its origin campaign, and its reuse count. After 100 campaigns this is the
brand's world, and it cannot be replicated by outspending — it took 100
campaigns to build.

---

## 7. Known open issues

Recorded, not resolved. Resolution belongs to the founder or the Architect.

1. **K6 / Mechanism 1 contradiction.** Mechanism 1 unlocks 3 practice classes in
   year 1. K6 permits max 2 per 8 consecutive, which caps at 6 across 8. The two
   rules cannot both hold. Generation of the first ten briefs proceeded on **4**
   practice classes, the minimum that satisfies K6. Formal resolution outstanding.
2. **Location class breadth.** Year-1 unlock of 4 location classes may be too
   narrow for 4 practice classes; Craft and Maintenance both default to Workshop.
3. **Restless / Oscillating overlap.** Emotional temperature *Restless* and
   proximity arc *Oscillating* may be the same instruction twice. Under
   observation.
4. **Engine placement.** Whether sampling and memory-query logic extends the root
   `campaign-engine` or requires a new engine is an Architect decision. Standing
   recommendation: extend, add nothing.
5. **Geography unset.** All location IDs are provisional until the base city is
   fixed.
