<!-- markdownlint-disable-file -->
# Platform Foundation and Options Plan

## User Requests

* Move the existing ERD HTML files into an `html/` folder.
* Structure the project for overview, data model, ontology, business, and technical views.
* Research graph and alternate data/platform solutions in a separate options folder.
* Estimate what must be built and outline delivery phases and stability gates to help Teresa and the owner plan a dependable launch.
* Include the owned Superteam and Racecar Discipleship Framework repositories in this workspace and use the squad to build the product.

## Overview

Restructure the existing documentation and diagram assets; produce evidence-based architecture views, a lightweight ontology, and separate solution-option records; distinguish build, integrate, and unresolved work; and define staged delivery with explicit operational gates. Do not implement application code, select vendors, or present legal conclusions.

## Context

* Research: `.copilot-tracking/research/2026-10-16/platform-architecture-and-stability-research.md`
* Existing requirements: `README.md`
* Existing architecture index: `docs/architecture/README.md`
* Previous local ERD extraction: `.copilot-tracking/research/2026-10-16/erd-project-foundation-research.md`
* Applicable instructions: HVE Core Markdown and writing-style instructions, plus HVE Core location guidance supplied in the session.

## Implementation Checklist

### Phase 1: Research

* [x] Inspect current files, links, requirements, and architecture docs.
* [x] Assess persistence and platform alternatives against the BRD.
* [x] Identify build/integrate effort, decision gates, and stability criteria.

### Phase 2: Plan

* [x] Keep the work documentation-first and vendor-neutral.
* [x] Gate payment implementation on legal and provider feasibility.

### Phase 3: Implement

* [x] Move original HTML diagrams into root `html/` and fix references.
* [x] Separate architecture index, overview, business, data, ontology, and technical views.
* [x] Add a dedicated options folder with relational, graph, hybrid, and assembled-platform alternatives.
* [x] Link the architecture navigation from the BRD and update the proposed project tree.
* [x] Record build/integrate inventory and phased stability gates.
* [x] Add the accessible discipleship repository as an independent submodule and define the build-squad working agreement.
* [ ] Add Superteam as a submodule and review its agent configuration after environment read access is available.

### Phase 4: Review

* [x] Verify moved files and all local links.
* [x] Check Markdown diagnostics and whitespace.
* [x] Confirm tradeoffs, legal caveats, effort bands, and phase gates are explicit.
* [ ] Review Superteam's actual configuration; blocked until read access is granted to this environment.

### Phase 5: Discover

* [x] Identify the next concrete decision or delivery phase for Teresa and the owner.

## Success Criteria

* [x] The HTML viewers live under `html/` with no broken references.
* [x] The architecture folder offers distinct, linked views for overview, business, data, ontology, technical design, and options.
* [x] The relational, graph, hybrid, and assemble-first options are compared fairly without an unsupported vendor decision.
* [x] Build versus integrate work, dependencies, and stable-launch gates are visible to non-technical and technical stakeholders.
* [x] The discipleship framework is included without granting agents product or financial authority.
* [ ] Superteam is added and reviewed after repository read access is available.

## Blocker

GitHub returned 404 through the API and 403 for `git ls-remote` on
`trust-fullstop/superteam`. This environment cannot resolve its commit or inspect
its agent configuration. The user needs to enable read access for the Codespace
Git credential or GitHub App before that submodule step can complete.