---
title: Expression is Devotion Business Requirements
description: Business requirements, product scope, governance, and open decisions for the Expression is Devotion platform
---

## Expression is Devotion — Business Requirements Document

Oct 14, 2026 · @Teresa

## 1. Executive summary

Expression is Devotion is a faith-based platform that turns donated art into staged funding for vetted Christian missions, and gives missions one place to share testimonies with followers. Artists donate a piece and choose one approved mission per artwork (a mission can be funded by many artworks); supporters buy it at auction or give directly with a quick donation; the payment is held and released to the mission in tranches, each signed off by an administrator.

Around the auction sit three supporting capabilities: published testimonies with automatic posting to Instagram, Facebook and TikTok; a newsletter list that needs no account; and an admin portal with role-based approvals and separation of duties.

| Item | Value |
| --- | --- |
| Organisation | Expression is Devotion (intended Dutch stichting, ANBI status sought) |
| Product | Website and app |
| Document status | Draft v0.2, updated with the owner's review notes of 15 Oct 2026 |
| Reading key | **Decided** = confirmed by the owner; **Proposed** = suggested, not yet confirmed; **Open** = see section 12 |

## 2. Business objectives

The platform exists to raise trustworthy funds for missions and to make their stories easy to share. Targets are not yet set; each objective has a measure, and these will be tracked on an admin dashboard added later as a module.

| # | Objective | Suggested measure (to confirm) |
| --- | --- | --- |
| BO-1 | Fund approved missions through donated-art auctions | Funds raised per selectable reporting period (not fixed in the build); share of auctions that sell |
| BO-2 | Release money responsibly, in stages tied to progress | Share of tranches released with evidence (a testimony, plus other proof) and dual sign-off where required |
| BO-3 | Capture and share testimonies and mission overviews with ease | At least one testimony published per month; time for a post to be processed from upload to live (baseline to be measured) |
| BO-4 | Grow and keep an engaged follower base | Newsletter subscribers; opt-out rate |
| BO-5 | Give artists a meaningful way to serve and be seen | Active artists; repeat donations |
| BO-6 | Earn trust through vetting, transparency and compliance | Applications vetted on a set cadence; zero data or payment incidents |

## 3. Scope

Release 1 covers the full auction-to-tranche flow, testimonies, newsletter and admin approvals; richer shipping and posting rules follow as modules.

**In scope (release 1)**

- Public site: home, mission pages, artist pages, a gallery page of all artworks, individual auction pages, testimonies, newsletter sign-up
- Portals and application forms for Missionaries, Artists and Supporters
- Art auction with bidding, checkout and held payment, plus a quick-donate button for direct gifts
- Tranche-based release of funds to missions, with milestone reports in the form of testimonies
- Testimony capture (text, photo, audio, video) and posting to Instagram, Facebook and TikTok
- Newsletter list with per-subscriber on/off switch
- Admin portal with four approval permissions and a super-admin
- Shipping shown as a fixed note on the auction page

**Planned later (modular additions)**

- Shipping zone and rate table for (international) fees, optionally per artist
- Dynamic format rules and per-platform limits for social posts
- Admin dashboard showing the success measures in section 2
- Additional social channels (for example Snapchat)

**Out of scope (for now)**

- Supporters paying in instalments (the supporter pays in full; only the release is staged)
- Storing card or bank details on the platform

## 4. Stakeholders and user roles

Four roles share one login; Missionaries, Artists and Supporters each have their own portal and application form, and visitors and followers need no account.

