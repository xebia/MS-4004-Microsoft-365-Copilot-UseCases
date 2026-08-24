# Session 1 — Supply Chain / Logistics Hands-On Lab
### Acme Bottling · Microsoft 365 Copilot

**Audience:** Supply chain and logistics team members who already use Copilot and want to
work faster on shipment status, exceptions, and escalations.
**Format:** ~60 minutes of hands-on (up to ~75 if your group goes deep), inside a
~90-minute session.
**Level:** Intermediate. We skip the basics and get straight into real Acme Bottling work.

You'll start from a spreadsheet exported from Acme's ERP — exactly like your real Monday
morning — and leave with reusable prompts you can drop into your own reports.

> **How to use this lab:** Just read and follow along. Nothing to install, no repo to
> download, no code to save. Open the files linked below and go.

---

## What you'll be able to do

- Analyze an order/shipment export to find delays, exceptions, and missing information.
- Decide who owns the next step — Acme, a supplier, a customer, or the carrier.
- Turn a messy export into a clear status briefing for a manager.
- Build reusable prompts for report analysis, exception ID, status briefings, and
  escalations.
- Keep your Copilot work clean and trustworthy with a simple validation habit.

## Before you start

- You have a licensed **Microsoft 365 Copilot** account and can open **Excel, Word,
  Outlook, and Copilot Chat** on the desktop.
- Download the two files you'll use. **Open them in Excel as-is — do not convert to CSV.**
  Copilot in Excel needs the real workbook to analyze the data.
  - **Orders/shipments export** — `AcmeBottling_Orders_Shipments.xlsx`
    Download: `<ARTIFACT_URL>`
  - **Master reference workbook** (customers, products, suppliers, inventory) —
    `AcmeBottling_Master_Reference.xlsx`
    Download: `<ARTIFACT_URL>`

> **Copilot capabilities in this lab:** Excel, Copilot Chat / Researcher, Word, Outlook.
> We're skipping PowerPoint and image tools — they don't serve this job today.

---

## The one rule to protect

**Copilot assists. A human validates.** At the end of every exercise you'll name the
source Copilot used, the assumptions it made, the risk, and what you must check before
acting. Copilot speeds up the work — you make the call.

---

# Exercise 1 — Find what's slipping (about 30 min)

**Scenario:** It's Monday. You've exported open and recent orders from Acme's ERP. A few
customers are asking where their bottles are. Let's find the problems fast.

### Task 1 — Open the export and get a clean read (8 min)

1. Open `AcmeBottling_Orders_Shipments.xlsx` in Excel.
2. Open **Copilot** in Excel (Home tab → Copilot).
3. Paste this prompt:

   ```
   You are helping me review this order/shipment export. Give me a plain-English
   summary: how many orders total, how many are Delivered, In Transit, Delayed,
   Processing, or On Hold, and how many rows are missing a Status, Quantity, or
   PromisedDate. List the missing-data rows by OrderID. Do not guess missing values.
   ```
4. Read the summary. Notice Copilot flags the rows with blanks instead of filling them in.

> **Why this matters:** Real exports are messy. You want Copilot to surface gaps, not
> paper over them.

### Task 2 — Find the delays and who owns them (8 min)

1. In the same Copilot pane, paste:

   ```
   From this data, list every order where Status is Delayed or On Hold. For each, show
   OrderID, CustomerID, SKU, PromisedDate, DelayOwner, and ExceptionNote. Group them by
   DelayOwner (Acme, Supplier, Customer, Carrier). Which owner has the most delays?
   ```
2. You now have a delay picture sorted by who needs to act.

### Task 3 — Add customer and supplier context (8 min)

1. Open `AcmeBottling_Master_Reference.xlsx` so you can see customer and supplier names.
2. Back in Copilot Chat (or Excel Copilot), paste:

   ```
   For the delayed and on-hold orders, help me translate IDs to names. Customer CUST-1001
   is Cascade Craft Beverages, CUST-1002 is Sunrise Juice Co., CUST-1004 is Blue Ridge
   Springs (Net 60), and CUST-1007 is Summit Sparkling. Supplier SUP-202 (PolyForm
   Resins) is flagged "at risk" and SUP-204 (GreenLeaf Packaging) is "delayed." Re-list my
   delays using names, and call out any delay tied to an at-risk or delayed supplier.
   ```
