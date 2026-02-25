# Prompt: Master List Synthesis

*Copy-paste this prompt into Claude Code (or any capable LLM with file access) to synthesize all sector research into a single prioritized master list. Run from the root of your phd-internship-campaign directory.*

---

## Instructions for the Agent

You are synthesizing internship research into a single prioritized master list for a PhD student in computational materials science.

### Step 1: Load Candidate Profile

Read `POSITIONING_TEMPLATE.md` in this directory. Extract and hold in context:
- Research focus and thesis topic (in plain language)
- Technical stack (simulation codes, characterization tools, programming languages)
- Key quantified accomplishments (with numbers)
- Differentiators: clearance status, prior national lab experience, open source contributions, language skills, anything non-standard
- What the candidate is looking for: sector preferences, role type, location flexibility (hard constraints vs. preferences), timing, compensation floor

If POSITIONING_TEMPLATE.md does not exist or is not filled out, stop and output: "POSITIONING_TEMPLATE.md is missing or blank. Fill it out before running synthesis. See prompts/positioning.md."

### Step 2: Load Scoring Framework

Read `METHODOLOGY.md`. Extract the scoring rubric (0-100 scale). If METHODOLOGY.md does not exist, use this default scoring framework:

**Default Scoring Framework (0-100):**
- Technical stack overlap (0-30 pts): How well does the role's required tooling / technical area match the candidate's stack?
- Research-to-role translation (0-25 pts): How directly does the candidate's thesis/research translate to value in this role?
- Differentiator leverage (0-20 pts): Does the candidate hold a hard differentiator for this role (clearance required, specific prior lab, specific code expertise)?
- Strategic value (0-15 pts): Does this role advance long-term goals (publications, skills, network, employment pipeline)?
- Practical fit (0-10 pts): Location, timing, pay, duration, and any hard constraints.

Scores ≥ 85: Tier 1 or top Tier 2. Scores 75-84: Tier 2. Scores 65-74: Tier 3. Scores < 65: Watch/Monitor or skip.

### Step 3: Read All Research Documents

Read every file in the `research/` directory. For each file:
- Note the sector it covers
- Extract every company and specific role mentioned
- Note any application URLs, deadlines, pay ranges, or clearance requirements explicitly mentioned in the research
- Flag companies described as hard matches (clearance required, specific PhD background required, or explicitly described as top-fit for the candidate profile)

Maintain a running list as you read. Do not score yet — just collect.

### Step 4: Score Every Opportunity

For each company/role pair collected in Step 3:
1. Apply the scoring framework from METHODOLOGY.md (or the default above) against the candidate profile from POSITIONING_TEMPLATE.md
2. Assign a score 0-100
3. Write a one-sentence rationale for the score (what drives the score up or down relative to a generic materials PhD candidate)
4. Note any hard flags: clearance required, deadline within 7 days, rolling/fills fast, location constraint, no formal posting (cold outreach required)

### Step 5: Assign Tiers

Group all scored opportunities into tiers:

**Tier 1 — Urgent / High Score:** Score ≥ 80 AND (deadline within 14 days OR explicitly marked urgent in research). Action: submit this week.

**Tier 2 — High Fit, Open Now:** Score ≥ 75, no urgent deadline pressure. Action: apply this week in a focused sprint.

**Tier 3 — Strong Secondary:** Score 65-74, confirmed-active posting. Action: apply within 2 weeks.

**Cold Outreach:** No formal ATS posting exists — requires direct email or warm introduction. Include regardless of score if technical fit is high.

**Watch / Monitor:** Posting not yet live, URL expired, or deadline passed but worth calendaring for next cycle. Include if score would be ≥ 70 when posted.

### Step 6: Generate MASTER_LIST.md

Write a single file `MASTER_LIST.md` with the following structure:

