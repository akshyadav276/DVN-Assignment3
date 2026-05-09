# Data Preparation Track

This folder holds the code-track work for Assignment 3.

## Workflow

1. `01_raw_audit/` - raw dataset audits and source checks.
2. `02_cleaning/` - dataset-specific cleaning notebooks.
3. `03_integration/` - joins and dashboard-ready master files.
4. `04_eda/` - exploratory summaries that decide the dashboard story.
5. `05_tableau_inputs/` - final CSVs used in Tableau.

## Rules

- Keep raw data unchanged.
- Document every cleaning rule.
- Validate row counts before and after joins.
- Use `master_dashboard.csv` for row-level Tableau visuals.
- Use `state_year_rates.csv` for fatalities per 100,000 population.

