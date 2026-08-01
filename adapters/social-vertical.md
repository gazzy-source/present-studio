# Adapter: social-vertical

```yaml
id: social-vertical
version: 1.0.0
status: stable
input:  [campaign, production-blueprint]
output: channel-ready deliverables
```

## Purpose

Renders campaign artifacts into vertical social placements — feed video, stories,
and the caption that accompanies them.

**This adapter introduces no reasoning.** It does not decide what the brand
thinks, invent claims, or alter positioning. It formats what the engines produced
(`adapters/README.md`).

---

## Renders

| Deliverable | Blueprint | Ratio |
|---|---|---|
| Feed reel | `short-form-reel` | 9:16 |
| Story sequence | `short-form-reel` | 9:16, split to ≤7s segments |
| Feed stills | `still-series` | 4:5 |
| Story stills | `still-series` | 9:16 |

---

## Caption generation

The only text this adapter originates. Rules:

1. **Voice register** — product register for `single-piece` and `process`;
   atmospheric for `world-building`; narrative for `collection-launch` and
   `manifesto`.
2. **Length** — one to three lines. Never a paragraph.
3. **No restatement.** The caption never describes what the frame already shows.
   It adds an adjacent fact or says nothing.
4. **Claims trace to `collection-dna`** (G1), including material, price and
   availability.
5. **No calls to action phrased as pressure** (`premium.md` anti-signals). "Now
   available" is permitted. "Don't miss out" is not.
6. **Hashtags** — none, or a single owned brand tag. Discovery tags are a
   different business decision and are not the adapter's to make.
7. **A blank caption is valid output** and is often correct for `world-building`.

---

## Platform handling

| Concern | Rule |
|---|---|
| Auto-captions | Disabled. Platform-styled text overrides brand typography |
| Trending audio | Never. Dates the work and borrows another brand's world |
| Platform filters | Never. The grade is set in `visual-identity` |
| Cover frame | Selected from campaign beats — never an auto-generated thumbnail |
| Aspect enforcement | Deliver native. Never letterbox or platform-crop |
| Compression | Deliver above platform requirement; assume one re-encode |

---

## Constraints

1. **No new claims.** If a placement seems to need a fact the campaign lacks,
   report the gap — do not supply it.
2. **No visual override.** Platform convention never outranks Visual Identity.
   If a placement cannot honour the identity, that placement is not used.
3. **No campaign restructuring.** Compression follows the blueprint's rules; the
   adapter does not reorder or add beats.
4. **No per-platform tone shift.** One voice across placements. Register may
   change; voice may not.

---

## Acceptance

- [ ] Every deliverable conforms to its blueprint's acceptance list
- [ ] Captions voice-conformant, ≤3 lines, claims traced
- [ ] No platform-native effects, filters or auto-captions applied
- [ ] Cover frame selected from campaign beats
- [ ] Native aspect ratio, no letterboxing
- [ ] No claim present that the campaign did not carry
