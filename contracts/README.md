# contracts/

The type system. One schema per artifact.

A contract defines what an artifact *is* — its required structure, its fields,
what makes it valid. Engines declare which contracts they consume and which they
emit. Adapters render contract-conformant artifacts.

**Depends on:** `foundation/`.
**Read by:** `engines/`, `adapters/`, `brandpacks/`.

This is the highest-leverage folder in the repository. Contracts are what make
output machine-verifiable rather than subjectively assessed, and what make
engines composable.

The schema is also the template — `contracts/` defines the shape of a valid brand
pack. Do not create parallel template files.
