# FX NEXUS

A modular product-data and marketplace workflow platform built from a real
operational need.

FX NEXUS started as a practical parts matcher for a motor-parts wholesaler.
The first version was a single Python program focused on matching catalogue
numbers, manufacturers and marketplace products. As the workflow grew, the
project was gradually split into independent modules for identity, enrichment,
research, storage, marketplace integrations and offer preparation.

That evolution is still visible in the codebase. The project deliberately keeps
old boundaries and recovery notes where they explain why the current
architecture looks the way it does.

## What it does

FX NEXUS currently covers several connected areas:

- product import from tabular sources,
- manufacturer, MPN, GTIN and reference identity,
- catalogue matching with explicit confidence and conflict states,
- evidence-first product enrichment,
- manufacturer catalogue and web research,
- resumable long-running collection jobs,
- local SQLite-backed working state,
- pricing and inventory separation,
- marketplace integrations behind replaceable adapters,
- offer preparation and controlled publication planning,
- profile-scoped configuration and data,
- Linux-first development and runtime tooling.

The project is intentionally conservative around identity. A plausible match is
not automatically treated as truth. Raw observations, provenance, conflicts and
candidate values are preserved so that important decisions can be reviewed.

## Design approach

A recurring design rule in FX NEXUS is what I call the **USB approach**:
providers and capabilities should plug into explicit ports instead of becoming
hard-wired into the core.

That means, for example, that a marketplace, research source or storage backend
can be replaced without rewriting the whole application.

Another rule is:

> **wide harvest, strict promotion**

Research can collect broadly, but only well-supported information should become
canonical product data.

## Project history

The earliest working ancestor was a monolithic parts matcher. It already dealt
with messy warehouse descriptions, manufacturer normalization, MPN overrides
and catalogue ambiguity.

From there the project evolved through:

1. matcher and parser separation,
2. reusable product identity,
3. modular workflows,
4. profile-scoped data,
5. provider adapters,
6. evidence and provenance,
7. resumable research and enrichment,
8. controlled offer preparation.

Some historical material is intentionally retained because this project also
serves as a record of how a production-oriented tool grows from a useful script
into a larger modular system.

## Privacy

This public repository is intended to contain only sanitized source code,
architecture and synthetic or anonymized examples.

The real business that originally motivated the project is represented only as
an anonymous motor-parts wholesaler. Production databases, credentials,
customer or supplier identities, infrastructure details and private operational
data are not part of the public project.

## Status

Active development.

The public repository is a portfolio and source-available representation of the
project. Private operational data and sensitive deployment material remain
outside it.

## Author

Created and maintained by **FenixMint**.

## License

FX NEXUS is source-available under the **PolyForm Shield License 1.0.0**.

The license permits use, modification and distribution for permitted purposes,
but does not permit using the software to provide a product that competes with
the licensor.

See [LICENSE](LICENSE) and [NOTICE](NOTICE).
