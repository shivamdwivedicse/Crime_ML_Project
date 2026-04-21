# Crime_ML_Project

A machine learning project for analyzing Indian crime data and building a regression model to predict crime-related values from state/UT-level features.

## Overview

This repository contains a Jupyter notebook that explores a crime dataset, performs basic cleaning and feature engineering, visualizes trends, and trains machine learning models to predict crime statistics.

The workflow in the notebook includes:

- loading the dataset from `crime.csv`
- cleaning column names and removing aggregate rows.
- exploratory data analysis with plots and correlation heatmaps.
- feature engineering from year-wise crime counts.
- training and evaluating regression models.
- comparing model performance with train/test split and cross-validation.
- checking the effect of outliers on prediction quality.

## Dataset

The project uses a CSV file named `crime.csv`.

The notebook works with state/UT-level crime data and includes columns such as:

- `State/UT`
- `2020`
- `2021`
- `2022`
- `Mid-Year Projected Population (in Lakhs) (2022)`
- `Rate of Cognizable Crimes (IPC) (2022)`
- `Chargesheeting Rate (2022)`

During preprocessing, the notebook also removes aggregate rows such as:

- `Total State (S)`
- `Total UT(S)`
- `Total ALL India`

## Project Workflow

### 1. Data Loading and Inspection
The notebook begins with:
- importing `pandas`, `numpy`, `matplotlib`, and `seaborn`
- reading `crime.csv`
- checking shape, null values, duplicated rows, and data types

### 2. Data Cleaning
The following cleaning steps are performed:

- dropping the `Sl. No.` column.
- stripping extra spaces from column names.
- renaming columns to simpler names.
- removing total/aggregate rows.
- renaming the population, crime rate, and chargesheeting rate columns for readability.

### 3. Exploratory Data Analysis
The notebook visualizes:
- the top 10 states with the highest crime rate.
- the total crime trend from 2020 to 2022.
- the correlation heatmap across numerical features.

### 4. Feature Engineering
New features are created to capture changes across years:

- `Crime_change_20_21`
- `Crime_change_21_22`
- `Crime_change_pct`
- `Crime_per_lakh_2022`
- `Crime_Average`

### 5. Model Building
The notebook experiments with regression models, including:

- **Linear Regression**
- **Random Forest Regressor**

The target variable is first explored as `Crime_rate_2022`, and later the notebook focuses on predicting `Crime_2022` using features like:

- `Crime_2020`
- `Crime_2021`
- `Population_2022`
- `Crime_change_20_21`

### 6. Evaluation
The project uses:
- `r2_score`
- `mean_absolute_error`
- `cross_val_score`

It also compares performance before and after handling outliers.

## Key Findings

- The dataset is relatively small, so model performance is limited.
- Outliers such as Delhi and Kerala can strongly affect regression results.
- Random Forest is tested as the main model because it can capture non-linear patterns better than simple linear regression.
- Cross-validation is used to get a more reliable estimate of performance on a small dataset.

## Repository Structure

```text
Crime_ML_Project/
├── Crime_ project.ipynb
└── crime.csv
```

## Requirements

Install the required Python libraries before running the notebook:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/shivamdwivedicse/Crime_ML_Project.git
   cd Crime_ML_Project
   ```

2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```

3. Open the notebook:
   ```bash
   jupyter notebook
   ```

4. Run `Crime_ project.ipynb` cell by cell.

## Results

The notebook explores whether past-year crime values and population-related features can help predict crime counts in 2022. Because the dataset is small and contains outliers, results may vary depending on:
- feature selection.
- train/test split.
- model type.
- outlier handling.

## Author

**Shivam Dwivedi**
