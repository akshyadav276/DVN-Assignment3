#  Road Deaths Are Not Random
### DVN Assignment 3 — Data Narrative Studio

> *"Across Australia's road fatality record, deaths are not random. This dashboard shows where they are concentrated and what a Transport Minister can do about it."*

---

##  Project Overview

We are a specialist data consultancy presenting to a **State Transport Minister**.
Using the **Sparkline narrative arc** showing the gap between current road deaths 
and Australia's 2030 National Road Safety Target.

---

##  Team & Roles

| Name | Role | Responsibilities |
|------|------|-----------------|
| Sonika Nanjundaiah |  Architect |  GitHub, enrichment, What-If Parameter Action |
| Remith Sajin |  Data Preprocessor | Data cleaning, standardisation, data dictionary |
| Karthik Ramesh |  Data Analyst | EDA, insights, drill-down analysis, supporting charts |
| Muhammad Asif |  Integration Analyst | Join logic, ABS + weather enrichment, dataset validation |
| Shameel Zeshan |  Dashboard Developer | Tableau build, advanced features, deployment |
| Pal Patel |  Orator | User persona, narrative script, pitch deck |
| Akshita Yadav |  Coordinator | Sprint coordination, task tracking, submission |

---

##  Repository Structure

---

##  Datasets

### Primary Dataset
| Field | Detail |
|-------|--------|
| **Name** | Australian Road Deaths Database (ARDD) |
| **Source** | Bureau of Infrastructure and Transport Research Economics (BITRE) |
| **URL** | https://www.bitre.gov.au/statistics/safety/fatal_road_crash_database |
| **Updated** | Monthly — current to 2025 |

### Enrichment Datasets
| Dataset | Source | Purpose |
|---------|--------|---------|
| ABS Population Estimates | Australian Bureau of Statistics | Deaths per 100,000 normalisation |
| Open-Meteo Weather Data | open-meteo.com | Environmental crash context |

---

##  Narrative Design

| Element | Choice |
|---------|--------|
| **Narrative Arc** | The Sparkline |
| **Core Argument** | Road deaths are not random — they are concentrated by place, time, road user and environment |
| **Target Audience** | State Transport Minister |
| **Call to Action** | Fund targeted intervention in highest-risk state, time and road-user combinations |

---

## Advanced Features

- [ ] **What-If Parameterization** — slider to model lives saved under different speed reduction scenarios
- [ ] **Context-Aware Filtering** — selections update narrative text and visuals dynamically
- [ ] **Visual Tooltips** — hover reveals deeper stats and mini-charts

---

## Key Deadlines

| Part | Description | Due |
|------|-------------|-----|
| Part 1 | Individual Proposal | Sun 19 Apr |
| Part 2 | Live Pitch (in class) | Wed 13 May |
| Part 3 | Final Portfolio | Sun 17 May |

---

## Data Dictionary

See `docs/data_dictionary.md` for full variable definitions, data types and provenance.

---

## Credits

| Resource | Source |
|----------|--------|
| Road fatality data | BITRE — Australian Road Deaths Database |
| Population data | Australian Bureau of Statistics (ABS) |
| Weather data | Open-Meteo Historical Archive API |
| Narrative framework | Segel & Heer (2010) — Narrative Visualisation |
