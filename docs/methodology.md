# Methodology

## Pipeline

1. Raw data audit.
2. Dataset-specific cleaning.
3. Validation of missing values, duplicates, date coverage, and key fields.
4. Integration using explicit join keys.
5. Focused EDA to determine the evidence-led dashboard story.
6. Tableau dashboard build and visual QA.

## Join Logic

| Join | Keys | Purpose |
|---|---|---|
| BITRE + population | `state`, `year` | Fatalities per 100,000 residents |
| BITRE + weather | `state`, `year`, `month` | Latest-period state-month weather context |

## Dashboard Grain

- Tableau integrated extract / `master_dashboard_story`: one row per fatality in the dashboard-ready model.
- `population_state_year_clean.csv`: one row per state-year for the population denominator.
- `bitre_state_month.csv`: one row per state-month for efficient trend and monthly aggregation support.
- `weather_monthly_state_clean_2024_jan2026.csv`: one row per state-month for contextual weather enrichment.
