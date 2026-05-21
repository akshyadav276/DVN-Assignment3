# Road Deaths Are Not Random
### DVN Assignment 3 - Data Narrative Studio

> "A single crash can feel unpredictable. But repeated fatality patterns are warnings."

---

## Project Overview

We are a specialist data consultancy presenting to an **Australian Transport Minister / Road Safety Funding Committee**.

Our dashboard transforms road fatality data into a decision tool. The project uses historical BITRE fatality data, ABS population enrichment, and latest-period weather context to identify where targeted intervention should go first.

## Core Story

**The Preventable Pattern: Two Road-Safety Problems Hidden in One National Number**

Australia's road fatalities have fallen since 1989, but recent progress has stalled. The latest data shows that deaths cluster into two intervention patterns:

1. Regional high-speed vehicle-occupant fatalities.
2. Urban arterial vulnerable-road-user fatalities.

The dashboard is designed to help policymakers choose targeted interventions rather than relying on a single generic road-safety campaign.

---

## Team & Roles

| Name | Role | Responsibilities |
|------|------|-----------------|
| Sonika Nanjundaiah | Architect | GitHub, project structure, enrichment logic, quality control |
| Remith Sajin | Data Preprocessor | Data cleaning, standardisation, data dictionary |
| Karthik Ramesh | Data Analyst | EDA, insights, drill-down analysis, supporting charts |
| Muhammad Asif | Integration Analyst | Join logic, ABS + weather enrichment, dataset validation |
| Shameel Zeshan | Dashboard Developer | Tableau build, advanced features, deployment |
| Pal Patel | Orator | User persona, narrative script, pitch deck |
| Akshita Yadav | Coordinator | Sprint coordination, task tracking, submission |

---

## Datasets

### Primary Dataset
| Field | Detail |
|-------|--------|
| **Name** | Australian Road Deaths Database (ARDD) |
| **Source** | Bureau of Infrastructure and Transport Research Economics (BITRE) |
| **URL** | https://www.bitre.gov.au/statistics/safety/fatal_road_crash_database |
| **Updated** | Monthly - current to January 2026 |

### Enrichment Datasets
| Dataset | Source | Purpose |
|---------|--------|---------|
| ABS Population Estimates | Australian Bureau of Statistics | Deaths per 100,000 normalisation |
| Open-Meteo Weather Data | open-meteo.com | Environmental crash context |

---

## Narrative Design

| Element | Choice |
|---------|--------|
| **Narrative Arc** | The Detective |
| **Core Argument** | Road deaths feel random, but the data reveals repeatable intervention patterns |
| **Target Audience** | Australian Transport Minister / Road Safety Funding Committee |
| **Call to Action** | Fund targeted intervention in high-risk road environments and user groups |

---

## Advanced Features

- [ ] **What-If Parameterization** - slider to model estimated lives saved under intervention scenarios.
- [ ] **Context-Aware Filtering** - selections update visuals and narrative context dynamically.
- [ ] **Visual Tooltips** - hover details reveal road-user, heavy-vehicle, and weather context.
- [ ] **Optional Dynamic Narrative Text** - selected state/segment updates explanatory text.

---

## Repository Structure

```text
Data Preperation/
  01_raw_audit/
  02_cleaning/
  03_integration/
  04_eda/
  05_tableau_inputs/
coordination/
data/
  raw/
  cleaned/
  integrated/
docs/
tableau/
presentation/
```

---

## Key Deadlines

| Part | Description | Due |
|------|-------------|-----|
| Part 1 | Individual Proposal | Sun 19 Apr |
| Part 2 | Live Pitch (in class) | Wed 13 May |
| Part 3 | Final Portfolio | Sun 17 May |

---

## Data Dictionary

See [`docs/data_dictionary.md`](docs/data_dictionary.md) for full variable definitions, data types, dashboard use, join logic, and limitations.

---

## Credits

| Resource | Source |
|----------|--------|
| Road fatality data | BITRE — Australian Road Deaths Database |
| Population data | Australian Bureau of Statistics (ABS) |
| Weather data | Open-Meteo Historical Archive API |
| Narrative framework | Segel & Heer (2010) - Narrative Visualisation |
