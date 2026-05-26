# Tableau Dashboard Documentation

## The Everyday Fatality Pattern

**Where Australia should target road safety funding first**

This Tableau workbook presents a data narrative about recent Australian road fatalities. It is designed to help a road-safety funding stakeholder move from a national warning signal to a targeted funding decision.

**Key message:** recent road fatalities are not random. In the latest intervention window, **70.8% of deaths sit in two priority theatres: regional high-speed roads and major-city urban streets**. These theatres harm different people and need different safety responses.

## Live Dashboard

Tableau Public: [The Everyday Fatality Pattern](https://public.tableau.com/app/profile/shameel.zeshan.khader.sheriff/viz/RoadDeathsAreNotRandomAustraliasPreventableFatalityPattern/FinalDashboard)

Workbook file: `DVN AT3 Final.twbx`

## Target Persona

**Primary persona:** Federal Transport Minister reviewing national road safety funding priorities.

The dashboard uses Australia-wide fatality data so the stakeholder can identify national intervention theatres and compare funding priorities fairly across states and road environments. The decision need is not to inspect every fatality record, but to answer:

> Where should limited road-safety funding be prioritised first, and what type of intervention should follow?

## Research Questions

1. Are Australian road fatalities still improving, or has progress slowed?
2. Which states carry the highest population-adjusted fatality risk?
3. Which road environments explain the largest share of recent fatalities?
4. Do those road environments harm different types of people?
5. What could a small targeted reduction mean in potential lives saved?

## Narrative Structure

The Tableau story follows a **What -> So What -> What Next** arc.

| Story point | Purpose | Main visual evidence |
|---|---|---|
| Story 1 - Warning | Establish urgency: fatalities rose again after the 2020 low. | Annual trend and 2025 callout |
| Story 2 - Fairness & Focus | Compare fair state risk and reveal the two priority theatres. | Fatalities per 100k and focus-area bar chart |
| Story 3 - Human Pattern | Show that different road environments harm different people. | Road-user group bars and day/time heatmap |
| Story 4 - Decision / What-if | Turn the insight into a funding scenario estimator. | Intervention theatre selector and target reduction parameter |
| Final Dashboard | Combine the evidence into one decision summary. | KPI row, trend, state risk, focus, human layer, heatmap, what-if panel |

## Dashboard Screenshots

### Story 1 - Warning

![Story 1 Warning](screenshots/Story%201%20Warning.png)

### Story 2 - Fairness & Focus

![Story 2 Fairness and Focus](screenshots/Story%202%20Fairness%20%26%20Focus.png)

### Story 3 - Human Pattern

![Story 3 Human Pattern](screenshots/Story%203%20Human%20Pattern.png)

### Story 4 - Decision / What-if

![Story 4 What if](screenshots/Story%204%20What%20if.png)

### Final Dashboard

![Final Dashboard](screenshots/Final%20Dashboard.png)

## Data Sources

| Dataset | Source | Level of detail | Dashboard role |
|---|---|---|---|
| Australian Road Deaths Database | BITRE | Fatality-record level, current to Jan 2026 | Primary fatality data: state, year, month, time, speed limit, road user, remoteness, road type |
| Estimated Resident Population | Australian Bureau of Statistics | State-year level | Converts raw state fatality counts into fatalities per 100,000 residents |
| Historical Weather Context | Open-Meteo | State-month level | Environmental context only; not used as crash-day causation |

## Data Integration Logic

The BITRE dataset is the base table. Each row represents one person killed in a road crash. A single crash can appear more than once if multiple people died.

Population was joined at **state + year** because the ABS population table is annual state-level data.

Weather was joined at **state + year + month** because the weather table was prepared as monthly state-level context.

Weather was not joined at exact date-time level because the BITRE data provides year, month, day of week, and time, but not the exact calendar date of each crash. Joining daily or hourly weather without the exact date would create false precision.

## Key Derived Fields

### Intervention Theatre

The `intervention_theatre` field groups fatalities into decision-relevant road environments using remoteness and speed limit.

| Category | Rule | Plain-language meaning |
|---|---|---|
| Regional high-speed roads | Inner Regional, Outer Regional, Remote, or Very Remote + speed limit 90 km/h and above | Non-major-city road environments where high speeds make crashes more severe |
| Major-city urban streets | Major Cities + speed limit 80 km/h and below | City road environments where vehicles mix with pedestrians, cyclists, and motorcyclists |
| Other road contexts | All other combinations | Mixed road contexts such as city motorways, lower-speed regional roads, unknown values, or less directly targeted patterns |

### Road User Group

The `road_user_group` field simplifies BITRE's detailed road-user categories into two policy groups.

| Category | Included values | Reason |
|---|---|---|
| Vulnerable road user | Pedestrian, pedal cyclist, motorcycle rider, motorcycle pillion passenger | These users have less physical protection in a crash |
| Vehicle occupant | Mainly drivers and passengers | Occupants are protected by a vehicle body, but still dominate regional high-speed fatalities |

Unknown values were handled separately during data preparation.

### Time Band

Crash time was grouped into policy-readable time windows such as late night, morning, daytime, evening, and night. This supports the day-of-week by time-band heatmap.

## What-if Scenario Estimator

The what-if panel is a transparent scenario estimator, not a causal prediction model.

Formula:

```text
potential lives saved = selected fatalities x target reduction %
```

Example shown in the dashboard:

```text
(1,065 regional high-speed fatalities + 857 major-city urban fatalities) x 5%
= 96.1
~= 96 potential lives saved
```

This feature helps a stakeholder test how small reductions in selected fatality patterns could translate into human impact. It does not claim that a specific policy will automatically produce that reduction.

## Advanced Tableau Features

| Feature | Where implemented | Purpose |
|---|---|---|
| Narrative story flow | Story 1 to Story 4 tabs + final dashboard | The final dashboard is the stakeholder-facing view; the story tabs are guided explanation views used to show the Federal Transport Minister how to read and use the dashboard |
| Visual tooltips | Trend, state risk, focus, and human-layer visuals | Reveals exact values and context without crowding the dashboard |
| What-if parameterisation | Story 4 and final dashboard | Lets the user select theatres and target reduction percentage |
| Context-aware filtering | Intervention theatre selector | Updates the lives-saved estimate based on selected road environments |

## Design System

The dashboard uses a restrained policy-style design system.

| Design choice | Rationale |
|---|---|
| Blue baseline marks | Neutral evidence and comparison values |
| Orange highlight marks | Orange is used as a universal attention signal — it marks the highest-risk element within each chart, not a fixed category.|
| Grey secondary marks | Mixed or lower-priority context that should remain visible but not dominate |
| Direct labels | Reduces cognitive load and avoids forcing the viewer to cross-reference legends |
| Story tabs | Breaks the analysis into smaller steps before showing the final decision summary |
| Callouts and annotations | Pull the viewer toward the intended story rather than leaving charts to be interpreted alone |

The final dashboard is the main stakeholder-facing product. It places the graphs in a deliberate reading path from warning, to fairness, to focus area, to human impact, to timing, and finally to the what-if decision tool. The story tabs are supporting explanation views used during presentation or onboarding to show the Federal Transport Minister how to interpret and use the final dashboard.

## Tableau Workbook Organisation

Worksheets and dashboards are organised around the story sequence:

- `Story 1 - Warning`
- `Story 2 - Fairness & Focus`
- `Story 3 - Human Pattern`
- `Story 4 - Decision / What-if`
- `Final Dashboard`
- Supporting worksheets for annual trend, state risk, focus area, human layer, timing heatmap, and scenario estimate

The workbook avoids using the default Tableau sheet names in the final presentation flow so that the dashboard structure is easier to audit.

## Limitations

1. **Weather is contextual, not causal.** Weather is joined at state-month level, so it cannot prove crash-day causation.
2. **No exact crash date is available.** BITRE provides year, month, day of week, and time, but not the full calendar date.
3. **The what-if tool is a scenario estimator.** It applies a user-selected percentage reduction to historical fatalities; it is not a predictive causal model.
4. **Population risk is state-level.** Fatalities per 100,000 residents does not include exposure measures such as vehicle kilometres travelled, pedestrian volumes, or trip frequency.
5. **Other road contexts is mixed.** This category preserves the full dataset but is less directly actionable than the two priority theatres.

## Future Improvements

- Add vehicle kilometres travelled, traffic volume, and pedestrian/cyclist exposure data.
- Add road safety investment and infrastructure data to assess intervention return more directly.
- Add exact crash-date weather if source data becomes available.
- Add LGA or SA4 hotspot mapping for local implementation planning.
- Convert the dashboard into a quarterly accountability tracker.

## Related Documentation

- [`../docs/data_dictionary.csv`](../docs/data_dictionary.csv)
- [`../docs/data_dictionary.md`](../docs/data_dictionary.md)
- [`../docs/methodology.md`](../docs/methodology.md)
- [`../docs/limitations.md`](../docs/limitations.md)
- [`../docs/credits.md`](../docs/credits.md)
- [`advanced_features_checklist.md`](advanced_features_checklist.md)
- [`tableau_workbook_notes.md`](tableau_workbook_notes.md)

## Credits

Data sources:

- BITRE Australian Road Deaths Database
- Australian Bureau of Statistics Estimated Resident Population
- Open-Meteo historical weather data

Tools:

- Tableau Public for dashboard development and deployment
- Python and pandas for data preparation and integration
- GitHub for version control and portfolio documentation

Project:

- 36104 Data Visualisation and Narratives
- DVN Assignment 3, Group 18
- May 2026
