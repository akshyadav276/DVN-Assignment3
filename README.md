# The Everyday Fatality Pattern

## Where Australia should target road safety funding first

DVN Assignment 3 - Data Narrative Studio  
Group 18 | 36104 Data Visualisation and Narratives | May 2026

> A single crash can feel unpredictable. Repeated fatality patterns are warnings.

## Live Portfolio

**Live Tableau dashboard:** [The Everyday Fatality Pattern](https://public.tableau.com/app/profile/shameel.zeshan.khader.sheriff/viz/RoadDeathsAreNotRandomAustraliasPreventableFatalityPattern/FinalDashboard)

**Video walkthrough:** [3-minute technical walkthrough](https://youtu.be/NHzn_t8_Xpc)

**Tableau workbook:** [`tableau/DVN AT3 Final.twbx`](tableau/DVN%20AT3%20Final.twbx)

**Technical Tableau documentation:** [`tableau/README.md`](tableau/README.md)

## Executive Summary

We are a specialist data consultancy presenting to a **Federal Transport Minister reviewing national road safety funding priorities**.

Our dashboard transforms Australian road fatality data into a national funding decision tool. The core finding is:

> **Recent Australian road fatalities are not random: 70.8% sit in two priority theatres - regional high-speed roads and major-city urban streets. These theatres harm different people and need different safety responses.**

The dashboard therefore argues against generic road-safety messaging. It supports targeted national investment in the road environments where intervention can affect the most deaths.

## SILO Alignment

| Subject Intended Learning Outcome | How this portfolio demonstrates it |
|---|---|
| **SILO 1: Justify the selection and analysis of data as the basis for data narratives for different stakeholders** | The project selects BITRE fatality records as the primary real-world source because they contain national road death patterns relevant to a Federal Transport Minister. ABS population enrichment supports fair state comparison, while Open-Meteo is included only as state-month context with clear limitations. |
| **SILO 2: Apply a range of visualisation and narrative techniques to a variety of data types** | The dashboard uses temporal trend analysis, population-adjusted state bars, intervention-theatre comparison, stacked road-user bars, a day/time heatmap, KPI cards, tooltips, and a what-if parameter. These visuals combine temporal, spatial, categorical, and derived scenario data. |
| **SILO 3: Justify the selection of narrative tools and techniques to illuminate critical aspects of problems** | The Tableau story uses a What -> So What -> What Next arc to move from warning, to concentration, to human impact, to decision. Orange pre-attentive highlighting, Gestalt grouping, direct labels, and progressive story tabs reduce cognitive load and make the funding logic visible. |
| **SILO 4: Justify and communicate data narratives to stakeholders from a range of industries and contexts drawing on relevant data patterns and analyses** | The final dashboard is designed for a national road-safety funding decision maker. It translates the 70.8% concentration finding, NT risk comparison, road-user patterns, timing heatmap, and 96-lives what-if estimate into a clear recommendation for targeted policy action. |

## Key Findings

| Finding | Evidence |
|---|---:|
| Latest intervention window | 2024-Jan 2026 |
| Fatalities in scope | 2,714 |
| Change from 2024 to 2025 | +1.9% |
| Highest state resident risk | NT, 37.4 fatalities per 100,000 residents |
| Share in two priority theatres | 70.8% |
| Regional high-speed road fatalities | 1,065 |
| Major-city urban street fatalities | 857 |
| Highest timing cell | Sunday daytime, 198 fatalities |
| What-if estimate | 96 potential lives saved at 5% reduction across the two priority theatres |

## Target Persona

**Federal Transport Minister reviewing national road safety funding priorities**

The persona needs a concise, evidence-led view of where road-safety intervention should be prioritised nationally. They need to understand:

- whether the national trend is still improving
- which states carry the highest population-adjusted risk
- which road environments explain most recent fatalities
- which people are most harmed in those environments
- how a small targeted reduction could translate into potential lives saved

Detailed persona and user stories: [`docs/user_persona_and_stories.md`](docs/user_persona_and_stories.md)

## Narrative Arc

The project uses a **What -> So What -> What Next** narrative arc.

| Stage | Dashboard question | Evidence |
|---|---|---|
| What | Are fatalities still improving? | Annual trend and +1.9% increase from 2024 to 2025 |
| So What | Where should attention focus? | Population-adjusted state risk and 70.8% in two priority theatres |
| So What | Who is harmed and when? | Road-user group comparison and day/time heatmap |
| What Next | What could targeted action achieve? | What-if scenario estimator showing 96 potential lives saved at 5% |

The Tableau story tabs provide guided explanation. The **Final Dashboard** is the stakeholder-facing decision view.

## Data Sources And Rationale

| Dataset | Source | Level of detail | Why selected |
|---|---|---|---|
| Australian Road Deaths Database | BITRE | Fatality-record level, current to Jan 2026 | Primary real-world fatality data with temporal, spatial, road environment, and road-user fields |
| Estimated Resident Population | Australian Bureau of Statistics | State-year level | Enables fair state comparison through fatalities per 100,000 residents |
| Historical Weather Context | Open-Meteo | State-month level | Adds environmental context for the latest period; used carefully as context only |

This satisfies the rich-data requirement through recent real-world data, temporal variables, spatial variables, and enrichment beyond a single CSV.

## Data Integration Logic

BITRE is the base fatality-level dataset. Each row represents one person killed in a road crash. A crash can appear more than once if multiple people died.

Population is joined by:

```text
state + year
```

Weather is joined by:

```text
state + year + month
```

Weather is **state-month context only, not crash-day causation**. BITRE provides year, month, day of week, and time, but not the exact calendar crash date, so a daily or hourly weather join would create false precision.

Full methodology: [`docs/methodology.md`](docs/methodology.md)

## Key Derived Fields

| Field | Definition | Dashboard use |
|---|---|---|
| `intervention_theatre` | Combines remoteness and speed band into regional high-speed roads, major-city urban streets, and other road contexts | Focus area, human layer, what-if estimator |
| `road_user_group` | Groups detailed road users into vehicle occupants and vulnerable road users | Human layer |
| `fatalities_per_100k` | Fatalities divided by population, multiplied by 100,000 | State risk |
| `time_band` / `Time Band Short` | Groups crash time into policy-readable bands | Timing heatmap |
| `Potential lives saved` | Selected fatalities multiplied by target reduction percentage | What-if scenario estimator |

Full data dictionary:

- [`data_dictionary.csv`](data_dictionary.csv)
- [`calculated_fields_dictionary.csv`](calculated_fields_dictionary.csv)
- [`docs/data_dictionary.csv`](docs/data_dictionary.csv)
- [`docs/data_dictionary.md`](docs/data_dictionary.md)

## Dashboard Structure

| View | Purpose |
|---|---|
| `Story 1 - Warning` | Explains the annual trend and recent rise |
| `Story 2 - Fairness & Focus` | Shows population-adjusted state risk and the two priority theatres |
| `Story 3 - Human Pattern` | Shows how different road environments harm different people and when deaths cluster |
| `Story 4 - Decision / What-if` | Explains the scenario estimator |
| `Final Dashboard` | Main stakeholder-facing decision view |

Screenshots and Tableau documentation: [`tableau/README.md`](tableau/README.md)

## Advanced Tableau Features

| Feature | Implemented | Purpose |
|---|---:|---|
| Narrative story flow | Yes | Story tabs guide the viewer from warning to decision |
| Visual tooltips | Yes | Hover details reveal exact values and supporting context without cluttering the main view |
| What-if parameterisation | Yes | Target reduction percentage estimates potential lives saved |
| Context-aware filtering | Yes | Intervention theatre selection updates the potential lives saved estimate |

Advanced feature documentation: [`tableau/advanced_features_checklist.md`](tableau/advanced_features_checklist.md)

## What-if Scenario Estimator

The what-if panel is a transparent scenario estimator, not a causal prediction model.

```text
potential lives saved = selected fatalities x target reduction %
```

Current final-dashboard scenario:

```text
(1,065 regional high-speed fatalities + 857 major-city urban fatalities) x 5%
= 96.1
~= 96 potential lives saved
```

This lets the Federal Transport Minister test the scale of possible impact. It does not claim that a specific intervention will automatically produce that reduction.

## Visual Design Principles

| Principle | Application |
|---|---|
| Gestalt proximity | Related visuals are grouped by decision stage: warning, fairness, focus, human pattern, timing, and what-if action |
| Gestalt similarity | Repeated blue, orange, and grey encodings help the viewer recognise baseline evidence, priority highlights, and mixed context |
| Pre-attentive attributes | Orange highlights immediately draw attention to priority insights such as 70.8%, NT state risk, regional high-speed roads, and high-intensity heatmap cells |
| Cognitive load optimisation | Story tabs introduce the logic step by step; final dashboard uses direct labels, short callouts, and tooltips rather than long explanatory text |
| Accessibility | High-contrast labels, numeric annotations, direct chart labels, and legends reduce reliance on colour alone |

Detailed design notes: [`docs/visual_design_principles.md`](docs/visual_design_principles.md)

## Limitations

- The dashboard supports funding prioritisation, not causal proof.
- Weather is state-month context only and cannot prove crash-day causation.
- The what-if tool is a proportional scenario estimate, not a predictive policy model.
- State risk uses resident population, not exposure measures such as vehicle kilometres travelled or pedestrian/cyclist volumes.
- `Other road contexts` is intentionally mixed and therefore less directly actionable than the two priority theatres.

Full limitations: [`docs/limitations.md`](docs/limitations.md)

## Final Portfolio Files

```text
DVN-Assignment3/
|
|-- README.md                                  # Final portfolio landing page with dashboard link, story, methods, credits, and limitations
|-- data_dictionary.csv                        # Root copy of the mandatory data dictionary for marker access
|-- calculated_fields_dictionary.csv           # Tableau calculated fields, parameters, and scenario logic dictionary
|
|-- tableau/
|   |-- DVN AT3 Final.twbx                     # Packaged Tableau workbook for the final dashboard and story tabs
|   |-- README.md                              # Tableau-specific technical documentation and screenshot walkthrough
|   |-- advanced_features_checklist.md         # Evidence of narrative flow, tooltips, what-if parameter, and context-aware filtering
|   |-- tableau_workbook_notes.md              # Workbook organisation, calculated fields, QA notes, and design notes
|   |-- screenshots/                           # Exported screenshots of story views and final dashboard
|   |   |-- Story 1 Warning.png
|   |   |-- Story 2 Fairness & Focus.png
|   |   |-- Story 3 Human Pattern.png
|   |   |-- Story 4 What if.png
|   |   |-- Final Dashboard.png
|   |-- assets/                                # Dashboard visual assets used in Tableau
|
|-- docs/
|   |-- data_dictionary.csv                    # Mandatory variable dictionary with types, definitions, provenance, and dashboard use
|   |-- data_dictionary.md                     # Human-readable data dictionary summary
|   |-- methodology.md                         # Data cleaning, integration, joins, and derived-field methodology
|   |-- limitations.md                         # Analytical caveats and dashboard limitations
|   |-- credits.md                             # Supporting credits for data, tools, and sources
|   |-- user_persona_and_stories.md            # Persona, user stories, acceptance criteria, and definition of done
|   |-- visual_design_principles.md            # Gestalt, pre-attentive, cognitive load, and accessibility rationale
|   |-- dashboard_story.md                     # Written narrative flow behind the Tableau story and final dashboard
|
|-- data/
|   |-- cleaned/
|   |   |-- bitre_clean_detail.csv              # Cleaned fatality-level BITRE records
|   |   |-- bitre_state_month.csv               # State-month fatality aggregation
|   |   |-- population_state_year_clean.csv     # Cleaned ABS population data
|   |   |-- weather_monthly_state_clean_2024_jan2026.csv  # State-month weather context
|   |-- raw/                                   # Raw-data structure retained; source provenance is documented in docs/
|   |-- integrated/
|   |   |-- master_dashboard_story.csv           # Main Tableau-ready integrated fatality-level dataset
|
|-- Data Preperation/
|   |-- 01_Data_cleaning/                      # Data cleaning notebook(s)
|   |-- 02_integration/                        # Data integration notebook(s)
|   |-- 03_eda/                                # Exploratory analysis notebook(s)
|   |-- 04_tableau_inputs/                     # Tableau input preparation notebook(s)
|   |-- README.md                              # Data preparation notes
|
|-- presentation/
|   |-- README.md                              # Part 2 pitch summary and supporting presentation notes
|   |-- pitch_outline.md                       # Slide-by-slide pitch outline
|   |-- speaker_script_pal.md                  # Speaker script and Q&A preparation
|   |-- slides/                                # Pitch deck file
|   |-- screenshots/                           # Presentation screenshots
|
|-- coordination/
|   |-- coordination_tract.md                  # Integrated studio roles, task tracking, and collaboration evidence
|   |-- meeting_notes.md                       # Team meeting notes
|   |-- sprint_plan.md                         # Sprint plan and milestone tracking
```

## Team And Roles

| Name | Role | Responsibilities |
|---|---|---|
| Sonika Nanjundaiah | Architect | GitHub, project structure, enrichment logic, quality control |
| Remith Sajin | Data Preprocessor | Data cleaning, standardisation, data dictionary |
| Karthik Ramesh | Data Analyst | EDA, insights, drill-down analysis, supporting charts |
| Muhammad Asif | Integration Analyst | Join logic, ABS and weather enrichment, dataset validation |
| Shameel Zeshan | Dashboard Developer | Tableau build, advanced features, deployment |
| Pal Patel | Orator | User persona, narrative script, pitch deck |
| Akshita Yadav | Coordinator | Sprint coordination, task tracking, submission |

## Credits

### Data Sources

| Dataset | Source | Use in project |
|---|---|---|
| Australian Road Deaths Database | Bureau of Infrastructure and Transport Research Economics (BITRE) | Primary fatality-level road death records, current to January 2026 |
| Estimated Resident Population | Australian Bureau of Statistics (ABS) | State-year population denominator for fatalities per 100,000 residents |
| Historical Weather API | Open-Meteo | State-month weather context for the latest intervention window |

### Tools And Platforms

| Tool / platform | Use in project |
|---|---|
| Tableau Public | Interactive dashboard, story tabs, tooltips, parameter controls, and public deployment |
| Python / pandas | Data cleaning, validation, integration, derived fields, and EDA |
| GitHub | Code-track version control and final portfolio documentation |
| SharePoint / Teams | Design and strategy collaboration, presentation coordination, and group evidence |
| PowerPoint | Part 2 pitch deck and supporting presentation material |

### Frameworks And References

| Reference | Use in project |
|---|---|
| Segel and Heer (2010), Narrative Visualisation | Narrative design reference for structuring data storytelling |
| Human-centred design principles | Persona, user stories, acceptance criteria, and decision-focused dashboard design |
| Visual design principles | Gestalt proximity/similarity, pre-attentive attributes, cognitive load optimisation, and accessibility |

### Team Contributions

| Name | Contribution credited |
|---|---|
| Sonika Nanjundaiah | GitHub structure, project architecture, enrichment logic, and quality control |
| Remith Sajin | Data cleaning, standardisation, and data dictionary support |
| Karthik Ramesh | EDA, insight generation, and supporting analysis |
| Muhammad Asif | Data integration, ABS and weather joins, and validation |
| Shameel Zeshan | Tableau dashboard build, advanced Tableau features, deployment, and technical documentation |
| Pal Patel | Persona, narrative arc, pitch deck, and presentation script |
| Akshita Yadav | Sprint coordination, task tracking, and submission coordination |

Supporting credits file: [`docs/credits.md`](docs/credits.md)
