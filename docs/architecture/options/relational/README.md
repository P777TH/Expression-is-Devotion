---
title: Relational-First Option
description: Relational transactional source of truth for the initial platform release
---

## Summary

Use a relational database as the authoritative store for users, missions,
artworks, auctions, payments, tranches, approvals, consent, and audit records.
Keep files in private object storage and external services behind adapters.
Modules may share a database initially while retaining ownership of their
business rules.

## Why It Fits

The BRD centers on linked records, financial state transitions, constraints,
approval policy, auditability, and reporting. Relational transactions and
constraints directly support these needs, and the current ERDs already use
relational entities and keys.

## Costs and Risks

* Cross-module ownership can degrade into a shared-schema tangle unless writes
  follow module interfaces.
* Polymorphic references and application-level constraints need deliberate
  integrity checks.
* The database does not solve provider reconciliation, legal custody, privacy,
  or operational support by itself.

## Recommendation

Preferred for Release 1, subject to legal/provider feasibility, residency
review, and a recorded stack decision. Do not infer a specific database vendor
from the current ERD notation.