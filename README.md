# Digital Consumer Twin

**Methodology explainer and interactive Q&A demo for LLM-based synthetic consumer personas built from real research transcripts. Fictional persona, vanilla JS, self-contained HTML.**

A consumer twin is a synthetic respondent built from a real interview transcript and shopalong session. Once built and validated, it can be queried across use cases that weren't in the original research brief — creative briefing, concept reaction, co-creation — without running a new study.

This tool explains the methodology, shows the build pipeline, and demonstrates a twin in action using a fictional persona (Maya, 29, beauty and personal care shopper).

---

## Previews

### The case — why consumer twins exist
![The case tab](previews/preview_case.png)

### How it's built — the evaluation pipeline
![Build pipeline](previews/preview_build.png)

### Ask the twin — KOL briefing use case
![KOL briefing](previews/preview_twin-brief.png)

### Ask the twin — concept reaction use case
![Concept reaction](previews/preview_twin-concept.png)

### Ask the twin — co-creation use case
![Co-creation](previews/preview_twin-cocreate.png)

### Limitations — the honest slide
![Limitations](previews/preview_limits.png)

---

## What it demonstrates

**The core claim:** take a single real research session — an in-depth interview, a shopalong, or both — and turn it into a permanently queryable asset that lets stakeholders ask questions that weren't in the original brief, without recruiting new respondents.

The tool shows four things:

| Tab | What it covers |
|-----|---------------|
| **The case** | Problem framing, use case map, time and cost headline |
| **How it's built** | Six-step pipeline from raw transcript to deployed twin, with the analyst's role at each step |
| **Ask the twin** | Interactive Q&A demo across three use case types, with confidence tagging on every response |
| **Limitations** | What the twin cannot do, failure modes, when to run a real study instead |

---

## The three use case types

The core methodological contribution is mapping **temperature to use case** — not treating temperature as a single dial.

| Use case | Temperature | Output label | How to use it |
|----------|-------------|--------------|---------------|
| KOL & creative briefing | Low (0.2–0.4) | Grounded | Verbatim-quality consumer language for brief writing and copy platforms |
| Concept & promo reaction | Medium (0.5–0.7) | Extrapolated | Directional hypothesis — probe in a real study before acting |
| Co-creation & ideation | High (0.8–1.0) | Speculative | Ideation stimulus only — not research findings |

The **confidence tag** on every response (Grounded / Extrapolated / Speculative) makes the temperature setting visible to stakeholders, so they know how to interpret what they're reading.

---

## The build pipeline

```
Raw transcripts (IDI + shopalong)
        ↓
Cleaning & annotation by research context
        ↓
Persona system prompt construction
  — recalled statements vs inferred tendencies
        ↓
Validation against source transcript
  — accuracy, tone fidelity, hallucination rate
        ↓
Temperature calibration by use case
  — the core guardrail design
        ↓
Deployed twin + stakeholder enablement guide
```

The analyst's role doesn't disappear at deployment — it shifts from transcribing and summarizing to designing prompts, validating outputs, and knowing when to stop querying and start fielding a real study.

---

## On the demo format

Responses in the "Ask the twin" tab are pre-authored and manually validated against Maya's fictional research transcripts. A live API implementation is straightforward but omitted to avoid rate limits and cost in a public portfolio context.

The Q&A set was deliberately designed to show the full range:
- **Grounded** — direct transcript recall, minimal inference
- **Extrapolated** — reasoned from established patterns to new stimuli
- **Speculative** — imaginative, co-creation territory
- **Out of scope** (documented in Limitations) — where the twin declines to answer

That last one is the most important design decision: a twin that answers everything confidently is less useful than one that knows its own edges.

---

## Files

```
digital-consumer-twin/
├── index.html          # Self-contained tool (open in any browser)
├── README.md           # This file
└── previews/
    ├── preview_case.png
    ├── preview_build.png
    ├── preview_twin-brief.png
    ├── preview_twin-concept.png
    ├── preview_twin-cocreate.png
    └── preview_limits.png
```

No build step, no dependencies, no server. Open `index.html` in a browser.

---

## Persona

Maya is a fictional composite constructed to demonstrate the methodology. She is not based on any real individual.

| Attribute | Detail |
|-----------|--------|
| Age | 29 |
| Life stage | Working professional, single |
| Category | Beauty & personal care |
| Routine | 3-step minimalist — strict about it |
| Channels | Drugstore for staples, online for discovery |
| Price stance | Mid-tier; skeptical of premium claims |
| Built from | Brand usage IDI · Drugstore shopalong · Pack size study |

---

## Stack

- Vanilla JS — no framework
- No external dependencies (Chart.js not used in this tool)
- CSS custom properties for theming
- `noindex` meta tag set

---

## Suggested repo topics

`consumer-research` `llm-evaluation` `synthetic-persona` `qualitative-research` `generative-ai` `insights` `vanilla-js` `portfolio`

---

*Built as part of a custom analytics and AI tools portfolio. Synthetic persona, illustrative methodology. Not for distribution.*
