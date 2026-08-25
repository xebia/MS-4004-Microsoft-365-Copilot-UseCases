![Acme Bottling — Microsoft 365 Copilot Curriculum](images/acme_banner.png)

# MS-4004.X — Empower your workforce with Microsoft 365 Copilot Use Cases
### Acme Bottling · role-based lab variants

> Based on the Microsoft course
> **[MS-4004: Empower your workforce with Microsoft 365 Copilot Use Cases](https://learn.microsoft.com/en-us/training/courses/ms-4004)**.
> The `.X` sessions here are Acme Bottling variants of that course's use-case exercises —
> same intent, one shared fictional company.

Welcome. This is the home page for a set of role-based, hands-on Microsoft 365 Copilot
labs built around one fictional company: **Acme Bottling Co.**

Each session is a **standalone lab** you can follow start to finish. But they all share
the **same company and the same master dataset**, so the whole curriculum feels like one
real place. Learn the Copilot skill in your lane, and you'll also see how your work
connects to everyone else's.

> **How to use these labs:** Just read this page and follow the steps in your session.
> You don't need to install anything, sign into GitHub, download a repo, or save any
> code. Everything you need is linked right in the lab. Open, read, do. That's it.

---

## The company: Acme Bottling Co.

Acme Bottling makes glass and PET bottles, caps and closures, and custom packaging for
beverage brands across the U.S. — breweries, juice and water companies, distillers, soda
and cold-brew makers. Think amber glass bottles, 1-liter PET, screw caps, crown caps,
shipper cartons, and labels.

Because it's fictional, you can practice freely. Nothing here is real customer or company data — it's all made up for training.

---

## The Sessions

Delivered in this order. Each lab runs about **60 minutes of hands-on** (up to ~75 min if
your group wants to go deeper) inside a ~90-minute session — roughly 15 min Copilot
refresher, the lab, then open Q&A. Every lab is two 30-minute exercises with the same
shape: **find the truth, then act on it.**

- **[`Session 1 — Supply Chain / Logistics`](sessions/MS-4004.X_Supply_Chain_Logistics.md)** —
  read an ERP order/shipment export for delays, exceptions, and missing data, decide who
  owns each next step (Acme, supplier, customer, carrier), then produce a manager status
  briefing in Word and a supplier escalation email in Outlook. Includes the
  orders/shipments export and the master reference workbook.

- **[`Session 2 — Marketing & Creative`](sessions/MS-4004.X_Marketing_and_Creative.md)** —
  build a launch campaign brief for the new 500 mL PET bottle with Researcher, write
  brand-safe copy from approved proof points, draft a 6-slide executive pitch deck and a
  sales enablement one-pager, then run a brand and usage-rights review pass. Includes the
  campaign goals brief, product catalog, and customers file.

- **[`Session 3 — Finance`](sessions/MS-4004.X_Finance.md)** — find variance drivers and
  anomalies in monthly actuals with the Analyst agent, make Copilot show its arithmetic
  and spot-check it, QA a messy AR aging sheet, then write a one-page CFO memo and a
  single leadership slide. Includes monthly actuals, an AR aging sheet with planted
  data-quality issues, the leadership audience profile, and the executive memo format.

- **`Session 4 — Customer Service (ACs)`** *(lab in development)* — summarize a long
  customer thread, cross-check it against the shipment data, build a PTO handoff, and
  draft a customer-ready reply. Includes the sample email thread, orders export, and
  master reference.

- **`Session 5 — Design & Engineering`** *(lab in development)* — analyze a CRM/opportunity
  export for aging deals and trends, flag data-quality gaps, and write a leadership
  summary + one slide. Includes a new opportunities export (with intentional messy rows)
  and the master reference. This one carries Kyle's note that it's the group most likely
  to raise big agent ideas.

- **[`Session 6 — Talent / HR`](sessions/MS-4004.X_Talent_HR.md)** — turn a Logistics
  Coordinator requisition into a competency-mapped, bias-checked interview guide, build a
  30-60-90 onboarding plan from messy manager notes, turn a skills gap into a prioritized
  learning path, and draft a change announcement in three formats. Includes the role
  description, onboarding notes, skills list, and change-communication brief.

- **`Session 7 — Legal`** *(lab in development)* — summarize a contract with Researcher,
  compare it clause-by-clause against Acme's standard-terms playbook, flag missing or
  non-standard terms, and produce an executive briefing. Includes a sample customer
  contract and the standard-terms playbook, plus the cite-the-playbook context workaround.

> **Note on IT:** The IT group is a **recap and debrief conversation**, not a hands-on
> lab. We walk their team through what everyone else learned and flag agent-readiness
> opportunities. No lab file needed.

> **Still to build:** sessions 4, 5, and 7 need both their lab file in `sessions/` and
> their artifacts in `data/` — the customer email thread, the CRM/opportunity export with
> messy rows, the sample customer contract, and the standard-terms playbook. Sessions 1,
> 2, 3, and 6 are complete and all their data files are in place.

---

## Shared-dataset

Every lab pulls from one **master shipment/order dataset** plus a few linked reference files (customers, products, suppliers, inventory). The same delayed order a Supply Chain learner investigates is the same customer Finance reviews for payment risk and the same product Marketing plans a launch around...etc.

That means:

- **One story, seven angles.** You see Acme Bottling from your role's point of view.
- **Consistent names and numbers.** Priya Shah, Cascade Craft Beverages, SKU-GB12 — they
  show up across labs, so the world holds together.
- **Realistic starting point.** Most labs begin with a spreadsheet "exported from Acme's
  ERP/CRM," just like your real Monday morning.

**Master files everyone shares** (in `data/`):

| File | What it is |
|------|------------|
| `AcmeBottling_Orders_Shipments.xlsx` | The backbone — orders, promised vs. actual dates, status, delay owner, exceptions |
| `AcmeBottling_Master_Reference.xlsx` | Customers, Products, Suppliers, Inventory, and Orders in one workbook |
| `AcmeBottling_Customers.csv` | Customer accounts, segments, regions, account managers |
| `AcmeBottling_Products.csv` | Product catalog (SKUs, sizes, materials, unit costs) |
| `AcmeBottling_Suppliers.csv` | Suppliers, what they supply, on-time status, quality scores |
| `AcmeBottling_Inventory.csv` | On-hand, committed, available, reorder flags |

**Role-specific files** (also in `data/`, used by one session each):

| File | Session |
|------|---------|
| `AcmeBottling_Campaign_Goals.md` | 2 — Marketing & Creative |
| `finance_monthly_actuals.xlsx` | 3 — Finance |
| `finance_spreadsheet_with_anomalies.xlsx` | 3 — Finance |
| `leadership_audience_profile.docx` | 3 — Finance |
| `executive_memo_format.docx` | 3 — Finance |
| `role_description.docx` | 6 — Talent / HR |
| `onboarding_scenario.docx` | 6 — Talent / HR |
| `skills_list.csv` | 6 — Talent / HR |
| `employee_comm_brief.docx` | 6 — Talent / HR |

> **Open the `.xlsx` files in Excel as-is — don't convert them to CSV.** Copilot in Excel
> needs the real workbook to analyze the data. The CSVs are just the raw source.

---

## The learning arc across Acme Bottling

Read top to bottom, the curriculum tells one story:

1. **Supply Chain** finds the delayed bottle orders and the exceptions behind them.
2. **Marketing** plans the launch those bottles are headed toward.
3. **Finance** checks the numbers underneath it all — variances, risk, reporting.
4. **Customer Service** handles the customers affected by delays and questions.
5. **Design & Engineering** looks across the CRM for trends and aging opportunities.
6. **Talent / HR** staffs and onboards the people who run all of it.
7. **Legal** protects the agreements holding the customer relationships together.

Same company. Same data. Seven jobs. One trusted way to use Copilot.

---

## What "intermediate" means here

You've already had foundational Copilot training and use it regularly. These labs skip
the basics and get straight into real role scenarios. Each session teaches **only the
Copilot capabilities that genuinely serve that job** — no feature tours, no filler. See
the full role → feature-map in [Acme_Bottling_Company_Kit.md](Acme_Bottling_Company_Kit.md).
