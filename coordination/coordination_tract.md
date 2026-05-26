# Coordination Track — DVN Assignment 3
### Road Deaths Are Not Random
**Coordinator:** Akshita Yadav | **Last updated:** 21 May 2026

---

## Project at a Glance

| Item | Detail |
|---|---|
| Assignment | DVN Assignment 3 — Data Narrative Studio |
| Unit | 36104 Data Visualisation and Narratives — University of Technology Sydney |
| Team | Group 18 — Sonika · Remith · Karthik · Asif · Shameel · Pal · Akshita |
| Audience | Federal Transport Minister reviewing national road safety funding priorities |
| Core argument | 70.8% of recent Australian road fatalities concentrate in two targetable intervention theatres |
| Dashboard tool | Tableau Public |

---

## Deadlines

| Part | Deliverable | Due | Status |
|---|---|---|---|
| Part 1 | Individual proposals submitted | Sun 19 Apr 2026 | ✅ Complete |
| Part 2 | Live pitch + slides | Wed 13 May 2026 | ✅ Submitted |
| Part 3 | Final portfolio | Tue 26 May 2026 | ✅ in progress |

---

## Responsibility Map

| Role | Owner | Evidence Location |
|---|---|---|
| Architect | Sonika Nanjundaiah | Root `README.md`, GitHub commit history, project structure |
| Data Preprocessor | Remith Sajin | `Data Preperation/01_Data_cleaning/`, `data_dictionary.csv` |
| Data Analyst | Karthik Ramesh | `Data Preperation/03_eda/` |
| Integration Analyst | Muhammad Asif | `Data Preperation/02_integration/` |
| Dashboard Developer | Shameel Zeshan | `tableau/`, Tableau Public deployment |
| Orator | Pal Patel | `presentation/`, pitch slides, speaker script |
| Coordinator | Akshita Yadav | `coordination/` — this document |

---

## Sprint Plan

### Sprint 1 — Data Foundation *(target: complete by 6 May)*

| Task | Owner | Output | Status |
|---|---|---|---|
| Raw BITRE data audit | Remith | `Data Preperation/01_Data_cleaning/` notes | ✅ Done |
| BITRE cleaning and standardisation | Remith | `bitre_clean_detail.csv` | ✅ Done |
| Population data cleaning | Remith | `population_state_year_clean.csv` | ✅ Done |
| Weather data cleaning | Remith | `weather_monthly_state_clean_2024_jan2026.csv` | ✅ Done |
| Data dictionary | Remith | `docs/data_dictionary.csv`, `docs/data_dictionary.md` | ✅ Done |
| EDA notebook | Karthik | `Data Preperation/03_eda/` | ✅ Done |
| Dataset integration | Asif | `Data Preperation/02_integration/` | ✅ Done |
| GitHub repo structure | Sonika | Root `README.md`, folder structure | ✅ Done |

### Sprint 2 — Dashboard Build and Pitch Preparation *(target: complete by 13 May)*

| Task | Owner | Output | Status |
|---|---|---|---|
| Tableau dashboard build | Shameel | `tableau/` | ✅ Done |
| Advanced Tableau features (what-if, filtering, tooltips) | Shameel | Tableau Public deployment | ✅ Done |
| Deploy to Tableau Public | Shameel | Public dashboard URL | ✅ Done |
| User persona and stories | Pal | `docs/user_persona_and_stories.md` | ✅ Done |
| Pitch narrative arc | Pal | `presentation/pitch_outline.md` | ✅ Done |
| Pitch slides | Pal | `presentation/slides/` | ✅ Done |
| Speaker script | Akshita, Shameel | `presentation/speaker_script_pal.md` | ✅ Done |
| Group rehearsal | Akshita, Shameel | — | ✅ Done |
| Slides submitted by midday | Akshita | Submission portal | ✅ Done |
| Live pitch delivered | Akshita, Shameel | — | ✅ Done |

### Sprint 3 — Final Portfolio *(target: complete by 26 May)*

