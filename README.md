# Traffic Pattern Analysis 🚦

## Project Overview 🚦

This project analyzes **hourly traffic patterns** across multiple junctions using historical vehicle count data. The focus is on **data cleaning, exploratory data analysis (EDA), time-based feature engineering, and visualization**, preparing the dataset for time series modeling and forecasting.

**Contents**

* `Train.csv` – historical traffic counts
* `Test.csv` – future timestamps
* `Traffic-Patterns.ipynb` – complete analysis workflow

---

## Dataset Description

### Train Dataset

| Column   | Description                                   |
| -------- | --------------------------------------------- |
| DateTime | Timestamp of observation (hourly frequency)   |
| Junction | Junction identifier                           |
| Vehicles | Number of vehicles observed (target variable) |
| ID       | Unique record identifier                      |

* **Rows:** ~48,000
* **Granularity:** Hourly traffic counts

### Test Dataset

| Column   | Description              |
| -------- | ------------------------ |
| DateTime | Timestamp for prediction |
| Junction | Junction identifier      |
| ID       | Unique record identifier |

---

## Data Cleaning & Preprocessing

* Converted `DateTime` to proper `datetime` format (day-first).
* Checked and confirmed absence of missing values.
* Ensured consistent hourly time granularity.
* Transformed timestamps into Unix time for modeling compatibility.

### Time-Based Feature Engineering

Extracted key temporal features:

* Year, Month, Day, Quarter
* Weekday, Week of Year
* Time of day (seconds)

These features enable daily, weekly, and seasonal traffic analysis.

---

## Exploratory Data Analysis (EDA)

* Analyzed distribution of vehicle counts using histograms (right-skewed pattern).
* Identified peak and off-peak traffic behavior.
* Applied **Extra Trees** model for exploratory feature importance.
* Found strong influence of time-related variables (DateTime, Time of Day, Weekday).

Visualizations include traffic distributions and feature-importance bar charts.

---

## Time Series Perspective

* Hourly data captures **diurnal traffic cycles**.
* Weekly and monthly features reflect **recurring seasonal patterns**.
* Junction-wise analysis highlights spatial traffic variation.

The dataset is well-structured for forecasting and trend analysis.

---

## Data Preparation for Modeling

For modeling readiness:

* Non-essential identifiers (`ID`, redundant date parts) were dropped where appropriate.
* Both train and test datasets were aligned to ensure consistent feature sets.
* Final feature matrices (`X`, `X_test`) and target vector (`y`) were prepared.

This clean separation ensures reproducibility and smooth transition to predictive modeling.

---

## Tools & Libraries Used

### Core Libraries (from `Traffic-Patterns.ipynb`)

* **Python**
* **Pandas, NumPy** – data manipulation & feature engineering
* **Matplotlib** – traffic and feature visualizations
* **Scikit-learn** – Extra Trees model for feature importance
* **Datetime, Time** – temporal processing

---

## Key Takeaways

* Traffic volume is highly **time-dependent**.
* Timestamp-based feature engineering adds significant analytical value.
* Visual EDA reveals congestion patterns and peak hours.
* The cleaned dataset is ready for advanced **time series forecasting**.

*Concise, reproducible traffic analysis workflow suitable for data analytics and urban mobility projects.*
