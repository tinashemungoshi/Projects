# Titanic: Exploring Passenger Survival

Were younger passengers more likely to survive the Titanic disaster than older passengers?

In this project, I use Python to explore that question through summary statistics and visualisations. I also compare survival across passenger class and sex to give the age findings some context.

[View the notebook](titanic_project.ipynb)

## About the data

The dataset contains **891 passenger records and 12 original columns**, including age, sex, ticket class, fare and survival status. `Survived` is coded as `0` for passengers who did not survive and `1` for those who did.

The notebook loads the CSV from a [pinned commit in my Uni repository](https://raw.githubusercontent.com/tinashemungoshi/Uni/872ed86305b06ea0c73ec13a29af2bcfaecd7725/titanic.csv). These records are a subset of the people aboard, so the findings describe this dataset rather than everyone on the ship.

## What I explored

- The structure of the dataset and its missing values.
- The distribution of passenger ages, fares, sexes and classes.
- Differences in fares and survival across class and sex.
- Mean and median ages for survivors and non-survivors.
- Survival rates across five age groups.

The analysis uses pandas for inspection, filtering and grouping, with Matplotlib and Seaborn for charts. NumPy is used to define the age-group boundaries.

## Key findings

Survivors were younger on average, with a mean age of **28.34 years**, compared with **30.63 years** for non-survivors. However, the median age was **28 years in both groups**, and their age distributions overlapped substantially.

| Age group | Age interval used in the code | Passengers with recorded ages | Survival rate |
| --- | --- | ---: | ---: |
| Children | 0–12, inclusive | 69 | 57.97% |
| Teenagers | Over 12 to 17 | 44 | 47.73% |
| Young adults | Over 17 to 35 | 384 | 38.02% |
| Middle-aged adults | Over 35 to 59 | 191 | 39.79% |
| Older adults | Over 59 | 26 | 26.92% |

The upper boundary of each interval is included. Passengers with missing ages are excluded from these age-group calculations.

Children had the highest survival rate and older adults had the lowest. The pattern was not a steady decline: middle-aged adults had a slightly higher survival rate than young adults.

Passenger class also showed a substantial difference. **62.96%** of first-class passengers survived, compared with **24.24%** of third-class passengers. Age alone therefore gives an incomplete picture of survival.

## Project files

| File | Purpose |
| --- | --- |
| [titanic_project.ipynb](titanic_project.ipynb) | Full analysis, charts and discussion |
| `README.md` | Project overview and setup instructions |

A local copy of the CSV can also be kept in this folder for reference. The notebook currently reads the online version directly.

## How to run

1. Download or clone the repository and open this project folder.
2. Use a Python environment with Jupyter Notebook, JupyterLab or VS Code's notebook support.
3. Install the required packages:

   ```bash
   python -m pip install notebook pandas numpy matplotlib "seaborn>=0.12"
   ```

4. Launch Jupyter:

   ```bash
   python -m notebook
   ```

5. Open `titanic_project.ipynb`, select your Python kernel and run the cells from top to bottom.

An internet connection is required to load the CSV. The notebook contains IPython plotting commands, so it should be run as a notebook. Seaborn 0.12 or later is needed for the plotting code's `errorbar` argument.

## Limitations

- **Missing ages:** 177 passengers, or 19.87%, have no recorded age. If those passengers differ from the rest, the age findings could be biased.
- **Small groups:** Only 26 passengers fall into the oldest age group, making its rate sensitive to individual outcomes.
- **Chosen age boundaries:** Different cut-offs could change the group rates and their ordering.
- **Other factors:** The age comparisons do not adjust for class or sex. The findings show associations and do not establish causation.

## What I would explore next

I would compare age-specific survival within each sex and passenger class, then use logistic regression to examine whether age remains associated with survival after accounting for those factors. I would also test different age bands and ways of handling missing ages.

These are possible extensions; the current project is an exploratory analysis and does not fit a predictive model.

## Author

**Tinashe Sean Mungoshi**
