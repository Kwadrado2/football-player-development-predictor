# Data instructions

This repository does not redistribute the underlying football datasets. Before making the repository public, check the applicable terms of use for FBref, Understat and Transfermarkt, together with any university requirements. Do not commit full raw or processed datasets unless redistribution is permitted.

## Expected source files and locations

| Source file | Location | Notebook |
|---|---|---|
| `Top5_League_Players_2017to2024_dataset.csv` | `data/raw/fbref/` | 01 |
| `players_data-2025_2026.csv` | `data/raw/fbref/` | 01 |
| `Bundesliga X(g).xlsx` | `data/raw/understat/` | 02 |
| `EPL X(g).xlsx` | `data/raw/understat/` | 02 |
| `La liga X(g).xlsx` | `data/raw/understat/` | 02 |
| `Ligue 1 X(g).xlsx` | `data/raw/understat/` | 02 |
| `Serie A X(g).xlsx` | `data/raw/understat/` | 02 |
| `players.csv` | `data/raw/transfermarkt/` | 04 |
| `player_valuations.csv` | `data/raw/transfermarkt/` | 04 and 05 |

## Generated files

| Generated file | Location | Created by |
|---|---|---|
| `Top5_League_Players_2017to2026_combined.csv` | `data/processed/` | Notebook 01 |
| `Top5_League_Players_observation_scope.csv` | `data/processed/` | Notebook 01 |
| `Understat_dataset.xlsx` | `data/processed/` | Notebook 02 |
| `combined_fbref_understat_final.csv` | `data/processed/` | Notebook 03 |
| `combined_with_valuations.csv` | `data/processed/` | Notebook 04 |
| `final_labeled_dataset.csv` | `data/processed/` | Notebook 05 |

Run notebooks 01–05 in order, then run Notebook 07 for modelling. Launch Jupyter from the repository root. Notebooks use project-relative paths.

## Important scope and processing notes

- Notebook 01 combines the historical and 2025–26 FBref exports, then creates the observation-scope file for the Big Five leagues, seasons 2019–20 to 2023–24 and ages 18–24. The 2025–26 export is not part of the observation sample.
- Notebook 02 combines the five Understat workbooks. The supplied workbooks cover 2019–20 to 2025–26; downstream matching retains the seasons relevant to the dissertation.
- Notebook 03 applies the 900-minute threshold, retains the highest-minute club record for multi-club player-seasons, then uses exact and fuzzy name matching within season. Fuzzy matches are reviewed according to the thresholds documented in the notebook.
- Notebook 04 uses Transfermarkt player records and valuation history to attach player IDs and observation/future market values.
- Notebook 05 creates the three component signals and applies the 2-of-3 future-elite label rule.

The public portfolio ZIP intentionally contains no raw or processed provider datasets. Obtain source data independently and only where permitted. The notebooks' recorded outputs and the aggregate result tables provide a summary of the executed workflow.
