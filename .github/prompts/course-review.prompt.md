---
description: Deep course review of one MS-4004.X lab session against its Course Offering — coverage, learning arc, shared content, and 60-minute timing.
model: Claude Opus 5 (copilot)
---

# Deep course review — one MS-4004.X session

Perform a deep review of a single lab session in `sessions/` against the Course Offering
I provide below. **Implement the fixes directly in the files** — don't just report them.

Session to review: `${input:session:Which session file? e.g. sessions/MS-4004.X_Finance.md}`

Course Offering:

```
PASTE THE COURSE OFFERING HERE — the description, the "Topics Covered" list,
and the "Key Learning Outcomes" list.
```

---

## Context you need before you start

Read these first:

1. The session file being reviewed.
2. `Acme_Bottling_Company_Kit.md` — the canonical company, cast, data files, and the
   **role → Copilot feature-map** in section 4. That table is a hard guardrail.
3. At least two sibling session files in `sessions/` — this is how you learn the shared
   structure. `MS-4004.X_Marketing_and_Creative.md` is the reference standard; it has
   already been through this review.
4. Every data file the session tells learners to download. **Actually open the CSVs and
   read the numbers.**

## The five checks

### 1. Topic and outcome traceability
Map every single item in "Topics Covered" and "Key Learning Outcomes" to a specific
numbered Task in the lab. Anything you can't map to a task is a gap you must close by
adding or reworking a task. Be strict: a topic is not "covered" because a word appears in
the intro, and summarizing an attached file is not "research."

### 2. Dead files
Every file listed under "Before you start" must be used by at least one prompt in the lab.
If a file is downloaded but never used, either put it to work or remove it from the list.
Prefer putting it to work.

### 3. Data reconciliation
Open the data files and verify that every number, SKU, claim, person, and segment named in
a prompt actually matches the source data. Mismatches are common and valuable — the
preferred fix is to **turn the mismatch into a claim-checking / data-quality teaching
moment**, not to quietly correct the data. If you do that, document the planted defect in
the kit's defect note so facilitators aren't blindsided.

### 4. Sixty-minute timing
The lab must be honestly deliverable in ~60 minutes of hands-on, ~30 per exercise. Build a
per-task minute budget that sums to exactly 60 and put it in `## Facilitator notes` as a
small table, along with guidance on **what to cut if running long and what must never be
cut**. Do **not** put time boxes on individual task headings — that breaks the shared
structure across labs.

### 5. Shared content
These blocks repeat near-verbatim across all seven labs. Preserve them; don't let this
session drift:

- Header: **Audience / Format / Level**, each as its own paragraph. Format line is
  `~60 minutes of hands-on (up to ~75 if your group goes deep), inside a ~90-minute session.`
  **Finance is the documented exception** at `~65–80 minutes of hands-on` with three
  exercises; keep it in sync with the timing note on the README.
- `## What you'll be able to do`
- `## Learning arc` — the same 5-row, 2-exercise comparison table
  (You're doing / Copilot's job / Your job / Stakes / You leave with), followed by the two
  beat lines: *"prompt → read it critically → keep what's reusable"* and
  *"Source / Assumptions / Risk / Human check."*
- `## Before you start` — the compact four-part form: a pointer blockquote to
  [home page setup](../../README.md#before-your-session) naming this lab's apps and agents,
  then **1.** the OneDrive folder, **2.** a `File | What it is | Link` table of **Save file**
  links to `https://github.com/xebia/MS-4004-Microsoft-365-Copilot-UseCases/raw/main/data/`,
  and **3.** the "open `.xlsx` as-is" note where the lab uses workbooks. Each session links
  **only its own files**. Generic setup — prerequisites, right-click download mechanics, the
  ZIP fallback, and the "Where to find things" reference — lives on the README and must
  **not** be repeated here.
- The `> **Copilot capabilities in this lab:**` blockquote
- `## The one rule to protect` — **Copilot assists. A human validates.**
- **Ex.1 Task 1** always teaches the same two habits: a custom instruction set via
  Copilot Chat → Settings → Personalization, and a clean folder / new chat.
- `### Validation checkpoint` closing every exercise: Source / Assumptions / Risk / Human check.
- The **last task of Exercise 2** is always "Save your prompt library."
- `## Prompt Library (your leave-behind)` with `[PLACEHOLDER]` slots.
- `## Facilitator notes` — including the "capture agent ideas → route to **Chris Bartlow**"
  bullet and the "keep agents future-state" rule.
- `## Recommended close (read this)` — uses the exact wording from kit section 7.
- Recurring phrase: *"This is a first pass, not an approval."*

## Hard rules

- **Stay in the Acme Bottling fiction.** All companies, people, customers, suppliers, and
  SKUs come from `Acme_Bottling_Company_Kit.md`. Don't invent a new named person, company,
  or event. First names must stay unique across the cast. Data filenames always start with
  `AcmeBottling_`.
- **Respect the feature map.** Only teach the Copilot capabilities listed for this role in
  kit section 4. If a genuine gap requires a new capability, update that table in the kit
  as part of the change and say so — don't silently expand scope.
- **The Researcher agent is allowed to reach the real web** where a lab uses it for market,
  role, or domain research. Write those prompts to describe the *category, product, or
  role* rather than naming Acme or real competitors, so the question is answerable and the
  fiction stays intact. This is a settled decision — don't propose reverting it.
- **Every lab is standalone.** Never reference another session by name or number.
- **Keep labs current-state Copilot.** Agent-building ideas get captured and routed, never
  built in session.
- Markdown is hard-wrapped at roughly 90 characters. Match the existing voice: direct,
  practical, second person, em dashes, bold on the habits that matter.

## Also update, when scope changes

- `Acme_Bottling_Company_Kit.md` — the role → feature-map row, the data-file table
  description, and the planted-defects note.
- `README.md` — the session blurb in the session list.

## What to report back

A short summary containing:

- Coverage gaps found, and the task you added or reworked to close each one.
- Any data mismatch discovered, and how you turned it into a teaching moment.
- Dead files found and how they're now used.
- The final per-task minute budget and total.
- Which shared blocks you preserved, and any cross-file syncing you did.
- Anything that now differs from the other labs and may need normalizing later
  (for example, Marketing's prompt library grew from 4 prompts to 6).

Do not create new markdown files to document the changes.