3. Now the story reads in business terms: which customers, which shaky suppliers.

### Validation checkpoint (6 min)

Answer these four before moving on — this is the rule in action:

- **Source:** Which file(s) did Copilot use? (The ERP export; you supplied the name lookups.)
- **Assumptions:** Did it assume anything about blank rows or dates? Did it guess?
- **Risk:** What would go wrong if you sent this list as-is? (Missing statuses = blind spots.)
- **Human check:** Which 2–3 orders will you personally verify before escalating?

---

# Exercise 2 — Turn findings into action (about 30 min)

**Scenario:** Your manager wants a quick status read, and one delayed order needs to be
escalated to a supplier. Let's produce both — cleanly.

### Task 1 — Keep your context clean (7 min)

Good habit before you generate anything customer-specific:

1. In OneDrive, create a folder named **`Acme - Blue Ridge Springs`**.
2. Save a copy of the orders export and reference workbook into it.
3. When you prompt about this customer, work from that folder / a fresh chat so Copilot
   references only Blue Ridge material — nothing bleeds in from other accounts.

> **Why:** One folder, one clean chat per customer keeps outputs accurate and easy to trust.

### Task 2 — Build a manager status briefing in Word (9 min)

1. Open a new **Word** document in the Blue Ridge folder.
2. Open **Copilot in Word** and paste:

   ```
   Draft a one-page operational status briefing for my manager about Blue Ridge Springs
   (CUST-1004). Use these facts: they have delayed and on-hold orders, one tied to a
   customer credit hold and one to a delayed packaging supplier (GreenLeaf). Structure it
   as: What's delayed, Who owns the next step, What needs escalation, What to monitor.
   Keep it under 250 words, plain English, no filler. End with an "Assumptions & to
   verify" line.
   ```
3. Review and tighten. Confirm the "Assumptions & to verify" line is there.

### Task 3 — Draft an escalation email in Outlook (8 min)

1. Open **Outlook**, start a new email, open **Copilot**.
2. Paste:

   ```
   Draft a short, professional escalation email to GreenLeaf Packaging (supplier SUP-204)
   about a delayed carton shipment affecting a Blue Ridge Springs order. Ask for a firm
   revised ship date and a reason for the delay. Friendly but direct, under 120 words.
   Leave a placeholder for the OrderID and promised date so I can fill them in.
   ```
3. Read it, drop in the real OrderID, and you've got an escalation ready to send after review.

### Task 4 — Save your prompt library (6 min)

You just wrote four reusable prompts. Keep them. Create a Word doc titled
**"Acme Supply Chain — Prompt Library"** and paste in:

1. **Report analysis prompt** (Ex.1 Task 1 — summarize + flag missing data)
2. **Delay & exception prompt** (Ex.1 Task 2 — group by DelayOwner)
3. **Status briefing prompt** (Ex.2 Task 2 — manager one-pager)
4. **Escalation email prompt** (Ex.2 Task 3 — supplier follow-up)

These are your leave-behind. Adapt the names and SKUs to whatever you're working next week.

### Validation checkpoint (5 min)

- **Source:** Did the briefing and email use only Blue Ridge facts from your clean folder?
- **Assumptions:** Anything Copilot inferred about dates, blame, or next steps?
- **Risk:** What's the cost of sending the escalation without checking the OrderID?
- **Human check:** Who signs off before this goes to the supplier?

---

## Facilitator notes

- **Data hygiene:** The clean-folder step in Ex.2 Task 1 is the teachable habit — one
  customer, one folder, one clean chat.
- **Capture agent ideas:** If someone says "I wish this whole exception review just ran
  itself every morning" — that's a real agent opportunity. Capture it and send it to
  **Chris Bartlow**. Don't build it here; keep this lab current-state Copilot.
- **Timing:** If the group is fast, spend the extra time letting them rerun the prompts on
  a different customer (Cascade Craft or Summit Sparkling) from the same dataset.

## Recommended close (read this)

- Today we focused on what your team can do now with Microsoft 365 Copilot.
- The next opportunity is to identify repeatable patterns that could become governed agent
  workflows once the right data, permission, security, and process guardrails are in place.
- The outputs from this session should feed a prompt library now and an agent-readiness
  roadmap later.
