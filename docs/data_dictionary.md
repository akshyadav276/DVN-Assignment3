# Data Dictionary - DVN Assignment 3

This data dictionary covers the cleaned datasets used for the road-fatality narrative dashboard. The core analytical unit is a road fatality from the BITRE Australian Road Deaths Database. Population is used for fair state-level risk comparison, and weather is used as state-month contextual enrichment for the latest policy window.

## Dataset Overview

| File | Rows | Columns | Grain | Main Dashboard Use |
|---|---:|---:|---|---|
| `bitre_clean_detail.csv` | 58,284 | 34 | One row per fatality | Main detailed fatality dataset for historical and pattern analysis |
| `bitre_state_month.csv` | 3,367 | 6 | One row per state-month | Efficient historical trend chart |
| `population_state_year_clean.csv` | 360 | 5 | One row per state-year | Fatalities per 100,000 population |
| `weather_monthly_state_clean_2024_jan2026.csv` | 200 | 15 | One row per state-month | Latest-period weather context |

## `bitre_clean_detail.csv`

| Column | Type | Definition | Dashboard Use | Notes |
|---|---|---|---|---|
| `crash_id` | Integer | Unique crash identifier from BITRE. | Traceability only; usually hidden from visuals. | Duplicate crash IDs can be valid because one crash may involve multiple fatalities. |
| `state` | Text | Australian state or territory code. | Main filter, state comparisons, population join. | Values: ACT, NSW, NT, QLD, SA, TAS, VIC, WA. |
| `month` | Integer | Month of fatality record, 1-12. | Time filtering and monthly aggregation. | Used with `year` to join monthly weather. |
| `year` | Integer | Calendar year of fatality record. | Trend, filter, population join. | 1989 to 2026 in BITRE file. |
| `dayweek` | Text | Day of week of the fatal crash. | Time-risk heatmap. | Monday to Sunday. |
| `time` | Text | Recorded crash time. | Source field for `hour` and `time_band`. | Use derived `time_band` for dashboard readability. |
| `crash_type` | Text | Whether the crash was single-vehicle, multiple-vehicle, or unknown. | Road environment/pattern analysis. | Useful with speed and road type. |
| `bus_involvement` | Text | Whether a bus was involved. | Tooltip/filter for heavy-vehicle context. | Values standardised to Yes, No, Unknown. |
| `heavy_rigid_truck_involvement` | Text | Whether a heavy rigid truck was involved. | Tooltip/filter for heavy-vehicle context. | Historical missingness is high, so use carefully. |
| `articulated_truck_involvement` | Text | Whether an articulated truck was involved. | Tooltip/filter for heavy-vehicle context. | Values standardised to Yes, No, Unknown. |
| `speed_limit` | Numeric | Posted speed limit at crash location. | Road environment analysis. | Missing or `-9` values converted to blank/unknown. |
| `road_user` | Text | Road-user type of the fatality. | Road-user exposure visual. | Driver, passenger, pedestrian, motorcycle rider, pedal cyclist, etc. |
| `gender` | Text | Gender of person killed. | Demographic breakdown and tooltip. | Use with sensitivity; avoid overclaiming without exposure data. |
| `age` | Numeric | Age of person killed. | Source for `age_band`; tooltip detail. | `-9` converted to missing. |
| `national_remoteness_areas_2021` | Text | ABS remoteness category for crash location. | Source for `remoteness_group`. | Historical records have many Unknown values; recent data is more complete. |
| `sa4_name_2021` | Text | Statistical Area Level 4 name. | Geographic detail, tooltip, optional ranking. | Stronger in recent years than historical records. |
| `national_lga_name_2021` | Text | Local Government Area name. | Local detail, tooltip, optional ranking. | Stronger in recent years than historical records. |
| `national_road_type` | Text | Type/classification of road. | Road environment matrix. | Historical records have many Unknown values. |
| `christmas_period` | Text | Whether fatality occurred in BITRE Christmas period. | Holiday-period filter/context. | Values: Yes, No. |
| `easter_period` | Text | Whether fatality occurred in BITRE Easter period. | Holiday-period filter/context. | Values: Yes, No. |
| `month_start` | Date | Month-start date created from `year` and `month`. | Time-series axis and monthly aggregation. | Not exact crash date; BITRE file provides month/year, not day. |
| `year_month` | Text | Year-month label. | Join key support and labels. | Format: YYYY-MM. |
| `month_name` | Text | Month name derived from `month_start`. | Seasonal/monthly labels. | Example: January, February. |
| `deaths` | Integer | Count field where each fatality row equals 1. | Measure for counts and aggregations. | Sum to calculate fatalities. |
| `age_band` | Text | Age grouped into dashboard-friendly bands. | Road-user exposure and demographic visuals. | Values: 0-16, 17-25, 26-39, 40-64, 65+, Unknown. |
| `hour` | Numeric | Hour extracted from `time`. | Source for time-band analysis. | Missing if time cannot be parsed. |
| `time_band` | Text | Crash time grouped into policy-relevant time windows. | Day x time heatmap. | Late night, morning commute, daytime, evening commute, night. |
| `speed_band` | Text | Speed limit grouped into broader risk environments. | Risk segment matrix. | Local/urban, urban arterial, high speed, very high speed, Unknown. |
| `road_user_group` | Text | Road users grouped into vulnerable road users vs vehicle occupants. | High-level exposure comparison. | Vulnerable includes pedestrians, cyclists, motorcycle riders, and pillion passengers. |
| `remoteness_group` | Text | Simplified remoteness category. | Risk segment matrix and filter. | Remote and Very Remote combined. |
| `holiday_period` | Text | Combined Christmas/Easter flag. | Holiday-period filter or annotation. | Values: Christmas / Easter, Non-holiday. |
| `heavy_vehicle_involved` | Text | Combined flag for bus, heavy rigid truck, or articulated truck involvement. | Filter/tooltip for heavy-vehicle context. | Values: Yes, No, Unknown. |
| `analysis_window` | Text | Historical vs latest-period flag. | Dashboard toggle/filter. | Historical: 1989-2023; Recent: 2024-Jan 2026. |
| `full_recent_year` | Text | Flag for full recent years. | Fair annual comparison filter. | 2024-2025 full years vs Other. |

