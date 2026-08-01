# brandpacks/

Brand implementations. The application layer.

A brand pack is **configuration plus instance data**. It never contains core
logic. It may read the entire core; it may not write to it.

```
brandpacks/<brand>/
├── pack.yaml       manifest: identity, version, engines enabled, adapter config
├── brand/          resolved brand artifacts (contract instances)
├── campaigns/      instances of root campaign archetypes
├── production/     output rendered from production blueprints
└── assets/         binaries owned by this brand
```

**Depends on:** the entire core.
**Depended upon by:** nothing.

There is no pack template. `contracts/` defines what a valid brand pack is — the
schema is the template.

If brand work reveals a needed core change, raise it. Do not inline a
brand-specific exception into a core file.

## Packs

- `present-clothing/` — scaffold only. No brand content authored.