| Role | Who | Needs from the platform | Account |
| --- | --- | --- | --- |
| Missionary | Member of a mission team or organisation; a mission has one or more (lead or member) | Present the mission, post testimonies (text, numbers, photo, voice, video), receive tranches, report milestones, supply follower emails | Yes, after approved application |
| Artist | Creator donating a piece | Artist page with testimony and services, submit artwork, choose one approved mission per artwork, receive contact requests | Yes, after approved application |
| Supporter | Buyer, bidder or quick donor | Bid, pay, give a quick donation, track purchase, receive progress on the funded mission | Yes |
| Follower | Newsletter reader | Subscribe, unsubscribe | No |
| Visitor | Public | Browse missions, artists, auctions, testimonies; send a contact request | No |
| Administrator | Board or staff volunteer | Approve applications, auctions and payments as permitted | Yes, with two-step login |
| Super-admin | Platform owner | Assign the four approval permissions to administrators | Yes, with two-step login |
| Board (stichting) | Legally accountable people | Oversight of funds, compliance, policy | Outside the platform |
| External parties | Payment provider, social platforms (Meta for Instagram and Facebook, TikTok), email service, KvK and tax authority | Integrations, reviews and audits, registrations | n/a |

## 5. Functional requirements

Requirements are grouped by module, matching the modular build: each module owns its data and screens so it can be changed without touching the others.

### 5.1 Accounts and applications

| ID | Requirement | Status |
| --- | --- | --- |
| FR-ACC-1 | One login for all roles; role decides portal and permissions | Decided |
| FR-ACC-2 | Separate application form per role: missionary (NL), missionary (international), artist, supporter; versioned and localised | Decided (forms per role); variants from ERD |
| FR-ACC-3 | Missionary and artist accounts become active only after admin approval | Decided |
| FR-ACC-4 | Organisations are verified (registration, charity status, IBAN name match, sanctions, safeguarding) and re-checked on a schedule | Modelled in ERD |
| FR-ACC-5 | Supporting documents uploaded to private storage, malware-scanned, classified and kept per retention rule | Modelled in ERD |
| FR-ACC-6 | Minors: date of birth, age consent and guardian link; child-safety screening (VOG) recorded as outcome and date only | Modelled in ERD; a consent checkbox is supported: ticking it stores a timestamped consent record (type, policy version), so consent is provable |

### 5.2 Missions

| ID | Requirement | Status |
| --- | --- | --- |
| FR-MIS-1 | Mission page: what the mission focuses on, why and how, organisation details and services offered | Decided |
| FR-MIS-2 | A mission has at least one missionary and can have several | Decided |
| FR-MIS-3 | Mission shows region, beneficiary group and budget | Modelled in ERD |
| FR-MIS-4 | Only approved missions can be selected by artists; a mission can be funded by multiple artworks | Decided |

### 5.3 Artists and artworks

| ID | Requirement | Status |
| --- | --- | --- |
| FR-ART-1 | Artist page: testimony on the art they make and why, plus services offered | Decided |
| FR-ART-2 | Each artwork funds exactly one approved mission; one mission can receive funds from multiple artworks | Decided |
| FR-ART-3 | "Request contact" replaces the artist's email: open form, no login; visitor leaves message and email; artist replies directly | Decided |
| FR-ART-4 | Optional link to the artist's social media channel | Decided |

### 5.4 Auctions

| ID | Requirement | Status |
| --- | --- | --- |
| FR-AUC-1 | Auction page order: (1) two-sentence mission and intention; (2) artist's reason for this mission, linking to the mission page; (3) artist's text on the piece; (4) social link, "Request contact" button, link to artist page | Decided |
| FR-AUC-2 | 1 to 3 photos or videos per auction | Decided |
| FR-AUC-3 | Highest bid wins; auction has start price and end time | Proposed (mechanics open) |
| FR-AUC-4 | Auction goes live only after "readiness" approval | Decided |
| FR-AUC-5 | Shipping note shown on the page: "be mindful that shipping fees will be added to the price upon payment" | Decided |
| FR-AUC-6 | Gallery page showing all artworks, each linking to its individual auction page | Decided |
| FR-AUC-7 | Quick-donate button so a supporter can give directly without buying artwork | Decided (rules open, see section 12) |

### 5.5 Testimonies and social posting

