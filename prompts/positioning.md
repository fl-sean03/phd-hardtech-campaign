# Prompt: Candidate Positioning Interview

*Copy-paste this prompt into Claude Code (or any capable LLM) to build your POSITIONING_TEMPLATE.md through a structured interview. The agent will ask you a series of questions and then generate a completed positioning document from your answers.*

---

## Instructions for the Agent

You are helping a PhD student in a STEM field build a positioning document for an internship application campaign. This document is the single most important input to the entire application pipeline — it determines how every cover letter, cold email, and scoring decision gets made.

Your job is to interview the candidate, then generate a completed `POSITIONING_TEMPLATE.md` from their answers.

**Do not skip straight to generating the template.** The questions exist because most PhD students undersell themselves, use vague language, or don't know which parts of their background are actually differentiated. The interview process surfaces the specific, concrete, and quantified details that make applications stand out.

---

## Phase 1: Interview (Ask These Questions)

Work through these question sets in order. Ask one set at a time. Wait for answers before proceeding. If an answer is vague, ask a follow-up.

---

### Set 1: Research Focus

Ask:
1. What is your thesis about? Describe it the way you would to an intelligent person outside your field — not your advisor, not a conference audience. Two or three sentences max.
2. What is the central problem you are trying to solve? What breaks, fails, or doesn't work yet that your research addresses?
3. What is the one result from your research so far that you are most proud of? If you had to put a number on it — a percentage improvement, a quantity measured, a scale or system size — what would it be?

**If the answer to #3 is vague (e.g., "I've been developing a method"), push:** "Give me the closest thing to a number you have. Even an order of magnitude. Even a comparison: 'previous methods took X days, mine takes Y hours.'"

---

### Set 2: Technical Stack

Ask:
4. List every simulation or modeling code you have used in your research, not just your primary one. Include codes you've only used in coursework if you understand them well enough to use them without hand-holding.
5. List every characterization or experimental technique you have personally run data on — either your own experiments or someone else's data you analyzed. (SEM, XRD, TEM, FTIR, nanoindentation, DSC, etc.)
6. What programming languages do you actually use in your research workflow, day to day? Be honest — list only languages you could use right now without Googling basic syntax.
7. Have you contributed to any open source code? Maintained a public repository? Built any tooling that others in your group use?
8. What does your HPC usage look like? What systems have you run jobs on? What is the largest job you have run in terms of CPU-hours, node count, or simulation size?

---

### Set 3: Background and Differentiators

Ask:
9. Do you hold any security clearance? If yes: what level, when was it initiated, and is it active?
10. Have you worked at a national laboratory, FFRDC, government agency, or defense contractor in any capacity — internship, co-op, REU, fellowship, contract? For each: where, what did you work on, and for how long?
11. Have you been through any government-funded program (DOE I-Corps, NSF I-Corps, NSIN Hacking for Defense, AFWERX, SBIR/STTR work)? Describe briefly.
12. What is your citizenship status? (US citizen / permanent resident / visa type — relevant for clearance-gated and ITAR roles)
13. Do you speak any languages other than English at a professional or working level?
14. What is one thing about your background or skills that most PhD students in your cohort do NOT have?

---

### Set 4: What You Are Actually Looking For

Ask:
15. What sectors are you most interested in? Rank these if you have preferences: national labs, defense primes, FFRDCs (MITRE/Aerospace Corp/APL), nuclear energy, hard tech startups, composites/aerostructures, semiconductor fabs, energy materials (batteries/fuel cells), space and launch, biotech/pharma, consulting.
16. What kind of work do you want to do this summer? Rank: (a) computational / simulation-heavy, (b) experimental / hands-on characterization, (c) manufacturing floor / process engineering, (d) systems engineering / design, (e) research-to-product translation, (f) doesn't matter.
17. Location: Is there a city or region where you are based and cannot relocate? Or are you fully flexible? If you have a home institution, list it.
18. Timing: When are you available? What is your earliest possible start date and latest possible end date?
19. Compensation: Do you have a floor below which an internship is not financially viable? (Optional — but useful for filtering out roles where pay is consistently too low for your situation.)
20. Is there anything you explicitly do NOT want in an internship? (e.g., "no purely theoretical work," "no roles that require a specific clearance I don't have," "no relocation to certain regions," etc.)

---

### Set 5: Honest Self-Assessment

Ask:
21. What is your biggest genuine gap as a candidate for the roles you want? Not fishing for false modesty — what would a hiring manager at your top target company or lab actually wish you had done more of?
22. If you had to describe yourself to a hiring manager in one sentence — leading with your most differentiated capability and ending with what you are looking for — what would you say?

---

## Phase 2: Clarifying Follow-ups

Before generating the template, check for any of these and ask if missing:

- If clearance was mentioned: confirm the level (Confidential, Secret, Top Secret, SCI, TS/SCI) and whether it is current/active or just initiated
- If national lab experience was mentioned: confirm the specific division or program and the approximate dates
- If a quantified result was mentioned but vague: push for the number one more time ("You said 'significantly faster' — can you give me an order of magnitude?")
- If location flexibility is unclear: confirm whether "flexible" means "will relocate anywhere" or "prefer not to relocate but would for the right role"

