# Advanced Tableau Features Checklist

This file documents the advanced Tableau features used in the final dashboard portfolio. The features are implemented to support the persona: **Federal Transport Minister reviewing national road safety funding priorities**.

## Implemented Features

| Requirement | Status | Where it appears | How it supports the story |
|---|---:|---|---|
| Narrative scrollytelling / guided narrative flow | Complete | `Story 1 - Warning` to `Story 4 - Decision / What-if`, plus `Final Dashboard` | The story tabs explain how to read the evidence. The final dashboard is the stakeholder-facing decision view arranged from warning, to fairness, to focus, to human impact, to timing, to what-if action. |
| Visual tooltips | Complete | Annual trend, state risk, focus area, human layer, timing heatmap | Tooltips reveal exact year values, population denominators, fatality counts, and category context without overloading the main view. |
| What-if parameterisation | Complete | `Story 4 - Decision / What-if` and `Final Dashboard` | The target reduction percentage lets the stakeholder estimate potential lives saved under different reduction scenarios. |
| Context-aware filtering | Complete, scoped to scenario estimator | Intervention theatre selector in the what-if panel | Selecting or removing intervention theatres updates the `Potential lives saved` estimate and turns the dashboard from description into a decision tool. |

## What-if Scenario Logic

The what-if panel is a transparent scenario estimator, not a causal prediction model.

```text
potential lives saved = selected fatalities x target reduction %
```

Current dashboard example:

```text
(1,065 regional high-speed fatalities + 857 major-city urban fatalities) x 5%
= 96.1
~= 96 potential lives saved
```

## Feature Notes

- The final dashboard shows the stakeholder-ready decision view.
- The story tabs are supporting explanation views used during presentation or onboarding.
- Weather is present as contextual enrichment and source context, but it is not used to claim crash-day causation.
- Dynamic narrative text by selected state was considered but not used in the final build, because the assessment story is focused on national funding priorities rather than single-state drilldown.

## QA Status

| Check | Status | Notes |
|---|---:|---|
| Tableau Public dashboard opens without requiring login | Complete | Dashboard is hosted publicly. |
| Story tabs are named logically | Complete | `Story 1 - Warning`, `Story 2 - Fairness & Focus`, `Story 3 - Human Pattern`, `Story 4 - Decision / What-if`. |
| Final dashboard is available as the stakeholder-facing view | Complete | `Final Dashboard` combines the full decision path. |
| What-if value matches selected priority theatres | Complete | Two priority theatres selected at 5% produces 96 potential lives saved. |
| Tooltips do not replace visible labels | Complete | Main charts retain direct labels; tooltips provide detail only. |
| 2026 is handled as partial year | Complete | 2026 is excluded from full-year annual comparison and documented as partial. |
| Colour system is consistent and documented | Complete | Orange = attention signal throughout; blue = baseline evidence; grey = secondary context |
