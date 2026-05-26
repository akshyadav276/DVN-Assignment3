# Pitch Outline — The Everyday Fatality Pattern
**DVN Studio — Group 18 | Assessment 3 Part 2 | 13 May 2026**

---

## Presentation Overview

| Item | Detail |
|------|--------|
| **Title** | The Everyday Fatality Pattern: Where Australia Should Target Road Safety Funding First |
| **Duration** | 5 minutes + 1.5 min Q&A |
| **Stakeholder Hat** | Federal Transport Minister reviewing national road safety funding priorities |
| **Narrative Arc** | Sparkline — concentration of fatalities in targetable road environments |
| **Decision Question** | Which road safety theatres should receive priority funding to reduce fatalities fastest and most fairly? |
| **Tool** | Tableau Public |
| **Orator** | Pal Patel |

---

## Narrative Arc — The Sparkline

The story is not just that road deaths happen. The story is that recent fatalities are **concentrating in specific road environments** — which means funding can be targeted much more intelligently.

```
WARNING          →    FAIRNESS LENS      →    FOCUS LENS         →    DECISION TOOL
Trend reversing       Population-adjusted      70.8% in two            96 lives at
after 2020 low        state risk rates         intervention theatres   5% intervention
```

Every visual answers one part of the Federal Transport Minister's national funding-priority decision question.

---

## Slide-by-Slide Breakdown

---

### Slide 1 — Title
- **Purpose:** Set the stakeholder hat and decision context immediately
- **Key message:** "Which road safety theatres should receive priority funding to reduce fatalities fastest and most fairly?"
- **Design choice:** Deep navy background, steel blue accent — matches Tableau dashboard palette, colourblind accessible

---

### Slide 2 — About the Data
- **Purpose:** Establish data credibility before the story begins
- **Key message:** Three sources. One integrated story.
- **Sources:**
  - BITRE ARDD — primary fatality records (1989–Jan 2026)
  - ABS Population Data — enables per-capita state comparison
  - Open-Meteo Weather API — seasonal context only, not crash causation
- **Narrative function:** Transparency builds trust with a strategy and funding audience

---

### Slide 3 — The Scale
- **Purpose:** Set the warning — progress has stalled
- **Key message:** After the lowest recent full year in 2020, fatalities are rising again. 1,316 deaths in 2025, +1.9% from 2024.
- **Visual:** Annual trend line chart 1989–2025 + 4 KPI cards
- **Narrative function:** The national trend alone is not enough — we need to know *where* deaths concentrate
- **Note:** 2026 excluded from trend — only January data available, would be misleading to compare as full year
- **Dashboard link:** Mirrors the Annual Trend chart with tooltip showing year-level detail

---

### Slide 4 — The Where
- **Purpose:** Fairness lens — population-adjusted state risk + intervention theatre definition
- **Key message:** NT has the highest resident risk at 37.4 deaths per 100k, showing why population-adjusted comparison matters.
- **Visual:** Horizontal bar chart by state (population-adjusted) + NT/ACT callout stats
- **Narrative function:** Raw counts mislead — per-capita rates reveal true structural disparity
- **Intervention theatre definition:**
  - Regional high-speed roads = remoteness (inner regional to very remote) + speed limit ≥ 90 km/h
  - Major-city urban streets = major city classification + speed limit ≤ 80 km/h
  - Other road contexts = everything outside those two patterns
- **Dashboard link:** Mirrors the State Risk chart with population denominator in tooltip

---

### Slide 5 — The Concentration
- **Purpose:** Focus lens — 70.8% of deaths in two targetable environments
- **Key message:** Regional high-speed roads: 1,065 deaths. Major-city urban streets: 857 deaths. Together = 70.8% of all fatalities.
- **Visual:** Focus area bar chart (left) + Human layer grouped bar chart (right)
- **Narrative function:** Concentration finding justifies targeted funding over generic spending
- **Human layer classification:**
  - Vulnerable road users = pedestrians, cyclists, motorcycle riders, pillion passengers
  - Vehicle occupants = drivers and passengers (all other known road users)
- **Key insight:** Regional roads → vehicle occupants dominant. City streets → vulnerable users dominant. Different environments need different interventions.
- **Dashboard link:** Mirrors Focus Area and Human Layer charts; orange highlight is pre-attentive cue for priority theatres

---

