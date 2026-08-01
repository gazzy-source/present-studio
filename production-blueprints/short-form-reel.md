# Blueprint: short-form-reel

```yaml
id: short-form-reel
version: 1.0.0
status: stable
deliverable: vertical short-form video, 8-15s
adapter: social-vertical
```

## Purpose

The system's highest-volume deliverable. Vertical short-form video for social
feeds.

Optimised for repeatable production at volume without degrading into template
output — the distinction being that structure repeats while content, motif and
tension do not.

---

## Inputs

By contract id. Never by brand.

- `campaign` — beats and frames, already gated
- `visual-identity` — via `visual_source`
- `brand-voice` — via `copy_source`
- `collection-dna` — for any on-screen product claim

**Not restated here.** This blueprint references identity and voice; it never
inlines them.

---

## Structure

| Property | Spec |
|---|---|
| Beats | 4–6. Five is the default |
| Beat duration | 1.5–3.0s. Rest beats may reach 4.0s |
| Total duration | 8–15s. Target 11s |
| Turn position | Beat 4 of 5, or beat 3 of 4 |
| Opening | First 0.8s must carry the frame's strongest visual information |
| Copy beats | Maximum 2 |
| Silent beats | Minimum 2 |

**Archetype compression.** Archetypes longer than 6 beats compress by cutting
`escalate` beats first, never `rest` or `turn`:

| Archetype | Native | Compressed to |
|---|---|---|
| `single-piece` | 5 | 5 — no compression |
| `world-building` | 4 | 4 — no compression |
| `process` | 5 | 5 — no compression |
| `collection-launch` | 7 | 5 — cut beats 2 and 5 |
| `manifesto` | 6 | 4 — cut beats 2 and 4; never cut 3 |

---

## Technical

| Property | Spec |
|---|---|
| Aspect ratio | 9:16 |
| Resolution | 1080 × 1920 minimum, 2160 × 3840 preferred |
| Frame rate | 24fps capture and delivery |
| Duration tolerance | ±0.5s of target |
| Audio | Designed for silent playback. Any audio is atmospheric, never voiceover |
| Text safe area | Inset 12% top, 20% bottom, 8% sides |
| Text placement | Never over a subject's face; never in the bottom 20% |
| Colour | Rec.709, graded per `visual-identity` |
| Export | H.264, ≥12 Mbps, no platform-applied filters |

**24fps, not 30 or 60.** Frame rate is an identity decision, not a technical
default — 24 reads cinematic, 60 reads as capture.

---

## Constraints

1. **No text in the first beat.** The opening frame carries image alone.
2. **No music-driven cutting.** Cuts follow beat function, not a track. Music-led
   edits produce interchangeable output.
3. **No platform-native effects.** No auto-captions, stickers, transitions, or
   trending audio. These date the work and belong to the platform, not the brand.
4. **No logo bumper.** If the work needs a logo to be identifiable, the visual
   identity has failed (`principles.md` — consistency compounds).
5. **Silent-first.** The reel must work with sound off. Audio adds; it never
   carries.
6. **One idea.** A reel carrying two ideas is two reels.

---

## Acceptance

Objectively checkable by a producer without the brand team.

- [ ] Duration within 8–15s, target 11s ±0.5s
- [ ] 4–6 beats, each within duration bounds
- [ ] Exactly one turn beat, correctly positioned
- [ ] ≥2 silent beats, ≤2 copy beats
- [ ] No text in beat 1
- [ ] Text within safe areas, never over a face
- [ ] 9:16, ≥1080×1920, 24fps
- [ ] Comprehensible with sound off
- [ ] No platform-native effects, no logo bumper
- [ ] Grade matches `visual-identity`
- [ ] Every on-screen claim traces to `collection-dna`

---

## Volume production

For batch generation, vary in this order — first variable produces the most
differentiation per unit of effort:

1. **Tension** — different contradiction, different reel
2. **Archetype** — different shape
3. **Piece** — different subject
4. **Environment** — different world fragment
5. **Hour** — different light within the identity

Varying only 4 and 5 produces a set that reads as one reel recut. Every batch
should span at least two archetypes and three tensions.

Log every produced reel's tension and motifs to `campaign-memory`. At volume,
memory is the only thing preventing convergence.
