---
title: Delivery Roadmap and Stability Gates
description: Build-versus-integrate scope, dependency ordering, and operational launch criteria
---

## Build and Integrate

Effort bands are relative, not time estimates. Team size, skills, budget, and
vendor choices are unknown.

| Capability | Approach | Relative effort | Critical dependency |
| --- | --- | --- | --- |
| Public site and role portals | Build product workflows; consider CMS for editorial pages | Large | Build-versus-assemble and web/native scope |
| Identity and authorization | Integrate proven authentication; build domain roles and permissions | Medium | Residency, recovery, and MFA policy |
| Applications, vetting, and consent | Build workflows; integrate private storage and malware scanning | Large | Legal basis, safeguarding, retention |
| Missions, artists, artworks, and auctions | Build domain workflows | Large | Auction and non-paying-winner policies |
| Payments and payouts | Integrate provider; build state, reconciliation, approval, and reporting | Extra large, gated | Legal custody and eligible payout countries |
| Tranche schedules and approvals | Build rules and audit; provider executes transfers | Large | Pooling, evidence, thresholds, separation of duties |
| Testimonies and media | Build consent-aware workflow; integrate storage/transcoding as needed | Medium-large | Safeguarding, rights, moderation |
| Social posting | Begin manually; integrate official APIs after approval | Medium-large | Meta/TikTok account eligibility and review |
| Newsletter | Integrate delivery; build consent, subscriber state, delivery records | Small-medium | Provider and communication policy |
| Operations | Use managed hosting, keys, monitoring, backups; build and test runbooks | Medium-large | EU residency, budget, named owners |

Do not build payment processing, card vaulting, email delivery infrastructure,
or social networks. Own the domain records and control workflows around them.

## Phases and Exit Gates

### Phase 1: Decisions and operating model

Resolve custody/legal structure, sale-versus-donation and tax treatment, VAT,
refunds, provider capabilities, tranche pooling, quick donations, approval
thresholds, fees, failed-mission handling, safeguarding, and initial board/admin
roles. Assign a decision owner and evidence source to each blocker.

**Gate:** legal and finance owners approve an operable model and a provider
confirms the required settlement and payout flow. Otherwise revise the business
model before implementing real-money flows.

### Phase 2: Architecture and foundations

Select build-versus-assemble, stack, hosting/data residency, identity approach,
data classification, threat model, retention, source-of-truth rules, audit,
backup/recovery, environments, CI, observability, and support ownership.

**Gate:** decisions are recorded; access-control and restore tests are defined;
privacy/security responsibilities and incident escalation are assigned.

### Phase 3: Non-money vertical slice

Deliver mission and artist applications, verification review, artwork
submission, public browsing, testimony capture, and admin audit with synthetic
data. Keep payment actions disabled.

**Gate:** role/object authorization tests, critical end-to-end tests,
accessibility baseline, support process, and data lifecycle checks pass.

### Phase 4: Auction and payment sandbox

Implement auction state transitions, bidding concurrency, checkout integration,
provider webhook idempotency, reconciliation, refunds/chargebacks, tranche
calculation, evidence, dual control, and payout simulation.

**Gate:** finance reconciles normal, duplicate, delayed, failed, refunded, and
reversed cases. No real-money release occurs in this phase.

### Phase 5: Controlled pilot

Use limited participants, capped exposure, manual checks for high-risk
operations, named support coverage, staged rollout, rollback, and monitoring.
Exercise backup restoration, incident response, provider outage, and payment
reconciliation.

**Gate:** board/operations, legal, finance, and technical owners sign off;
provider/legal prerequisites are met; recovery exercises pass; no critical
security or privacy findings remain.

### Phase 6: Launch and measured expansion

Expand by cohort. Measure funds raised, tranche evidence/sign-off, onboarding
time, publishing failures, newsletter opt-outs, incidents, support load, and
reconciliation exceptions. Add richer shipping, dynamic formats, dashboards,
or graph analysis only when justified by operating evidence.

Phases 1 and 2 may overlap. Payment implementation remains gated by Phase 1.
Manual social publishing can serve as an initial path while API approval
proceeds.

## Stable Means Operable

Before broad launch, the team must demonstrate that it can prevent unauthorized
actions, account for every money-state transition, recover data, detect and
explain failures, honor privacy/retention rules, and support users through
named humans with tested procedures. A demo or happy-path test alone is not a
stability gate.