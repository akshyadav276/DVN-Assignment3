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

- `master_dashboard.csv`: one row per fatality.
- `state_year_rates.csv`: one row per state-year.
- `state_month_dashboard.csv`: one row per state-month.

