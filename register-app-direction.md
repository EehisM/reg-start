# Register — Project Summary & Direction

*Compiled from planning conversation — August 2026*

---

## 1. Background

- **Team:** 3 people, second-year computer systems student + 2 friends, based in Munster, Ireland
- **Goal:** Start a small AI-assisted business/product with real revenue potential, buildable by a student team without major capital
- **Path taken:** Broad brainstorm → narrowed to AI business tools for boring/unglamorous professions → landed on a specific niche: **RTB (Residential Tenancies Board) compliance tooling for small Irish letting agents**

## 2. The Problem

Small letting agencies (1–5 people) in Ireland are responsible for:
- **RTB registration** — now an **annual** filing requirement (changed from once every 4 years), easy to miss
- **RPZ (Rent Pressure Zone) rent-cap calculations** — statutory limits on rent increases, easy to miscalculate
- **Statutory notice periods** — minimum notice scales with tenancy length, another manual lookup

Most small agencies track this manually or in spreadsheets. Rules have gotten stricter and continue to change, and mistakes carry real financial/legal risk for landlords and agents.

## 3. Competitive Landscape (researched directly)

- **Property CRM (propertycrm.ie)** — the closest thing to a market leader for Irish estate/letting agents. 35 years established, used by real agencies (DNG, Jordan Auctioneers, Citadel Property Management). Covers sales, lettings, PSRA (estate agent licensing) compliance, AML, LOEs, client accounting.
  - **Key finding:** its compliance tools are PSRA/AML-focused, **not** RTB/RPZ-focused. No dedicated annual-registration reminder or rent-cap calculator found in its feature list.
  - Site weaknesses found: broken "free demo" CTA (links to `#`), no visible pricing, outdated copyright year, a likely PSRA/PRSA typo in their own feature list.
- **AgentPro** — UK-based, also used by some Irish agencies, similar breadth, less Irish-specific.
- **Standalone RPZ calculators** already exist for free — confirmed via search. This means a single-purpose rent-cap calculator alone is **not** a defensible product on its own.
- **No dedicated Irish AI-native RTB compliance tool found** — this remains a genuine, open gap.
- **No meaningful public review data exists** for this whole B2B category (no Trustpilot/G2/Capterra presence) — small Irish agencies aren't reviewing this kind of software online, which means direct validation conversations are the only real source of insight here.

## 4. Strategic Decision: Narrow Tool First, Not a Full Platform

Considered building a **full property management platform** (a Property CRM competitor) with RTB/RPZ built in from day one. Decided against this as a starting point:

| Full platform (rejected as MVP) | Narrow compliance tool (chosen) |
|---|---|
| Competes head-on with a 35-year incumbent | Sits alongside what agents already use |
| High switching cost for agents (must migrate all data) | Low-friction, "try it this week" adoption |
| Long, considered sales cycle | Fast sales cycle, easy free pilot |
| Months of scope before first real user test | Weeks to a working pilot |

**Chosen strategy: land-and-expand.** Win agencies with a sharp, cheap, easy-to-adopt compliance tool first. Only build toward a fuller platform once real paying customers are asking for it — this is already reflected in the Phase 2/3 roadmap below.

## 5. Does Building With AI Change This?

Yes, meaningfully — but selectively.

**What AI-assisted building genuinely cuts:**
- Time to build CRUD screens, dashboards, reminders, PDF generation
- Iteration speed — prototypes in a day instead of a sprint
- This *reinforces* starting narrow: the MVP becomes even faster and cheaper to reach

**What it does *not* cut:**
- Domain research — verifying real RTB/RPZ rules against actual legislation is human legwork, not code generation
- Trust and switching costs — an agency's willingness to rely on new software is a business decision, not an engineering one
- Real integrations (Daft.ie, MyHome.ie, DocuSign) — often partnership/approval processes, not just APIs
- Liability on high-stakes modules — compliance calculations and any future money-handling features need careful human verification regardless of how fast the first draft was written

**Conclusion:** AI tooling makes the chosen "narrow tool first" path faster and cheaper — it does not make the "build the full platform immediately" path a good idea.

## 6. Deliverables Already Produced

- **Working interactive HTML demo** — property register, RTB renewal status stamps, RPZ rent-cap calculator, notice-period lookup. Built to make validation conversations concrete rather than abstract. Explicitly marked "not verified against current RTB rules" to avoid misleading anyone.
- **Two-page product roadmap (Word doc)** — problem statement, target customer, three-phase feature roadmap, guardrails, go-to-market plan, current status table. Meant to be shown to co-founders and, cautiously, to early customer conversations.
- **Cold outreach email drafts** (validation-focused and direct-pitch versions)
- **A first list of small/independent letting agents** across Limerick, Ennis, and Newcastle West to approach

