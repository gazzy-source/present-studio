# Contract: campaign-memory

```yaml
id: campaign-memory
version: 1.0.0
status: stable
```

## Purpose

The record of what a brand has already made. Prevents self-repetition and makes
consistency compound (principle 7).

Without memory, a generative system produces work that is individually
acceptable and collectively incoherent — the same three ideas rediscovered every
quarter, motifs that never accumulate meaning, lines said twice.

Required in every Brand Pack. May be empty; may not be absent.

---

## Required sections

### `campaigns`

One entry per campaign that reached status `produced`.

| Field | Type | Rule |
|---|---|---|
| `id` | string | Campaign id |
| `season` | string | |
| `tension` | 1 sentence | Copied verbatim from the campaign |
| `spine` | 1 sentence | The narrative shape in brief |
| `pieces` | list | Pieces featured |
| `outcome` | string / null | What was learned. Null until reviewed |

### `motifs`

Tracks accumulation. A motif gains meaning through repetition and loses force
through overuse.

| Field | Type | Rule |
|---|---|---|
| `motif` | string | Must resolve to Visual Identity |
| `uses` | integer | Times deployed |
| `last_used` | string | Campaign id |
| `state` | enum | `establishing` (1–2) · `established` (3–6) · `saturated` (7+) |

### `spent`

Things that must not be reused without deliberate variation.

| Field | Type | Rule |
|---|---|---|
| `tensions` | list | Every tension used, with campaign id |
| `lines` | list | Memorable copy already said |
| `environments` | list | Settings already used, with campaign id |
| `openings` | list | How campaigns have begun |

---

## Validation rules

1. **Write-on-produce** — an entry is written when a campaign reaches `produced`,
   not at brief. Memory records what happened, not what was planned.
2. **Verbatim tension** — copied exactly, not paraphrased. Paraphrase defeats
   repetition detection.
3. **Motif resolution** — every motif resolves to Visual Identity. Memory never
   introduces new motifs.
4. **Saturation blocking** — a motif at `saturated` may not anchor a new
   campaign. It may appear incidentally.
5. **Append-only** — entries are never edited or deleted, only appended and
   annotated. Rewriting memory to permit a reuse defeats the contract.
6. **Consulted before briefing** — checked at brief time. Checking after
   drafting means discovering repetition too late to act cheaply.

---

## Conformance checklist

- [ ] All three sections present (may be empty)
- [ ] Every produced campaign has an entry
- [ ] Tensions recorded verbatim
- [ ] Every motif resolves to Visual Identity
- [ ] Motif `state` matches `uses` count
- [ ] No entry edited or removed since creation
- [ ] Spent lists cover tensions, lines, environments and openings

---

## How engines use this

The Campaign Engine reads memory **before** generating a brief and refuses to
anchor on a spent tension or saturated motif.

Repetition is not always failure — deliberate return to a motif is how brand
language forms. The contract distinguishes deliberate return, which is declared,
from accidental repetition, which is not.
