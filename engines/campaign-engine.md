# Engine: campaign-engine

```yaml
id: campaign-engine
version: 1.0.0
status: stable
input:  [brand-pack, campaign-memory, archetype]
output: campaign (complete), deliverable manifest
```

## Purpose

The orchestrator. Takes a brief and a collection, selects an archetype, runs the
narrative and cinematic engines, gates the result, and emits a campaign with its
deliverable manifest.

This is the engine that produces a campaign end to end. The other two are its
stages.

---

## Process

### 1. Verify the pack

Check `pack.yaml → status`. Anything below `complete` means required artifacts
are missing.

- `scaffold` → block. Report which artifacts are absent.
- `partial` → proceed only if the specific missing artifact is not required by
  the selected archetype. Otherwise block.

Never generate around a missing artifact. Output that compensates for an absent
Brand Voice is generic output with extra steps.

### 2. Consult memory before briefing

Read `campaign-memory` **first**, not after drafting. Extract: spent tensions,
spent openings, spent environments, motif saturation states.

Checking memory after a draft exists means discovering repetition once it is
expensive to fix, and biases toward keeping work that should be discarded.

### 3. Select the tension

From the brief, or from Collection DNA `tension`.

Validate: genuinely contradictory, true of the collection, not spent. If the
tension is spent, either vary it deliberately and declare the variation, or
choose another.

### 4. Select the archetype

Match the campaign's intent to a root archetype. The archetype supplies required
beat shape; it does not supply content.

If no archetype fits, report it. Do not invent one inline — archetypes are root
artifacts and inventing one from inside a pack violates the isolation boundary.

### 5. Select the register

Choose a Brand Voice register using its declared trigger, and record the
justification in the campaign's `register` field. An unjustified register
selection usually means the default was taken without thought.

### 6. Resolve pieces

Every piece must exist in Collection DNA with status `production` or `available`.
Concept pieces are never campaigned — they change, and the campaign outlives the
change.

### 7. Run narrative-engine

Produces spine, beat functions, and copy. See `narrative-engine.md`.

### 8. Run cinematic-language-engine

Produces frames and shot direction for those beats. See
`cinematic-language-engine.md`.

Order matters: narrative before cinematic. Visual-first campaigns produce
beautiful sequences with nothing happening in them.

### 9. Assemble the deliverable manifest

For each deliverable: name the production blueprint and the adapter. Verify the
blueprint's required inputs are all present in the pack.

### 10. Gate the whole campaign

Run the full quality bar against the assembled campaign, not only its parts. A
campaign can consist of individually passing beats and still fail as a whole —
most often on S4 (tension) or S6 (silence).

Run the `campaign` contract conformance checklist.

### 11. Write memory on produce

When status reaches `produced`, append to `campaign-memory`: tension verbatim,
spine, pieces, motifs used, opening, environments. Append-only.

Not at brief. Not at draft. Memory records what happened.

---

## Heuristics

**Brief quality caps output quality.** A vague brief cannot be rescued downstream.
If the brief has no tension, stop and get one — this is cheaper than two revision
passes.

**Two revisions maximum.** Failing after two passes means the problem is upstream:
weak brief, thin DNA, or wrong archetype. Report that rather than polishing
(`quality-bar.md`).

**Prefer fewer deliverables, fully realised.** Six considered assets outperform
twenty adapted ones. Volume is the adapter's job, not the campaign's.

**Deliberate repetition is how brand language forms.** Returning to a motif is not
a failure — undeclared repetition is. Declare it.

**The campaign is the turn.** If the turn is weak, nothing else matters. Spend
effort there before polishing copy.

**Do not let the channel choose the story.** Format constraints are applied by
adapters after the campaign exists. A campaign written for a format is an ad.

---

## Failure modes

| Symptom | Cause | Fix |
|---|---|---|
| Output generic despite a complete pack | Voice/DNA loaded after generation | Restart; load constraints first |
| Campaign is beautiful but forgettable | Cinematic ran before narrative | Re-run in order |
| Repetition found at review | Memory consulted after drafting | Move memory check to step 2 |
| Assets feel disconnected | Deliverables generated independently | Generate the campaign once; adapters render it |
| Endless revision | Upstream problem being fixed downstream | Stop at two passes; report |

---

## Reports the gap when

- `pack.yaml → status` is `scaffold`, or a required artifact is missing
- No archetype matches the brief's intent
- Every candidate tension is spent and no variation is authorised
- A required piece is `concept` or `sampling`
- A production blueprint's required inputs are absent from the pack
- Two revision passes have not cleared the hard gates