---

## 7. Full Product Direction

### Phase 0 — Validation (before writing significant code)

**Goal:** Confirm the pain is real and someone will pay, before building further.

1. Send outreach emails/calls to **15–20 small letting agents** (batch, not one at a time) — prioritise small, owner-led agencies over large sales-driven ones.
2. Follow up once after 3–4 days if no reply.
3. In every conversation, ask directly:
   - *"How do you currently track RTB registration deadlines and rent increase calculations — software, spreadsheet, or memory/experience?"*
   - *"Do you currently use an RPZ calculator or similar tool? What's missing from it?"*
   - *"Would you pay for this? Roughly how much?"*
4. Use the interactive demo on calls to make the conversation concrete.
5. Target milestone: **5 real, substantive conversations** within two weeks. If the pain isn't there or no one will pay, that's a signal to adjust — not a failure.
6. In parallel (not sequentially): read actual RTB.ie guidance directly, so the team can speak knowledgeably and start correcting the demo's placeholder logic.

**Team roles for this phase:**
- One person: outreach and calls (sales)
- One person: becomes the RTB/RPZ rules expert — starts reading every RTB circular, ideally gets time with a solicitor or experienced agent to sanity-check
- One person: keeps refining the demo/prototype based on what's learned in calls

### Phase 1 — Core MVP (Launch / Pilot)

**Goal:** 3–5 pilot agencies using it for free, giving real feedback and a testimonial.

- Property register — add/edit properties, tenants, tenancy dates, rent
- RTB registration tracking — auto-calculated renewal dates, compliance status per property
- Automated reminders — email/SMS before renewal deadlines
- Pre-filled RTB registration forms, ready for agent review and manual submission (no auto-submission)
- RPZ rent-cap calculator — checks proposed increases against the *verified, current* legal cap
- Notice-period lookup — correct statutory minimum notice by tenancy length, verified against current rules
- Multi-user accounts for small teams

**Build principle carried through from the AI-cost discussion:** compliance logic (rent cap, notice periods) must be **deterministic, human-verified code** — never AI-generated on the fly — even though AI tools may be used to help write and scaffold that code.

### Phase 2 — Expansion (once there are paying customers)

Only build what pilot customers actually ask for. Candidates:
- Document storage (leases, BER certs, deposit records)
- AI-assisted lease data extraction from uploaded PDFs
- Deposit protection tracking and return-deadline reminders
- BER certificate tracking and expiry alerts
- Compliance audit trail, exportable per property or portfolio
- Bulk actions across a whole property portfolio

### Phase 3 — Growth

- Client-facing compliance reports agents can show landlords
- Integrations with existing property management software (e.g. Property CRM, AgentPro) rather than requiring double entry
- Calendar sync (Google/Outlook)
- Rules-change alerts when RTB regulations update — a strong long-term differentiator, since it requires ongoing human maintenance a generic/international tool won't bother with
- Multi-branch/franchise support for larger agencies

**This is also the point — not before — where evolving toward a fuller property-management platform (competing more directly with Property CRM) could make sense, informed by real customer demand rather than a starting guess.**

### Guardrails (by design, throughout every phase)

- No auto-submission to the RTB — agent always reviews and submits manually
- No language framed as legal advice anywhere in the product — every compliance check is marked as an estimate to verify
- Compliance logic is deterministic, human-verified code, never an AI guess presented as fact
- Errors-and-omissions insurance worth pricing out once there are paying customers

### Go-to-Market (unchanged from roadmap, still current)

- Direct outreach to small independent letting agencies across Munster, expanding nationally
- Free pilot for first 3–5 agencies in exchange for feedback and a testimonial
- Distribution via property management Facebook/LinkedIn groups, landlord forums (askaboutmoney.com), and professional bodies (IPAV, SCSI)
- Pricing to validate directly with pilot customers: per-property (€3–5/month) vs. flat tier (€50–100/month for smaller agencies)

---

## 8. Immediate Next Actions

1. [ ] Finalise and personalise outreach email with real agency names
2. [ ] Call agencies where no contact name is available, ask for the right person
3. [ ] Send first batch of 15–20 outreach emails/calls
4. [ ] Begin reading RTB.ie guidance directly to start correcting the demo's placeholder rent-cap and notice-period logic
5. [ ] Log every conversation's answers (current tooling, pain points, willingness to pay) in one shared doc
6. [ ] Revisit this roadmap after 5 real conversations and adjust before writing further code
