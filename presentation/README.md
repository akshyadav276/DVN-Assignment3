The Everyday Fatality Pattern
Where Australia Should Target Road Safety Funding First

DVN — Group 18 | 36104 Data Visualisation and Narratives | Insight Lane

---

Overview

This repository contains the Part 2 pitch deck and supporting materials for our data visualisation project on Australian road safety fatalities.

We analysed 2,714 fatalities recorded between 2024 and January 2026 across the Australian Road Deaths Database, enriched with ABS population data and Open-Meteo weather context, to answer one funding question:

> "Which road safety theatres should receive priority funding to reduce fatalities fastest and most fairly?"

---

Target Audience

Stakeholder Hat: Federal Transport Minister reviewing national road safety funding priorities

Our stakeholder is a Federal Transport Minister reviewing national road safety funding priorities. They need to decide which road environments and road-user groups should receive priority attention across Australia.

---

Narrative Arc

We follow a What -> So What -> What Next narrative arc: first the warning, then the concentration and human pattern, then the funding decision.

```
THE SCALE          →    THE CONCENTRATION      →    THE OPPORTUNITY      →    THE ASK
2,714 deaths             70.8% in two                96 potential lives       3 targeted
+1.9% trend              intervention theatres       at just 5% reduction      funding actions
```

---

Live Dashboard

Tableau Public: https://public.tableau.com/app/profile/shameel.zeshan.khader.sheriff/viz/RoadDeathsAreNotRandomAustraliasPreventableFatalityPattern/FinalDashboard

The interactive dashboard supports:
- Population-adjusted state risk comparison for fair national prioritisation
- Visual tooltips that reveal year values, population denominators, fatality counts, and category context
- What-if scenario modelling: select an intervention theatre and target reduction % to estimate potential lives saved

---

Data Sources

| Dataset | Source | Scope | Role |
|---------|--------|-------|------|
| Australian Road Deaths Database (ARDD) | [BITRE](https://www.bitre.gov.au/statistics/safety/fatal_road_crash_database) | 1989–Jan 2026, monthly updates | Primary — all fatality records including road type, user group, state, time of day |
| ABS Population Data | [Australian Bureau of Statistics](https://www.abs.gov.au) | State-year estimated resident population | Enrichment — converts raw counts to per-capita rates for fair state comparison |
| Open-Meteo Historical Weather API | [Open-Meteo](https://open-meteo.com) | State-month context | Enrichment — seasonal and weather background context. Not used for crash-day causation |

---

Key Findings

| Finding | Data Point |
|---------|-----------|
| Total fatalities in scope | 2,714 (2024–Jan 2026) |
| Year-on-year change | +1.9% (2024 to 2025) |
| Highest state risk | NT — 37.4 deaths per 100,000 population |
| Lowest state risk | ACT — 4.2 deaths per 100,000 population |
| Highest resident risk | NT — 37.4 deaths per 100,000 population |
| Concentration | 70.8% of deaths in two intervention theatres |
| Deadliest cell | Sunday Daytime — 198 deaths |
| Lives saveable | 96 at a 5% targeted reduction across the two priority theatres |

---

Intervention Theatres

The dashboard identifies three road environments, each requiring a different intervention strategy:

| Theatre | Fatalities | Dominant User Group | Priority Action |
|---------|-----------|-------------------|----------------|
| Regional high-speed roads | 1,065 | Vehicle occupants (874) | Infrastructure upgrades, speed enforcement |
| Major-city urban streets | 857 | Vulnerable road users (506) | Speed reduction, pedestrian/cyclist infrastructure |
| Other road contexts | 792 | Mixed | Context-specific intervention |

---

Advanced Dashboard Features

| Feature | Description |
|---------|-------------|
| **What-If Parameterisation** | Select intervention theatre + target reduction % → see potential lives saved |
| **Context-Aware Filtering** | Intervention theatre selections dynamically update the potential lives saved estimate |
| **Visual Tooltips** | Hover on charts reveals detailed breakdown by road type and user group |

---

Call to Action

Three evidence-based recommendations for the Federal Transport Minister:

**01 — Prioritise Regional Roads in the Next Funding Cycle**
Regional high-speed roads carry the largest fatality count of any theatre. They should be prioritised for infrastructure, speed-management, and regional safety interventions.

**02 — Protect Urban Pedestrians and Cyclists Before Fatalities Rise Further**
Major-city streets account for 30% of deaths, overwhelmingly affecting pedestrians and cyclists. Targeted speed reduction and infrastructure upgrades will address the city-specific risk profile.

**03 — Turn the Dashboard into a National Accountability Tracker**
The dashboard is already built and live on Tableau Public. Commission it as an official quarterly monitoring tool. Transparent public reporting sustains political will across election cycles.

---

Team — DVN Group 18

| Name | Role | Responsibilities |
|------|------|-----------------|
| Sonika Nanjundaiah | Architect | Data pipeline, GitHub setup, project governance, Gantt |
| Karthik Ramesh | Data Analyst | EDA, insight generation, drill-down analysis |
| Remith Sajin | Data Preprocessor | Data cleaning, standardisation, data dictionary |
| Shameel Zeshan | Dashboard Developer | Tableau build, advanced features, deployment |
| Pal Patel | Orator | User persona, narrative arc, pitch deck, script |
| Muhammad Asif | Integration Analyst | Dataset joins, ABS + weather enrichment |
| Akshita Yadav | Coordinator | Sprint coordination, task tracking, submission |

---

Assessment Timeline

| Part | Deliverable | Status |
|------|------------|--------|
| Part 1 | Individual proposal + team plan | ✅ Submitted 19 April 2026 |
| **Part 2** | **Live pitch + slides** | **✅ Submitted 13 May 2026** |
| Part 3 | Final portfolio + video walkthrough | 🔄 Due 26 May 2026 |

---

Data Dictionary

| Variable | Type | Source | Description |
|----------|------|--------|-------------|
| Year / Month / Time | Temporal | BITRE ARDD | Fatality timing fields used for trend, monthly context, day-of-week, and time-band analysis |
| State | Categorical | BITRE ARDD | Australian state or territory |
| Road Type | Categorical | BITRE ARDD | Regional high-speed / Major-city urban / Other |
| User Group | Categorical | BITRE ARDD | Vehicle occupant / Vulnerable road user |
| Fatalities | Integer | BITRE ARDD | Number of fatality records, counted as one death per row |
| Population | Integer | ABS | State-year estimated resident population |
| Deaths per 100k | Float | Derived | Fatalities / Population × 100,000 |
| Weather Context | Categorical | Open-Meteo | State-month seasonal condition (context only) |

---

Methodology Notes

- Weather data is used as **state-month context only** — it is not attributed to individual crash causation
- Population-adjusted rates use ABS state-year estimated resident population as the denominator
- The what-if model applies a proportional reduction to selected recent fatalities; it is a scenario estimate, not a causal forecast
- Population joins use `state + year`; weather joins use `state + year + month`

---

*36104 Data Visualisation and Narratives | University of Technology Sydney | May 2026*
*Data sources: BITRE, Australian Bureau of Statistics, Open-Meteo*