### Slide 6 — The Pattern
- **Purpose:** Myth-buster — daytime is the real fatality peak, not late night
- **Key message:** Sunday Daytime = 198 deaths — the highest single cell. Fatalities concentrate in ordinary everyday travel.
- **Visual:** Timing heatmap (day × time band) with daytime column highlighted
- **Narrative function:** Challenges assumption that road deaths are mainly a late-night problem
- **Dashboard link:** Mirrors the Timing Heatmap; Gestalt proximity groups related charts together to reduce cognitive load

---

### Slide 7 — The Opportunity
- **Purpose:** Decision tool — translate analysis into potential lives saved
- **Key message:** At 5% targeted reduction across both priority theatres, 96 potential lives saved.
- **Visual:** Large 96 stat (left) + intervention theatre selector (right)
- **Breakdown:** Regional high-speed: 53 lives | Major-city urban: 43 lives | Other: 40 lives
- **Narrative function:** Moves audience from understanding the problem to testing what action achieves
- **Dashboard link:** Directly mirrors the What-If Parameter Action widget — select theatre + % → lives saved updates live
- **Advanced feature highlighted:** What-If Parameterisation
- **Limitation:** Model is proportional calculation, not causal forecast

---

### Slide 8 — The Ask
- **Purpose:** Three specific, evidence-based funding recommendations
- **Key message:** The evidence is already visible. The remaining question is whether action follows.
- **Actions:**
  1. Prioritise regional roads in the next funding cycle (largest fatality theatre)
  2. Protect urban pedestrians and cyclists before fatalities rise further (30% of deaths, vulnerable users)
  3. Turn the dashboard into a national accountability tracker (already live on Tableau Public)
- **Narrative function:** Closes the arc — from data to decision

---

### Slide 9 — Closing / Thank You
- **Purpose:** Clean professional close + Q&A invitation
- **Key message:** "Road fatalities are no longer a mystery problem. The data now shows exactly where intervention saves the most lives."
- **Design:** Split panel — dark left with key stats recap, light right with Thank You + Questions

---

## Design Principles Applied

| Principle | Application |
|-----------|------------|
| Pre-attentive attributes | Orange/blue highlight on priority theatre bars draws eye immediately |
| Gestalt proximity | Related charts grouped together on concentration and human layer slides |
| Cognitive load reduction | Tableau story breaks analysis into sequential steps, one insight per view |
| Colour accessibility | Tableau steel blue `2E86AB` — colourblind safe, matches dashboard palette |
| Tooltips | Used throughout dashboard to reveal detail without cluttering main view |

---

## User Persona — Federal Transport Minister Reviewing National Road Safety Funding Priorities

| Attribute | Detail |
|-----------|--------|
| **Role** | Reviews national road safety funding priorities |
| **Goal** | Direct limited national attention and funding to road environments where intervention can reduce fatalities fastest and most fairly |
| **Pain point** | Raw counts mislead — bigger states dominate without per-capita adjustment |
| **What they need** | Fairness lens (per-capita state risk) + focus lens (intervention theatres) + decision tool (what-if) |
| **What moves them to act** | Clear concentration finding + specific theatre recommendations + lives-saved estimate |

---

## Dataset Sources

| Dataset | Source | Update Frequency | Role |
|---------|--------|-----------------|------|
| BITRE ARDD | [bitre.gov.au](https://www.bitre.gov.au/statistics/safety/fatal_road_crash_database) | Monthly (to Jan 2026) | Primary fatality records |
| ABS Population Data | [abs.gov.au](https://www.abs.gov.au) | Annual (2024 projections) | Per-capita rate normalisation |
| Open-Meteo Historical Weather API | [open-meteo.com](https://open-meteo.com) | Historical | Seasonal context only |

---

## Advanced Features (Tableau)

| Feature | Slide Reference | Description |
|---------|----------------|-------------|
| What-If Parameterisation | Slide 7 | Select theatre + target % → lives saved updates dynamically |
| Context-Aware Filtering | All data slides | State/year selections update all KPIs and charts in sync |
| Visual Tooltips | Slides 3, 4, 5 | Hover reveals population denominators, exact counts, theatre breakdowns |

---

## Key Limitations

- Dashboard designed for **funding prioritisation, not causal proof**
- Does not prove any single factor causes deaths
- Weather data is **state-month context only** — not crash-day causation
- What-if model is a **proportional linear calculation** — not a causal forecast
- 2026 data excluded from annual trend — January only, not a full year

---

*DVN — Group 18 | 36104 Data Visualisation and Narratives | University of Technology Sydney | May 2026*
