# Methodology

The full process for running a systematic, AI-assisted internship campaign as a STEM PhD student. Read this before touching anything else in the repo.

The process has five phases. They are sequential. Skipping Phase 1 and jumping straight to applications is the single most common failure mode — and it produces generic letters that hiring managers discard in 10 seconds.

---

## Phase 1: Candidate Positioning

**Do this first. Everything else depends on it.**

Fill in `POSITIONING_TEMPLATE.md` before you research a single company. The template forces you to answer the questions that will determine every application you write.

### What to define

**Technical stack** — Not your research area in general terms. The specific methods, tools, and computational infrastructure you have hands-on experience with. Examples: "MD simulation using LAMMPS + custom PYTHON post-processing, DFT using VASP/Quantum ESPRESSO, HPC allocation management on NCAR/RMACC Summit, experimental: XRD, SEM/EDS, nanoindentation." Be specific. "Computational materials science" is not a technical stack.

**Key findings with numbers** — Your research produces results. Name them with quantitative specificity. Not "I study thermal transport in polymer composites" but "I identified a processing window (155-165°C, 0.8-1.2 MPa) that increases interlaminar shear strength by 23% in CF/PEEK laminates compared to industry standard cycles." The number is the anchor. The context is the translation.

**Differentiators** — What puts you in a smaller pool? Active security clearance is the most powerful differentiator in this market — it eliminates 80-90% of competing applicants from cleared roles. Others: prior national lab experience (return candidate signal at peer institutions), HPC scale (production core-hours, not classroom allocations), active SBIR-relevant research, open source code with real usage, prior industry internship in the target sector, DOE I-Corps or tech commercialization experience.

**Honest gaps** — Where are you weak? No manufacturing experience? No experimental background, only computational? Never worked at scale outside academia? Write these down. You will need to address them directly in letters for roles that require those skills, and the framing matters enormously.

**The trade you're offering** — For each employer type, what is the specific value exchange? For a national lab: "I bring a computational pipeline that is already calibrated against experimental data in your materials system — I can extend it to the parameters your current program needs without a 3-month ramp-up." For a defense prime: "I have active clearance and a materials modeling background directly applicable to your [program] — you get a cleared PhD student who doesn't need onboarding on the technical domain." Make the trade explicit.

### The translation layer thesis

This is the framing that works for PhD students applying to non-academic roles.

PhD research produces findings. Companies need those findings translated into engineering decisions — processing windows, material specifications, failure margins, property predictions at production conditions. The typical PhD framing is "I am a researcher, I can learn your tools." The better framing is: "I am already producing the outputs you need. My current work produces [X]. Your manufacturing/design/testing problem requires [Y]. Here is the direct connection."

Position yourself as the translation layer between atomic-scale physics and engineering specification. Not just a researcher. The person who bridges the two. That positioning is rare, it is legible to both technical and non-technical hiring managers, and it answers the unspoken question behind every PhD internship application: "Can this person actually do something useful in 10 weeks?"

---

## Phase 2: Sector Identification

**Start with sectors, not job boards.**

Job boards show you what is posted. Sector research shows you who works on what you work on, which programs use your methods, and which companies have the infrastructure to make a 10-week PhD intern productive. Those are different questions with different answers.

### Which sectors are legible for your background?

For materials science / computational science PhD students:

| Sector | Why it's legible | What they actually need |
|--------|-----------------|------------------------|
| National labs (DOE) | Largest concentration of materials PhD work in the US | MD/DFT modeling, property prediction, experiment-simulation integration |
| Defense primes | Structural materials, thermal protection, propulsion | Processing-property relationships, failure modeling, qualification support |
| FFRDCs | Policy-adjacent technical work | Analysis, characterization, materials assessment |
| Nuclear companies | Advanced reactor materials, fuel performance | High-temperature materials, radiation effects, qualification |
| Composites/aerostructures | Structural materials, manufacturing process development | Process modeling, cure kinetics, interlaminar mechanics |
| Semiconductor fabs | Thin films, dielectrics, metals | Deposition process development, materials characterization |
| Energy materials | Batteries, fuel cells, hydrogen | Electrochemical modeling, interface physics, degradation mechanisms |
| Hard tech startups | SBIR-funded, often AFRL-adjacent | Flexible — PhD skills applied directly to core technical problem |

### Researching each sector

For each sector you identify as a target: research 10-15 companies before writing a single cover letter.

What you need to know for each company:
- What specific programs or products use your technical area?
- What is their current published challenge (papers, patents, press releases)?
- Do they have an intern program, and is it structured or ad-hoc?
- What does their technical staff look like (PhD-heavy vs. BS-heavy)?
- What is the clearance requirement landscape?

