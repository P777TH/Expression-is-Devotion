<!-- markdownlint-disable-file -->
# Platform Foundation and Options Changes

## Related Plan

`.copilot-tracking/plans/2026-10-16/platform-foundation-and-options-plan.instructions.md`

## Implementation Date

2026-10-16

## Summary

Moved the original ERD HTML viewers to `html/`, organized architecture and
option documentation, defined delivery/stability gates and a build-squad
working agreement, and added the accessible discipleship framework as a
submodule. Superteam remains pending environment read access.

## Added

* `.gitmodules` entry for `projects/racecar-discipleship-framework`
* `.copilot-tracking/changes/2026-10-16/platform-foundation-and-options-changes.md`
* `.copilot-tracking/details/2026-10-16/platform-foundation-and-options-details.md`
* `.copilot-tracking/plans/2026-10-16/platform-foundation-and-options-plan.instructions.md`
* `.copilot-tracking/plans/logs/2026-10-16/platform-foundation-and-options-log.md`
* `.copilot-tracking/research/2026-10-16/platform-architecture-and-stability-research.md`
* `.copilot-tracking/reviews/2026-10-16/platform-foundation-and-options-review.md`
* `docs/architecture/build-squad.md`
* `docs/architecture/business-view.md`
* `docs/architecture/data-model.md`
* `docs/architecture/delivery-roadmap.md`
* `docs/architecture/ontology/README.md`
* `docs/architecture/options/README.md`
* `docs/architecture/options/assembled-platform/README.md`
* `docs/architecture/options/graph/README.md`
* `docs/architecture/options/hybrid/README.md`
* `docs/architecture/options/relational/README.md`
* `docs/architecture/overview.md`
* `docs/architecture/related-projects.md`
* `docs/architecture/technical-view.md`
* `projects/racecar-discipleship-framework` submodule at `47140f3668c97ef96eabdb759fae05fd25ade71b`

## Modified

* `README.md`, linked the architecture views, HTML archive, related projects,
  and squad working agreement.
* `docs/architecture/README.md`, added view navigation, project shape, and
  corrected HTML viewer paths.

## Moved

* `erd_applications_consent_access_v5.html` to `html/`
* `erd_auction_shipping_payments_v4.html` to `html/`
* `erd_content_formats_outreach_v3.html` to `html/`
* `erd_identity_organisations_v5.html` to `html/`

## Blocked

* `trust-fullstop/superteam` could not be fetched or inspected from this
  Codespace. GitHub API returned 404 and Git fetch returned 403. Add it after
  this environment receives repository read access.

## Deviations

* The squad integration is documented as a development-time workflow based on
  the accessible RDCF roster. Superteam's actual instructions/configuration
  remain unreviewed, so no agents or hooks were activated.
* No application framework or vendors were selected; the BRD leaves these open.

## Release Summary

The repository now has stakeholder architecture views, separate options,
phased stability gates, the RDCF submodule, and moved ERD viewers. Actual
Superteam onboarding is the remaining access-dependent step.