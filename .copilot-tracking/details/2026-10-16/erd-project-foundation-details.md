<!-- markdownlint-disable-file -->
# ERD and Project Foundation Details

## Context

* Plan: `.copilot-tracking/plans/2026-10-16/erd-project-foundation-plan.instructions.md`
* Research: `.copilot-tracking/research/2026-10-16/erd-project-foundation-research.md`
* Instructions: HVE Core Markdown, writing-style, and location guidance supplied in the session.

## Phase 3: Implement

1. [x] Copy each Mermaid template literal into a same-domain `.mmd` source under `docs/architecture/erd/` without altering schema semantics.
2. [x] Add a Mermaid module map that identifies domain ownership and shared capabilities.
3. [x] Document the proposed modular-monolith repository layout, staged adoption, and constraints against premature stack selection.
4. [x] Add root README links while preserving its BRD content and status.

## Phase 4: Review

1. [x] Compare each standalone ERD source with its embedded template literal.
2. [x] Run `git diff --check` and inspect changed paths for unrelated edits.
3. [x] Ensure recommendations are labeled as proposals and data-model issues remain open.

## Phase 5: Discover

1. [x] Prioritize legal, finance, and technology decisions using README section 12.
2. [x] Capture ERD reconciliation and implementation scaffolding as follow-up work.