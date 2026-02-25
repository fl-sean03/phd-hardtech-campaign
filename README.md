# phd-internship-campaign

> Built by [Sean Florez](https://seanflorez.com) — PhD student, Materials Science & Engineering, CU Boulder.
> [Twitter](https://x.com/seanf1orez) · [LinkedIn](https://linkedin.com/in/sean-florez) · [GitHub](https://github.com/fl-sean03)

---

I'm a second-year materials science PhD student. The standard advice for finding a summer internship is: update your LinkedIn, go to career fairs, apply to a few places, hope.

I decided to build a systematic campaign instead.

In one session, using parallel AI agents running across every sector I'd ever want to work in, I generated:

- **130+ companies researched** across 12 sectors (national labs, defense primes, nuclear, hard tech, composites, semiconductor, energy materials, and more)
- **70+ complete application packages** — each with a tailored cover letter, pre-filled form fields, and a submission checklist
- **74 tracked opportunities** scored and tiered by fit, with confirmed URLs, deadlines, and pay
- Research that would have taken weeks done in hours

This repo is the public version of that system — stripped of my personal details, generalized into templates and prompts, and documented so anyone can run the same pipeline for their own background.

---

## What's in the Repo

```
phd-internship-campaign/
├── README.md                    ← you are here
├── METHODOLOGY.md               ← the full process, start to finish
├── MASTER_LIST.md               ← 130+ scored opportunities by sector and tier
├── POSITIONING_TEMPLATE.md      ← fill this in first, everything else reads it
├── COVER_LETTER_PRINCIPLES.md   ← what actually works for PhD→industry letters
│
├── research/                    ← deep company research, 12 sectors
│   ├── national-labs.md
│   ├── defense-energetics.md
│   ├── defense-fellowships.md
│   ├── nuclear.md
│   ├── ffrdc.md
│   ├── hardtech.md
│   ├── vc-portfolio.md
│   ├── composites.md
│   ├── hypersonics-propulsion.md
│   ├── energy-materials.md
│   ├── semiconductor-quantum.md
│   └── science-ai-materials.md
│
├── templates/                   ← fill-in-the-blank application packages
│   ├── STATUS_TEMPLATE.md
│   ├── APPLICATION_TEMPLATE.md
│   └── OUTREACH_TEMPLATE.md
│
└── prompts/                     ← AI prompts to run your own pipeline
    ├── README.md
    ├── positioning.md
    ├── sector_research.md
    ├── application_package.md
    └── master_list_synthesis.md
```

---

## How It Works

The system has three layers:

**1. Positioning.** Before writing a single cover letter, you define yourself precisely as a candidate. Technical stack. Key findings with numbers. What you don't have and why that's the honest framing for each application. This is `POSITIONING_TEMPLATE.md` — fill it in first. Every AI agent in the pipeline reads it.

**2. Sector research.** You don't start with job boards. You start with sectors — which ones use your technical background, which have programs that are legible to your experience, which have hard filters you clear or don't. The `research/` directory has done this for 12 sectors. The `prompts/sector_research.md` prompt lets you generate new sector research for your specific background.

**3. Application generation.** One directory per opportunity. `STATUS.md` holds company research, role analysis, fit score, URL, deadline. `APPLICATION.md` holds the cover letter, pre-filled form fields, and submission checklist. The `prompts/application_package.md` prompt generates both files when given your positioning doc + company research + job description. Run 10 of these in parallel. That's 10 tailored packages per hour.

---

## Quick Start

**If you want to use the research directly:**
1. Fill in `POSITIONING_TEMPLATE.md` with your background
2. Browse `MASTER_LIST.md` — sort by sector and score
3. Open the relevant `research/` files
4. Adapt `templates/APPLICATION_TEMPLATE.md` with your information

**If you want to run the full AI pipeline:**
1. Fill in `POSITIONING_TEMPLATE.md`
2. Read `METHODOLOGY.md`
3. Use `prompts/sector_research.md` to generate fresh research for your sectors
4. Use `prompts/application_package.md` to generate tailored packages in parallel

---

## Who This Is For

STEM PhD students — especially materials science, computational science, chemical engineering, and applied physics — applying to:

- **DOE national labs** — ORNL, LANL, ANL, LLNL, INL, PNNL, NREL, Sandia, BNL
- **Defense primes** — Lockheed Martin, RTX, Northrop Grumman, L3Harris, General Dynamics
- **FFRDCs** — MITRE, The Aerospace Corporation, MIT Lincoln Lab
- **Nuclear** — Kairos Power, TerraPower, X-energy, Oklo, Westinghouse, BWXT
- **Hard tech startups** — SBIR-funded, AFRL/DARPA-adjacent, advanced materials
- **Composites & aerostructures** — Hexcel, Spirit, Albany Engineered Composites
- **Semiconductor & quantum** — Applied Materials, Lam Research, Quantinuum
- **Energy materials** — Solid Power, Antora, Indium Corporation, Henkel

If your research produces results that translate to engineering decisions — processing parameters, material specifications, failure mechanisms — this system is calibrated for your context.

---

## The Core Problem This Solves

The bottleneck is not finding opportunities. Every PhD student can find a list of national labs. The bottleneck is **research depth at scale**.

A real application to a national lab or defense prime requires: knowing what programs they run, understanding what technical problems they're trying to solve, connecting your specific work to their specific needs, and writing a letter that demonstrates all of that clearly. Done manually, that's 2-3 hours per application.

Across 70 applications, that's months.

AI handles the research and generation. You handle the positioning inputs and the final review. The output is letters that name specific programs, reference specific technical work, and make a non-generic argument for why you specifically — not any materials science PhD — fit this role.

---

## The Research

The `research/` directory contains ~330KB of company intelligence across 12 sectors, compiled February 2026. Each file covers 10-25 companies with: what they do, what they hire PhD interns for, fit signals, application URLs and deadlines, and pay ranges.

This is not scraped from LinkedIn. It's written at the level of someone who read the company's published technical work.

It will go stale. URLs break, postings expire, programs change. Verify before submitting. But the company intelligence — what each organization works on, who funds them, what problems they're trying to solve — stays accurate longer than the posting links.

---

## License

MIT. Use it, adapt it, share it.

If you run this pipeline and it works, consider opening a PR with your sector research. The more sectors covered, the more useful this becomes for PhD students in fields other than materials science.

---

*Questions or feedback: [Twitter](https://x.com/seanf1orez) · [sean.florez@colorado.edu](mailto:sean.florez@colorado.edu)*
