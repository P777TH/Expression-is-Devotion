---
title: Build Squad Working Agreement
description: How Superteam can help build the product while preserving human ownership and financial controls
---

## Intent

Superteam is the intended build-time delivery squad for this project. It should
work from the product requirements and architecture records in this repository
and deliver reviewed code in small, testable increments. It is not part of the
production fundraising platform.

The accessible [discipleship framework roster](../../projects/racecar-discipleship-framework/ROSTER.md)
describes role mappings, but its README says the framework is exploration-only
and not wired into a live agent session. The Superteam repository itself could
not be read by this Codespace. Treat the mapping below as an initial working
model, not a verified copy of current agent configuration.

## Proposed Responsibility Map

| Role from the framework | Contribution to this project | Human owner or boundary |
| --- | --- | --- |
| Peter / Steve, project lead | Keep one prioritized product direction and resolve scope conflicts | Teresa and the project owner retain final product decisions |
| Andrew / Marlo, UX and product voice | Research user journeys, applications, supporter and mission workflows | Teresa approves the business experience |
| James (Zebedee) / Eric, SDU lead | Coordinate engineering work and integrate module delivery | Human technical lead owns release readiness |
| Philip / Bob, solution architect | Maintain module boundaries, ADRs, and integration contracts | Architecture decisions are reviewed and recorded |
| Bartholomew / G, money role | Support financial data and reporting design | Finance/board owners approve policy; no agent authorizes funds |
| Atlas, data and graph engineer | Own schema, integrity, and any graph-option spike | Keep relational/graph decision evidence-based |
| Diesel, backend developer | Implement server-side rules, integrations, and authorization | Code review and tests required |
| Pixel, frontend developer | Implement accessible public and portal workflows | Product acceptance remains with Teresa/owner |
| Orbit and selected cloud specialist | Implement deployment, observability, backup, and recovery | Use only the provider approved in the architecture decision |
| Thomas / Vera, quality gate | Design and run unit, integration, end-to-end, and regression checks | Release gate requires human acceptance of results |
| James (Alphaeus) / Paulien, planner | Maintain backlog, dependencies, scope, and phase readiness | Product owner sets priority |
| Thaddaeus / Athanasios, researcher | Investigate open decisions and document evidence | Legal and provider conclusions require qualified human sources |
| Simon / Coach, squad coach | Facilitate collaboration and retrospectives | Does not replace project ownership |
| Judas / Kryptonite, red team | Challenge assumptions and probe security, abuse, and operational failure modes | Findings are triaged by the human technical owner |
| Matthew / Kevin, reporting | Prepare progress and decision summaries | Reports cite source records and distinguish facts from proposals |

The ROSTER names and role mappings are copied from the accessible framework;
verify that they match the current Superteam repository once access is restored.

## Working Method

1. Teresa and the project owner choose a bounded outcome and acceptance
   criteria from the BRD and phase roadmap.
2. Research and architecture work records sources, assumptions, and open
   decisions before code changes.
3. The SDU lead decomposes the work into small vertical slices with an owner,
   tests, and explicit dependencies.
4. Backend, frontend, data, and cloud roles implement only their scoped slices;
   changes are reviewed and tested before integration.
5. Quality and red-team roles independently challenge the critical paths,
   particularly permissions, payment state, privacy, and recovery.
6. A named human accepts the release gate. Agents may recommend, test, and
   prepare evidence; they do not exercise legal, governance, or financial
   authority.

## Non-Negotiable Guardrails

* No agent receives production payment credentials or independently releases
  funds.
* Legal classification, payment custody, approval policy, safeguarding, data
  retention, and production launch require named human owners.
* Do not place secrets or personal data in prompts, test fixtures, commits, or
  agent-readable logs.
* Use synthetic data until the privacy/security foundation is approved.
* Require code review, automated tests, auditability, rollback, and operational
  ownership for changes that affect money, identity, or sensitive data.
* Keep agent tooling and agent personas outside the runtime application and its
  authorization model.

## Access Prerequisite

The Superteam source repository is not readable from the current Codespace
credential. Before configuring its agents here, grant this environment
read-only access, then review its actual instructions, tool permissions,
startup hooks, and secret handling. The RDCF roster alone is not sufficient to
activate the squad safely.