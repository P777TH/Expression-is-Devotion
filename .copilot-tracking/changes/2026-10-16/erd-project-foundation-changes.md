<!-- markdownlint-disable-file -->
# ERD and Project Foundation Changes

## Related Plan

`.copilot-tracking/plans/2026-10-16/erd-project-foundation-plan.instructions.md`

## Implementation Date

2026-10-16

## Summary

Extracted the current Mermaid ERD definitions into reviewable source files,
documented a proposed stack-neutral modular architecture and project layout,
and linked the architecture guide from the business requirements document.

## Added

* `.copilot-tracking/changes/2026-10-16/erd-project-foundation-changes.md`
* `.copilot-tracking/details/2026-10-16/erd-project-foundation-details.md`
* `.copilot-tracking/plans/2026-10-16/erd-project-foundation-plan.instructions.md`
* `.copilot-tracking/plans/logs/2026-10-16/erd-project-foundation-log.md`
* `.copilot-tracking/research/2026-10-16/erd-project-foundation-research.md`
* `.copilot-tracking/reviews/2026-10-16/erd-project-foundation-plan-review.md`
* `docs/architecture/README.md`
* `docs/architecture/erd/applications-consent-access.mmd`
* `docs/architecture/erd/auction-shipping-payments.mmd`
* `docs/architecture/erd/content-formats-outreach.mmd`
* `docs/architecture/erd/identity-organisations.mmd`

## Modified

* `README.md`, added required front matter and architecture links.

## Removed

* None.

## Deviations

* No application framework, dependencies, or code directories were scaffolded because the BRD marks the build approach and technology stack as undecided.
* Existing model gaps were documented, not silently fixed in the extracted ERDs.

## Release Summary

Four extracted ERDs and one platform-boundary flowchart are available as
Mermaid. The structure proposal remains stack-neutral pending product,
financial, legal, and technology decisions.