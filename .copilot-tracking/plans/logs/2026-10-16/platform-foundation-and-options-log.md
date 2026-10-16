<!-- markdownlint-disable-file -->
# Platform Foundation and Options Planning Log

## Initial Research Decisions

* Treat the BRD and four Mermaid ERDs as the only current product evidence; no runtime or source-code architecture exists yet.
* Favor a relational transactional source of truth because financial state, approvals, consent, and audit dominate the first-release constraints.
* Evaluate graph, RDF ontology, hybrid projection, document database, and assemble-first separately; do not conflate a vocabulary/ontology with a transactional database.
* Use relative effort bands and milestone gates because team capacity and delivery dates are unknown.
* Treat Superteam as build-time tooling, not runtime software. Use the accessible RDCF roster only as an initial role map pending review of Superteam's own configuration.
* Add the public RDCF repository as a submodule; Superteam remains blocked by HTTP 403/404 access from this Codespace.

## Discrepancies and Limits

* Vendor/legal/platform details are not verified externally. The assessment explicitly assigns these to Phase 1 evidence gathering.
* Existing Mermaid sources remain in their current location to preserve the previous work's links; the original HTML viewers move to `html/` as requested.

## Implementation and Validation Log

* Moved the four HTML ERD viewers under `html/`; kept Mermaid sources at their existing paths.
* Added architecture views, a vocabulary, separated storage/platform option records, a delivery roadmap, and a build-squad working agreement.
* Added `racecar-discipleship-framework` as an independent submodule pinned to `47140f3668c97ef96eabdb759fae05fd25ade71b`.
* Could not add `superteam`: GitHub API returned 404 and `git ls-remote` returned 403 from the current Codespace credential.
* Validation: all local Markdown links resolve, four ERD sources match the moved HTML definitions, `git diff --check` passes, and VS Code reports no Markdown errors.
* `markdownlint` and Mermaid CLI are unavailable; dedicated lint/parser checks could not be run.