| Task | Owner | Output | Status |
|---|---|---|---|
| Dashboard story doc | Sonika | `docs/dashboard_story.md` | ✅ Done |
| Methodology doc | Sonika | `docs/methodology.md` | ✅ Done |
| Limitations doc | Sonika | `docs/limitations.md` | ✅ Done |
| Visual design principles | Sonika | `docs/visual_design_principles.md` | ✅ Done |
| Credits doc | Team | `docs/credits.md` | ✅ Done |
| Coordination track (this file) | Akshita | `coordination/coordination_tract.md` | ✅ Done |
| Meeting notes | Akshita | `coordination/meeting_notes.md` | ✅ Done |
| Final portfolio submission | All | Submission portal | ✅ Done |

---

## Dashboard QA Checklist

*Owner: Shameel Zeshan + Sonika Nanjundaiah | Completed before pitch on 13 May*

| Check | Detail | Status |
|---|---|---|
| Dashboard deployed to Tableau Public | URL accessible without login | ✅ |
| All four datasets connected correctly | BITRE detail, state-month, population, weather | ✅ |
| Intervention theatre selector updates scenario estimate | Selected theatres update potential lives saved | ✅ |
| Target reduction parameter updates scenario estimate | Changing target % updates potential lives saved | ✅ |
| Population-adjusted rates correct | Fatalities per 100,000 calculation verified | ✅ |
| What-if parameter functional | Theatre + reduction % → lives saved updates live | ✅ |
| Tooltips present on key charts | State risk, timing heatmap, human layer | ✅ |
| 2026 excluded from annual trend | January-only data not shown as full year | ✅ |
| Colour accessibility checked | No red/green-only encoding; colourblind safe | ✅ |
| Mobile/browser rendering tested | Renders correctly in Chrome and Safari | ✅ |

---

## Pitch Checklist

*Owner: Akshita Yadav | Completed by 13 May*

| Item | Status |
|---|---|
| Slides finalised and reviewed by group | ✅ |
| Speaker script finalised (Pal) | ✅ |
| Tableau dashboard URL confirmed working | ✅ |
| Group rehearsal completed (timed) | ✅ |
| Slides submitted to portal by midday 13 May | ✅ |
| Backup PDF of slides prepared | ✅ |
| All members briefed on Q&A responses | ✅ |

---

## Portfolio Submission Checklist

*Owner: Akshita Yadav | Completed by 26 May*

### Repository Files

| File / Folder | Owner | Status |
|---|---|---|
| `README.md` (root) | Sonika | ✅ |
| `Data Preperation/01_Data_cleaning/` — cleaning notebook | Remith | ✅ |
| `Data Preperation/02_integration/` — integration notebook | Asif | ✅ |
| `Data Preperation/03_eda/` — EDA notebook | Karthik | ✅ |
| `docs/data_dictionary.csv` | Remith | ✅ |
| `docs/data_dictionary.md` | Remith | ✅ |
| `docs/credits.md` | Team | ✅ |
| `docs/methodology.md` | Sonika | ✅ |
| `docs/limitations.md` | Sonika | ✅ |
| `docs/dashboard_story.md` | Sonika / Akshita | ✅ |
| `docs/user_persona_and_stories.md` | Pal | ✅ |
| `docs/visual_design_principles.md` | Sonika | ✅ |
| `presentation/pitch_outline.md` | Pal | ✅ |
| `presentation/speaker_script_pal.md` | Pal | ✅ |
| `tableau/` — assets and screenshots | Shameel | ✅ |
| `coordination/coordination_tract.md` (this file) | Akshita | ✅ |
| `coordination/meeting_notes.md` | Akshita | ✅ |
| `coordination/sprint_plan.md` | Akshita | ✅ |

### Contribution Evidence

| Team Member | Role | Evidence Location |
|---|---|---|
| Sonika Nanjundaiah | Architect | Root README, GitHub commit history, `docs/` structure |
| Remith Sajin | Data Preprocessor | `Data Preperation/01_Data_cleaning/`, `docs/data_dictionary.csv` |
| Karthik Ramesh | Data Analyst | `Data Preperation/03_eda/` |
| Muhammad Asif | Integration Analyst | `Data Preperation/02_integration/` |
| Shameel Zeshan | Dashboard Developer | `tableau/`, Tableau Public URL |
| Pal Patel | Orator | `presentation/` — outline, slides, speaker script |
| Akshita Yadav | Coordinator | `coordination/` — this document, meeting notes, sprint plan |