---

## Phase 3: Generate POSITIONING_TEMPLATE.md

Once you have answers to all questions (or the best available answers — don't block on perfect responses), generate `POSITIONING_TEMPLATE.md` with the following structure. Write the document in the third person ("The candidate...") so it reads as a reference document rather than a personal statement.

```markdown
# Candidate Positioning Document

*Generated [date]. Update this document whenever your background changes significantly. This is the single source of truth for all application materials.*

---

## Research Snapshot

**Thesis topic (one sentence, plain language):**
[Fill from interview — no jargon, no abbreviations]

**Core problem being solved:**
[Fill from interview]

**Key result with number:**
[Fill from interview — this must have a number, even approximate]

**Research elevator pitch (2-3 sentences for a technical but non-specialist audience):**
[Synthesized from interview answers — write this for the candidate based on their responses]

---

## Technical Stack

### Simulation / Modeling
| Code | Proficiency | Context |
|------|-------------|---------|
| [code] | [primary / working / familiar] | [what you use it for] |

### Characterization / Experimental
| Technique | Proficiency | Context |
|-----------|-------------|---------|
| [technique] | [primary / working / familiar] | [hands-on / data analysis only] |

### Programming
| Language | Proficiency | Context |
|----------|-------------|---------|
| [language] | [fluent / working / basic] | [what you use it for] |

### HPC
- Systems used: [list]
- Largest job: [CPU-hours / nodes / simulation scale]
- Job scheduler experience: [SLURM / PBS / etc.]

### Open Source / Public Work
[List any public repos, contributed packages, or tools others use. Link if available.]

---

## Differentiators

**Security clearance:** [Level — active/initiated — date initiated] OR [None]

**National lab / government experience:**
[For each: Organization | Division/Program | Duration | What you worked on]

**Government programs:**
[DOE I-Corps, NSF I-Corps, AFWERX, NSIN, SBIR/STTR involvement, etc.]

**Citizenship:** [US Citizen / Permanent Resident / Visa type]

**Languages:** [List non-English languages at working level or above]

**Non-standard differentiator:**
[The one thing most PhD students in your cohort don't have — from interview Q14]

---

## What I Am Looking For

**Target sectors (ranked):**
1. [highest priority]
2. [second]
3. [third]
[continue as needed]

**Preferred work type (ranked):**
1. [e.g., computational/simulation-heavy]
2. [e.g., research-to-product translation]
[continue as needed]

**Location:**
- Home institution: [city, state]
- Relocation: [fully flexible / prefer no relocation / hard constraint — cannot relocate]
- No-relocation radius: [N miles from home institution, if applicable]

**Timing:**
- Earliest start: [date]
- Latest end: [date]
- Target duration: [weeks]

**Compensation floor:** [$ per hour or per month, or "no constraint stated"]

**Explicit exclusions:**
[Anything from Q20 — roles, regions, work types to filter out]

---

## Honest Gaps

**Biggest gap for target roles:**
[From Q21 — be specific. "Limited hands-on manufacturing floor experience" is useful. "Could always know more" is not.]

**How to address in applications:**
[One sentence on how to frame this gap honestly without tanking the application]

---

## The Trade You Are Offering

*This section is the most important. For each major employer type, articulate what the candidate uniquely brings and what they need in return. Use these as the opening frame for cover letters and cold emails.*

### For national labs:
"I bring [specific computational/experimental capability] developed during [prior national lab or AFRL work]. I can contribute to [specific lab program area] immediately. I am looking for [what you need — manufacturing context / experimental scale-up / classified program access]."

### For defense primes:
[Same structure — fill from candidate's profile and target roles]

### For hard tech startups:
[Same structure]

### For nuclear companies:
[Same structure — only include if nuclear is in target sectors]

[Add additional employer types as relevant to this candidate's target list]

---

## One-Sentence Pitch

*From Q22 — refined for clarity and impact:*

"[Candidate's most differentiated capability] — looking for [what they want to do this summer] at [sector/role type]."

---

*This document was generated through a structured interview on [date]. It represents the candidate's profile as of that date. Update Section 4 (What I Am Looking For) whenever priorities shift.*
```

---

## Output Instructions

- Write the file to `POSITIONING_TEMPLATE.md` in the current directory
- If any section is genuinely incomplete because the candidate could not answer (e.g., they have no HPC experience), write "None — not applicable" rather than leaving it blank or making something up
- Do not invent accomplishments, numbers, or experience the candidate did not describe
- The "Research elevator pitch" and "The Trade You Are Offering" sections should be drafted by you (the agent) based on the interview, not copied verbatim from the candidate's answers — these are the sections where synthesis and framing matter most
- After writing the file, output a brief summary: what are the 3 strongest differentiators this candidate has, and which 2-3 employer types should be highest priority given their profile?

---

*This prompt is designed to be run interactively in a single session. Estimated time: 15-30 minutes for the interview, 5 minutes for the agent to generate the document.*
