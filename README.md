
# Least American Songs — US vs UK Chart Analysis

**Project**: Portfolio adaptation of the "Least American Songs" prototype concept to a US vs UK chart comparison.


## Summary
This project computes an "Americanness Score" for songs using weekly chart data from the US (Billboard Hot 100) and the UK (Official UK Singles Chart). The score is:

```
chart_score = sum(101 - rank)  # summed across chart weeks
americanness = US_chart_score - UK_chart_score
```

Songs with US chart score > 1000 are excluded to focus on songs that were not genuinely popular in the US.

## Files
- `analysis.ipynb` — executed Jupyter notebook with the full analysis, figures and outputs.
- `figures/` — generated plots referenced in the notebook.

## Key findings (automatically generated)
See the notebook `analysis.ipynb` for the full results: top/bottom songs overall, decade-by-decade analysis, and visualisations.

## How to run locally
1. Clone the repository
2. Place the two data files in the same folder or update the paths in the notebook:
   - `charts.csv` (Billboard Hot 100 weekly data)
   - `top_100_songs_1952_to_2024.xlsx` (UK weekly data)
3. Open `analysis.ipynb` in JupyterLab / VS Code and run the notebook. The notebook was executed in the included copy; re-running will reproduce the figures.

## Tech stack
- Python (pandas, numpy, matplotlib)
- Jupyter Notebook

## Notes & Next steps
- This repo uses US vs UK only. To replicate the actual method used, one must collect weekly charts from additional countries and compute the World score as the mean across countries.
- Improve entity standardisation (artists with collaborators, remixes) using fuzzy matching or MusicBrainz IDs.
