# Blueprint: still-series

```yaml
id: still-series
version: 1.0.0
status: stable
deliverable: photographic series, 3-8 frames
adapter: social-vertical
```

## Purpose

A sequenced set of stills. Carries a campaign where motion is unnecessary or
where the work must survive as individual frames.

Stills are held longer than video and are screenshotted, saved and re-shared. The
bar for individual frame quality is higher than for reels.

---

## Inputs

- `campaign` — beats and frames, already gated
- `visual-identity` — via `visual_source`
- `brand-voice` — via `copy_source`
- `collection-dna` — for any caption claim

---

## Structure

| Property | Spec |
|---|---|
| Frames | 3–8. Five is the default |
| Sequence | Beat order preserved; every frame maps to one campaign beat |
| Turn frame | Must be included. Never cut in compression |
| Rest frames | ≥1 in any series over four frames |
| Caption | One per series, not per frame |

**Every frame must stand alone.** Unlike a reel, frames are encountered
individually. A frame that only works in sequence has failed.

---

## Technical

| Property | Spec |
|---|---|
| Aspect ratio | 4:5 primary, 9:16 for full-bleed placements |
| Resolution | 2000px minimum on the short edge |
| Colour | Rec.709 / sRGB, graded per `visual-identity` |
| Format | JPEG q90 for delivery, TIFF retained as master |
| Text | None burned in. Captions are adapter-supplied |
| Crop | Never crop a master to fit; frame for ratio at capture |

---

## Constraints

1. **No burned-in text.** Frames stay reusable across placements.
2. **No frame is a duplicate angle.** Two frames of the same setup is one frame
   and one offcut.
3. **The rest frame ships.** Empty frames are cut first in review and are the
   most saved in practice. Defend them.
4. **Grade consistency across the series is absolute.** A single frame off-grade
   breaks the set more than a weak composition does.
5. **No product-only frames unless the archetype is `single-piece`.** Isolated
   product shots belong in commerce, not campaign.

---

## Acceptance

- [ ] 3–8 frames, each mapping to a campaign beat
- [ ] Turn frame present
- [ ] ≥1 rest frame if over four frames
- [ ] Every frame stands alone
- [ ] No duplicate angles
- [ ] ≥2000px short edge, correct ratio, no post-crop
- [ ] Grade consistent across the full series
- [ ] No burned-in text
- [ ] One caption for the series, voice-conformant
- [ ] Every caption claim traces to `collection-dna`