## `bitre_state_month.csv`

| Column | Type | Definition | Dashboard Use | Notes |
|---|---|---|---|---|
| `month_start` | Date | Month-start date for the state-month record. | Historical line chart axis. | Created from BITRE year and month. |
| `year` | Integer | Calendar year. | Filter, trend, population join if needed. | 1989 to 2026. |
| `month` | Integer | Month number, 1-12. | Monthly filtering and labels. | Use with year for chronology. |
| `year_month` | Text | Year-month label. | Tooltip or label. | Format: YYYY-MM. |
| `state` | Text | Australian state or territory code. | State filter and trend colour. | Values: ACT, NSW, NT, QLD, SA, TAS, VIC, WA. |
| `fatalities` | Integer | Number of fatality rows in that state-month. | Historical trend measure. | Aggregated by summing `deaths` from BITRE detail. |

## `population_state_year_clean.csv`

| Column | Type | Definition | Dashboard Use | Notes |
|---|---|---|---|---|
| `year` | Integer | Calendar year for the population denominator. | Join key with BITRE. | 1981 to 2025. |
| `quarter_date` | Date/Text | June-quarter date used as annual population reference. | Documentation and validation. | June quarter chosen as annual denominator. |
| `state` | Text | Australian state or territory code. | Join key with BITRE. | Excludes Australia total (`AUS`). |
| `state_name` | Text | Full state or territory name. | Label or tooltip. | Example: New South Wales. |
| `population` | Integer | Estimated resident population, persons. | Fatalities per 100,000 calculation. | Use as denominator; do not sum repeated population after row-level joins. |