```
# [Candidate Field] Internship Master List — [Season Year]

*[One-sentence description of the candidate profile this list was built for. Include key differentiators so readers can calibrate fit.]*

*Scores reflect fit for: [brief candidate profile]. Verify all URLs and deadlines before applying.*

---

## Quick Stats

| Tier | Count | Action |
|------|-------|--------|
| Tier 1 | N | Submit this week |
| Tier 2 | N | Apply this week |
| Tier 3 | N | Apply within 2 weeks |
| Cold Outreach | N | Direct contact required |
| Watch / Monitor | N | Not posted or expired |

[If candidate has location constraints: list no-relocation companies here]

---

## TIER 1: Urgent — Submit This Week

[Table: Company | Role | Score | Deadline | Notes]

---

## TIER 2: High Fit, Open Now

[Group by sector. Table per sector: Company | Role | Score | Location | Notes]

---

## TIER 3: Strong Secondary

[Single table: Company | Role | Score | Location | Notes]

---

## COLD OUTREACH

[Table: Company | Approach | Contact | Notes]

---

## WATCH / MONITOR

[Table: Company | Role | Notes | Action]

---

## CLEARANCE / DIFFERENTIATOR NOTES

[If candidate has active clearance: list which roles require it as hard gate vs. decisive advantage]
[If candidate has other differentiators: note where they apply]

---

## APPLICATION FRAMING NOTES

[3-4 framing templates derived from the candidate's positioning, tailored to the top employer types in this list]

---

*Sources: [N] research documents compiled [date] covering [N]+ opportunities. All URLs and statuses reflect research date — verify before submitting.*
```

### Step 7: Populate Each Entry

For every entry in the master list, fill in:
- **Company**: Full company name, bolded for Tier 1/2
- **Role**: Full role title as posted
- **Score**: 0-100 integer
- **Deadline / Location**: As found in research; "Rolling" if no hard deadline, "Verify" if URL was uncertain
- **Notes**: Include: (a) one sentence on why this fits the candidate's specific profile, (b) pay range if available, (c) any hard gates or clearance requirements, (d) application portal or contact method, (e) any time-sensitivity signals ("fills fast", "check weekly", etc.)

Do NOT include: internal file paths, personal tracking statuses, or references to a specific named person.

### Step 8: Flag Special Cases

At the top of the document or inline in the Notes column, flag:

- **[CO/NO RELOCATION]** — roles within commutable distance of the candidate's stated home institution (if provided in POSITIONING_TEMPLATE.md)
- **[DEADLINE: X DAYS]** — roles with hard deadlines within 7 days of synthesis date
- **[CLEARANCE GATE]** — roles where active clearance is a hard requirement
- **[COLD OUTREACH]** — roles with no ATS, requiring direct contact
- **[CALENDAR]** — roles or fellowships that should be calendared for a future cycle

### Output Requirements

- Single file: `MASTER_LIST.md`
- All tables must render in standard GitHub Markdown
- No internal file paths, personal names, or tracking statuses in the output
- Every entry must have a Notes cell that is useful to a reader who does NOT have any context beyond the candidate profile — explain why this is a good fit in one sentence
- Scores must be consistent — if you score QuesTek at 84 for LAMMPS/DFT match, a role with identical technical overlap should be within ±5 points
- The document should be usable by any materials PhD student with a similar background, not just the specific candidate who generated the research

### Quality Check Before Writing

Before writing the file, internally verify:
1. Every Tier 1 entry has either a deadline within 14 days or an explicit urgent flag from the research
2. No entry has a score ≥ 80 in Tier 3 (should be Tier 2)
3. Cold Outreach section contains only entries with no active ATS posting
4. Watch/Monitor contains only entries where the posting is expired, not yet live, or needs URL verification
5. Notes column for each entry answers: why does this fit THIS candidate, not any materials PhD student?

---

*This prompt is designed to be run with Claude Code in the root of the phd-internship-campaign directory. For best results: fill POSITIONING_TEMPLATE.md completely before running, and ensure research/ directory contains at least 5 sector research documents.*
