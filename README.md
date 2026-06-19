# fantasy-league-stats

Analysis tools and historical data for a private ESPN fantasy football league.

## What's here

| Path | Description |
|------|-------------|
| `Updated_Fantasy_Football_Analysis.ipynb` | Main analysis notebook — standings, scoring metrics, alternate schedules, win-probability |
| `table_collector.py` | Helper class that displays DataFrames in-notebook and exports them to a multi-page PDF or stitched PNG |
| `weekly_matchups.csv` / `weekly_scores.csv` | Raw weekly data used by the notebook |
| `2024/` | Season-specific data and notes for 2024 |

## Requirements

```
pip install pandas matplotlib pillow
```

Run the notebook with `jupyter notebook` or open it in VS Code / JupyterLab.

## Data

Weekly matchup and score CSVs are exported from ESPN and loaded directly by the notebook. The `2024 season data.xlsx` and `2025 season data.xlsx` files contain the raw ESPN exports for those seasons.
