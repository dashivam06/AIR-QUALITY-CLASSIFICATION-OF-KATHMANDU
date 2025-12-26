# Kathmandu PM2.5 Time Series Forecasting (2017–2021)

This project analyzes and models hourly **PM2.5 concentrations** in Kathmandu using the **“Air Quality Data in Kathmandu”** dataset from **Open Data Nepal**. [web:38]  
The dataset spans from **March 2017 to March 2021** and provides continuous records of particulate matter (PM2.5) collected from the **US Diplomatic Post, Phora Durbar** station. [web:32][web:51]

The study seeks to understand how air pollution trends evolved during this period — including seasonal variations, possible sensor downtime, and the pollution impact during the **COVID‑19 lockdown** — while comparing the performance of different forecasting models. [web:44][web:62]

---

## Dataset Overview

- **Source:** [Open Data Nepal – Air Quality Data in Kathmandu][dataset-link] [web:38]  
- **Period Covered:** March 2017 – March 2021 [web:32]  
- **Frequency:** Hourly readings [web:32]  
- **Pollutant Focus:** PM2.5 (Particulate Matter ≤ 2.5 µm) [web:62]  
- **Main Columns:** `local`, `utc`, `parameter`, `value`, plus optional metadata like `location`, `latitude`, and `country`. [web:38]

The dataset is openly licensed by **Open Knowledge Nepal** under a **Creative Commons Attribution 4.0 International (CC BY 4.0)** license, making it freely reusable for research and educational projects, provided proper attribution is given. [web:54][web:56][web:63][web:65]

[dataset-link]: https://opendatanepal.com/datasets/air-quality-data-in-kathmandu/918b774b-2a51-404f-92a0-0be1fe780f90

---

## Project Objective

The goal of this project is to explore and forecast PM2.5 levels to understand Kathmandu’s air quality behavior over time and to evaluate which statistical or machine learning model performs best. [web:32][web:44]

### Key Aims

- Detect outliers or invalid data and handle potential sensor downtime.  
- Smooth missing hourly values and prepare a consistent, gap-aware time series.  
- Visualize PM2.5 distribution, seasonal variations, and monthly trends.  
- Analyze air quality behavior specifically during **2020‑2021 (COVID period)**. [web:44][web:62]  
- Build and compare **Linear Regression**, **Random Forest**, and **LSTM** models. [web:29]  
- Evaluate all models based on **MAE**, **MSE**, **RMSE**, and **R²** to identify the most accurate approach. [web:29]

---

## Approach Summary

All major preprocessing, analysis, and visualization steps are explained directly within the Jupyter notebook through **detailed inline comments**, rather than in this README.  

The workflow generally follows:

1. **Data loading and filtering** for PM2.5.  
2. **Cleaning and missing value handling**, including invalid readings and downtime flags.  
3. **Visualization** of trends, seasonal patterns, and anomalies.  
4. **Feature engineering** with lag variables for time-series forecasting.  
5. **Model training, evaluation, and prediction comparison** across different algorithms.

By embedding explanations inside the code, readers can easily follow the logic and modify any part of the analysis.

---

## Models Used

- **Linear Regression**  
  Serves as a simple baseline model to capture short-term dependencies using lag features. [web:29]

- **Random Forest Regressor**  
  Captures complex, nonlinear relationships in the PM2.5 series using an ensemble of decision trees. [web:23]

- **LSTM (Long Short-Term Memory)**  
  A deep learning sequence model designed to capture longer temporal dependencies in time-series data, expected to handle more complex temporal patterns than basic regression models. [web:29]

---

## How to Run

1. **Clone or download** this project.  
2. Place the dataset file (e.g., `kathmandu_pm25_dataset.csv`) in the project folder. [web:38]  
3. Install dependencies:
    pip install pandas numpy matplotlib seaborn scikit-learn tensorflow


4. Open the notebook (e.g., `kathmandu_pm25_analysis.ipynb`) in Jupyter or VS Code.  
5. Run all cells sequentially.  
6. Explore the outputs:
- Data cleaning and preprocessing steps.  
- Visualizations (time series, trends, etc.).  
- Model training results and performance comparison.

All logic, explanations, and findings are documented **within the notebook itself** using comments and cell outputs.

---

## License and Acknowledgment

- **Data:** © Open Knowledge Nepal / Open Data Nepal, provided under **Creative Commons Attribution 4.0 International (CC BY 4.0)**. [web:54][web:56][web:63][web:65]  
- **Project Code:** You may choose your own license for the code (e.g., MIT, GPL); specify it in a `LICENSE` file in this repository.  

**Acknowledgment:**  
The dataset is derived from the **US Embassy Air Quality Monitoring Initiative** at **Phora Durbar, Kathmandu**, and made available through **Open Data Nepal** and partners working on open data and air quality monitoring in Nepal. [web:32][web:38][web:51]