The `research/` files in this repo cover this for 12 sectors and 130+ companies. Use them as starting points. They are current as of early 2026 but company-specific program details change — verify before citing in a letter.

---

## Phase 3: Opportunity Scoring

Score every opportunity before investing application effort. The scoring is not about being selective for its own sake — it is about allocating finite time to the applications most likely to produce an outcome.

### Scoring rubric (0-100)

| Factor | Weight | What to look for |
|--------|--------|-----------------|
| Technical stack overlap | 0-30 | Do they use your specific methods? Not adjacent methods — your methods. |
| Role-type match | 0-20 | Is this a modeling/simulation role, not just "materials intern"? |
| Differentiator relevance | 0-20 | Do your hard differentiators (clearance, prior lab experience, specific stack) matter here? |
| Program quality | 0-15 | Structured mentorship, conference attendance, final presentation, return offer track? |
| Strategic value | 0-15 | Publication opportunity, clearance sponsorship, future hire pathway, network value? |

### Hard filters (disqualifying, check first)

- Citizenship requirement you do not meet
- Clearance requirement you cannot satisfy (and the role has no non-cleared variant)
- Timing mismatch (end date before your program start, or start date before defense/quals)
- Location constraint you cannot accommodate

Check these before scoring. A perfect technical fit at a company that requires TS/SCI from a citizen when you hold neither is not an opportunity — it's a distraction.

### How to use the scores

- **80-100**: Priority applications. Research deep. Tailor hard. Apply immediately on rolling postings, day-of on competitive programs.
- **70-79**: Apply, but don't over-invest. Use the standard template structure with moderate customization.
- **60-69**: Apply if you have bandwidth. Minimal tailoring beyond basic substitution.
- **Below 60**: Cold outreach only if you have a specific connection to the program or person. Don't apply through ATS.

The `MASTER_LIST.md` has scores pre-calculated for all 74 tracked opportunities. Review them and adjust downward if your background differs significantly from the materials science / computational profile this campaign was built for.

---

## Phase 4: Application Package Generation

### The directory structure

One directory per opportunity. Two files per directory.

```
applications/
  lockheed-sikorsky-materials-intern-2026/
    STATUS.md
    APPLICATION.md
  ornl-cnms-summer-scholar-2026/
    STATUS.md
    APPLICATION.md
  ...
```

### STATUS.md contents

- Company overview (2-3 sentences, technical focus)
- Specific role analysis: what they are actually asking for
- Fit table: your qualifications mapped to stated requirements, row by row
- Confirmed posting URL (verify it is live before filing)
- Application deadline
- Compensation range if posted
- Application type: ATS portal, Zintellect, direct email, cold outreach
- Notes on anything unusual: clearance adjudication time, interview process, reference requirements

### APPLICATION.md contents

- Cover letter: three paragraphs, role-specific (see `COVER_LETTER_PRINCIPLES.md`)
- Pre-filled form fields: answers to standard ATS questions ("describe your research in 200 words," "why are you interested in this role," GPA, expected graduation, citizenship)
- Resume selection: which resume version fits this role, which projects to highlight
- Submission checklist: every required document, every required field, confirmation of deadline

### Running the AI pipeline

The application package prompt in `prompts/application_package.md` takes three inputs:
1. Your `POSITIONING_TEMPLATE.md` (your background, findings, differentiators)
2. Company + role research (from the `research/` files or your own)
3. The specific job posting text

It returns a complete `STATUS.md` + `APPLICATION.md` pair. Review every output before submitting — the AI can produce technically plausible but factually wrong company details. Verify the program names, the technical framing, and the posting URL independently.

### Running agents in parallel

AI tools that support parallel agents (or simply multiple terminal sessions) let you run sector research and application package generation simultaneously. For sector-level research, spin up 5-10 agents simultaneously on different sectors. For application package generation, run 3-5 in parallel on different companies within a sector.

Each agent needs:
- Your complete positioning doc
- The company-specific research or job posting
- Explicit instruction not to fabricate program names or dates — to leave a placeholder if uncertain

Do not run one agent sequentially across 70 companies. The session context accumulates, quality degrades, and it takes an order of magnitude longer than parallel execution.

---

## Phase 5: Prioritization and Submission

### Hard deadlines first

National lab structured programs (Zintellect portal: ORNL SULI/HERE, INL, PNNL, SNL, LLNL) have fixed application windows, typically:
- Fall window: September-October for spring starts
- Spring window: January-February for summer starts

These are not rolling. Missing the window means waiting a year. Treat these like exam deadlines with a 48-hour buffer for technical issues with the portal.

Zintellect requires a completed profile before you can apply. Set it up now, not the day before the deadline.

### Rolling postings: 72-hour rule

