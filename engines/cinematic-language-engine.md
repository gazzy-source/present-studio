# Engine: cinematic-language-engine

```yaml
id: cinematic-language-engine
version: 1.0.0
status: stable
input:  [visual-identity, campaign (beats), collection-dna]
output: campaign (frames), shot direction
```

## Purpose

Turns narrative beats into executable visual direction — what the camera sees,
where the light comes from, how the frame moves.

Output is precise enough to hand to a photographer, director or generation model
without further creative interpretation. If a producer returns with questions,
this engine under-delivered.

---

## Process

### 1. Load visual constraints

Read `visual-identity` in full before looking at the beats. The identity governs;
the beat is the assignment.

Note the `prohibitions` list first. It is faster to generate inside the boundary
than to filter afterwards.

### 2. Read the beat's function, not just its content

A beat's function determines its visual treatment before its content does:

| Function | Default treatment |
|---|---|
| `establish` | Widest frame in the sequence. Environment dominant, subject small or absent |
| `escalate` | Closer, tighter, less air. Movement enters |
| `turn` | The break. Whatever the sequence has been doing, do something else |
| `rest` | Stillness. Often no subject. The frame the audience exhales into |
| `close` | Resolution of the visual argument, not a repeat of `establish` |

### 3. Specify light first

Light before framing, always. Light carries more identity than composition and
constrains what framing is possible.

For every beat, specify: quality, direction, hour, source, shadow behaviour. All
five, drawn from Visual Identity — a beat may sit at a different point within the
brand's light world, never outside it.

### 4. Choose the lens with a reason

Focal length is a point of view, not a default. State the length and what it
does: wide-close is intimate and complicit; long is observational and detached.

A sequence where every beat sits at the same focal length is flat. A sequence
where every beat differs is incoherent. Establish a home length; depart from it
at the turn.

### 5. Frame

Apply Visual Identity composition rules: negative space, subject placement,
horizon policy. Specify what is in frame **and what is deliberately excluded**.

### 6. Direct the subject

Posture, gaze, expression, hands, movement — per `subject_direction`.

Gaze policy is the highest-leverage decision. To-camera is confrontation; away is
observation. Changing gaze policy at the turn is one of the most reliable moves
available.

### 7. Specify motion

For time-based work: camera movement, its motivation, pace, and cut rhythm into
the next beat.

Motion without motivation reads as production value rather than direction. If a
move cannot be justified by what the beat is doing, hold the frame.

### 8. Deploy motifs deliberately

Draw only on motifs declared in Visual Identity. Never improvise (principle 7).

Check `campaign-memory.motifs`. A `saturated` motif may appear incidentally but
may not anchor the campaign.

### 9. Gate

Run hard gates G2–G5 against the visual direction. G1 applies wherever a frame
shows a product detail — a garment cannot be shown with construction that
Collection DNA does not record.

---

## Heuristics

**The rest beat has no subject.** Empty frames are the hardest to justify in a
review and the most valuable in an edit.

**Shoot the hour, not the light.** Named hours are repeatable and identity-forming;
"golden light" is a look anyone can buy.

**Exclusion is direction.** Naming what is not in frame is often more useful to a
producer than listing what is.

**The turn changes one variable, not all of them.** Change gaze, or lens, or light —
not all three. Changing everything reads as a different campaign.

**Weight is visible.** Fabric weight, drape and movement communicate quality faster
than any copy line. Direct for it: air, motion, the way a hem falls.

**Hands resolve awkwardness.** Most unconvincing apparel imagery fails at the hands.
Direct them explicitly in every beat.

**Product enters as consequence.** The garment is never the subject of the frame's
first sentence (principle 4).

---

## Failure modes

| Symptom | Cause | Fix |
|---|---|---|
| Producer returns with questions | Direction adjectival, not executable | Quantify: hour, focal length, direction of light |
| Looks like every other brand | Generic light, default framing | Return to Visual Identity; it was not consulted |
| Sequence feels flat | Single focal length throughout | Establish a home length; depart at the turn |
| Turn does not land visually | Too many variables changed at once | Change one |
| Subject looks staged | Gaze and hands unspecified | Direct both in every beat |
| Motif appeared unplanned | Improvised rather than declared | Remove, or add to Visual Identity deliberately |

---

## Reports the gap when

- Visual Identity `light` lacks any of its five sub-properties
- A beat requires an environment on the `never` list
- The campaign requires a motif not declared in Visual Identity
- A frame would show construction detail absent from Collection DNA
