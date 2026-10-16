<!-- markdownlint-disable-file -->
# Platform Foundation and Options Details

## Context

* Plan: `.copilot-tracking/plans/2026-10-16/platform-foundation-and-options-plan.instructions.md`
* Research: `.copilot-tracking/research/2026-10-16/platform-architecture-and-stability-research.md`
* Previous work: `.copilot-tracking/changes/2026-10-16/erd-project-foundation-changes.md`

## Phase 3: Implement

1. [x] Move the four tracked root HTML viewers to `html/` with `git mv` and update architecture links.
2. [x] Keep existing `.mmd` paths stable; organize them under the data-model view by documentation links rather than unnecessary renames.
3. [x] Add overview, business, data-model, ontology, and technical-view documents under `docs/architecture/`.
4. [x] Add `docs/architecture/options/` with a comparison index and separate records for relational-first, graph-first, hybrid, and assemble-first options.
5. [x] Update the architecture index and BRD links, and ensure the proposed repository tree reflects current and future folders.
6. [x] Capture build/integrate estimates, phase dependencies, go/no-go gates, and operational stability definition.
7. [x] Add the accessible discipleship framework as an independent submodule and document Superteam's intended build role and required human controls.
8. [ ] Add Superteam as a submodule and inspect its configuration after Codespace read access is granted. Blocked by GitHub 403/404.

## Phase 4: Review

1. [x] Confirm the original HTML files exist under `html/` and old paths no longer appear in Markdown.
2. [x] Check relative links, `git diff --check`, Markdown diagnostics, and source file status.
3. [x] Verify that graph and alternate platform choices are evaluated separately from the recommended relational transactional core.
4. [x] Preserve the legal/provider limitations and avoid presenting estimates as calendar commitments.
5. [ ] Review Superteam's own configuration after read access is granted.

## Phase 5: Discover

1. [x] Prioritize enabling Superteam read access so the intended squad can be onboarded safely.
2. [x] Keep legal/finance feasibility as the first product delivery gate.