## `weather_monthly_state_clean_2024_jan2026.csv`

| Column | Type | Definition | Dashboard Use | Notes |
|---|---|---|---|---|
| `state` | Text | Australian state or territory code. | Join key with BITRE. | Values: ACT, NSW, NT, QLD, SA, TAS, VIC, WA. |
| `city` | Text | Representative capital city used for weather extraction. | Data provenance/tooltip. | Weather is representative state-month context, not exact crash-site weather. |
| `year` | Integer | Calendar year of weather month. | Join key with BITRE. | Covers 2024, 2025, and Jan 2026. |
| `month` | Integer | Month number, 1-12. | Join key with BITRE. | Join by state + year + month. |
| `year_month` | Text | Year-month label. | Tooltip or label. | Format: YYYY-MM. |
| `avg_temp_mean` | Numeric | Average of daily mean temperature for the state-month. | Weather context tooltip/panel. | Units: degrees C. |
| `max_temp` | Numeric | Highest daily maximum temperature in the state-month. | Heat context. | Units: degrees C. |
| `min_temp` | Numeric | Lowest daily minimum temperature in the state-month. | Weather context. | Units: degrees C. |
| `total_precipitation_mm` | Numeric | Total monthly precipitation. | Rain context. | Units: millimetres. |
| `total_rain_mm` | Numeric | Total monthly rain. | Rain context. | Units: millimetres. |
| `max_wind_speed_kmh` | Numeric | Maximum daily wind speed recorded in the state-month. | Wind context. | Units: km/h. |
| `rainy_days` | Integer | Count of days in the month where rain was recorded. | Rain context tooltip. | Range: 0 to 31. |
| `rain_context` | Text | Categorised monthly rain level. | Filter/tooltip context. | Low, Moderate, High, Extreme rain. |
| `heat_context` | Text | Categorised monthly heat level based on maximum temperature. | Filter/tooltip context. | Below 30C, 30-35C, 35-40C, 40C+. |
| `wind_context` | Text | Categorised monthly wind level. | Filter/tooltip context. | Low, Moderate, High, Extreme wind. |

## Join Logic

| Join | Keys | Purpose | Caution |
|---|---|---|---|
| BITRE detail to population | `state` + `year` | Calculate fatalities per 100,000 people | Population is annual; use 2024-2025 for fair recent rate comparisons because 2026 population is unavailable. |
| BITRE detail to weather | `state` + `year` + `month` | Add latest-period weather context | Weather is monthly context, not exact crash-day causation. |
| BITRE detail to state-month trend | Not required | The state-month file is a pre-aggregated helper | Use either detail or aggregate, not both in the same calculation, to avoid double counting. |

## Recommended Calculated Measures

| Measure | Formula | Use |
|---|---|---|
| Fatalities | `SUM(deaths)` or `SUM(fatalities)` | Core count measure. |
| Fatalities per 100,000 | `SUM(deaths) / AVG(population) * 100000` | Fair state risk comparison after joining population. |
| Lives saveable | `Selected fatalities * reduction parameter` | What-if decision panel. |
| Latest fatalities | Filter `analysis_window = Recent: 2024-Jan 2026` | Latest policy window KPI. |
| Full recent comparison | Filter `full_recent_year = 2024-2025 full years` | Fair 2024 vs 2025 comparison. |

## Data Limitations

- BITRE does not include an exact crash date in the supplied fatality file, only year and month plus day-of-week/time. Therefore weather is joined at state-month level only.
- Historical remoteness, SA4, LGA, and road-type fields contain many Unknown values. These fields are strongest for the latest 2024-Jan 2026 window.
- Population data is available to 2025, so 2026 rows should not be used for annual population-normalised comparisons unless a clear assumption is added.
- Weather uses representative cities for state-level context and should not be interpreted as exact crash-location weather.
