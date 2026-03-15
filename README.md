# Longitudinal Autism Study: Multilevel and Marginal Regression Analysis

This project performs a statistical analysis on data from a [longitudinal study of children with autism](https://pmc.ncbi.nlm.nih.gov/articles/PMC2893550/). The primary focus is to examine how various factors interact with a child's socialization levels as they progress through early life stages.

## Dataset Overview

The analysis utilizes a dataset containing 612 entries. The data structure includes the following variables:

* **`childid`**: A unique identifier for each child, used to track repeated measurements over time.
* **`age`**: The child's age at the time of observation, ranging from 2 to 13 years.
* **`vsae`**: The Vineland Social Age Equivalent score, representing the child's socialization level.
* **`sicdegp`**: A categorical grouping variable with values 1, 2, and 3.

## Analytical Approach

The study employs two main statistical modeling techniques to account for the correlation inherent in longitudinal data:

1. **Multilevel Modeling**: This approach uses explicit random effects for each child to account for repeated measurements.
2. **Marginal Regression (GEE)**: The notebook utilizes Generalized Estimating Equations (GEE) via `statsmodels`.
* **Exchangeable Structure**: Assumes a constant correlation between any two observations of the same child.
* **Robust Covariance**: Uses "sandwich" estimators to ensure reliable estimates even if the correlation structure is not perfectly specified.



## Key Features & Findings

* **Data Preprocessing**: The analysis includes data cleaning steps, specifically dropping a small number of cases with missing `vsae` values.
* **Visualizations**: The notebook generates scatterplots and boxplots to visualize the relationship between socialization levels (`vsae`) and `age`.
* **Model Comparison**: The analysis notes that point estimates for coefficients are very similar between multilevel and marginal models, a characteristic feature of GEE.
* **Significant Effects**: Preliminary findings from the marginal model highlight significant effects for **Age** (4.48, P<0.001) and **Group 3** (21.40, P<0.001).

## Technical Requirements

The analysis is implemented in Python using the following libraries:

* `pandas` and `numpy` for data manipulation.
* `statsmodels` for multilevel and GEE modeling.
* `matplotlib` and `seaborn` for data visualization.
