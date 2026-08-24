# Acme Bottling — Canonical Company Kit

This is the shared foundation behind every lab. It gives all seven sessions the same
company, the same people, and the same data, so the curriculum feels like one real place.
Trainers: read this once and you'll understand every scenario. Students: you'll meet
these names and files in your lab.

---

## 1. Company profile

**Acme Bottling Co.** — a fictional bottle and packaging manufacturer serving U.S. beverage brands.

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

| Person | Role at Acme |
|--------|--------------|
| Priya Shah | Account Manager (West — Cascade Craft, Summit Sparkling) |
| Tom Alvarez | Account Manager (East — Blue Ridge Springs, Harbor Cold Brew) |
| Marcus Lee | Account Manager (West — Sunrise Juice) |
| Dana Kowalski | Account Manager (Midwest — Northwind Distilling) |
| Elena Fisher | Account Manager (Midwest — Prairie Kombucha) |
| Ray Nguyen | Account Manager (South — Gulf Coast Sodas) |

Key customers: **Cascade Craft Beverages, Sunrise Juice Co., Northwind Distilling, Blue
Ridge Springs, Prairie Kombucha, Gulf Coast Sodas, Summit Sparkling, Harbor Cold Brew.**

Key suppliers: **Meridian Glassworks, PolyForm Resins (at risk), CapTech Industries,
GreenLeaf Packaging (delayed), Clearview Colorants.**

---

## 3. The master files (shared by all labs)

Stored in the `/data/` folder of the repo.

| File | Format | Purpose |
|------|--------|---------|
| `data/AcmeBottling_Orders_Shipments` | .xlsx / .csv | **The backbone.** Every order with dates, status, delay owner, exceptions. |
| `data/AcmeBottling_Master_Reference` | .xlsx | All tables in one workbook (Customers, Products, Suppliers, Inventory, Orders). |
| `data/AcmeBottling_Customers` | .csv | Accounts, segments, regions, account managers, terms, tier. |
| `data/AcmeBottling_Products` | .csv | SKU catalog, sizes, materials, colors, unit cost. |
| `data/AcmeBottling_Suppliers` | .csv | Suppliers, what they supply, on-time status, quality score. |
| `data/AcmeBottling_Inventory` | .csv | On-hand, committed, available, reorder flags. |

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
> should flag what's missing, not quietly fill it in.

---

## 4. Role → Copilot feature-map (only what serves the job)

A hard rule for this curriculum: **each session teaches only the Copilot capabilities
that genuinely help that role.** No feature tours, no filler. This map is the guardrail.

| Session | Copilot capabilities we DO teach | We intentionally SKIP |
|---------|----------------------------------|-----------------------|
| **Supply Chain / Logistics** | Copilot in **Excel** (analyze the export), **Copilot Chat/Researcher** (exception analysis, follow-up questions), **Word** (status briefing), **Outlook** (escalation email) | PowerPoint decks, image generation, Loop |
| **Marketing & Creative** | **Researcher** (campaign brief), **Copilot Chat** (brand-safe copy), **PowerPoint** (exec presentation), **Word** (one-pager) | Deep Excel analysis, heavy image gen (their creative work lives in Adobe) |
| **Finance** | Copilot in **Excel** (variance, anomaly, QA), **Word** (finance memo), **PowerPoint** (one summary slide) | Researcher-heavy web tasks, Teams meeting features |
| **Customer Service (ACs)** | **Copilot Chat** (thread summary, exception list), **Outlook** (customer-ready reply, PTO handoff), **Word** (response template) | PowerPoint, Researcher, complex Excel modeling |
| **Design & Engineering** | Copilot in **Excel** (opportunity aging, trends), **Copilot Chat/Analyst** (data-quality review), **Word/PowerPoint** (leadership summary) | Outlook workflows, image generation |
| **Talent / HR** | **Researcher** (job analysis), **Copilot Chat** (interview guide, learning path), **Word** (onboarding plan), **Outlook** (employee comms) | Excel-heavy analysis, PowerPoint decks |
| **Legal** | **Researcher** (multi-doc contract summary + citations), **Copilot Chat** (clause comparison vs. standard language), **Word** (executive briefing) | Excel, PowerPoint, image generation |

---

## 5. The one rule to protect (in every lab)

**Copilot assists. A human validates.** Each exercise closes with: source used,
assumptions made, risk, and required human check. This is non-negotiable across all
seven sessions.

## 6. Facilitator reminders (all labs)

- **Data hygiene:** teach one folder / one clean chat per customer or scenario so Copilot
  references only the right material.
- **Keep agents future-state.** These labs are current-state Copilot only. If a learner
  surfaces a big "this would change how we work every day" idea, capture it for follow-up
  outside the session — don't build it here.

## 7. Recommended close (use this exact wording, every session)

- Today we focused on what your team can do now with Microsoft 365 Copilot.
- The next opportunity is to identify repeatable patterns that could become governed agent
  workflows once the right data, permission, security, and process guardrails are in place.
- The outputs from this session should feed a prompt library now and an agent-readiness
  roadmap later.
