# COVID-19 Data Analysis & Visualization (EDA)
COVID-19 Data Analysis &amp; Visualization Performed exploratory data analysis on COVID-19 data to study daily trends, rolling averages, recovery rates, and fatality rates using Python and interactive visualizations.


## 📌 Project Overview

This project focuses on performing **Exploratory Data Analysis (EDA)** on the COVID-19 dataset to understand the spread, trends, and impact of the pandemic over time.  
Using Python, the project analyzes **daily confirmed cases, recoveries, deaths**, and derives meaningful health indicators such as **Case Fatality Rate (CFR)** and **Recovery Rate**.

Interactive and static visualizations are used to clearly communicate pandemic trends at both **global** and **country-level (India)**.

---

## 🎯 Project Objectives

- Perform data cleaning and preprocessing on COVID-19 datasets
- Analyze daily new confirmed cases, recoveries, and deaths
- Apply **7-day rolling averages** to smooth daily fluctuations
- Calculate key metrics:
  - Case Fatality Rate (CFR)
  - Recovery Rate
- Visualize trends using **interactive Plotly graphs**
- Compare global trends with country-specific analysis

---

## 📊 Dataset Information

- **Dataset Type**: Time-series COVID-19 data
- **Source**: Public COVID-19 datasets (Johns Hopkins / Kaggle)
- **Time Period**: From the beginning of the pandemic till available date
- **Granularity**: Daily records

### Key Columns:
- `Date`
- `Confirmed`
- `Recovered`
- `Deaths`
- `NewConfirmed`
- `NewRecovered`
- `NewDeaths`
- `NewConfirmed_7d`
- `CFR`
- `RecoveryRate`

---

## 🔧 Tools & Technologies Used

- **Python**
- **Pandas** – Data manipulation and analysis
- **NumPy** – Numerical computations
- **Matplotlib & Seaborn** – Static visualizations
- **Plotly** – Interactive charts
- **Google Colab**

---

## 🧹 Data Preprocessing Steps

- Converted date columns to datetime format
- Handled missing values using `fillna()`
- Removed infinite values caused by division by zero
- Created new derived features such as daily cases and rates

Example:
```python
df['CFR'] = (df['Deaths'] / df['Confirmed']) \
            .replace([np.inf, -np.inf], np.nan) \
            .fillna(0)
```

## 🧠 Feature Engineering

Feature engineering was performed to convert raw cumulative COVID-19 data into meaningful features that help analyze trends and patterns over time.

---

### 🔹 Daily New Metrics

Since the dataset contains cumulative values, daily metrics were derived using the difference between consecutive days.

**Daily New Confirmed Cases**
```python
df['NewConfirmed'] = df['Confirmed'].diff().fillna(df['Confirmed'])
```
**7- Day Rolling Average**
```python
df['NewConfirmed_7d'] = df['NewConfirmed'].rolling(7).mean()
```
**Recovery Rate**
```python
df['RecoveryRate'] = (df['Recovered'] / df['Confirmed']) \
                     .replace([np.inf, -np.inf], np.nan) \
                     .fillna(0)
```
---

## 📈 Visualizations:

The following visualizations are included in the project:

- 📉 Daily New Confirmed Cases
- 📊 7-Day Rolling Average Trends
- 🧮 Case Fatality Rate (CFR) over time
- 💚 Recovery Rate analysis
- 🌍 Global vs India comparison
- 🟦 Interactive Line and Bar Charts using Plotly

----

## 🔍 Key Insights

- Daily COVID-19 data contains high fluctuations due to reporting delays
-  Rolling averages help reveal true pandemic trends
- CFR decreases over time with improved healthcare response
- Recovery rate increases as treatment and testing improve
- Significant differences observed between global and country-level trends


👩‍💻 Author

Darshini
📧 Email: darshinio245@gmail.com

🔗 GitHub: https://github.com/darshinio-debug





