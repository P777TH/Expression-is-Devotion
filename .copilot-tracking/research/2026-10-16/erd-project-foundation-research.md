<!-- markdownlint-disable-file -->
# ERD and Project Foundation Research

## Request and scope

Analyze the existing project and ERD tooling, make the diagrams available as Mermaid source, and establish an initial project structure. The product technology stack is explicitly undecided, so recommendations must remain stack-neutral.

## Evidence

* `README.md` is the current business requirements document. It defines release 1, modularity requirements, a staged funding workflow, and 52 open decisions.
* Four root-level HTML files contain Mermaid `erDiagram` source inside JavaScript template literals and render it through Mermaid 11 from a remote ESM URL.
* The diagrams cover identity and organisations, applications and consent, auction and payments, and content and outreach.
* No application source, test suite, package manifest, or project tooling is present on this branch.
* The README says the stack is only suggested, and lists legal and payment-provider decisions as high-priority open items.

## Findings

* The current ERDs are already Mermaid, but the source is embedded in large interactive HTML documents. Standalone `.mmd` files make the data models reviewable and versionable without duplicating the renderer or HTML styling.
* Some fields named as missing in README open item 42 already exist, but their relationships are not drawn: `PAYMENT.supporter_id`, `SHIPPING_RATE.artist_id`, `CONTACT_REQUEST.artwork_id`, and `POST_ATTEMPT.render_id`.
* The payment ERD has no supporter-to-payment relationship line, and the bid line targets `USER` although the bid field is `supporter_id`.
* The requirements identify model changes that are not in the diagrams: quick donations, mission-owned tranche schedules, testimony-linked tranche evidence, artist-application-to-artwork linkage, and optional organisation on artist applications.
* The diagrams contain polymorphic owner/target references and application-level constraints. Those need explicit application/database integrity rules before implementation.

## Selected approach

Extract each embedded ERD without schema edits into `docs/architecture/erd/*.mmd`. Document current omissions separately from the source diagrams so proposed decisions are not presented as accepted schema. Recommend a modular-monolith boundary map and a staged repository layout, but do not scaffold a framework or choose vendors while those decisions remain open.

## Success criteria

* Four standalone Mermaid ERD sources are available and retain the current entities, attributes, and relationship lines.
* A fifth Mermaid diagram communicates the proposed platform module boundaries.
* Project structure guidance separates current artifacts from proposed directories and identifies unresolved decisions that block code scaffolding.
* README links the architecture materials; whitespace and source-consistency checks pass.