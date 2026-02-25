# Contributing

This repo is maintained as a living resource. There are two types of contributions:

---

## Type 1: Quick Fixes (15 minutes)

For stale data that doesn't change the methodology:

- **Dead URL → working URL:** Open a PR with the fix, label `fix: dead-link`
- **Posting closed or deadline passed:** Update `MASTER_LIST.md`, label `fix: stale-posting`
- **Pay rate outdated:** Update with a source citation, label `fix: compensation`

No issue required. Open a PR directly.

---

## Type 2: New Content (1–3 hours)

For adding new sectors, companies, or fields:

**New sector research doc:** Use `prompts/sector_research.md` with your own `POSITIONING_TEMPLATE.md` filled in for your background. Review and verify all company details (URLs, deadlines, program names). Submit a PR to `research/`.

**New field adaptation:** If you're adapting this for a different PhD field (biomedical, ChemE, computational physics, etc.), open an issue first describing your target background and intended scope. The current research is calibrated for computational/experimental materials science — contributions from adjacent fields are welcome but must specify their target audience clearly.

**New prompt:** Add to `prompts/` with the naming convention `[action]_[output].md`. Include a one-paragraph description at the top of the file explaining what the prompt does, what inputs it requires, and what it produces.

---

## Field Coverage Guidelines

Each research doc should specify its target background in the file header. Good:

> *This sector research is calibrated for materials science or chemical engineering PhDs with experience in MD simulation, DFT, or experimental characterization. Candidates from adjacent fields should use as background context, not direct fit signal.*

Bad: *"This sector works for all STEM students."*

Generic STEM advice is not useful. Specificity is the point.

---

## Staleness Policy

Each `research/` file has a compilation date in the header. PRs that update a file should bump the date. Files older than 18 months with no activity will be labeled `stale: needs-review`.

Company intelligence (what organizations work on, their programs, their funding) stays accurate longer than posting links. URL fixes are urgent. Program description updates are lower priority.

---

## What We Don't Accept

- Generic career advice not specific to STEM PhD candidates
- Companies with no documented intern program (cold outreach targets are fine in `MASTER_LIST.md` under Cold Outreach — not in research docs)
- Unverified pay rates without a source
- Personal information — no names, institutions, or identifying details in research files

---

## Annual Cycle

Each summer application cycle (roughly October–March for the following summer), the current `MASTER_LIST.md` is frozen in place and a new cycle branch begins. Contributors updating for a new cycle should open an issue tagged `cycle: [year]`.

---

## PR Checklist

- [ ] All URLs in my changes are live as of today
- [ ] Compilation date is specified in any new or updated research file
- [ ] New company entries include: program name, posting URL, deadline, pay (if public), citizenship/clearance requirements, fit signal
- [ ] No personal information (my name, institution) in research or template files