| ID | Requirement | Status |
| --- | --- | --- |
| FR-CON-1 | Missionaries capture testimonies with text, photo, audio and video, linked to a mission | Decided |
| FR-CON-2 | Testimonies can be shared to Instagram, Facebook and TikTok | Decided |
| FR-CON-3 | Workflow: testimony and media are first placed into a post format (frame), then rolled out with an explicit action button; each attempt logged with retry and error | Decided |
| FR-CON-4 | Post formats combine media slots (video, audio, image, text) with aspect ratio and duration limits | Decided (rules and per-platform limits later) |
| FR-CON-5 | Text and photo testimonies need a video version for TikTok | Platform constraint |

### 5.6 Newsletter

| ID | Requirement | Status |
| --- | --- | --- |
| FR-NEW-1 | Subscriber list separate from accounts, with on/off switch per subscriber | Decided |
| FR-NEW-2 | Missionaries can supply additional email addresses | Decided |
| FR-NEW-3 | Supplied addresses receive a confirmation email with a confirm-subscription button before they are subscribed | Decided |
| FR-NEW-4 | Send newsletters and track delivery per subscriber | Modelled in ERD |

## 6. Admin, approvals and governance

Every sign-off is a separate, logged permission, and no single administrator can both put an auction live and release its money.

| Permission | What it approves | Status |
| --- | --- | --- |
| Approve missionary applications | New missions and organisations joining | Decided |
| Approve artist applications | New artists joining | Decided |
| Approve auction readiness | An auction going live | Decided |
| Approve payment | A tranche being released to a mission | Decided |

| ID | Rule | Status |
| --- | --- | --- |
| GOV-1 | A super-admin assigns any combination of the four permissions to administrators | Decided |
| GOV-2 | The person who approves an auction cannot approve its payment | Decided |
| GOV-3 | Payments above a threshold need two approvers | Decided in principle; threshold open |
| GOV-4 | Every approval, permission change and read of a restricted document is written to an audit log | Decided |
| GOV-5 | Administrators use two-step login | Decided |
| GOV-6 | Real board members remain legally accountable; AI agents may assist but do not hold financial authority | Noted in NGO setup |

## 7. Payments, tranches and shipping

The supporter pays once in full; the platform holds the item amount and releases it to the mission in approved stages, while shipping is kept apart from the donation.

1. Supporter wins the auction and pays item amount plus shipping through the payment provider.
2. The item amount is held; shipping is recorded separately and never flows into tranches.
3. The payment is split into tranches by the schedule set for that mission.
4. Each tranche is triggered by a date, a milestone report with evidence, or a manual release.
5. A payment approver (not the auction approver) signs off; two approvers above the threshold.
6. The release is executed and logged; a per-tranche report is published for the mission and supporter.

| ID | Requirement | Status |
| --- | --- | --- |
| PAY-1 | Supporter pays in full; funds released to the mission in tranches | Decided |
| PAY-2 | Each release goes through the payment approver | Decided |
| PAY-3 | Item amount and shipping amount stored separately | Modelled in ERD |
| PAY-4 | Tranche schedule set per mission at creation: number, share (percentage or amount), trigger | Decided (per mission) |
| PAY-5 | Site-wide tranche limits set by super-admin; schedule changes after the mission receives its first funds need a logged approval | Proposed |
| PAY-6 | Payment provider handles card, iDEAL and SEPA; platform stores tokens only, never card or bank data | Modelled in ERD |
| PAY-7 | Shipping zone and rate table (by size class, optionally per artist) can be added later without changing existing tables | Decided as later module |

## 8. Data, privacy and compliance

The platform handles personal, financial and child-safety data under EU rules, so consent, retention and erasure are built into the data model from day one.

