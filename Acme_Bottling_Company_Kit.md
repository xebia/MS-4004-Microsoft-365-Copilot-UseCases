# Acme Bottling — Canonical Company Kit

This is the shared foundation behind every lab. It gives all seven sessions the same
company, the same people, and the same data, so the curriculum feels like one real place.
Trainers: read this once and you'll understand every scenario. Students: you'll meet
these names and files in your lab.

> **Every lab is standalone.** A learner can take one session and never touch another.
> This kit is what makes the world consistent *across* them — it isn't a prerequisite for
> any single lab, and no lab references another by name or number.

---

## 1. Company profile

**Acme Bottling Co.** — a fictional bottle and packaging manufacturer serving U.S.
beverage brands.

- **What they make:** glass bottles (amber and flint), PET bottles, caps and closures
  (screw, sports, crown), shipper cartons, and pressure-sensitive labels.
- **Who they sell to:** breweries, juice and water companies, distillers, soda and
  cold-brew makers.
- **Footprint:** four U.S. regions — West, Midwest, East, South.
- **How work flows:** orders come in from customers, Acme sources materials from
  suppliers, produces and ships through several carriers, and tracks everything in an
  ERP/CRM that people export to Excel to actually get their jobs done.

Everything is invented for training. There is no real customer or company data here.

---

## 2. The recurring cast

These names appear across labs so the world stays consistent.

**Inside Acme**

| Person | Role at Acme | Appears in |
|--------|--------------|------------|
| Nora Whitfield | CFO | Finance |
| Priya Shah | Account Manager (West — Cascade Craft, Summit Sparkling) | Customers data |
| Tom Alvarez | Account Manager (East — Blue Ridge Springs, Harbor Cold Brew) | Customer Service thread |
| Marcus Lee | Account Manager (West — Sunrise Juice) | Customers data |
| Dana Kowalski | Account Manager (Midwest — Northwind Distilling) | Customers data |
| Elena Fisher | Account Manager (Midwest — Prairie Kombucha) | Customers data |
| Ray Nguyen | Account Manager (South — Gulf Coast Sodas) | Customers data |

**Customer-side contacts**

| Person | Role | Appears in |
|--------|------|------------|
| Sarah Kettner | Procurement, Blue Ridge Springs | Customer Service |
| Mia Torres | Line Operations, Blue Ridge Springs | Customer Service |

> **Naming rule:** keep first names unique across the cast. If you add a character, check
> this table first — two people sharing a first name makes a prompt ambiguous.

Key customers: **Cascade Craft Beverages, Sunrise Juice Co., Northwind Distilling, Blue
Ridge Springs, Prairie Kombucha, Gulf Coast Sodas, Summit Sparkling, Harbor Cold Brew.**

Key suppliers: **Meridian Glassworks, PolyForm Resins (at risk), CapTech Industries,
GreenLeaf Packaging (delayed), Clearview Colorants.**

The open hire used in the Talent / HR lab is a **Logistics Coordinator** for the Midwest
DC.

---

## 3. The data files

All live in the `data/` folder of the repo. **Every filename starts with `AcmeBottling_`**
— keep that convention when you add one.

**Shared across labs**

| File | Format | Purpose |
|------|--------|---------|
| `AcmeBottling_Orders_Shipments` | .xlsx / .csv | **The backbone.** Every order with dates, status, delay owner, exceptions. |
| `AcmeBottling_Master_Reference` | .xlsx | Six tabs in one workbook: Customers, Products, Suppliers, Inventory, Orders, Opportunities. |
| `AcmeBottling_Customers` | .csv | Accounts, segments, regions, account managers, terms, tier. |
| `AcmeBottling_Products` | .csv | SKU catalog, sizes, materials, colors, unit cost. |
| `AcmeBottling_Suppliers` | .csv | Suppliers, what they supply, on-time status, quality score. |
| `AcmeBottling_Inventory` | .csv | On-hand, committed, available, reorder flags. |

**Role-specific** — used by exactly one lab each

| File | Lab | What it is |
|------|-----|------------|
| `AcmeBottling_Campaign_Goals.md` | Marketing & Creative | Launch input brief with approved proof points — one of which deliberately doesn't reconcile with the product catalog. |
| `AcmeBottling_Finance_Monthly_Actuals.xlsx` | Finance | Budget vs actual by region and product line, plus a YTD tab. |
| `AcmeBottling_Finance_AR_Aging.xlsx` | Finance | AR aging sheet with planted data-quality issues. |
| `AcmeBottling_Leadership_Audience_Profile.docx` | Finance | Who the memo is for and what "good" looks like. |
| `AcmeBottling_Executive_Memo_Format.docx` | Finance | The memo structure the Word output must match. |
| `AcmeBottling_Customer_Thread.md` | Customer Service | Long Blue Ridge Springs email thread about ORD-5006. |
| `AcmeBottling_Opportunities.xlsx` | Design & Engineering | CRM/opportunity export with intentional messy rows. |
| `AcmeBottling_Role_Description.docx` | Talent / HR | Logistics Coordinator requisition. |
| `AcmeBottling_Onboarding_Notes.docx` | Talent / HR | Rough manager notes with a deliberate TBD gap. |
| `AcmeBottling_Skills_List.csv` | Talent / HR | Current vs target skill levels with priorities. |
| `AcmeBottling_Employee_Comm_Brief.docx` | Talent / HR | Change-announcement brief with tone notes. |
| `AcmeBottling_Customer_Contract_Sample.md` | Legal | Sanitized Northwind Distilling supply agreement. |
| `AcmeBottling_Standard_Terms.md` | Legal | Acme's approved standard-language playbook. |

