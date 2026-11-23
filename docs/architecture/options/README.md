---
title: Architecture Options
description: Comparison of relational, graph, hybrid, and assembled-platform approaches
---

## Decision Summary

The current recommendation is a relational transactional source of truth in a
modular application, with managed providers for payments, email, storage,
identity primitives, and monitoring where they meet legal and operational
requirements. This recommendation is based on the current BRD, not vendor
due diligence.

| Option | Meaning | Fit now | Main cost | Details |
| --- | --- | --- | --- | --- |
| Relational-first | Relational transactions are authoritative; media is in private object storage | Strong | Schema design and migrations | [Relational option](relational/README.md) |
| Graph-first | Property graph is the primary domain store | Weak for current payment/approval authority; useful for exploration | Transaction, access, reporting, and operations validation | [Graph option](graph/README.md) |
| Relational plus graph | Relational source publishes a graph projection | Not needed for launch; possible later | Projection lag, reconciliation, privacy propagation, extra operations | [Hybrid option](hybrid/README.md) |
| Assemble-first | Existing SaaS/no-code products supply selected capabilities | Worth capability-level evaluation | Product fit, custody, portability, cross-system controls | [Assembled-platform option](assembled-platform/README.md) |

RDF/OWL is a semantic interoperability option, not a substitute for the
transactional database. A document database is not the leading primary-store
choice for current payment, approval, and audit needs. The
[ontology](../ontology/README.md) starts as a governed vocabulary without
requiring either technology.

## Decision Sequence

1. Resolve legal and finance feasibility for holding, classifying, and paying
   out funds.
2. Compare providers and assembly options against the approved workflow, EU
   residency, data portability, and total operating cost.
3. Choose a relational source of truth and module boundaries unless new
   requirements materially change the evidence.
4. Revisit graph/RDF only for a funded need for multi-hop discovery, semantic
   exchange, or network analysis that relational queries cannot meet at
   acceptable complexity or performance.

## Evaluation Questions

* Can it represent sale, direct gift, provider settlement, separate shipping,
  tranche release, refund, and chargeback without ambiguous balances?
* Can it enforce approval separation, per-action authorization, consent,
  retention, and restricted-document audit?
* Does it support eligible countries, reliable reconciliation, and export if a
  provider changes?
* Who owns upgrades, backups, restoration tests, security response, and support?
* What is the full implementation, operation, legal review, and exit cost?