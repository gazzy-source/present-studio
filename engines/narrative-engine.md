# Engine: narrative-engine

```yaml
id: narrative-engine
version: 1.0.0
status: stable
input:  [brand-voice, collection-dna, campaign-memory]
output: campaign (beats and copy)
```

## Purpose

Turns a collection and a tension into a narrative spine and its copy.

This engine decides **what happens and what is said**. It does not decide what
the camera sees — that is the Cinematic Language Engine — and it does not decide
what gets made — that is the Campaign Engine.

---

## Process

### 1. Load constraints before generating

Read in order: `foundation/`, `brand-voice`, `collection-dna`, `campaign-memory`.

Voice loaded **after** generation produces generic copy with vocabulary swapped
in. This is the single most common failure in the system (principle 9).

### 2. Establish the tension

Take the campaign tension, or derive it from Collection DNA `tension`.

A valid tension is a contradiction that is **true of the collection**, not a
clever phrase. Test it: state both halves. If one half is obviously
uninteresting, it is not a tension — it is a claim with decoration.

Check `campaign-memory.spent.tensions`. A spent tension may be returned to only
deliberately and declared as such.

### 3. Find the spine

The spine is one sentence describing what changes between the first beat and the
last. If nothing changes, there is no spine and the output will be a montage.

The spine is not the tension. The tension is the contradiction; the spine is the
movement through it.

### 4. Place the turn

Before writing any beat, decide where the turn falls — the beat where the tension
resolves, inverts, or is revealed to have been something else.

The turn is the campaign. Everything before it is setup; everything after is
consequence. Placing it late (roughly two-thirds through) is the default; placing
it first is a deliberate, harder move.

### 5. Build the beat sequence

Assign each beat a function: `establish`, `escalate`, `turn`, `rest`, `close`.

Constraints from the `campaign` contract:
- Exactly one `turn`
- ≥1 `rest` if over four beats
- `close` never restates `establish`

Write functions before writing content. Beats written content-first drift into
uniform escalation.

### 6. Write copy — sparingly

Not every beat carries copy. Decide **which beats are silent first**, then write
only the rest.

Copy is written in the selected register, at the specified cadence, using owned
vocabulary. Every product claim traces to Collection DNA.

### 7. Gate

Run the quality bar. Hard gates G1–G5, soft gates ≥4 of 6. Revise by subtraction.

---

## Heuristics

**Cut the first beat.** First beats are almost always throat-clearing. The
campaign usually starts at what was beat two.

**The best line is often the one you would cut for time.** Under pressure, writers
keep explanatory lines and cut atmospheric ones. Invert this.

**Name the thing, not the feeling.** "The coat holds the shape of yesterday" beats
"you'll feel confident" — one is an image, the other an instruction (principle 3).

**Silence carries the turn.** The turn beat frequently works better with no copy.
The image does the work; a line explains what the audience just understood.

**One idea per beat.** A beat carrying two ideas is two beats compressed.

**Specificity rises toward the turn.** Open wide and atmospheric; get concrete as
you approach the turn. Reversing this defuses the campaign.

**If the copy survives substitution, delete it.** Category-generic lines feel safe
because they are — they belong to nobody (G3).

---

## Failure modes

| Symptom | Cause | Fix |
|---|---|---|
| Reads as a product montage | No spine; nothing changes | Return to step 3. Not fixable in copy |
| Every beat same weight | No rest beats; uniform escalation | Insert silence |
| Copy is well-written but anonymous | Voice applied as post-filter | Regenerate with voice loaded first |
| Turn lands flat | Turn was explained by copy | Remove the line; let the image turn |
| Feels like the last campaign | Memory not consulted at brief | Check `spent` before step 2, not after |
| Claims appear that DNA lacks | Generated before loading DNA | Block. Never source retroactively |

---

## Reports the gap when

- The collection has no nameable tension
- A needed fact is `unverified` in Collection DNA
- Brand Voice has fewer than three calibration pairs (insufficient to match voice)
- Every candidate tension is `spent` and no variation is authorised

Reporting is correct behaviour, not failure (`foundation/taxonomy.md`).
