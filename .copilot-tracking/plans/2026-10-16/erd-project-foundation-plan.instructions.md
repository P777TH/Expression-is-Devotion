<!-- markdownlint-disable-file -->
# ERD and Project Foundation Plan

## User Requests

* "anayalsye this tool ... and redraw this diragrams also into mermaid and start to strcture this tooling and project"

## Overview

Make the four Mermaid ERDs embedded in the HTML files available as standalone sources, document their model gaps, and create stack-neutral architecture and project-structure guidance. Avoid changing the model or scaffolding software while foundational product, legal, and technology decisions remain open.

## Context

* Research: `.copilot-tracking/research/2026-10-16/erd-project-foundation-research.md`
* Applicable instructions: HVE Core Markdown and writing-style instructions, plus HVE Core location guidance supplied in the session.
* Existing requirements: `README.md`

## Implementation Checklist

### Phase 1: Research

* [x] Inspect current branch, README, and all four ERDs.
* [x] Identify current-state data model and structural gaps.

### Phase 2: Plan

* [x] Keep the approach stack-neutral and docs-first.

### Phase 3: Implement

* [x] Extract all four embedded Mermaid ERDs to `docs/architecture/erd/`.
* [x] Add platform module overview and proposed repository structure documentation.
* [x] Link architecture material from the root README.

### Phase 4: Review

* [x] Verify the four `.mmd` files preserve their embedded source.
* [x] Check Mermaid source structure and Markdown whitespace.
* [x] Confirm open decisions remain labeled as unresolved.

### Phase 5: Discover

* [x] Identify next high-value work from documented model gaps and build blockers.

## Success Criteria

* [x] ERD source is accessible without opening or executing HTML.
* [x] No unapproved schema changes or stack selections are introduced.
* [x] Initial modular boundaries and project layout are documented as proposals.
* [x] Validation results and remaining decisions are recorded in the review log.