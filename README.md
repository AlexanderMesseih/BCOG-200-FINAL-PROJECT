# BCOG-200-FINAL-PROJECT
# F1 Team Performance Analyzer

## Project Description

The purpose of this project is to analyze and aggregate F1 team's constructor/car performance over the last 10 years. The idea is to go a bit deeper than championship standings, and looking at things like how teams perform under different weather conditions, whether their results actually match their budget, and where certain constructors consistently fall apart. It's also to compare teams progression in rankings over the past 10 years and see what factors most intensely affected their results to determine which factors most heavily impact rankings. Mostly an excuse to pull together a decade of race data and see what patterns show up.

---

## Function Descriptions

### 1. `fetch_team_season_stats(team_name, year_range)`
Pulls race-by-race data for a given constructor across a range of seasons and returns summary stats like average finish position, points per race, and DNF rate.

### 2. `compare_performance_vs_budget(teams, season)`
Takes team results alongside estimated constructor budgets and calculates a rough efficiency score. In other words, who's getting the most out of what they're spending.

### 3. `detect_condition_tendencies(team_name)`
Looks at a team's historical results broken down by race conditions (wet, dry, mixed) and circuit type to spot any consistent patterns that don't show up in the overall standings.


## Planned functions

### `fetch_team_season_stats(team_name, year_range)`
Pulls race-by-race data for a given constructor across a range of seasons. Returns summary stats including average finish position, points per race, and DNF rate.

### `compare_performance_vs_budget(teams, season)`
Takes team results alongside estimated constructor budgets and calculates a rough efficiency score — who's getting the most out of what they're spending.

### `detect_condition_tendencies(team_name)`
Looks at a team's historical results broken down by race conditions (wet, dry, mixed) and circuit type to identify patterns that don't show up in overall standings.

---

## Step 2 progress — data collection

### Data sources identified

- **Ergast F1 API** — race results, lap times, DNF reasons (2015–2024)
- **Constructor budget estimates** — Forbes, Motorsport.com annual reports
- **Weather/condition data** — still sourcing, likely OpenF1 *(pending)*

### Planned data schema

```python
race_result = {
    "team_name": str,
    "season": int,
    "race_id": str,
    "finish_position": int,
    "points": float,
    "dnf": bool,
    "condition": "wet" | "dry" | "mixed",  # TBD — depends on data source
    "circuit_type": str
}
```

### Next step
Write `fetch_team_season_stats()` around this schema and test against 2023 season data.

---

## Notes
- Budget figures are estimates from public sources and press reporting — not official
- Condition classification method TBD (manual tagging vs. weather API)
