# Electricity Demand Forecasting

<p align="center">
  <img src="https://raw.githubusercontent.com/snsamia/M.Sc-Thesis/main/front%20photo.png" alt="Project Banner" width="900"/>
</p>

## Overview

This repository contains the implementation of my Master’s thesis on **U.S. hourly electricity demand forecasting**.

The goal of this project is simple:  
understand how electricity demand behaves over time and build a clean pipeline to predict it.

Think of it like this — we take raw hourly electricity data, clean it, understand patterns (like daily peaks), and then build a model that can predict future demand.

---

## Objectives

- Understand hourly electricity demand patterns  
- Identify trends and seasonality  
- Prepare data for forecasting  
- Apply time series models  
- Build a reproducible pipeline  

---
## Dataset

The dataset used in this project is sourced from the U.S. Energy Information Administration (EIA) open data platform.

- Source: U.S. electricity demand data (EIA)  
- Region: US48 (United States Lower 48)  
- Frequency: Hourly  
- Time span: 2019 – 2026  
- Main variable: Electricity demand  

You can directly explore the dataset here:

🔗 https://www.eia.gov/opendata/browser/electricity/rto/region-data?frequency=hourly&data=value;&facets=respondent;&respondent=US48;&start=2025-01-01T00&end=2025-12-31T00&sortColumn=period;&sortDirection=desc;

---

The raw data was collected and processed into a structured time series format for analysis and forecasting.

## Project Workflow

### 1. Data Preparation

First, we make the data usable.

- Load raw data  
- Convert timestamps properly  
- Sort by time  
- Create features like hour, day, month  

---

### 2. Exploratory Data Analysis (EDA)

Here we try to *understand the data*.

- Plot demand over time  
- Compare different years and months  
- Look at daily patterns (like morning vs night demand)  
- Check how values are distributed  

---

### 3. Time Series Analysis

Before modeling, we check if the data behaves nicely.

- ACF → shows how past values affect future  
- PACF → helps decide model structure  
- ADF & KPSS → check stationarity  
- Differencing → removes trend and seasonality  

---

### 4. Model Development

Now we build the forecasting model.

- Use SARIMA (time series model)  
- Select parameters using ACF & PACF  
- Run grid search  
- Compare models using AIC  

---

### 5. Forecasting

Final step — making predictions.

- Final model: **SARIMA (2,1,3)(2,1,2,24)**  
- Captures daily seasonality (24-hour cycle)  
- Predicts short-term electricity demand  

---

## Technologies Used

- Python  
- pandas  
- numpy  
- matplotlib  
- seaborn  
- statsmodels  
- scikit-learn  

---

## Repository Structure

```text
├── thesis-code-v2.ipynb   # Main notebook (data processing, EDA, modeling, forecasting)
├── data/                  # Raw and processed datasets
├── results/               # Model outputs, plots, and evaluation results
├── assets/                # Images (e.g., front banner, figures)
└── README.md              # Project documentation
