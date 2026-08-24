# Session 2 — Marketing & Creative Hands-On Lab
### Acme Bottling · Microsoft 365 Copilot

**Audience:** Marketing and creative team members who already use Copilot and want to move
faster on briefs, copy, and pitch decks.
**Format:** ~60 minutes of hands-on (up to ~75 if your group goes deep), inside a
~90-minute session.
**Level:** Intermediate. We skip the basics and get straight into real Acme Bottling work.

You're launching Acme's new **500 mL recyclable PET bottle**. You'll use Copilot to build
a campaign brief, an executive pitch deck, and brand-safe copy — and leave with reusable
prompts.

> **How to use this lab:** Just read and follow along. Nothing to install, no repo to
> download, no code to save. Open the files linked below and go.

---

## What you'll be able to do

- Build a campaign brief from goals and proof points using Researcher.
- Draft an executive presentation from that brief.
- Write brand-safe marketing copy that stays inside approved rules.
- Build reusable prompts for briefs, content, presentations, and brand-safe reviews.
- Keep a validation habit so nothing goes out without a human check.

## Before you start

- You have a licensed **Microsoft 365 Copilot** account and can open **Word, PowerPoint,
  and Copilot Chat / Researcher** on the desktop.
- Download the files you'll use:
  - **Campaign input brief** — `AcmeBottling_Campaign_Goals.md`
    Download: `<ARTIFACT_URL>`
  - **Product catalog** (for accurate SKU and spec references) —
    `AcmeBottling_Products.csv`
    Download: `<ARTIFACT_URL>`
  - **Customers file** (to name the featured accounts) — `AcmeBottling_Customers.csv`
    Download: `<ARTIFACT_URL>`

> **Copilot capabilities in this lab:** Researcher, Copilot Chat, Word, PowerPoint.
> We're keeping heavy Excel analysis and image generation out — your real creative work
> lives in Adobe, and Copilot's job here is briefs, copy, and decks.

---

## The one rule to protect

**Copilot assists. A human validates.** Every exercise ends with source, assumptions,
risk, and a human check — including a **brand and usage-rights review**, since Copilot
can't guarantee perfect brand or image fidelity.

---

# Exercise 1 — From goals to a campaign brief (about 30 min)

**Scenario:** Leadership approved the new PET line. You have goals and proof points. Turn
them into a brief the sales and creative teams can run with.

### Task 1 — Keep your context clean (6 min)

1. In OneDrive, create a folder named **`Acme - PET500 Launch`**.
2. Save the campaign input brief, product catalog, and customers file into it.
3. Work from this folder / a fresh chat so Copilot uses only approved launch material —
   nothing from other campaigns bleeds in.

> **Why:** One folder, one clean chat keeps your copy on-brand and on-message.

### Task 2 — Build the campaign brief with Researcher (10 min)

1. Open **Copilot Chat** and switch on **Researcher**.
2. Attach `AcmeBottling_Campaign_Goals.md` and paste:

   ```
   Using only the attached campaign input brief, build a one-page campaign brief for
   Acme Bottling's new 500 mL recyclable PET bottle (SKU-PET500). Include: objective,
   target audience, three key messages built from the approved proof points, the featured
   customers (Sunrise Juice, Blue Ridge Springs, Prairie Kombucha), and a simple success
   metric. Practical, confident tone — no hype words. Do not invent claims beyond the
   proof points. End with an "Assumptions & to verify" line.
   ```
3. Review. Confirm every claim traces back to the input brief.

### Task 3 — Draft brand-safe launch copy (8 min)

1. In the same clean chat, paste:

   ```
   Write three short pieces of launch copy from this brief: (1) a 40-word LinkedIn post,
   (2) a two-sentence email subject + preview line, (3) a 60-word sales one-liner.
   Follow the brand rules: practical and confident, no hype words, no new claims. Use only
   the approved proof points. Flag anything you're unsure about instead of guessing.
   ```
2. Read for tone. Mark anything Copilot flagged for you to confirm.

### Validation checkpoint (6 min)

- **Source:** Did Copilot use only the attached brief, or did it reach outside it?
- **Assumptions:** Any claim that isn't in the approved proof points?
- **Risk:** What happens if an unverified claim ships in a public post?
- **Human check:** Who approves brand tone and usage rights before anything goes live?

---

# Exercise 2 — Build the executive pitch (about 30 min)

**Scenario:** Sales leadership wants a short deck to open PET line conversations. Build it
from your brief — fast, clean, on-brand.

### Task 1 — Draft the deck in PowerPoint (12 min)

1. Open a new **PowerPoint** in your launch folder.
2. Open **Copilot in PowerPoint** and paste:

   ```
   Create a 6-slide executive pitch deck for Acme Bottling's new 500 mL recyclable PET
   bottle. Base it on my campaign brief. Slides: (1) title, (2) the opportunity, (3) three
   key messages, (4) proof points (18% lighter, 100% recyclable, 30% lower cost than glass),
   (5) featured customers, (6) call to action. Keep text tight — short bullets, no
   paragraphs. Do not add stock images or logos; leave image placeholders labeled
   "approved product photo here."
   ```
3. Review the flow. Note where you'll drop the approved product photo.

> **Brand-safe reminder:** Copilot may not match brand templates or images perfectly.
> That's expected — you place approved assets and review before sharing.

### Task 2 — Turn the deck into a one-pager (8 min)

1. Open a new **Word** doc in the same folder.
2. Open **Copilot in Word** and paste:

   ```
   From my campaign brief and pitch deck content, write a one-page sales enablement
   sheet for the PET500 launch: a short intro, the three key messages, the proof points as
   a tight bullet list, and a "who to call" line naming the featured customers' segments.
   Under 250 words, no hype. End with an "Assumptions & to verify" line.
   ```
3. Tighten and confirm the verify line is present.

### Task 3 — Save your prompt library (5 min)

Create a Word doc titled **"Acme Marketing — Prompt Library"** and paste in your four
reusable prompts:

1. **Campaign brief prompt** (Ex.1 Task 2)
2. **Brand-safe content prompt** (Ex.1 Task 3)
3. **Presentation draft prompt** (Ex.2 Task 1)
4. **One-pager / sales enablement prompt** (Ex.2 Task 2)

This is your leave-behind. Swap in the next product or campaign and reuse.

### Validation checkpoint (5 min)

- **Source:** Did the deck and one-pager stay inside the approved brief and proof points?
- **Assumptions:** Did Copilot add any claim, image, or logo it shouldn't have?
- **Risk:** What's the cost of shipping off-brand visuals or an unapproved claim?
- **Human check:** Who does the final brand + usage-rights review before this goes out?

---

## Facilitator notes

- **Data hygiene:** The clean-folder step (Ex.1 Task 1) is the teachable habit — one
  campaign, one folder, one clean chat.
- **Brand reality:** Reinforce that Copilot won't perfectly follow brand templates or
  generate brand-safe imagery. Teach method and source control, not image generation.
- **Capture agent ideas:** If someone imagines "a brand-checker that reviews every draft
  automatically," that's a real agent opportunity — capture it and route to **Chris
  Bartlow**. Keep this lab current-state Copilot.
- **Timing:** Fast groups can rerun the brief for a second product (SKU-GB16 flint glass)
  from the same catalog.

## Recommended close (read this)

- Today we focused on what your team can do now with Microsoft 365 Copilot.
- The next opportunity is to identify repeatable patterns that could become governed agent
  workflows once the right data, permission, security, and process guardrails are in place.
- The outputs from this session should feed a prompt library now and an agent-readiness
  roadmap later.
