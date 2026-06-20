# We Are How U Mean — Fantasy Football Analytics

Analysis tools and historical data for a private ESPN fantasy football league (ID: 722346), active since 2016.

## What's here

| Path | Description |
|------|-------------|
| `ff_app/` | **Main project** — Streamlit web app for interactive league analysis (see below) |
| `Updated_Fantasy_Football_Analysis.ipynb` | Original analysis notebook — standings, scoring metrics, alternate schedules, win-probability |
| `table_collector.py` | Helper class that displays DataFrames in-notebook and exports to PDF/PNG |
| `weekly_matchups.csv` / `weekly_scores.csv` | Raw weekly data used by the notebook |
| `2024/` | Season-specific data and notes for 2024 |

---

## Streamlit App (`ff_app/`)

A full interactive web app that pulls all data live from ESPN's API. No manual data entry.

### Running the app

```bash
cd ff_app
pip install -r requirements.txt
streamlit run app.py
```

App runs at http://localhost:8501.

### Pages

| Page | Description |
|------|-------------|
| Dashboard | Current week matchups, standings snapshot, weekly scoring trends |
| Standings | H2H, vs-median, combined, strength of schedule, luck index, alternate schedule |
| Scoring | Weekly trends, score distributions, best/worst scores, head-to-head matrix |
| Lineup Efficiency | Actual vs optimal scores, bench waste, top players, projections vs actual |
| Playoff Projections | Monte Carlo simulation, scoring distributions, magic numbers |
| Playoffs | Bracket display with per-week and cumulative round scores |
| Draft Review | Full draft board, team draft summaries, best value picks and busts |
| Data Validation | Verify our calculated scores match ESPN's published totals |

### Seasons covered

| Season | Data quality |
|--------|-------------|
| 2016–2017 | Player scores approximated from NFL play-by-play (nfl-data-py); team weekly totals exact from ESPN |
| 2018 | Full player-level data from ESPN API — 100% exact |
| 2019–2025 | Full player-level data from ESPN API — 100% exact |

### ESPN credentials

Seasons 2019–2023 are a private league and require ESPN cookies in `ff_app/.env`:

```
ESPN_S2=your_espn_s2_cookie
SWID={your-swid-here}
```

Grab these from your browser after logging into ESPN (F12 → Application → Cookies → espn.com).

### Season quirks

- **2022**: Regular season ran through week 14. Playoffs were 3 weeks — Round 1 (wk 15, 1 week), Finals (wks 16–17), Sacko Bowl (wks 15–17 cumulative). Playoff validation is skipped since the bracket was run manually outside ESPN.
- **2020 and earlier**: Playoffs are weeks 13–16 instead of 14–17.

---

## Legacy notebook

The original `Updated_Fantasy_Football_Analysis.ipynb` still works as a standalone analysis tool. It requires manual CSV exports from ESPN and covers seasons available at the time it was built.

```bash
pip install pandas matplotlib pillow
jupyter notebook
```
