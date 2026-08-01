# Present Clothing — Visual Identity

```yaml
contract: visual-identity
version: 0.1.0
status: proposed
```

> **Status: PROPOSED.** No references, existing imagery or art direction were
> supplied. Derived from the world in `brand-bible.md`. This is the artifact most
> improved by founder reference images — supply five and it can be made exact.

---

## Palette

| Name | Value | Role |
|---|---|---|
| Wet concrete | `#6E6E68` | Dominant |
| Raw | `#C9C2B4` | Dominant |
| Salt | `#E8E4DC` | Support |
| Westerly | `#4A5257` | Support |
| Dry black | `#1C1C1A` | Support |
| Dye lot | `#8A6F52` | Accent — one frame per campaign, never more |

Muted, desaturated, no pure white and no pure black. Colours match
`collection-dna` palette names where they overlap.

---

## Light

**The most identity-carrying field. All five properties bind.**

| Property | Spec |
|---|---|
| Quality | Diffuse, overcast. No hard sun, no visible sun disc |
| Direction | Broad top-side, from a large soft source — window or sky |
| Hour | The two hours after dawn, or the hour before rain |
| Source | Natural only. Practicals permitted if visible in frame |
| Shadow | Soft, long, low contrast. Shadow detail always retained |

**Never:** golden hour, direct sun, flash, coloured gels, studio key light,
backlight flare.

Overcast is not a compromise for lack of sun. It is the brand's weather.

---

## Lens

| Property | Spec |
|---|---|
| Home length | 50mm |
| Range | 35mm–85mm |
| Departure | Move to 85mm at the turn, or 35mm for `establish` |
| Aperture | f/2.8–f/5.6. Depth retained; no extreme separation |
| Distance | Middle distance. Neither intimate nor surveillance |

**Reasoning:** 50mm is the observational length — it neither flatters nor
distorts. The brand does not sell aspiration, so it does not use the wide-close
intimacy that lifestyle brands rely on. Bokeh-heavy separation reads as
commercial product photography and is out.

---

## Composition

- Subject placed off-centre, weighted toward the frame edge
- Negative space is the dominant element — target 60% empty
- Horizon low, or absent entirely
- Architecture squared to frame. No dutch angles
- Full-length or waist-up. Rarely tight portrait
- The garment is never centred as a specimen

---

## Motion

For time-based work.

| Property | Spec |
|---|---|
| Camera | Locked off by default. Handheld only where a beat justifies it |
| Movement | If moving: slow, single-axis, no more than one move per beat |
| Pace | Slow. Beat durations 1.5–3.0s; rest beats to 4.0s |
| Cut rhythm | Cut on stillness, not on action |
| Frame rate | 24fps. Never 60, never slow-motion |

**No slow motion.** It is the most common apparel-video signal and reads as
performance. Real time reads as presence.

---

## Grade

| Property | Spec |
|---|---|
| Contrast | Low. Lifted blacks, no crushing |
| Black level | Lifted to ~8% — never true black |
| Highlights | Rolled off. No clipping |
| Saturation | Reduced ~15% from capture |
| Cast | Slight cool-green in shadow. Warmth only in the `dye lot` accent |
| Grain | Fine grain retained. Not clean-digital |

---

## Motifs

Five. Declared here, tracked in `campaign-memory`, never improvised.

1. **Weather arriving** — wind in fabric, the first rain, cloud moving in
2. **The hand on the seam** — a hand finding a construction detail unprompted
3. **The empty garment** — hung, folded or draped, no wearer, holding its shape
4. **Wet stone** — concrete, pavement or rock, darkened by rain
5. **The turned back** — subject facing away, gaze withheld from camera

---

## Environments

**Used:** working buildings, unheated rooms with large windows, coastal
industrial edges, concrete stairwells, harbour walls, unstyled domestic interiors
in winter light, empty streets before traffic.

**Never:** styled apartments, studios with visible seamless, restaurants and
bars, sunshine, resorts, gyms, nightlife, anything warm-toned, anything with
visible crowds, anything after dark.

The exclusion list binds absolutely. A campaign requiring a `never` environment
reports the gap.

---

## Subject direction

| Property | Spec |
|---|---|
| Posture | Settled. Standing still, sitting, leaning. Weight on both feet |
| Gaze | **Away by default.** To camera only at the turn, and rarely |
| Expression | Neutral to unaware. No smiling. No performed intensity |
| Hands | Occupied — in pockets, holding something, on a surface. Never idle |
| Movement | Real actions with a purpose. No walking toward camera |
| Casting | Range of ages. Faces that look weathered rather than styled |

**Gaze policy is the single strongest differentiator** available. Away-gaze reads
as observation; to-camera reads as advertising. Changing it at the turn is the
most reliable move in the system.

---

## Typography

| Property | Spec |
|---|---|
| Face | Single grotesque, neutral. One family only |
| Weights | Regular and medium. No bold, no light |
| Case | Sentence case. Never all-caps, never title case |
| Size | Small. Text never dominates a frame |
| Spacing | Generous leading. Default tracking |
| Alignment | Left, always. No centring |
| Placement | Lower-left, within safe area. Never over a face |

---

## Prohibitions

Absolute. Any occurrence fails G5.

1. No direct sun or golden hour
2. No slow motion
3. No lens flare, bokeh balls, or shallow-depth product separation
4. No smiling to camera
5. No pure white or pure black in the grade
6. No dutch angles or handheld shake as style
7. No text over a face
8. No visible logo treatment as a frame element
9. No warm colour grading
10. No environment from the `never` list

---

## Conformance

- [x] All eleven required fields present
- [x] `light` complete across five sub-properties
- [x] `lens` gives range and reasoning
- [x] 5 motifs, each concrete
- [x] `environments` includes explicit exclusions
- [x] `subject_direction` states gaze policy
- [x] `motion` present
- [x] Every field executable without interpretation
- [x] Breaks under substitution
- [x] No product claims present

**Gap:** palette hex values are proposed, not sampled from real product. Confirm
against actual fabric before production use.
