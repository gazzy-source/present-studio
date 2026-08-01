# adapters/

The I/O boundary. Artifact in, channel-ready output out.

An adapter renders an existing artifact into a target format — deck, site copy,
social, long-form, print.

**Depends on:** `foundation/`, `contracts/`, `engines/`.
**Read by:** `brandpacks/`.

Rules:

- An adapter must not introduce new brand reasoning, new positioning or new
  claims. If it is deciding what the brand thinks, that work belongs upstream in
  an engine.
- Adapters are brand-agnostic. Per-brand adapter settings live in `pack.yaml`.

Keeping this layer separate is what stops channel formatting from leaking into
brand reasoning. Adding a channel costs one file.
