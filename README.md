# D603 – Data Mining II
**Western Governors University**  
**Student:** John David  
**Program:** Master of Science, Data Analytics

---

## Repository Overview

This repository contains all code, notebooks, and analysis for the three tasks in D603 Data Mining II. Each task is developed in its own branch with progressive commits documenting each step of the analysis.

---

## Branch Structure

| Branch | Task | Method | Dataset |
|---|---|---|---|
| task-1-working | Task 1 – Classification | Random Forest | medical_clean.csv |
| task-2 | Task 2 – Clustering | K-Means | medical_clean.csv |
| task-3 | Task 3 – Time Series | ARIMA | teleco_time_series_.csv |

---

## Task 1 – Medical Readmission Classification

**Branch:** task-1-working  
**Notebook:** D603_Task1_Medical_Readmission.ipynb  
**Dataset:** medical_clean.csv  
**Method:** Random Forest Classification  

### Research Question
Can patient demographic characteristics, medical conditions, hospitalization details, and service utilization be used to accurately predict whether a patient will be readmitted to the hospital within one month of discharge?

### Goal
Build and optimize a Random Forest classification model that classifies patients as likely or unlikely to be readmitted within 30 days, enabling the hospital chain to implement targeted post-discharge interventions and reduce CMS penalty exposure.

### Files
- `D603_Task1_Medical_Readmission.ipynb` — full analysis notebook
- `medical_clean_prepared.csv` — cleaned and encoded dataset (D4)
- `medical_train.csv` — training set 70% (E1)
- `medical_validation.csv` — validation set 15% (E1)
- `medical_test.csv` — test set 15% (E1)

### Steps Completed
- D3: Data preparation — dropped identifiers, checked missing values and duplicates, encoded categorical variables, descriptive statistics
- D4: Saved cleaned dataset
- E1: Train/validation/test split (70/15/15)
- E2: Initial Random Forest model trained and evaluated on training set
- E3: Hyperparameter tuning with GridSearchCV and 5-fold cross-validation
- E4: Optimized model evaluated on held-out test set

---

## Task 2 – Patient Clustering Analysis

**Branch:** task-2  
**Notebook:** D603_Task2_Clustering.ipynb  
**Dataset:** medical_clean.csv  
**Method:** K-Means Clustering  

### Research Question
Can hospital patients be grouped into distinct clusters based on their continuous clinical and demographic characteristics in order to identify patient segments with similar care utilization profiles?

### Goal
Apply k-means clustering to identify naturally occurring groups of patients with similar hospitalization and demographic profiles, enabling the hospital to design differentiated care pathways and allocate resources more efficiently.

### Files
- `D603_Task2_Clustering.ipynb` — full analysis notebook
- `medical_clustering_prepared.csv` — cleaned dataset with selected variables (D4)
- `medical_clustering_results.csv` — dataset with cluster labels assigned

### Steps Completed
- D3: Selected 10 continuous variables, checked missing values and duplicates, descriptive statistics, applied StandardScaler
- D4: Saved cleaned clustering dataset
- E1: Elbow Method, Silhouette Score, and Davies-Bouldin Index to determine optimal k
- F1: Trained final k-means model, generated PCA scatter plot, cluster profile heatmap, box plots, and cluster size chart

---

## Task 3 – Telecommunications Revenue Time Series Forecasting

**Branch:** task-3  
**Notebook:** D603_Task3_Teleco_TimeSeries.ipynb  
**Dataset:** teleco_time_series_.csv  
**Method:** ARIMA Time Series Modeling  

### Research Question
Using time series analysis, how does daily revenue trend over the first two years of operation for this telecommunications company, and can an ARIMA model accurately forecast the next 30 days of revenue beyond the available data to support business planning and customer retention strategy?

### Goal
Analyze the 731-day daily revenue time series, fit an optimal ARIMA model, and generate two forecasts: one against the held-out test data to evaluate accuracy, and one projecting 30 days beyond all available data for financial planning.

### Files
- `D603_Task3_Teleco_TimeSeries.ipynb` — full analysis notebook
- `teleco_timeseries_clean.csv` — cleaned time series dataset with train/test labels (D5)

### Steps Completed
- D1: Line graph of time series realization
- D2: Time step documentation
- D3: ADF stationarity test
- D4: Walk-forward train/test split (80/20)
- D5: Saved cleaned dataset
- E1a: Trend analysis — rolling mean and standard deviation
- E1b: ACF and PACF plots
- E1c: Spectral density analysis
- E1d: Seasonal decomposition
- E1e: Residual diagnostics
- E2: ARIMA model identification using auto_arima (AIC selection)
- E3: Forecast 2 — forecast vs actual test data with 95% prediction interval
- E4: Error metrics — MAE, RMSE, MAPE
- F2: Forecast 1 — 30-day future forecast beyond available data

---

## Libraries Used

| Library | Version | Purpose |
|---|---|---|
| pandas | latest | Data loading and manipulation |
| numpy | latest | Numerical operations |
| matplotlib | latest | Data visualization |
| seaborn | latest | Statistical visualization |
| scikit-learn | latest | Random Forest, K-Means, metrics, preprocessing |
| statsmodels | latest | ARIMA, ADF test, ACF/PACF, decomposition |
| pmdarima | latest | auto_arima model selection |
| scipy | latest | Spectral density (periodogram) |

---

## How to Run

### Requirements
```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels pmdarima scipy
```

### Running the Notebooks
1. Clone this repository
2. Switch to the relevant branch (`task-1-working`, `task-2`, or `task-3`)
3. Place the required dataset CSV in the same folder as the notebook
4. Open the notebook in VS Code or Jupyter
5. Run all cells from top to bottom using Run All

### Dataset Files Required
| Task | Dataset File |
|---|---|
| Task 1 and 2 | medical_clean.csv |
| Task 3 | teleco_time_series_.csv |

---

## Commit History

Each branch contains progressive commits made after completing each lettered requirement, documenting the step-by-step development of the analysis. See the Commits page on each branch for the full history.

---

## Course Information

| Field | Detail |
|---|---|
| Course | D603 – Data Mining II |
| University | Western Governors University |
| Program | MS Data Analytics |
| Tasks | Classification, Clustering, Time Series |
| Submission | 2024-2025 Academic Year |
