# engines/

The logic of the system. The unit of work.

An engine is a transform: it consumes contract-conformant input, applies a
defined and repeatable process, and emits contract-conformant output.

**Depends on:** `foundation/`, `contracts/`.
**Read by:** `adapters/`, `brandpacks/`.

Rules:

- An engine must declare its input contract and its output contract.
- An engine emits **artifacts**, never channel-formatted deliverables. Formatting
  belongs to `adapters/`.
- Engines are brand-agnostic. Brand-specific behaviour is supplied as
  configuration from a brand pack, never hardcoded here.

One engine per file. Adding a process costs one file.
