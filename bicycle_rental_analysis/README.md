# Bicycle Rental Demand Analysis

How does bicycle rental demand vary with weather and season? This project explores daily rental records with Python, compares demand across groups, and checks how sample sizes and unusual observations affect the conclusions.

The focus is on interpreting the results carefully: an average can highlight a pattern, but it can also hide variation between days.

## Research question

How do weather conditions and seasons relate to bicycle rental demand, and how might unusual observations affect the conclusions?

## Project files

| File | Description |
| --- | --- |
| [bicycle_rental_analysis.ipynb](bicycle_rental_analysis.ipynb) | Analysis, saved outputs, explanations and limitations |
| README.md | Project overview and instructions |

## Data

The notebook loads a CSV from [Bikes/bike.csv in my Projects repository](https://github.com/tinashemungoshi/Projects/blob/main/Bikes/bike.csv). Each row represents a recorded day, with rental counts, seasonal and weather categories, calendar information and weather measurements.

The code renames `yr`, `mnth` and `cnt` to `year`, `month` and `count`. The saved missing-value check reports no missing values. The CSV itself is not included with these two files; running the notebook requires internet access to its existing URL.

This repository link identifies the CSV used by the code. The original collection source, measurement units and category definitions have not been independently verified in this presentation update. The URL follows the `main` branch, so its contents may change over time.

## Analysis workflow

1. **Load and inspect:** preview the data, rename columns and check for missing values.
2. **Explore high demand:** filter working days with good weather and identify days with more than 6,000 rentals.
3. **Compare groups:** calculate seasonal statistics and average demand by weather category, then visualise season-and-weather comparisons.
4. **Assess reliability:** examine group sizes and explain what aggregation hides.
5. **Check sensitivity:** apply global IQR boundaries, compare trimming and capping, and inspect seasonal rankings.

## Key findings

- Days with more than 6,000 rentals account for **24.62%** of recorded days.
- Summer has the highest seasonal mean (**5,644.30** rentals); winter has the lowest (**2,604.13**). Both seasonal summary tables now agree.
- The weather summary reports higher average demand in good weather than in misty or rain/snow/storm conditions.
- Weather groups are uneven: there are **463 good-weather days**, **247 misty days** and **21 rain/snow/storm days**. Some season-and-weather combinations contain only three or four observations.
- The global IQR check flags **zero observations**. Trimming and capping therefore leave the rental counts unchanged in the retained results.

These are descriptive associations, not evidence that weather alone causes changes in demand.

## Tools and skills

**Tools:** Python, pandas, NumPy, Matplotlib, Seaborn and Jupyter Notebook.

**Skills demonstrated:** Boolean filtering, column selection, grouped aggregation, descriptive statistics, visualisation, IQR-based outlier screening, sensitivity analysis and critical interpretation of observational data.

## How to run

Use Python 3 in an environment with Jupyter and the analysis libraries installed:

```bash
python -m pip install pandas numpy matplotlib seaborn notebook
python -m notebook bicycle_rental_analysis.ipynb
```

In Jupyter, select the Python kernel, restart it and run all cells from top to bottom. Internet access is needed for the CSV download. The original upload recorded Python **3.13.18**; the refreshed analysis was executed with Python **3.12.14**. Package versions are not pinned. The analysis cells ran successfully, but the installation commands above were not tested in a new environment.

You can also open the notebook on GitHub to read its saved outputs without running Python.

## Limitations and future work

The current analysis pools years and working-day categories together. It does not verify dates, duplicate records or seasonal coding against source documentation, and the global IQR rule may miss anomalies within individual seasons.

Useful next steps are to pin a fixed dataset version, verify the dataset definitions, compare demand within each year and working-day category, inspect rental distributions with plots and quantiles, and consider season-specific anomaly checks. These are proposed extensions rather than completed work.
