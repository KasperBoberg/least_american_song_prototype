# Least American Songs

A portfolio data analysis project prototyping “Least American Songs” concept.

The goal is simple: compare how songs performed in the **Billboard Hot 100** versus the **Official UK Singles Chart**, then score each song by how much more “American” it was than “British”:

\[
\text{chart\_score} = \sum (101 - \text{rank})
\]

\[
\text{Americanness Score} = \text{US Score} - \text{UK Score}
\]

Songs with only one-sided chart presence are discarded. A song must have **non-zero scores in both charts** to remain in the final analysis.

## Why this version

The original video compares the US against many countries. This repo scopes the idea down to a **US vs UK** comparison, which is easier to reproduce cleanly while still producing a meaningful cultural contrast.

## What’s in the notebook

`analysis.ipynb` contains:

- data loading and inspection
- UK date parsing with the requested `Week`-range extraction
- explicit datetime coercion and validation
- shared-date filtering so only overlapping calendar rows survive
- song-level chart scoring
- master table creation and Americanness scoring
- overall EDA
- decade-by-decade rankings
- visualisations
- an all-time Hall of Fame

## Key findings

On the shared sample used in this notebook:

- **2,794 songs** survive the two-sided merge
- the shared aligned window runs from **1969-08-02 to 2021-11-06**
- the strongest UK-leaning end is led by songs such as **“AMAZING GRACE” — JUDY COLLINS**
- the strongest US-leaning end is led by songs such as **“TENDER LOVER” — BABYFACE**

A few recurring patterns stand out:

- the **least-American** side is crowded with UK/European pop, dance, and soft-rock acts
- the **most-American** side leans heavily toward US pop, R&B, adult contemporary, and country-adjacent hits
- the score behaves like a geography filter as much as a popularity filter

## Tech stack

- Python
- pandas
- numpy
- matplotlib
- seaborn
- openpyxl
- Jupyter Notebook

## Repository contents

- `analysis.ipynb`
- `charts.csv`
- `top_100_songs_1952_to_2024.xlsx`

## How to run locally

1. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn openpyxl jupyter
   ```

2. Put the data files in the project root:
   - `charts.csv`
   - `top_100_songs_1952_to_2024.xlsx`

3. Open the notebook:
   ```bash
   jupyter notebook analysis.ipynb
   ```

## Data sources

- Billboard Hot 100: https://www.billboard.com/charts/hot-100/
- Official UK Singles Chart: https://www.officialcharts.com/charts/singles-chart/

The datasets used in this repo are local exports of those chart archives.
