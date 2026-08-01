# Taxonomy

Shared vocabulary. Every engine, contract and adapter uses these terms with
exactly these meanings. Ambiguity here becomes incoherence downstream.

---

## System structure

**Foundation** — the invariants. Principles, the definition of premium, the
quality bar, this taxonomy. Depends on nothing; read by everything.

**Contract** — a schema defining what an artifact *is*: required fields,
validation rules, conformance checklist. The system's type system.

**Engine** — a defined, repeatable process. Consumes contract-conformant input,
emits contract-conformant output. Brand-agnostic.

**Adapter** — the boundary that renders an artifact into a target channel.
Introduces no new reasoning, positioning or claims.

**Brand Pack** — a brand implementation. Configuration and instance data.
Depends on the entire core; nothing depends on it.

**Archetype** — a reusable, brand-agnostic campaign shape. Lives at root.
Instantiated inside a Brand Pack.

**Blueprint** — a reusable production specification: how a class of deliverable
is made, its inputs, its standard.

---

## Content units

**Artifact** — any contract-conformant document the system produces. Brand Voice,
Collection DNA, a campaign, a shot list. The unit that gates run against.

**Deliverable** — an artifact rendered by an adapter into a channel format. A
reel, a caption, a page. Artifacts are internal; deliverables ship.

**Beat** — a single unit of time-based narrative. One shot, one moment, one line.
Campaigns are sequences of beats.

**Motif** — a repeated element that accrues recognition: a colour, a gesture, a
framing, a phrase, an hour of day. Motifs are declared in Visual Identity or
Brand Voice, never improvised.

**Tension** — the productive contradiction a campaign is built on. Nameable in
one sentence. Required.

**Claim** — any assertion about a product's material, origin, process or
performance. Every claim requires a source in Collection DNA.

---

## Brand layer

**Brand Voice** — how the brand speaks. Registers, cadence, vocabulary,
prohibitions.

**Collection DNA** — what exists and what is true. Pieces, materials,
construction, palette, provenance, drop structure. The sole source of claims.

**Visual Identity** — how the brand looks and is framed. Palette, light, lens,
composition, motif, typography, grade.

**Campaign Memory** — the record of what has been made: campaigns run, motifs
spent, tensions used, lines already said. Prevents self-repetition and enables
compounding.

---

## Process terms

**Scope** — an agent's write boundary. `core` or `pack`. Never both in one unit
of work.

**Gate** — a pass/fail test from the quality bar. Hard gates block emission; soft
gates are weighted.

**Substitution test** — swap the brand name for a competitor's. If the artifact
survives, it is category-generic and fails.

**Conformance** — an artifact satisfying every required field and validation rule
of its contract.

**Traceability** — every claim resolving to a source in the Brand Pack.

**Emit** — an engine releasing an artifact after gates pass.

**Report the gap** — the required response when an engine lacks input it may not
invent. Not a failure state; the correct behaviour.

---

## Prohibited usages

| Do not use | Use instead | Because |
|---|---|---|
| "Content" | Artifact, or deliverable | Content is undifferentiated by definition |
| "Asset" for a document | Artifact | Assets are binaries in `assets/` |
| "Template" for a contract | Contract | The schema *is* the template |
| "Guidelines" | Contract, or Brand Voice | Guidelines are optional; these are not |
| "Tone of voice" | Register | Voice is the whole; register is the setting |
| "Brand book" | Brand Pack | Brand Pack is machine-readable and scoped |

---

## Naming conventions

- Files and folders: lowercase kebab-case
- Artifacts named for what they are, not what they are about:
  `brand-voice.md`, not `present-clothing-voice-guidelines-v2.md`
- Campaign instances: `<season>-<name>/`, e.g. `aw26-first-light/`
- Versions live in frontmatter, never in filenames
