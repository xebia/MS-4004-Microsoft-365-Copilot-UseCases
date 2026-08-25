# MS-4004.X — Finance Hands-On Lab

> **Supporting artifacts this lab references** (download before you start; replace the placeholder URL):
> - `finance_monthly_actuals.xlsx` — `<ARTIFACT_URL>/finance_monthly_actuals.xlsx`
> - `finance_spreadsheet_with_anomalies.xlsx` — `<ARTIFACT_URL>/finance_spreadsheet_with_anomalies.xlsx`
> - `leadership_audience_profile.docx` — `<ARTIFACT_URL>/leadership_audience_profile.docx`
> - `executive_memo_format.docx` — `<ARTIFACT_URL>/executive_memo_format.docx`
>
> `<ARTIFACT_URL>` = your GitHub raw path, e.g. `https://raw.githubusercontent.com/<org>/<repo>/main/data`

**Audience:** Finance team members (analysts, accountants, FP&A, finance managers)
**Duration:** ~60 minutes
**Base module:** MS-4004.X Finance module
**Primary tool:** Microsoft 365 Copilot (desktop / work experience)
**Company world:** Acme Bottling — the same packaging business used across the curriculum. The revenue lines here (glass bottles, PET bottles, closures, cartons/labels, pumps/sprayers) and regions tie back to the Supply Chain shipment data, so numbers reconcile if you take more than one session.

In this lab you'll use Microsoft 365 Copilot to move from raw finance data to a reviewed, executive-ready story. You'll analyze a budget-vs-actual report, catch anomalies and data-quality issues, QA a messy spreadsheet, write a finance memo, and build a one-slide leadership summary — then save a reusable prompt library. Every output ends with a validation step, because in Finance the control matters as much as the answer.

> **Ground rules for this lab**
> - Copilot works from the **files you give it** — it is not wired into your GL, ERP, or BI here.
> - Use only the **dummy/sanitized data** provided. Never paste real financial records.
> - Copilot **accelerates review and communication** — it does **not** replace financial judgment. Every figure it produces is an estimate until a human confirms it.
> - Any "auto-close" or "agent that reconciles the ledger" idea is **future-state** — we note it, we don't build it today.

---

## Learning objectives

By the end of this lab you'll be able to:

- Set **custom instructions** so Copilot writes in a finance-appropriate, controls-first voice.
- Use **Copilot in Excel** and the **Analyst** capability to find variance drivers, anomalies, and missing values.
- QA a messy spreadsheet — bad dates, wrong buckets, negative/zero amounts — with a repeatable prompt.
- Draft a **finance memo** in Word that separates confirmed facts from estimates.
- Build a **one-slide executive summary** in PowerPoint tailored to a named audience.
- Save 3–5 reusable prompts to a **Prompt Library** and apply the source/assumption/risk/human-review check to every output.

---

## Prerequisites

- A licensed **Microsoft 365 Copilot** account (work sign-in).
- Desktop apps: **Excel, Word, PowerPoint**, plus **Copilot Chat** (Teams or the work experience).
- Access to the **Analyst** agent and the **Prompt Library** in Copilot Chat.
- **OneDrive/SharePoint** to save working files, and a **GitHub.com** repo for your finished `.md`.

---

## Materials & downloads

Download these four files and save them to your lab folder.

| Artifact | What it is | Download |
|---|---|---|
| `finance_monthly_actuals.xlsx` | Budget vs actual revenue and gross margin by region and product line (with a YTD tab) | Download: `<ARTIFACT_URL>/finance_monthly_actuals.xlsx` |
| `finance_spreadsheet_with_anomalies.xlsx` | An AR aging sheet with planted data-quality issues to catch | Download: `<ARTIFACT_URL>/finance_spreadsheet_with_anomalies.xlsx` |
| `leadership_audience_profile.docx` | Who you're writing for (CFO + regional GMs) and what "good" looks like | Download: `<ARTIFACT_URL>/leadership_audience_profile.docx` |
| `executive_memo_format.docx` | The memo structure your Word output should match | Download: `<ARTIFACT_URL>/executive_memo_format.docx` |

---

## Setup: tune Copilot before you start (5 min)

Before the exercises, set a **custom instruction** so every response fits Finance. In Copilot Chat, open your profile/settings and add a personal instruction like:

```
When I work with finance data: be precise and controls-first. Lead with the headline
number and the biggest driver. Always separate confirmed facts from estimates, label
anything unverified as "estimate pending review," and end with the assumptions you made
and what a human should verify. Use plain English, no jargon.
```

This single step changes the tone of everything below — you'll see Copilot flag its own assumptions without being asked each time.

---

## Exercise 1: From monthly actuals to a reviewed story

**Scenario:** Month-end close just finished. Your CFO, Dana Whitfield, wants the August variance story before tomorrow's leadership sync — what moved, why, and what needs a decision. You have the actuals export; you don't yet trust every number in it.

### Task 1 — Open the report and get oriented in Excel (8 min)

1. Open **`finance_monthly_actuals.xlsx`** in **Excel**. Note the two tabs: *Aug 2026 Actuals* and *YTD by Region*.
2. Open **Copilot in Excel** (Home tab → **Copilot**). Make sure the range is a table (`Ctrl+T`).
3. Get a fast lay of the land:

   ```
   Give me a quick overview of this actuals table: columns, number of rows, total budget
   vs total actual revenue, and the overall variance %. Then list any rows where the
   Actual Revenue is blank or the Notes column is filled in.
   ```

4. Jot down what Copilot flags — you'll dig into those in Task 2.

### Task 2 — Use Analyst to find variance drivers and anomalies (10 min)

1. Open **Copilot Chat**, start the **Analyst** agent, and attach `finance_monthly_actuals.xlsx`.
2. Run this analysis prompt — note it **defines what counts as an exception** so results are repeatable:

   ```
   Using ONLY the attached actuals file, analyze budget vs actual. Do three things:
   1) Identify the 3 largest unfavorable revenue variances and the 2 largest favorable
      ones, with region, product line, and variance %.
   2) Flag any anomalies: variances at or beyond +/-15%, gross-margin drops of 8 points
      or more, and any blank/missing actuals.
   3) For each flagged item, suggest one question I should ask before I trust it.
   End with the assumptions you made and which numbers you could not verify.
   ```

3. Spot-check two of the flagged rows against the spreadsheet. Confirm the missing-actual row and the large Midwest miss both show up.

> **Model note:** if the reasoning looks shallow or the math seems off, switch to a **more capable model** in Copilot Chat and re-run. Finance analysis is a good case for the stronger reasoning model.

### Task 3 — Turn the analysis into a reusable variance/anomaly prompt (10 min)

1. Make that one-off into a **template**:

   ```
   Rewrite the analysis prompt above as a reusable template with [placeholders] for
   [SOURCE FILE], [VARIANCE THRESHOLD], and [MARGIN THRESHOLD]. Keep it short enough to
   paste in under a minute.
   ```

2. Save it to the **Prompt Library** (Copilot Chat → **Prompts** → save), and drop a copy into a scratch doc titled **"Acme Finance Prompt Library."**
3. Test it: change the threshold to +/-10% and re-run to confirm the template still behaves.

### Task 4 — Validation checkpoint (7 min)

In your scratch doc, answer for this analysis:

- **Source:** Which file/tab did Copilot use? Any row it couldn't read?
- **Assumptions:** How did it treat the blank actual? Did it annualize or assume anything?
- **Risk:** What's the cost if a flagged variance is wrong — or a real one is missed?
- **Human review:** Who confirms these numbers before they reach the CFO?

> **Exercise 1 output:** a variance/anomaly analysis + a reusable prompt saved to your library.

---

## Exercise 2: QA the data, then write for leadership

**Scenario:** Before anything goes to Dana, you need to clean a messy AR aging sheet, then turn your findings into a one-page memo and a single leadership slide — in her voice, not yours.

### Task 1 — Spreadsheet QA on a messy sheet (10 min)

1. Open **`finance_spreadsheet_with_anomalies.xlsx`** in **Excel** (the *AR Aging* tab).
2. With **Copilot in Excel**, run a QA pass:

   ```
   Review this AR aging sheet for data-quality problems ONLY within this file. Check for:
   inconsistent or invalid date formats, aging buckets that don't match Days Past Due,
   negative or zero amounts, blank Days Past Due, status typos, and possible duplicate
   invoices. Return a table: row, field, the issue, and the suggested fix. Do not change
   the data — just list the problems.
   ```

3. Confirm Copilot catches the big ones: the bad date format, the mis-bucketed 90+ invoice, the negative amount, the blank/negative days-past-due, and the status typo.
4. Save this as a **Spreadsheet QA** prompt in your library.

