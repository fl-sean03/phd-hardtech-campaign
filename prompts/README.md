# Prompts Directory — Usage Guide

This directory contains structured instruction sets for AI agents. Each prompt, when run against
your filled-in `POSITIONING_TEMPLATE.md`, generates research documents or complete application
packages for specific roles or entire sectors.

---

## What These Prompts Do

Each file in this directory is a prompt — a set of instructions given to an AI agent (Claude,
GPT-4o, or any capable model) that tells it:

1. What context to read first (always your `POSITIONING_TEMPLATE.md`)
2. What research or document to produce
3. What structure to follow
4. What to verify before writing
5. Where to save the output

The agent does the time-consuming work: reading job descriptions, assessing fit, writing tailored
cover letters, populating form fields, and structuring research. You review, correct, and submit.

---

## Available Prompts

| File | What It Produces | When to Use |
|------|-----------------|-------------|
| `sector_research.md` | A research doc covering 10-20 companies in a sector | Start here — run once per sector before any applications |
| `application_package.md` | STATUS.md + APPLICATION.md for one specific role | Run once per company after you have a job posting |

More prompts can be added to this directory. The naming convention is `[action]_[output].md`.
Each new prompt should follow the same structure: read POSITIONING_TEMPLATE first, verify facts,
produce structured output in the correct directory.

---

## The Pipeline

```
[You fill in POSITIONING_TEMPLATE.md]
         |
         v
[Run sector_research.md for each sector]
  → produces: research/[sector]_research.md
  → identifies: 10-20 companies, scores, apply URLs, deadlines, flags
         |
         v
[For each promising company, run application_package.md]
  → produces: applications/[company]/STATUS.md
              applications/[company]/APPLICATION.md
         |
         v
[You review STATUS.md → confirm fit and flags → review APPLICATION.md → submit]
         |
         v
[Log submission in tracker → set follow-up reminder]
```

You are doing three things in this workflow: filling in your positioning document once, reviewing
research and application packages the agent produces, and clicking submit. The agent handles the
volume.

---

## How to Run

These prompts work with any LLM that supports file input and multi-turn conversation — Claude, GPT-4o, Gemini, or others with code/file access. The examples below use a CLI-based AI tool (like Claude Code), but the logic applies to any capable model.

### Single agent (one company):

```bash
claude -p "$(cat /path/to/phd-internship-campaign/prompts/application_package.md)"
```

The prompt will ask you to provide the company name, role title, and job description.
Paste the job posting text when prompted.

### With a specific company and role inline:

```bash
claude -p "$(cat prompts/application_package.md)

Company: Divergent Technologies
Role: PhD Intern — Computational Materials
Job description:
[paste job description here]
"
```

### Sector research:

```bash
claude -p "$(cat prompts/sector_research.md)

Sector: aerospace advanced manufacturing
Specific companies to include if found: Divergent Technologies, Hermeus, Relativity Space
"
```

### Parallel execution (the real power):

If your AI tool supports parallel subagents (or you open multiple terminal sessions), you can run 5-10 application packages simultaneously. This is the primary power of this system.

Example — running 5 application packages in parallel:

```
Use the Task tool to run 5 parallel sub-agents, one for each of the following companies.
Each sub-agent should:
1. Read ~/Workspace/phd-internship-campaign/POSITIONING_TEMPLATE.md
2. Read the job description provided below for their assigned company
3. Execute the instructions in ~/Workspace/phd-internship-campaign/prompts/application_package.md
4. Write output to ~/Workspace/phd-internship-campaign/applications/[company_name]/

Company assignments:
- Sub-agent 1: [Company A] — [URL or pasted JD]
- Sub-agent 2: [Company B] — [URL or pasted JD]
- Sub-agent 3: [Company C] — [URL or pasted JD]
- Sub-agent 4: [Company D] — [URL or pasted JD]
- Sub-agent 5: [Company E] — [URL or pasted JD]
```

---

## Parallel Execution: The Core Value Proposition

The point of this system is not to make one application slightly better. It is to produce 10
tailored, research-backed application packages in the time it takes to write 1.

Here is what that looks like in practice:

1. You spend 60-90 minutes filling in `POSITIONING_TEMPLATE.md` once.
2. You run `sector_research.md` for each target sector (1-2 hours of agent time, you wait).
3. You review the research doc and select 10-15 companies worth applying to.
4. You paste the 10-15 job descriptions into a parallel Task run.
5. While the agents work (30-60 minutes), you do something else.
6. You return to 10-15 STATUS.md + APPLICATION.md pairs ready for review.
7. You spend 10-15 minutes per application reviewing, correcting, and submitting.

Total time to submit 10 tailored applications: 4-6 hours, most of which is your review. Without
this system: 2-4 hours per application, so 20-40 hours for the same 10 applications.

The bottleneck shifts from writing to reviewing. Reviewing is faster and catches errors better
than writing from scratch.

---

## Cost Note

Each agent call uses LLM tokens. Running 10 application agents in parallel costs roughly the
equivalent of 10 separate API calls.

Approximate token costs per operation:

| Operation | Input tokens (est.) | Output tokens (est.) | Approx. API cost |
|-----------|--------------------|--------------------|-----------------|
| `sector_research.md` (10 companies) | ~8,000 | ~6,000 | ~$0.15-0.40 |
| `application_package.md` (one role) | ~5,000 | ~4,000 | ~$0.10-0.30 |
| 10 parallel application packages | ~50,000 | ~40,000 | ~$1.00-3.00 |

*Estimates based on typical frontier model pricing as of early 2026. Costs vary by model and
provider — check current pricing before running at scale.*

If you are on a flat-rate AI subscription, these costs are included. Run as many agents as you want.

---

## Output Directory Convention

All agent-generated files go into:

```
phd-internship-campaign/
  applications/
    [company-slug]/
      STATUS.md         ← research + fit analysis
      APPLICATION.md    ← cover letter + form fields + checklist
  research/
    [sector]_research.md  ← sector-level research doc
```

Use lowercase, hyphen-separated company slugs for directory names.
Example: `divergent-technologies/`, `boeing-phantom-works/`, `mit-lincoln-lab/`

Do not put application packages in the `templates/` directory — templates are reusable blank
forms, `applications/` contains the filled-in, company-specific output.

---

## Adding New Prompts

To add a new prompt type (e.g., a prompt for generating a LinkedIn profile update, or a prompt
for preparing for a phone screen):

1. Create a new `.md` file in this directory
2. Start the prompt with: "Read the candidate's POSITIONING_TEMPLATE.md at [path] before writing."
3. Specify the output format and output path
4. Add an entry to the table at the top of this README

The pattern is always: read candidate context → do research → produce structured output.