| ID | Requirement | Status |
| --- | --- | --- |
| DAT-1 | EU consent captured at sign-up and stored per type and policy version (terms and privacy, marketing, photo and video, progress reports, age consent, safeguarding training, image rights) | Decided (consent); types from ERD |
| DAT-2 | Data deleted on request, with logged exceptions where law requires keeping it (for example financial records) | Decided |
| DAT-3 | Retention period and legal basis defined per data category | Modelled in ERD |
| DAT-4 | Sensitive fields (registration numbers, IBAN, contact details, date of birth) encrypted, keys held in a key management service | Modelled in ERD |
| DAT-5 | Documents in a private bucket, signed links only, checksum and classification | Modelled in ERD |
| DAT-6 | Hosting and database in the EU; data processing agreements with each vendor; cookie consent banner | Proposed |
| DAT-7 | The stichting is legally allowed to hold donated funds between collection and release | Open |
| DAT-8 | Donation receipts for tax purposes where the buyer qualifies | Open (needs legal input) |

The full field-level design lives in the data dictionary (four ERDs: identity and organisations; applications, consent and access; auction, shipping and payments; content, formats and outreach).

## 9. Non-functional requirements

The build must be modular, readable, easy to extend and secure; the rest of this section turns that into checkable requirements.

| ID | Area | Requirement | Status |
| --- | --- | --- | --- |
| NFR-1 | Maintainability | Modular framework: accounts and roles, applications, missions, artists, auctions, payments, content, newsletter, admin | Decided |
| NFR-2 | Extensibility | New modules (shipping rates, format rules, platform limits) plug in without restructuring tables | Decided |
| NFR-3 | Security | Permissions checked on the server for every action | Proposed |
| NFR-4 | Security | Passwords hashed (argon2 or bcrypt); two-step login for admins | Proposed |
| NFR-5 | Security | Spam protection on the open contact form and sign-up forms | Decided |
| NFR-6 | Reliability | Social posting retries with error capture; failed posts visible to admins | Decided |
| NFR-7 | Integrity | Application-level checks for polymorphic links and the 3-media limit | Modelled in ERD |
| NFR-8 | Usability | Mobile-first layout | Decided |
| NFR-9 | Localisation | Forms and accounts carry a locale; languages to confirm | Open |
| NFR-10 | Accessibility | Target level to confirm (for example WCAG 2.1 AA) | Open |

## 10. Design requirements

The visual design follows the existing Figma wireframes and the confirmed palette and type scale below.

| Element | Value |
| --- | --- |
| Accent colours | #FF0081 (pink), #1A66DE (blue), #FFD400 (yellow) |
| Background | #FFFDF7 (alternate: #E5E5E5) |
| Text | #232323 |
| Font | Inter |
| Inter Regular sizes | 12, 20, 24, 25, 32, 36, 40, 50, 64, 128 |
| Inter Bold sizes | 24, 32, 36, 50, 64, 128 |
| Wireframe pages | Home, Bid now (auction detail), NGO feature (mission grid), Support (how it works), Newsletter (mission deep-dive) |

Pages still to design: mission page, artist page, testimony page, the three portals, application forms and the admin portal.

## 11. Assumptions, constraints and dependencies

**Assumptions**

- The organisation registers as a Dutch stichting with the KvK and seeks ANBI status.
- Artists ship the artwork themselves; the shipping fee is added at payment (confirmed).
- Missions operate in several countries, so international organisations and payouts must be supported (confirmed).

**Constraints**

- Auto-posting depends on platform approval (checked 2026-10-06, may change): Instagram needs professional accounts, Meta app review, and allows 100 API posts per account per 24 hours; TikTok posts stay private until its audit passes, which can take weeks; Facebook posts go to a Facebook Page (not a personal profile), need Page posting permissions through the same Meta app as Instagram, and support text, links, photos and video (checked 2026-10-15).
- Card and bank data stay with the payment provider.
- A stichting needs real people on its board; financial authority cannot sit with AI agents.

**Dependencies**

- A payment provider that supports holding funds and split, staged payouts.
- An email service for newsletters and confirmations.
- Legal advice on holding funds, tax receipts and VAT before payments go live.