### Task 2 — Draft the finance memo in Word (10 min)

1. Open **`leadership_audience_profile.docx`** and **`executive_memo_format.docx`** — read who you're writing for and the structure to match.
2. In **Copilot in Word**, generate the memo:

   ```
   Draft a one-page finance executive memo for the audience described below, using my
   variance findings and QA notes. Follow this structure exactly: 1) Bottom line
   (2–3 sentences), 2) Variance highlights (table: area, budget vs actual, driver,
   confidence), 3) Margin notes, 4) Anomalies & data-quality flags, 5) Assumptions &
   what a human must verify, 6) Recommended next step. Label every unconfirmed number as
   "estimate pending review." Audience: [PASTE FROM PROFILE]. Findings: [PASTE].
   ```

3. Tighten the Bottom Line so it leads with the single decision Dana must make.

### Task 3 — Build the one-slide leadership summary in PowerPoint (10 min)

1. Open **PowerPoint**, start a blank deck, open **Copilot in PowerPoint**:

   ```
   Create ONE executive summary slide from the memo I paste below. Title = the headline
   decision. Include: 3 bullets max (biggest driver, margin note, top anomaly), and a
   one-line "what we need from you." Keep it plain and board-ready. Memo: [PASTE]
   ```

2. Check that nothing on the slide is an unverified figure presented as fact — if it is, label it as an estimate.
3. Save an **Executive finance briefing** prompt to your library.

### Task 4 — Validation checkpoint and save the library (10 min)

1. Run the four-question check (**Source / Assumptions / Risk / Human review**) on the memo and the slide.
2. Confirm your **Acme Finance Prompt Library** now holds **4–5 reusable prompts**:
   - Variance/anomaly analysis (Exercise 1)
   - Spreadsheet QA
   - Financial report summary
   - Finance executive memo
   - Executive briefing slide
3. Paste everything — objectives, your prompts, and validation notes — into a single Markdown file (next section).

> **Exercise 2 output:** a cleaned-data findings list, a one-page memo, a leadership slide, and a 4–5 prompt library.

---

## Prompt Library (your leave-behind)

Save these five. Fill the `[placeholders]` each time.

**1. Variance / anomaly analysis**
```
Using ONLY [SOURCE FILE], analyze budget vs actual. Give the largest unfavorable and
favorable variances (with region/line/%), flag variances beyond [VARIANCE THRESHOLD] and
margin drops beyond [MARGIN THRESHOLD] and any blanks, and suggest one verification
question per flag. End with assumptions and what you could not verify.
```

**2. Spreadsheet QA**
```
Review [SOURCE FILE] for data-quality issues ONLY: invalid dates, mismatched buckets,
negative/zero/blank values, status typos, and possible duplicates. Return row, field,
issue, and suggested fix. Do not change the data.
```

**3. Financial report summary**
```
Summarize [SOURCE FILE] for [AUDIENCE] in [WORD COUNT]. Lead with the headline number
and biggest driver. Separate confirmed facts from estimates. End with assumptions and
review items.
```

**4. Finance executive memo**
```
Draft a one-page finance memo for [AUDIENCE] from the findings below. Structure: Bottom
line, Variance highlights (table), Margin notes, Anomalies/data-quality, Assumptions &
what to verify, Recommended next step. Label unconfirmed numbers as "estimate pending
review." Findings: [PASTE]
```

**5. Executive briefing slide**
```
Create ONE board-ready slide from the memo below: title = the decision, 3 bullets max,
one "what we need from you" line. No unverified figure stated as fact. Memo: [PASTE]
```

---

## Save your work and store it in GitHub

1. Save this whole lab (with your prompts and notes) as **`finance-copilot-lab.md`**.
2. Open your repo on **GitHub.com** (e.g., `acme-bottling-copilot`).
3. Put the four data files in **`/data`** and this lab in **`/sessions`**.
4. Update each `<ARTIFACT_URL>` to the raw GitHub path so downloads work for the next person.
5. Commit with a clear message, e.g. `Add Finance Copilot lab + data`.

---

## Recommended close

- Today we focused on what your team can do now with Microsoft 365 Copilot.
- The next opportunity is to identify repeatable patterns that could become governed
  agent workflows once the right data, permission, security, and process guardrails are
  in place.
- The outputs from this session should feed a prompt library now and an agent-readiness
  roadmap later.
