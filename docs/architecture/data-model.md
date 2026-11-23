---
title: Data Model View
description: Current Mermaid ERDs, source-of-truth strategy, domain ownership, and integrity constraints
---

## Current Models

The four ERDs describe identity and organisations, applications and consent,
auction/shipping/payments, and content/outreach. The editable Mermaid sources
are in [`erd/`](erd/); original interactive viewers are in the root
[`html/`](../../html/) folder.

The diagrams are design artifacts, not migrations or a deployed schema. Fields
and relationships marked open must be reconciled with confirmed business rules
before implementation.

## Recommended Data Strategy

Use a relational database as the first-release transactional source of truth.
The current domain relies on stable identifiers, explicit relationships,
constraints, reporting, and coordinated state changes. Keep media binaries in
private object storage and store access-controlled metadata and references in
the database. A graph or RDF store is not required for current workflows.

## Domain Ownership

| Domain | Owns | Existing ERD |
| --- | --- | --- |
| Identity and organisations | Users, profiles, missions, membership, verification, addresses, guardians, key references | [Identity and organisations](erd/identity-organisations.mmd) |
| Applications and governance | Applications, consent, documents, retention, erasure, permissions, approvals, audit | [Applications, consent, and access](erd/applications-consent-access.mmd) |
| Commerce and funds | Artworks, auctions, bids, payment states, shipping, tranches, releases, reports | [Auctions, shipping, and payments](erd/auction-shipping-payments.mmd) |
| Content and outreach | Testimonies, media, post formats, renders, attempts, newsletters, delivery, contact | [Content, formats, and outreach](erd/content-formats-outreach.mmd) |

These are conceptual ownership boundaries. They do not require four databases
or four deployable services.

## Invariants to Enforce

* Each artwork benefits exactly one approved mission; a mission may receive
  funds from many artworks.
* A tranche release must not exceed its eligible amount, must exclude shipping,
  and must be traceable to provider settlement and transfer references.
* Auction readiness and payment-release approvals must be attributable to
  authorized people; the same person cannot approve both sides of a flow.
* Duplicate provider callbacks must not create duplicate payments or releases.
* Consent, restricted document access, permission changes, approvals, and
  erasure exceptions need attributable audit records.
* Private documents and sensitive fields need classification, access controls,
  retention, and deletion behavior.
* A polymorphic owner or target reference must resolve to a valid record; the
  current shape alone does not enforce this relationally.

## Reconciliation Before Migrations

The [model reconciliation backlog](README.md#model-reconciliation-backlog)
identifies missing links and undecided concepts. Prioritize supporter payment
linkage, application-to-artwork linkage, optional organisation on artist
applications, quick donations, mission-owned tranche schedules, testimony
evidence links, and cross-domain integrity. Confirm semantics first, then
revise ERDs and derive migrations from the approved model.