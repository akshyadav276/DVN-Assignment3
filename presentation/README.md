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

Stakeholder Hat: National Road Safety Funding Committee

Our stakeholder is a national road safety funding committee advising the Federal Transport Minister. They need to decide where limited road safety funding should be targeted first.

Secondary stakeholders: State transport agencies and road safety decision-makers across Australian jurisdictions.

---

Narrative Arc

We follow the Sparkline narrative arc — the story of the gap between where Australia currently sits on road fatalities and where it needs to be, framed around a funding decision.

```
THE SCALE          →    THE CONCENTRATION      →    THE OPPORTUNITY      →    THE ASK
2,714 deaths             70.8% in two                136 lives saveable        3 targeted
+1.9% trend              intervention theatres       at just 5% reduction      funding actions
```

---

Live Dashboard

Tableau Public: https://public.tableau.com/app/profile/shameel.zeshan.khader.sheriff/viz/DVNAT3_17785102792850/Dashboard1

The interactive dashboard supports:
- State and year filtering with dynamic KPI updates
- Geographic hotspot mapping at state level
- What-if scenario modelling — select an intervention theatre and target reduction % to estimate potential lives saved

---

Data Sources

| Dataset | Source | Scope | Role |
|---------|--------|-------|------|
| Australian Road Deaths Database (ARDD) | [BITRE](https://www.bitre.gov.au/statistics/safety/fatal_road_crash_database) | 1989–Jan 2026, monthly updates | Primary — all fatality records including road type, user group, state, time of day |
| ABS Population Data | [Australian Bureau of Statistics](https://www.abs.gov.au) | 2024 state-level projections | Enrichment — converts raw counts to per-capita rates for fair state comparison |
| Open-Meteo Historical Weather API | [Open-Meteo](https://open-meteo.com) | State-month context | Enrichment — seasonal and weather background context. Not used for crash-day causation |

---

Key Findings

| Finding | Data Point |
|---------|-----------|
| Total fatalities in scope | 2,714 (2024–Jan 2026) |
| Year-on-year change | +1.9% (2024 to 2025) |
| Highest state risk | NT — 37.4 deaths per 100,000 population |
| Lowest state risk | ACT — 4.2 deaths per 100,000 population |
| Risk disparity | NT drivers face 8.9× higher risk than ACT drivers |
| Concentration | 70.8% of deaths in two intervention theatres |
| Deadliest cell | Sunday Daytime — 198 deaths |
| Lives saveable | 136 at just 5% targeted intervention across all theatres |

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
| **Context-Aware Filtering** | State and year selections dynamically update all KPIs and charts |
| **Visual Tooltips** | Hover on charts reveals detailed breakdown by road type and user group |

---

Call to Action

Three evidence-based recommendations for the National Road Safety Funding Committee:

**01 — Prioritise Regional Roads in the Next Funding Cycle**
Regional roads carry 39% of all deaths — the highest of any theatre — yet receive the smallest share of safety investment. NT, WA, and QLD are the priority states.

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
| Part 3 | Final portfolio + video walkthrough | 🔄 Due 17 May 2026 |

---

Data Dictionary

| Variable | Type | Source | Description |
|----------|------|--------|-------------|
| Crash Date | Datetime | BITRE ARDD | Date and time of fatal crash |
| State | Categorical | BITRE ARDD | Australian state or territory |
| Road Type | Categorical | BITRE ARDD | Regional high-speed / Major-city urban / Other |
| User Group | Categorical | BITRE ARDD | Vehicle occupant / Vulnerable road user |
| Fatalities | Integer | BITRE ARDD | Number of deaths per crash record |
| Population | Integer | ABS | State-level population estimate (2024 projection) |
| Deaths per 100k | Float | Derived | Fatalities / Population × 100,000 |
| Weather Context | Categorical | Open-Meteo | State-month seasonal condition (context only) |

---

Methodology Notes

- Weather data is used as **state-month context only** — it is not attributed to individual crash causation
- Population-adjusted rates use ABS 2024 projections applied to ARDD state-level counts
- The what-if model applies a proportional reduction to historical fatality counts — a conservative linear approximation
- All three datasets were joined using state (spatial key) and state+month (temporal key)

---

*36104 Data Visualisation and Narratives | University of Technology Sydney | May 2026*
*Data sources: BITRE, Australian Bureau of Statistics, Open-Meteo*