---

## Meeting Log

### Group Chat Created — Tuesday 1:29 am (approx. late April)
- Shameel added all members to the DVN AT3 Teams group: Muhammad A., Pal P., Sonika N., Akshita Y., Karthik R., Remith S.
- All project communication to be kept in the Teams channel.

### Data Cleaning Update — Tuesday 10:45 pm
- **Remith** shared updated cleaned datasets and Python notebook.
- Files shared: `bitre_clean_detail.csv`, DVN Data Preparation notebook, `population_state_year_clean.csv`, `weather_monthly_state_clean.csv`
- Noted aggregation logic for `bitre_state_month` is SUM.
- Shared file-to-dashboard use mapping.

### Data Dictionary and Repo Updates — Friday 11:00 pm
- **Remith** shared `data_dictionary.csv` to the group.
- **Sonika** updated the root README on GitHub and notified the group.
- **Karthik** pushed the EDA notebook to GitHub.

### Integration PR — Saturday 3:14 am
- **Asif** pushed integration code to a new PR. Shared `integration_analyst_data` file (66 KB). Asked group to review and flag changes.

### Repo Structure and Notebook Mix-up
- **Shameel** pushed updated repo structure and documentation to main but accidentally included an older data cleaning notebook.
- **Remith** confirmed no issue and pushed the correct Data Cleaning notebook and data dictionary to GitHub.
- **Karthik** confirmed EDA notebook pushed (screenshot shared as evidence).

### Coordination Check-in — 11 May 2026
**Present:** Akshita (Coordinator) — async review via GitHub and Teams

- Reviewed GitHub and Teams activity against sprint plan.
- Chased Shameel on Tableau advanced features status — confirmed in progress.
- Chased Pal on pitch slides — confirmed in progress.
- Rehearsal scheduled for 11 May before midday submission deadline.

**Action items agreed:**
- Pal: slides to be finalised and sent to group by morning of 11 May ✅
- Shameel: confirm dashboard deployed to Tableau Public before 13 May ✅
- Akshita: submit slides  ✅

---

## Risk Register

| Risk | Likelihood | Impact | Mitigation | Status |
|---|---|---|---|---|
| Tableau dashboard not deployed before pitch | Medium | High | Akshita chasing Shameel from 9 May; backup: run from local Tableau Desktop | ✅ Resolved |
| Pitch slides not finalised in time | Medium | High | Akshita chasing Pal; deadline set as morning of 11 May | ✅ Resolved |
| Double-counting population in joins | Low | High | Data dictionary explicitly warns: do not sum population after row-level joins | ✅ Mitigated |
| 2026 partial year misleading trend | Medium | Medium | 2026 excluded from annual trend chart; flagged in limitations | ✅ Mitigated |
| Notebook conflict in repo (wrong version) | Low | Medium | Occurred and resolved: Remith pushed correct version after Shameel's accidental upload | ✅ Resolved |

---

## Key File Locations

| File | Path | Owner |
|---|---|---|
| Root README | `README.md` | Sonika |
| BITRE cleaned detail | `data/cleaned/bitre_clean_detail.csv` | Remith |
| Data dictionary (CSV) | `docs/data_dictionary.csv` | Remith |
| Data dictionary (MD) | `docs/data_dictionary.md` | Remith |
| EDA notebook | `Data Preperation/03_eda/` | Karthik |
| Integration notebook | `Data Preperation/02_integration/` | Asif |
| Dashboard assets | `tableau/assets/` | Shameel |
| Pitch outline | `presentation/pitch_outline.md` | Pal |
| Speaker script | `presentation/speaker_script_pal.md` | Pal |
| Coordination track | `coordination/coordination_tract.md` | Akshita |
| Meeting notes | `coordination/meeting_notes.md` | Akshita |
| Sprint plan | `coordination/sprint_plan.md` | Akshita |
| Dashboard story | `docs/dashboard_story.md` | Sonika / Akshita |
| Limitations | `docs/limitations.md` | Sonika |
| Methodology | `docs/methodology.md` | Sonika |

---

*DVN Assignment 3 — Group 18 | 36104 Data Visualisation and Narratives | University of Technology Sydney | May 2026*
*Coordinator: Akshita Yadav*
