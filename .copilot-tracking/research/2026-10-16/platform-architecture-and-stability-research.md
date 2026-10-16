<!-- markdownlint-disable-file -->
# Platform Architecture and Stability Research

## Request and Scope

Structure the project for clear overview, business, data, ontology, and technical views; move the original ERD HTML files into `html/`; compare relational, graph, and other solution models; estimate what must be built versus integrated; and define phases and stability gates that Teresa and the project owner can use to reach a dependable launch.

This is an evidence-led architecture assessment from the current repository and BRD. It is not legal advice, provider due diligence, or a vendor selection.

## Current-State Evidence

* The branch contains a business requirements document, four interactive ERD HTML files, and four standalone Mermaid ERD sources. It has no application source, dependencies, CI, test suite, deployment configuration, or operational runbooks.
* Each HTML viewer embeds its Mermaid source and imports Mermaid 11 from `esm.sh` at runtime. The HTML is a diagram viewer, not an application or a database definition.
* The BRD states that the stack is undecided. Its candidate stack is Next.js, EU-hosted Vercel, Supabase with EU data residency, and Stripe Connect.
* The first release includes applications and vetting, public pages and role portals, art auctions, quick donations, staged mission payouts, approval separation, testimonies, social publishing, and newsletters.
* Payment custody, legal classification of auction proceeds, tax/VAT treatment, payout provider capability, tranche pooling, quick-donation rules, two-approver threshold, build-versus-assemble, and launch stack remain open or proposed.
* Money movements, approval chains, consent, audit history, identity, and retention are explicit. The model has foreign-key-like links, state transitions, uniqueness, and cross-record constraints.

## Falsifiable Hypothesis

Use a relational transactional source of truth for the first release. Keep the ontology as a separate business vocabulary and treat property graph or RDF storage as optional later capabilities. This hypothesis would be weakened by a confirmed requirement for graph-native traversal as a core transaction path or an external semantic interoperability contract. Neither appears in the BRD today.

Cheap discriminating check: trace payment, tranche, approval, consent, and audit requirements. They require transactional integrity and explainable record history; the BRD does not identify graph-only queries or an RDF exchange requirement.

## Option Assessment

| Option | Fit for this project | Main benefit | Main cost or risk | Recommendation |
| --- | --- | --- | --- | --- |
| Relational database | Strong for financial records, constraints, approvals, reporting, and the current ERDs | Transactions, foreign keys, constraints, mature tooling, broad operator familiarity | Requires deliberate schema evolution and explicit handling of flexible content | Primary system of record for Release 1 |
| Property graph database | Useful for exploratory relationship queries across missions, people, organisations, artworks, and impact | Traversal and network analysis are natural | Second consistency/security surface; does not remove the need for financial transactions; extra operations and skills | Keep as a separately documented optional read model, only add for measured query needs |
| Relational plus graph projection | Fits if network discovery becomes an important product capability | Keeps transactions relational while enabling traversals | Event/projection lag, replay, reconciliation, authorization propagation, and additional failure modes | Defer until product evidence justifies the cost |
| RDF/OWL ontology store | Useful for formal semantics, interoperable vocabularies, and linked-data exchange | Explicit concept definitions and mappings across external vocabularies | Modeling and governance overhead; not a replacement for payment/approval transactions | Start with a human-readable domain glossary; add RDF only for a concrete interoperability need |
| Document database as primary | Some fit for evolving forms and social payloads | Flexible documents and nested content | Weaker fit for multi-entity financial workflows, relational constraints, and auditable joins; still needs a separate media store | Do not select as the primary operational store |
| Assemble from existing products | Could accelerate newsletter, identity, CMS, or marketplace operations | Less custom code for commodity capabilities | Workflow fit, data portability, cross-border finance, governance, privacy, and vendor lock-in need proof | Evaluate per capability; do not assume one product covers regulated money flows |

Large media files should live in private object storage with metadata and authorization in the system of record; storing media binaries in a graph or relational database is not the default recommendation.

## Build Versus Integrate

