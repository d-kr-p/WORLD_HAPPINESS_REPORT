# World Happiness Report Exploration (2015–2019)

Exploratory data analysis of the [World Happiness Report](https://www.kaggle.com/datasets/unsdsn/world-happiness) dataset, examining global happiness scores and their relationship with GDP, social support, health, and freedom across years and countries.

## Objective

Explore global happiness scores and their relationship with GDP, social support, health, and freedom. Identify trends across years and regions using data analysis and visualization.

## Dataset

- **Name:** World Happiness Report (2015–2019)
- **Source:** [Kaggle - unsdsn/world-happiness](https://www.kaggle.com/datasets/unsdsn/world-happiness)
- **Files used:** `2015.csv`, `2016.csv`, `2017.csv`, `2018.csv`, `2019.csv`

> Note: The CSV files are not included in this repo (see `.gitignore`). Download them from the Kaggle link above and place them in the project root before running the script.

## Project Structure

```
.
├── world_happiness_report_analysis.py   # Main analysis script
├── requirements.txt                     # Python dependencies
├── README.md
├── LICENSE
└── .gitignore
```

## Tasks Completed

1. Loaded multi-year CSV files with pandas.
2. Standardized column names across files and concatenated them into one DataFrame.
3. Used NumPy to calculate yearly mean happiness scores and identify the top 10 happiest countries.
4. Handled missing values by coalescing differently-named columns across years (e.g. `happiness_score` / `happiness.score` / `score`) and filling remaining gaps (e.g. corruption score) with the median.
5. Created a correlation heatmap (via `imshow`) between happiness score and contributing factors.
6. Plotted happiness score trends (2015–2019) for 5 selected countries on a single line chart.
7. Created a horizontal bar chart of the top 15 happiest countries in the most recent year.
8. Built a scatter plot of GDP per capita vs. happiness score.
9. Exported the merged and cleaned dataset to `cleaned_processed_data.csv`.

## Missing Value Strategy

Different years of the raw dataset use inconsistent column names for the same metric (e.g. `happiness_score`, `happiness.score`, `score`). These were merged into single "final" columns using `fillna` chains, so each metric has one consistent column across all years. The `corruption_final` column had a few remaining nulls, which were filled with the column median.

## Outputs

Running the script generates:
- `correlation_heatmap.png`
- `line-chart.png`
- `bar-chart.png`
- `scatter-plot.png`
- `cleaned_processed_data.csv`

## Requirements

- Python 3.x
- pandas
- numpy
- matplotlib

Install with:

```bash
pip install -r requirements.txt
```

## Usage

This script was originally written for Google Colab (it uses `google.colab.files.upload()` to upload the CSVs interactively). To run it locally instead, replace that upload step with local file paths pointing to the downloaded CSVs, then run:

```bash
python world_happiness_report_analysis.py
```

## License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.
