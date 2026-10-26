# Time Series Forecasting: Airline Passenger Traffic

A comprehensive data analysis and preprocessing pipeline for time series forecasting using Python. This repository explores historical airline passenger traffic data, handles missing values, detects outliers, and performs time series decomposition to uncover underlying trends and seasonality.

---

## 🚀 Project Overview

Time series forecasting is critical for trend analysis, capacity planning, and business intelligence. This project demonstrates foundational time series preprocessing and exploratory data analysis (EDA) techniques using standard Python data science libraries.

### Key Steps Covered:
1. **Data Loading & Parsing**: Importing time series data and formatting datetime indices.
2. **Exploratory Data Analysis (EDA)**: Visualizing passenger traffic trends over time.
3. **Missing Value Treatment**: Comparing mean imputation vs. linear interpolation (selecting linear interpolation for temporal continuity).
4. **Outlier Detection**: Using box plots, interquartile range (IQR), and distribution histograms.
5. **Time Series Decomposition**: Breaking down the series into trend, seasonal, and residual components.

---

## 📊 Dataset

* **File**: `airline-passenger-traffic.csv`
* **Description**: Contains monthly totals of international airline passengers (typically spanning from 1949 to 1960, depending on the standard dataset).
* **Columns**: 
  * `Month`: The timestamp of the observation (formatted as `YYYY-MM`).
  * `Passengers`: The number of passengers reported.

---

## 🛠️ Technologies & Libraries

This project is built in Python and relies on the following packages:
* **Pandas**: Data manipulation and time series indexing.
* **NumPy**: Numerical computations.
* **Matplotlib**: Data visualization and plotting.

---

## ⚙️ Workflow & Code Highlights

### 1. Data Initialization & Import
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# Load and set datetime index
data = pd.read_csv('airline-passenger-traffic.csv', header=None)
data.columns = ['Month', 'Passengers']
data['Month'] = pd.to_datetime(data['Month'], format='%Y-%m')
data = data.set_index('Month')

### 2. Missing Value Imputation
To preserve the temporal structure of the time series, **Linear Interpolation** is utilized to smoothly bridge missing data points compared to simple mean imputation.

### 3. Outlier Analysis & Time Series Decomposition
The pipeline utilizes box plots and visual summaries to inspect data distributions, followed by separating the trend, seasonality, and residuals.

---
