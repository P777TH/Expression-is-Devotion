---
title: Decisions and Risks
description: The few decisions that unblock the pilot, mapped to the 52 open BRD items, plus the startup risk register
---

## From 52 open items to 12 pilot decisions

The BRD lists 52 open items. The startup path needs only **12 decisions** before
the pilot drop. Each has a recommended default so the owner can say "yes",
"no" or "change" quickly. The rest are deferred to the stage where they matter.

| ID | Decision | Recommended default | Closes BRD items | Owner | Needed by |
| --- | --- | --- | --- | --- | --- |
| **D1** | Money structure | Grant model: gifts and sale proceeds are stichting income, earmarked, granted to missions in tranches under a grant agreement | 1, 8 (in part), 15 | Board + legal advisor | WP0 |
| **D2** | Sale versus donation and receipts | Artwork is donated to the stichting and sold; buyers receive an invoice, not a gift receipt; direct gifts and the Circle receive gift receipts | 2, 4 | Legal advisor | WP0 |
| **D3** | VAT on art and shipping | Follow the advisor's ruling; until then, sell only within the NL/EU and show prices including any VAT | 3 | Accountant | WP0 |
| **D4** | Payment provider | Mollie or Stripe standard checkout, no Connect in Stage 0 | 9 | Treasurer + builder | WP0 |
| **D5** | Tranche defaults | Two to four milestones per mission; default 40 / 30 / 30; amounts pooled per mission and released as a percentage of funds received so far | 10, 11 | Founder + treasurer | WP1 |
| **D6** | Quick donations | Guests may give without an account; always to a chosen mission milestone or the general mission fund; minimum 5 euro; follows the same tranche rules | 12 | Founder | WP4 |
| **D7** | Dual-approval threshold | Every tranche needs two approvers in the pilot (no threshold); review after two drops | 13 | Board | WP0 |
| **D8** | Fees | No platform fee on mission funds; operations funded by the Circle share, optional tips, sponsors and grants | 14 | Board | WP0 |
| **D9** | Auction mechanics | Timed 10-day drop, start price set with the artist, fixed bid steps (5 euro below 100, 10 euro below 500, then 25 euro), 2-minute soft close, no reserve, no buy-now in the pilot | 18 | Founder + artist lead | WP4 |
| **D10** | Non-paying winner | 72 hours to pay; then offered to the second bidder; a repeat non-payer cannot bid again | 19 | Founder | WP4 |
| **D11** | People | Name the board of three and the five pilot roles in the work packages | 26, 27 | Founder | WP0 |
| **D12** | Launch scope | Web only (mobile-first), Dutch and English, WCAG 2.1 AA basics, manual social posting, NL/EU shipping only | 36, 37, 38, 39, 50 | Founder + builder | WP4 |

## Deferred, with the stage where each one matters

| BRD items | Topic | Stage | Pilot workaround |
| --- | --- | --- | --- |
| 5, 6, 34, 35 | Privacy notices, retention, audit log, backups | Before pilot (part of WP0 and WP4) | Standard templates, Supabase backups, restore tested once |
| 7, 31, 46 | Image rights, content rules, moderation | Before pilot | Consent and rights checkboxes in every form; the founder approves every testimony |
| 16, 22 | Currencies, international shipping | Stage 1 | Euro only, NL/EU shipping |
| 17, 23 | Refunds, unsold art | Stage 0 policy page | Refund only if not received or damaged; unsold art goes to the next drop or back to the artist (artist's choice at intake) |
| 20 | Tranche evidence standard | WP6 | Testimony plus photos or receipts |
| 21 | Quality and authenticity | WP2 | Artist lead readiness checklist |
| 24 | Mission sourcing and re-vetting | Stage 1 | Yearly re-check of each mission |
| 25, 48 | Targets and baselines | WP8 | Measure the pilot first, then set targets |
| 28 | Escalation | Stage 1 | The chair decides |
| 29, 30 | Minimum age, VOG | Before pilot | Pilot artists 18+ only; VOG for anyone working with children on missions |
| 32, 33 | MFA for all users, bot protection | Stage 0 | MFA for admins; Turnstile on all forms |
| 40, 47 | Media pipeline, post formats | Stage 0 via Canva, Stage 2 automated | Canva frames |
| 41 | Hosting budget and maintenance | WP4 | Within the operations fund; the builder is named |
| 42 to 45 | ERD gaps | Stage 1 migrations | Stage 0 schema subset, plus the new campaign entity |
| 49 | Newsletter cadence | WP7 | Monthly testimony letter, plus one per drop |
| 51, 52 | Gallery filters and remaining designs | WP4 and Stage 1 | Filter by drop, mission, open or sold |

## Risk register

| # | Risk | Likelihood | Impact | Mitigation | Owner |
| --- | --- | --- | --- | --- | --- |
| R1 | The grant model is not accepted by the advisor or bank | Low to medium | High | Ask early (WP0 week 1); fallback: a fiscal host or partner charity holds funds | Board |
| R2 | ANBI status takes longer than the pilot | Medium | Medium | Run the pilot as a stichting without ANBI and be honest that gifts are not yet deductible; or partner with an existing ANBI | Founder |
| R3 | Too few artists or low-quality pieces | Medium | High | Founding Artists invited personally; curation checklist; smaller drop is fine | Artist lead |
| R4 | Low bids and unsold lots | Medium | Medium | Realistic start prices, matching donor, church closing evening, prints as a second chance | Founder |
| R5 | A mission fails a milestone | Low | High (trust) | Grant agreement fallback published in advance; transparent update | Board |
| R6 | Volunteer burnout | Medium | High | Drops, not always-on; runbook; templates; automate anything done three times | Founder |
| R7 | Safeguarding incident in content | Low | Very high | Consent forms, no identifiable children without guardian consent, founder approval | Founder |
| R8 | Social platform rules change | Medium | Low | Manual scheduling first; newsletter is the owned channel | Story and social |
| R9 | Vendor lock-in | Low | Medium | Postgres as source of truth, exports, adapters | Builder |
| R10 | Payment fraud or chargebacks | Low | Medium | Provider fraud tools; release tranches only after the chargeback window for large amounts | Treasurer |
| R11 | Mission drift away from the essence | Low | High | The essence table in the package README is reviewed at every retrospective | Board |

## How to record a decision

When the owner decides, update the status in the BRD (README section 12) from
**Open** to **Decided**, and add one line to this table with the date and
the person who decided. That keeps the BRD the single source of truth.