> **Open the `.xlsx` files in Excel as-is — don't convert to CSV.** Copilot in Excel needs
> the real workbook. The CSVs are the raw source behind those workbooks.

### Data dictionary — Orders/Shipments backbone

| Column | Meaning |
|--------|---------|
| OrderID | Unique order number (e.g., ORD-5001) |
| CustomerID | Links to Customers file (e.g., CUST-1001) |
| SKU | Links to Products file (e.g., SKU-GB12) |
| Quantity | Units ordered (some rows blank on purpose — a data-quality teaching moment) |
| SupplierID | Links to Suppliers file (e.g., SUP-201) |
| OrderDate | When the order was placed |
| PromisedDate | Date committed to the customer (some blank on purpose) |
| ActualDeliveryDate | Filled only when Delivered |
| Status | Delivered, In Transit, Delayed, Processing, On Hold (some blank on purpose) |
| Carrier | Ridgeline Freight, BlueDart Logistics, Interstate Haulers, Acme Fleet |
| DelayOwner | Who caused a delay: Acme, Supplier, Customer, Carrier (blank if none) |
| ExceptionNote | Short reason, e.g., "Supplier material shortage," "Customer hold - credit" |

> **The messy rows are intentional.** A few records have missing quantity, promised date,
> or status. Labs use these to teach the data-quality and validation habit — Copilot
> should flag what's missing, not quietly fill it in. Three files carry planted defects on
> purpose: `AcmeBottling_Orders_Shipments` (blank quantity / promised date / status),
> `AcmeBottling_Finance_AR_Aging` (bad dates, mis-bucketed invoice, negative amount,
> status typo), and `AcmeBottling_Opportunities` (blank Stage, LastActivityDate,
> EstValueUSD). `AcmeBottling_Onboarding_Notes` carries a deliberate "TBD."
> `AcmeBottling_Campaign_Goals` carries a deliberate **claim mismatch**: the approved proof
> point says PET500 is "30% below comparable glass (SKU-GB16)," but the catalog shows
> $0.15 vs $0.55 (≈73% lower). Marketing uses it to teach claim substantiation — flag and
> escalate, never silently restate an approved claim.

---

## 4. Role → Copilot feature-map (only what serves the job)

A hard rule for this curriculum: **each session teaches only the Copilot capabilities
that genuinely help that role.** No feature tours, no filler. This map is the guardrail.

| Session | Copilot capabilities we DO teach | We intentionally SKIP |
|---------|----------------------------------|-----------------------|
| **Supply Chain / Logistics** | Copilot in **Excel** (analyze the export), **Copilot Chat** (exception analysis, follow-up questions), **Word** (status briefing), **Outlook** (escalation email) | Researcher, PowerPoint decks, image generation |
| **Marketing & Creative** | **Researcher** (market/competitive research, campaign brief), **Copilot Chat** (claim substantiation, brand-safe copy, event comms, brand-risk pass), **PowerPoint** (exec presentation), **Word** (one-pager) | Deep Excel analysis, heavy image gen (their creative work lives in Adobe) |
| **Finance** | Copilot in **Excel** (overview, spreadsheet QA), **Copilot Chat / Analyst** (variance and anomaly analysis), **Word** (finance memo), **PowerPoint** (one summary slide) | Researcher, Outlook, Teams meeting features |
| **Customer Service (ACs)** | **Copilot Chat** (thread summary, claimed-vs-confirmed split, exception list), **Word** (PTO handoff brief), **Outlook** (customer-ready reply), light **Excel** lookup | PowerPoint, Researcher, complex Excel modeling |
| **Design & Engineering** | Copilot in **Excel** (data-quality review, opportunity aging), **Copilot Chat** (trend analysis), **Word** (leadership summary), **PowerPoint** (one slide) | Outlook workflows, image generation |
| **Talent / HR** | **Researcher** (role analysis, interview guide, bias pass), **Word** (onboarding plan, employee comms), **Excel** (skills-gap learning path) | Outlook, PowerPoint decks, image generation |
| **Legal** | **Researcher** (contract summary with citations), **Copilot Chat** (clause comparison vs. standard language, conclusion check), **Word** (executive briefing, talking points) | Excel, PowerPoint, image generation |

> **Every lab also teaches two habits, identically:** a **custom instruction** set in
> Copilot Chat → Settings → Personalization as Task 1, and a **clean folder / new chat**
> per customer, campaign, review, or matter.

---

## 5. The one rule to protect (in every lab)

**Copilot assists. A human validates.** Each exercise closes with: source used,
assumptions made, risk, and required human check. This is non-negotiable across all
seven sessions.

## 6. Facilitator reminders (all labs)

- **Data hygiene:** teach one folder / one clean chat per customer or scenario so Copilot
  references only the right material.
- **Capture agent ideas:** if a learner surfaces a big "this would change how we work
  every day" idea, capture it and route it to **Chris Bartlow** — don't build it in
  session. (Six of eight groups have a real agent opportunity; Design & Engineering is
  the most likely to raise ambitious ones.)
- **Keep agents future-state.** These labs are current-state Copilot only.

## 7. Recommended close (use this exact wording, every session)

- Today we focused on what your team can do now with Microsoft 365 Copilot.
- The next opportunity is to identify repeatable patterns that could become governed agent
  workflows once the right data, permission, security, and process guardrails are in place.
- The outputs from this session should feed a prompt library now and an agent-readiness
  roadmap later.
