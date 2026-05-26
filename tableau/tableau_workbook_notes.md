# Tableau Workbook Notes

Owner: Shameel Zeshan  
Workbook: `DVN AT3 Final.twbx`  
Primary persona: **Federal Transport Minister reviewing national road safety funding priorities**

## Workbook Purpose

The Tableau workbook presents a national road-safety funding narrative. The final dashboard is the stakeholder-facing decision view. The story tabs are guided explanation views used to show how the persona should read and use the final dashboard.

## Live Dashboard

Tableau Public: [The Everyday Fatality Pattern](https://public.tableau.com/app/profile/shameel.zeshan.khader.sheriff/viz/RoadDeathsAreNotRandomAustraliasPreventableFatalityPattern/FinalDashboard)

## Primary Data Model

The packaged workbook uses the integrated Tableau extract based on `master_dashboard_story`.

Core source inputs:

| Input | Role |
|---|---|
| `bitre_clean_detail.csv` | Fatality-level road death records from BITRE |
| `population_state_year_clean.csv` | ABS state-year population denominator for fatalities per 100k |
| `weather_monthly_state_clean_2024_jan2026.csv` | State-month weather context, not crash-day causation |
| `bitre_state_month.csv` | State-month fatality aggregation for trend support |

Join logic:

- BITRE is the base fatality-level dataset.
- Population joins by `state + year`.
- Weather joins by `state + year + month`.
- Weather is included as state-month context only because BITRE does not include the exact calendar date of each crash.

## Key Calculated Fields

| Field | Purpose |
|---|---|
| `Intervention Theatre` | Groups fatalities into `Regional high-speed roads`, `Major-city urban streets`, and `Other road contexts`. |
| `Road User Group` | Groups detailed road users into `Vehicle occupant` and `Vulnerable road user`. |
| `Fatalities per 100k` | Population-adjusted state risk measure. |
| `Priority Theatre Share` | Calculates the share of recent deaths in the two priority theatres. |
| `Potential lives saved` | What-if scenario estimate from selected fatalities and target reduction percentage. |
| `Time Band Short` | Simplifies time-of-day groups for the timing heatmap. |

## Parameter

| Parameter | Current setting | Role |
|---|---:|---|
| `Target reduction %` | 5% | Used in the what-if scenario estimator. |

Formula:

```text
potential lives saved = selected fatalities x target reduction %
```

Current final-dashboard state:

```text
Regional high-speed roads + Major-city urban streets selected
Other road contexts excluded
Target reduction = 5%
Potential lives saved = 96
```

## Workbook Structure

| View | Role |
|---|---|
| `Story 1 - Warning` | Explains the annual trend and recent increase. |
| `Story 2 - Fairness & Focus` | Explains population-adjusted state risk and the two priority theatres. |
| `Story 3 - Human Pattern` | Explains road-user differences and day/time concentration. |
| `Story 4 - Decision / What-if` | Explains how the scenario estimator works. |
| `Final Dashboard` | Main stakeholder-facing dashboard. |

Supporting worksheets include:

- `01 Intervention Theatres`
- `02 Human Layer`
- `03 Annual Trend`
- `04 State Risk Per 100k`
- `05 Timing Heatmap`
- `06 What If Lives Saved`
- `KPI 1: Latest Fatalities`
- `KPI 2: 2025 Increase`
- `KPI 3: Highest state risk per 100k`
- `KPI 4: Priority Theatre Share`

## Design Notes

- Orange is used as a pre-attentive highlight for priority insights and high-risk patterns.
- Blue is used as the neutral evidence colour.
- Grey is used for secondary or mixed context, especially `Other road contexts`.
- Direct labels are used on major charts to reduce cognitive load.
- The final dashboard reads from top to bottom: national warning, fair state risk, focus area, human pattern, timing pattern, and what-if decision.

## QA Checklist

| Check | Status | Notes |
|---|---:|---|
| Tableau Public link works | Complete | Link points to the final dashboard view. |
| Workbook is packaged for submission | Complete | `DVN AT3 Final.twbx` includes the extract and required visual asset. |
| Final dashboard text is readable | Complete | Dashboard uses direct labels and short callouts. |
| 2026 is documented as partial | Complete | 2026 is excluded from full-year annual trend comparison. |
| State risk uses population adjustment | Complete | Rates use fatalities per 100,000 residents. |
| Weather caveat is visible/documented | Complete | Weather is state-month context only, not crash-day causation. |
| What-if scenario displays 96 for the two priority theatres at 5% | Complete | `Other road contexts` is excluded in the final dashboard scenario. |
| Story tabs support explanation | Complete | Story tabs guide presentation/onboarding; final dashboard remains the main stakeholder view. |

## Known Limitations

- The dashboard is designed for funding prioritisation, not causal proof.
- The what-if estimate is a proportional scenario calculation, not a predictive policy model.
- Weather cannot be joined at crash date-time level because BITRE does not provide exact crash dates.
- `Other road contexts` is intentionally mixed and therefore less directly actionable than the two priority theatres.
