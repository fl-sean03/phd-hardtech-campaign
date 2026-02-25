# phd-internship-campaign

A systematic, AI-assisted internship application toolkit for STEM PhD students. Not a job board list. A complete research + application generation system — built by a second-year PhD student (materials science, CU Boulder) using Claude Code and parallel AI agents.

**What was built in a single session:**
- 130+ companies researched across 12 sectors
- 70+ complete application packages generated (cover letter + form fields + checklist)
- 74 tracked opportunities with status and scoring
- Research that would have taken weeks of manual effort, done in hours

---

## What's in This Repo

### `research/`
Sector-by-sector company intelligence for 130+ targets. Each file covers a specific sector: who the players are, what technical work they do, what they actually hire PhD interns for, and which programs are worth targeting. Written at the level of someone who read the company's published work — not scraped from LinkedIn.

Sectors covered:
- National laboratories (DOE complex)
- Defense primes (Lockheed, RTX, Northrop, L3Harris, General Dynamics)
- FFRDCs (MITRE, Aerospace Corp, IDA, RAND, Lincoln Lab)
- Nuclear companies (Kairos, X-energy, TerraPower, Oklo, Westinghouse)
- Hard tech startups (AFRL-adjacent, SBIR-funded)
- Composites and aerostructures
- Semiconductor fabs and materials
- Energy materials (batteries, fuel cells, hydrogen)
- Space and launch
- Government agencies (AFRL, ARL, NRL, NIST)
- DOD program offices
- Consulting and government services

### `templates/`
Fill-in-the-blank application packages. Each template is structured as one directory per opportunity with two files:
- `STATUS.md` — company research summary, role analysis, fit table, deadline, pay
- `APPLICATION.md` — cover letter (three paragraphs, role-specific structure), pre-filled form fields, resume selection guidance, submission checklist

### `prompts/`
The actual AI prompts used to generate research and application packages. Use these to run your own pipeline against your own background. Includes:
- `sector_research.md` — prompt for deep company research by sector
- `application_package.md` — prompt for generating a complete application package given company + role + your positioning doc
- `cold_email.md` — prompt for cold outreach to companies without open postings
- `scoring.md` — prompt for evaluating and scoring fit before investing effort

### `MASTER_LIST.md`
The scored opportunity database. 74 entries with company, role, sector, fit score (0-100), deadline, status, and application type (ATS vs. email vs. Zintellect). Sortable by score, sector, or deadline. Start here to prioritize.

### `METHODOLOGY.md`
The full process: candidate positioning, sector identification, opportunity scoring, AI pipeline architecture, submission prioritization, and cold outreach. Read this before using anything else.

### `POSITIONING_TEMPLATE.md`
A structured template for defining yourself as a candidate. Technical stack, key findings with numbers, differentiators, honest gaps, and the "trade" you're offering each type of employer. Fill this out first — everything else depends on it.

### `COVER_LETTER_PRINCIPLES.md`
Practical principles for cover letters and cold emails in this specific context: STEM PhD students applying to defense, national lab, and hard tech roles. Not generic advice.

---

## Who This Is For

STEM PhD students (especially materials science, computational science, chemical engineering, physics) applying to summer internships at:

- **National laboratories** — ORNL, LANL, ANL, NREL, INL, PNNL, LLNL, Sandia, SLAC, BNL
- **Defense primes** — Lockheed Martin, RTX (Pratt & Collins), Northrop Grumman, L3Harris, General Dynamics
- **FFRDCs** — MITRE, The Aerospace Corporation, Lincoln Laboratory, IDA, RAND, CMSRC
- **Nuclear companies** — Kairos Power, X-energy, TerraPower, Oklo, NuScale, Lightbridge, Westinghouse
- **Hard tech startups** — SBIR-funded companies with AFRL/DARPA contracts, advanced materials startups
- **Composites and aerostructures** — Toray, Hexcel, Spirit AeroSystems, Triumph, Albany International
- **Semiconductor fabs and materials** — Intel, GlobalFoundries, TSMC, Applied Materials, Lam Research
- **Energy materials** — QuantumScape, Solid Power, Bloom Energy, Plug Power, Nel Hydrogen

If your research produces results that translate to engineering decisions — processing parameters, material specifications, failure mechanisms, transport properties — this toolkit was built for your application.

---

## How to Use It

### Path 1: Use the research directly

You don't need to run any AI pipeline. The research is already done.

1. Open `MASTER_LIST.md` and filter to your target sectors and fit scores above 70
2. Open the relevant `research/` file for each sector you're targeting
3. Fill in `POSITIONING_TEMPLATE.md` with your own background
4. Adapt the `templates/` packages with your information — the structure is done, you're filling in the technical specifics
5. Submit using the checklist in each `APPLICATION.md`

This path works if your background is close enough to materials science / computational science that the sector research is directly applicable.

### Path 2: Run your own AI pipeline

If you're in a different subfield or want to generate fresh research for your specific background:

1. Fill in `POSITIONING_TEMPLATE.md` completely
2. Read `METHODOLOGY.md` to understand the scoring and prioritization logic
3. Use `prompts/sector_research.md` to generate research for sectors relevant to your work
4. Use `prompts/application_package.md` to generate application packages — provide your positioning doc + company research + specific role
5. Run multiple agents in parallel on different sectors simultaneously (Claude Code handles this natively)

The prompts are written to produce research-quality output, not generic summaries. Give them the company's actual technical work and they return application packages that name specific programs, technologies, and research areas.

---

## Quick Start (5 Steps)

1. Fill in `POSITIONING_TEMPLATE.md` with your background — technical stack, key findings with numbers, differentiators, honest gaps
2. Read `METHODOLOGY.md` — understand the scoring system before you start applying
3. Browse `MASTER_LIST.md` — sort by sector and score, identify your top 20 targets
4. Open the relevant `research/` file for each target sector — read it before writing anything
5. Use `prompts/application_package.md` to generate tailored packages with AI, or adapt `templates/` directly

---

## The Core Insight

The bottleneck is not finding opportunities. Every PhD student can find a list of national labs and defense primes. The bottleneck is **research depth + tailoring at scale**.

Reading a company's published work, identifying what they actually need, and writing a cover letter that demonstrates that reading — that takes 2-3 hours per application done manually. Multiplied across 70 applications, that is months of work.

AI solves the scale problem without sacrificing the tailoring. But only if you give it the right inputs. Generic company names produce generic letters. Specific technical context — the company's programs, their materials systems, their published challenges — produces letters that read like they came from someone who did their homework.

Every application package in this repo has company-specific technical framing. "I see that your work on SiC-SiC CMC turbine components requires a joining approach that maintains fiber architecture" is not a template line. It came from reading what that company actually works on and connecting it to a specific technical background.

That is what this toolkit is designed to produce at scale.

---

## License

MIT. Use it, adapt it, share it. If you run your own campaign with this toolkit and it works, consider contributing your sector research back to the repo.