A tech stack has been suggested (Next.js, EU-hosted Vercel, Supabase with EU data residency, Stripe Connect) but is not yet decided.

## 12. Open items to think through

52 points remain open after the 15 Oct review; the suggested order is Legal first, then Finance, then Technology, with the other subjects in parallel. Priority marks what blocks the build (High) versus what can follow.

| # | Subject | Open item | Why it matters | Priority |
| --- | --- | --- | --- | --- |
| 1 | Legal and compliance | Is the stichting allowed to hold donated funds between collection and release, and under what licence or structure? | Tranche model depends on it | High |
| 2 | Legal and compliance | Is an auction sale a donation, a sale or both? Can buyers and quick donors get a tax-deductible receipt (ANBI gift rules)? | Receipts, pricing, marketing claims | High |
| 3 | Legal and compliance | VAT on artwork sales and shipping across countries | Price shown versus price charged | High |
| 4 | Legal and compliance | Terms and conditions for artists, supporters and missions (donation agreement, ownership transfer, refunds) | Disputes and liability | High |
| 5 | Legal and compliance | Privacy policy, data processing agreements, cookie policy | GDPR | High |
| 6 | Legal and compliance | Retention periods and legal basis per data category; which data survives an erasure request | Fills the retention table | Medium |
| 7 | Legal and compliance | Image rights and copyright licence for artworks and testimony media used on social channels | Posting without permission | Medium |
| 8 | Legal and compliance | Anti-money-laundering and sanctions checks for international missions and large purchases | Payment provider and bank will ask | High |
| 9 | Finance and payments | Choose a payment provider that supports held funds and staged, split payouts to international organisations | Core of the money flow | High |
| 10 | Finance and payments | Confirm the dynamic tranche proposal: default schedule, limits, who sets it | Proposed only | High |
| 11 | Finance and payments | With one tranche schedule per mission (decided), how are proceeds from several artworks pooled into each tranche: fixed amounts, or percentages of the total received so far? | Funds arrive at different times | High |
| 12 | Finance and payments | Quick donations: allowed without an account? Always to a chosen mission, or also a general fund? Released in tranches like auction proceeds? Minimum amount? | New button needs rules | High |
| 13 | Finance and payments | Threshold for "larger amounts" needing two approvers | Governance rule incomplete | High |
| 14 | Finance and payments | Does the platform take a fee or cover provider costs from proceeds? | Business model, transparency | High |
| 15 | Finance and payments | What happens to held funds if a mission stops, misses milestones or fails verification? | Fallback for donors' money | High |
| 16 | Finance and payments | Currencies supported and who carries exchange and transfer costs | International payouts | Medium |
| 17 | Finance and payments | Refund policy (damaged, not received, not as described) and chargebacks | Held funds may need returning | Medium |
| 18 | Business and operations | Auction mechanics: timed end, extension on late bids, reserve price, bid increments, buy-now option | BID and AUCTION fields are placeholders | High |
| 19 | Business and operations | Non-paying winner: payment deadline, offer to second bidder, account consequences | Common auction failure | High |
| 20 | Business and operations | What counts as tranche evidence besides a testimony (photos, receipts, a written report)? | Approvers need a clear standard | Medium |
| 21 | Business and operations | Who checks artwork quality and authenticity before readiness approval? | Trust and reputation | Medium |
| 22 | Business and operations | Shipping: insurance, tracking, international customs, who pays for returns | Fee note covers price only | Medium |
| 23 | Business and operations | Unsold artwork: relist, return to artist, or reassign | Lifecycle gap | Medium |
| 24 | Business and operations | Mission onboarding: how missions are found and vetted, and the re-verification and vetting cadence | Verification schedule needs an interval | Medium |
| 25 | Business and operations | Targets for the objectives in section 2 and which reporting periods the dashboard offers | Dashboard is a later module | Low |
| 26 | Governance and roles | Who are the board members and the first administrators and super-admin? | Separation of duties needs at least 3 people | High |
| 27 | Governance and roles | Can one person hold several approval permissions besides the auction-payment split? | Permission matrix | Medium |
| 28 | Governance and roles | Escalation when approvers disagree or are unavailable | Releases may stall | Low |
| 29 | Safeguarding | Minimum age for artists; guardian consent process | ERD has guardian link, rule undefined | High |
| 30 | Safeguarding | Which roles need a VOG or equivalent abroad, and its validity period | Child-safety policy | Medium |
| 31 | Safeguarding | Content rules for testimonies showing children or vulnerable people | Consent and dignity | Medium |
| 32 | IT security | Two-step login for non-admin users too? (decided for admins) | Account security | Medium |
| 33 | IT security | Which spam and bot protection tool to use (requirement decided) | Tool choice only | Low |
| 34 | IT security | Audit log retention and who may read it | Accountability | Low |
| 35 | IT security | Backup, recovery and incident response plan | Data loss | Medium |
| 36 | Technology and build | Build versus assemble: custom build or website builder plus newsletter service | Cost, time, flexibility | High |
| 37 | Technology and build | Confirm the tech stack (suggested: Next.js, Vercel EU, Supabase EU, Stripe Connect) | Proposed only | High |
| 38 | Technology and build | Own platform approvals (one Meta app for Instagram and Facebook, plus TikTok) versus a third-party posting service | Weeks of review lead time | High |
| 39 | Technology and build | Website and app: web only, installable web app, or native apps? | Project says "website and app" | Medium |
| 40 | Technology and build | Media storage, video transcoding and making video versions of text or photo testimonies | TikTok is video-first | Medium |
| 41 | Technology and build | Hosting budget and who maintains the platform after launch | Running costs | Medium |
| 42 | Data model | Draw missing links: payment to supporter, shipping rate to artist, post attempt to render, contact request to artwork | Known ERD gaps | Medium |
| 43 | Data model | Link artist application to artwork; make organisation optional on artist applications | Known ERD gap | Medium |
| 44 | Data model | Application-level integrity for polymorphic references and the 3-media limit | Known ERD gap | Medium |
| 45 | Data model | Add quick donations (donation table linked to mission and supporter or guest), move the tranche schedule onto the mission, and link tranche evidence to testimonies | New decisions not yet in ERD | Medium |
| 46 | Content and social | Who writes or approves testimonies before publishing? Is there a moderation step? | Content quality and safety | Medium |
| 47 | Content and social | Which post formats (frames) exist at launch, and the brand rules for them | Format table is empty | Low |
| 48 | Content and social | Measure a baseline for how long a post takes to be processed, from upload to live on each platform | Needed before a target can be set | Low |
| 49 | Newsletter and communication | Newsletter frequency, owner, and tools; progress updates to supporters per tranche | Supporter engagement | Low |
| 50 | Design and UX | Languages for launch (Dutch, English, others?) and accessibility level | Locale and NFR targets | Medium |
| 51 | Design and UX | Gallery page: sorting and filters (by mission, artist, open or sold) | New page | Medium |
| 52 | Design and UX | Designs for gallery, mission, artist and testimony pages, the portals, forms and admin | Not yet in Figma | Medium |

## 13. Architecture and project structure

The current data models and stack-neutral architecture proposal are in
[docs/architecture/README.md](docs/architecture/README.md). Standalone Mermaid
sources for the four current ERDs are in [docs/architecture/erd/](docs/architecture/erd/).
The original HTML viewers are under [html/](html/). Related build projects and
the squad working agreement are listed in
[docs/architecture/related-projects.md](docs/architecture/related-projects.md)
and [docs/architecture/build-squad.md](docs/architecture/build-squad.md).

A lean, self-funding startup path to launch this platform (Campaign Drops,
funding engine, lean EU stack, work packages and a 90-day plan) is in
[docs/startup/README.md](docs/startup/README.md), with a visual one-pager at
[html/startup_work_package_v1.html](html/startup_work_package_v1.html).
