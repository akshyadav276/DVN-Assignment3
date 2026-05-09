# Data Dictionary — Road Safety Data Narrative
DVN Assignment 3 | Data Visualisation Design & Storytelling

---

## 1. Road Dataset (clean_road_data.csv)
**Source:** BITRE Australian Road Deaths Database

| Column Name | Data Type | Description | Provenance |
|-------------|-----------|-------------|------------|
| date | Date | Month and year of recorded road fatalities (standardised to YYYY-MM-01 format) | Derived from BITRE dataset (Year + Month fields) |
| state | String | Australian state or territory code (NSW, VIC, QLD, SA, WA, TAS, NT, ACT) | Derived and standardised from BITRE dataset |
| deaths | Integer | Total number of fatalities per state per month. Each record represents one death and was aggregated | Derived from BITRE Australian Road Deaths Database |

**Notes:**
- Original dataset: BITRE Australian Road Deaths Database
- Each row = 1 fatality
- Aggregated using: group by date + state

---

## 2. Population Dataset (clean_population_data.csv)
**Source:** Australian Bureau of Statistics (ABS)

| Column Name | Data Type | Description | Provenance |
|-------------|-----------|-------------|------------|
| date | Date | Month and year of population estimate (YYYY-MM-01 format) | Derived from ABS dataset |
| state | String | Australian state or territory code | Extracted and mapped from ABS dataset (state names → codes) |
| population | Integer | Estimated Resident Population (Persons) for each state | Australian Bureau of Statistics (ABS) |

**Notes:**
- Source: ABS National State and Territory Population dataset
- Only Persons category retained
- Removed Australia total
- Transformed from wide → long format

---

## 3. Weather Dataset (clean_weather_data.csv)
**Source:** Regional weather dataset (2017–2026)

| Column Name | Data Type | Description | Provenance |
|-------------|-----------|-------------|------------|
| date | Date | Date of weather observation | Derived from weather dataset (time column cleaned and converted) |
| temperature | Float | Average daily temperature (°C), aggregated across all locations | Derived from temperature_2m_mean field |
| rain | Float | Average daily precipitation (mm), aggregated across all locations | Derived from precipitation_sum field |

**Notes:**
- Original data = city-level observations
- Aggregated using: group by date → mean
- Represents overall national weather conditions per day
- Weather data was aggregated at the date level to align with the analytical objective of examining temporal trends rather than region-specific variations

---

## 4. Calculated Fields (Tableau)

These fields do not exist in the source CSV they are computed inside Tableau during analysis.

| Field Name | Formula | Purpose |
|------------|---------|---------|
| Deaths_Per_100k | (deaths / population) × 100,000 | Fair state-by-state comparison |
| Projected_Lives_Saved | Total_Deaths × (Speed_Reduction% / 100) × 0.3 | What-If Parameter Action slider |
| Year_on_Year_Change | (Current_Deaths - Previous_Deaths) / Previous_Deaths | Trend analysis |
