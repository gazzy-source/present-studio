# campaigns/

Campaign **archetypes** — reusable, brand-agnostic system definitions.

An archetype describes the shape of a campaign: its intent, its structure, the
engines it runs, the artifacts it produces. It names no brand.

**Depends on:** `foundation/`, `contracts/`, `engines/`.

Campaign **instances** — real campaigns for a real brand — live in
`brandpacks/<brand>/campaigns/`. Nothing in this folder may reference a specific
brand.

If it names a brand, it belongs in a brand pack.