| Capability | Likely approach | Relative effort | Decision or dependency |
| --- | --- | --- | --- |
| Public site, role portals, application workflow | Build product-specific experiences; consider a CMS for editorial pages | Large | Build/assemble and web/native scope |
| Identity, roles, MFA, permissions | Use a proven identity provider or library; build domain authorization and admin policy | Medium | Identity architecture, data residency, recovery, MFA policy |
| Organisation vetting, applications, consent, retention | Build domain workflow; integrate document malware scanning and private storage | Large | Legal basis, safeguarding policy, retention schedule |
| Missions, artists, artworks, gallery, auctions, bidding | Build domain rules; integrate email and media delivery as needed | Large | Auction lifecycle, non-paying winner, returns, moderation |
| Checkout, donations, holding and payouts | Integrate a licensed payment provider; build ledger-like state tracking, reconciliation, policy, approvals, and reporting | Extra large / gated | Legal permission and provider confirmation before real funds |
| Tranche schedules, release approvals, audit | Build domain workflow with immutable or append-only event evidence as appropriate | Large | Pooling, evidence standard, threshold and separation-of-duties policy |
| Testimonies and media | Build capture, consent, moderation, metadata, and workflow; use object storage/transcoding services | Medium-large | Child/vulnerable-person safeguarding and media rights |
| Instagram, Facebook, TikTok publishing | Start with human-reviewed/manual publishing; integrate official APIs behind adapters after approval | Medium-large | Platform app review and channel policy |
| Newsletter and email confirmations | Integrate a dedicated provider; build subscriber consent state and delivery records | Small-medium | Provider, sender reputation, opt-in and unsubscribe policy |
| Hosting, backups, monitoring, secrets, incident response | Buy managed primitives; configure and test operational procedures | Medium-large | EU residency, data-processing terms, support ownership, budget |

These are relative effort bands, not calendar estimates. No team size, skills, budget, or availability was provided, and vendor feasibility is unverified.

## Proposed Delivery Phases and Gates

1. **Decisions and operating model**: assign Teresa, board, legal, finance, and technical owners; resolve custody, legal form of receipts/sales, VAT, refunds, sanctions, provider capability, donation policy, auction lifecycle, safeguarding, and who can authorize money. Gate: counsel and provider evidence support a lawful, operable flow, or the money-handling scope is changed.
2. **Architecture and foundations**: choose build-versus-assemble and hosting/data residency, approve module boundaries and source-of-truth model, define threat model, data classifications, retention, backup/recovery, audit, environments, CI, and incident ownership. Gate: architecture decisions and security/privacy acceptance are recorded; restore and access-control tests are defined.
3. **Non-money vertical slice**: build application, organisation/mission and artist review, artwork submission, public browsing, and admin audit with synthetic data. Gate: end-to-end tests, accessibility baseline, authorization tests, and support procedures pass.
4. **Auction and payment sandbox**: implement auction lifecycle, checkout, provider webhooks, idempotency, reconciliation, refunds/chargebacks, separation of duties, tranche calculations, and payout simulation. Gate: finance reconciles test scenarios; duplicate, delayed, failed, and reversed events are handled; no real funds yet.
5. **Controlled pilot**: limited participants, capped exposure, manual review for high-risk operations, staged rollout, monitored support window, rollback, backup restore, and incident exercise. Gate: board/operations sign-off, legal/provider prerequisites, no unresolved critical security findings, reconciliation sign-off, and tested recovery.
6. **Launch and improve**: expand in measured cohorts; track business objectives, operational incidents, social-post failure rates, support load, and reconciliation; add richer shipping, dynamic post formats, dashboard, or graph analysis only when justified.

Phases 1 and 2 may overlap for discovery, but payment implementation must remain gated by Phase 1. Social API integration should not block launch if a manual publishing path meets the initial need.

## Stability Definition

“Stable” should mean the system can prevent unauthorized actions, preserve and reconcile every money state transition, recover from data loss, detect and explain operational failures, satisfy privacy and retention obligations, and be supported by named humans with tested procedures. A successful demo or passing happy-path test is not a launch gate.

## Proposed Documentation Structure

```text
html/                          Original interactive ERD viewers
docs/
  architecture/
    README.md                  Navigation and decision status
    overview.md                Scope, context, and system boundaries
    business-view.md           Actors, capabilities, workflows, controls
    data-model.md               Relational model and persistence decisions
    technical-view.md           Modules, integrations, security, reliability
    ontology/README.md         Domain vocabulary and semantic scope
    erd/*.mmd                  Mermaid data diagrams
    options/
      README.md                Comparison and recommendation
      relational/README.md
      graph/README.md
      hybrid/README.md
      assembled-platform/README.md
```

## Research Limits

This assessment uses only the local BRD and diagrams. It does not confirm Dutch legal treatment, provider custody/payout eligibility, platform API approval, vendor prices, or production compliance. Those require named owners and direct professional/provider evidence during Phase 1.

## Build Squad and Related Repositories

* `racecar-discipleship-framework` is public and was added as a submodule under `projects/`, pinned to `47140f3668c97ef96eabdb759fae05fd25ade71b`.
* Its README says it is exploration-only, is not wired into a live agent session, and is not a replacement for Superteam. Its ROSTER maps twelve personas and an outer ring of delivery roles, including architecture, data/graph, backend, frontend, cloud, QA, planning, research, and red team.
* The user clarified Superteam is the intended squad to build this product. Treat it as build-time tooling, not a product runtime dependency. Keep agent assistance separate from legal/financial authority.
* Superteam could not be accessed from this Codespace: GitHub API returned 404 and `git ls-remote` returned 403. Its actual source/configuration remains unreviewed; add it as a submodule and configure it only after read access is granted.