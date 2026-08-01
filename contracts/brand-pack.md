# Contract: brand-pack

```yaml
id: brand-pack
version: 1.0.0
status: stable
```

## Purpose

Defines what a valid Brand Pack is. A pack is the complete, machine-readable
representation of one brand — everything an engine needs to generate work that
could only belong to that brand.

This contract is also the pack template. No separate scaffold file exists.

---

## Structure

```
brandpacks/<brand>/
├── pack.yaml       manifest
├── brand/          artifacts (see required artifacts below)
├── campaigns/      campaign instances
├── production/     rendered output
└── assets/         binaries
```

`<brand>` is lowercase kebab-case and matches `pack.yaml → name`.

---

## Manifest fields — `pack.yaml`

| Field | Type | Required | Rule |
|---|---|---|---|
| `name` | string | yes | kebab-case, matches directory name |
| `version` | semver | yes | pack version, independent of system version |
| `status` | enum | yes | `scaffold` · `partial` · `complete` |
| `engines` | list | yes | engine ids this pack enables; may be empty |
| `adapters` | list | yes | adapter ids and per-brand config; may be empty |
| `campaigns` | list | yes | campaign instance ids; may be empty |

`status` is derived, not chosen:

- `scaffold` — no required artifact present
- `partial` — some required artifacts present and conformant
- `complete` — all four required artifacts present and conformant

---

## Required artifacts

A pack is `complete` only when all four exist in `brand/` and conform:

| Artifact | Contract | Supplies |
|---|---|---|
| `brand-voice.md` | `brand-voice` | how the brand speaks |
| `collection-dna.md` | `collection-dna` | what is true and sayable |
| `visual-identity.md` | `visual-identity` | how it looks and is framed |
| `campaign-memory.md` | `campaign-memory` | what has already been made |

`campaign-memory.md` may exist with an empty log; it may not be absent.

---

## Validation rules

1. **Isolation** — a pack contains no core logic. Engines, contracts, adapters
   and archetypes are referenced by id, never copied in.
2. **No upward writes** — nothing in a pack modifies root folders.
3. **Claim closure** — every claim in any pack artifact traces to
   `collection-dna.md`. A pack that asserts what its DNA does not contain is
   non-conformant.
4. **Naming** — artifacts use their contract id as filename. No brand prefix.
5. **Campaign instances** — each references the root archetype id it instantiates.
6. **Assets** — binaries live in `assets/`, never inline or in `brand/`.

---

## Conformance checklist

- [ ] Directory name matches `pack.yaml → name`
- [ ] All six manifest fields present and typed correctly
- [ ] `status` matches actual artifact completeness
- [ ] Four required artifacts present in `brand/` (or status is `scaffold`/`partial`)
- [ ] Each present artifact passes its own contract's checklist
- [ ] No claim in any artifact lacks a Collection DNA source
- [ ] No core logic duplicated inside the pack
- [ ] Every campaign instance names its archetype id

---

## Failure modes

| Symptom | Cause | Resolution |
|---|---|---|
| Engine cannot generate voice-conformant copy | `brand-voice.md` missing or `status: scaffold` | Block; report the gap |
| Claims appear that founders did not authorise | Claim closure violated | Delete claims; do not source retroactively |
| Two packs producing similar work | Voice/DNA under-specified, not a pack-structure fault | Sharpen the differentiating artifacts |
