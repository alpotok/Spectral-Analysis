# Spectral Analysis and Time Series Modeling

**Date:** 2026-02-27  

This repository contains a comprehensive study of spectral analysis and time series modeling using R. The project is divided into a primary research task focused on Earth's geomagnetic activity and a portfolio of signal processing and forecasting problems.

## Data Source  
* **Geomagnetic Data:** Historical measurements of the **Ap Index** (geomagnetic activity) sourced from https://kp.gfz.de/en/data.
* **Portfolio Datasets:** Supplementary data including S&P 500 returns, quarterly GDP (PKB), ozone levels, and economic indicators such as inflation and unemployment.

## Technologies  
* **Language:** R / R Markdown

## Key Analyses  

### 1. Geomagnetic Activity Spectral Study
* **Data Preprocessing:** Stabilization of variance using log-transformation and trend removal using **LOESS** regression to focus on periodic cycles rather than long-term solar trends.
* **Spectral Leakage Analysis:** A comparative study of how the choice of $N$ (number of observations) affects frequency resolution, demonstrating "leakage" when $N$ is not divisible by the signal period.
* **Estimation Methods:** Implementation and comparison of multiple spectral density estimation techniques:
    * Naive Periodograms (defined by FFT).
    * **Welch’s Method** for noise reduction.
    * **Daniell Window** smoothing (single and multi-level).
    * **Bartlett’s Method** using disjoint sub-periods.
* **Missing Data Recovery:** Utilizing the **Lomb–Scargle Periodogram** to detect periodicities in datasets with 30% missing values, comparing its performance against standard methods.

### 2. Time Series Portfolio
* **Filter Comparison:** Analyzing the impact of lagged vs. centered Moving Averages and comparing the **Christiano-Fitzgerald (CF)** and **Hodrick-Prescott (HP)** filters in extracting business cycles.
* **Harmonic Regression:** Modeling seasonal patterns (e.g., ozone concentration) using sinusoidal combinations and discussing the risks of overfitting.
* **Memory in Time Series:** Comparing **ARFIMA** (Fractionally Integrated) and **ARIMA** models to demonstrate "long memory" effects and their impact on forecast confidence intervals.
* **Cross-Spectral Analysis:** Investigating the relationship between inflation and unemployment through **Coherence** and **Phase** analysis to calculate the time lag (approx. 7 months) between the two variables.

## Project Structure  
* `spectral_analysis.Rmd` - The primary R Markdown document containing all code, data processing, and analytical logic.
* `data/kp.csv` - Directory containing the required dataset.
* `reports/spectral_analysis.html` - The compiled report featuring visualizations and final conclusions.