Defense primes (Lockheed, RTX, Northrop, L3Harris, GD) post on their ATS portals and postings close when the position fills or when the requisition is cancelled. Apply within 72 hours of finding an open posting. A posting that is two weeks old may have already closed internally even if the URL still resolves.

### Cold outreach: when there is no posting

Some of the highest-quality opportunities have no ATS posting. This is especially true for:
- Hard tech startups under 200 people
- SBIR Phase II companies building out their first intern program
- FFRDC technical groups with discretionary hiring authority
- University-adjacent research centers (ARL cooperative agreements, AFRL CRADAs)

The cold outreach template is in `prompts/cold_email.md`. The structure:

**Subject line:** PhD intern inquiry — [specific technical area] / [your institution]

**Body:**
- Sentence 1-2: Who you are and a single specific technical connection to their work. Not "I am interested in your company." Something like: "I am a second-year materials science PhD at [institution] working on processing-structure relationships in CMC systems — I saw your AIAA paper on SiC-SiC joining for turbine hot section components."
- Sentence 3-4: What you would contribute, specifically. What pipeline, what method, what analysis.
- Sentence 5: Single low-friction ask. "Is there a summer 2026 intern program, or would a 15-minute call be possible?"

Under 200 words. No attachments on the first email. If they respond, send the resume and a one-page technical summary.

Target the CEO or VP of Engineering at companies under 200 people. At companies over 200, target the program manager or principal investigator whose work you cited, not HR.

### Tracking

Everything goes in `MASTER_LIST.md`. Status field has five values:

| Status | Meaning |
|--------|---------|
| `not-started` | Identified, not yet applied |
| `ready` | Package complete, not yet submitted |
| `submitted` | Application sent, awaiting response |
| `response` | Any response received (interview, rejection, info request) |
| `closed` | Complete (offer received, declined, rejected, deadline passed) |

Update status in real time. The list is only useful if it's current.

---

## The Cold Outreach Layer

Cold outreach deserves its own section because it is the highest-leverage activity most PhD students never do.

The typical PhD student applies through ATS portals to posted roles, competes against hundreds of applicants with similar backgrounds, and wonders why the return rate is low. Cold outreach to the right person at a company without a posting puts you in a pool of one.

### Who to target

- **Under 50 people**: Email the CEO directly. They are making hiring decisions personally.
- **50-200 people**: VP Engineering or Director of R&D. They have budget discretion.
- **200-1000 people**: Program manager or PI whose published work you're citing. They can advocate internally.
- **Over 1000 people**: Cold outreach rarely works. Use the ATS or find an internal referral.

### ITAR and clearance signaling

One sentence. Not a paragraph. "I hold an active [clearance level] from [program/agency]." That is sufficient. Hiring managers who care about clearance will ask follow-up questions. Hiring managers who don't will skip past it without confusion. Do not elaborate on the nature of the cleared work in a cold email.

### Follow-up

One follow-up, 7-10 days after the first email, if no response. Single sentence: "Following up on my note from [date] — happy to share my CV or schedule a brief call if there's interest." No more than one follow-up. After two unanswered emails, the answer is no.

---

## The Differentiator Calculus

Not all differentiators are equal. Here is how to weight them in this market:

**Active security clearance (Secret or above):** The strongest differentiator in the defense/national lab market. It eliminates 80-90% of competing applicants from cleared roles, removes a 6-18 month adjudication delay, and signals prior trusted access to sensitive programs. If you have this, lead with it in every letter for a cleared role. Put it in paragraph 2, one sentence, not buried at the bottom.

**Prior national lab experience (SULI, HERE, co-op, research visit):** A return candidate signal at peer institutions. ORNL alumni are looked at carefully at PNNL, SNL, ANL. The network is real and hiring managers check. Name the lab, the division, and the PI if possible.

**HPC scale:** "I ran MD simulations" is not a differentiator. "I managed a 2M core-hour allocation on NCAR Derecho to run 500 independent LAMMPS trajectories for uncertainty quantification" is a differentiator. It shows you operate at production scale, not classroom scale. If you have significant HPC allocations, name them with specificity.

**Open source code with real usage:** An active GitHub repo with stars, forks, or citations in other people's papers. Shows independent initiative, follow-through, and the ability to produce something others find useful. Rare for a first-year PhD student. If you have it, it is worth more than most academic accomplishments.

**DOE I-Corps / tech commercialization:** Exceptionally rare for a PhD student and valued at both national labs (who have explicit commercialization mandates) and hard tech startups (who want PhDs who understand the gap between research and deployment). If you have gone through I-Corps, SBIR, or similar, lead with it for startup and national lab applications.

**Publications and conference presentations:** Table stakes at the national lab level for competitive programs. Not a differentiator — an expectation. Do not lean on publications as your primary pitch. They tell the reader you can do research. They don't answer whether you can do useful work in 10 weeks.
