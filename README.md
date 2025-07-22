# Flood Prediction in Assam Using Historical Rainfall Data

## Overview

This project explores the feasibility of predicting floods in the Indian state of **Assam** using only historical **rainfall data (1999–2019)**. In a region frequently impacted by seasonal monsoon flooding, the study demonstrates how accessible machine learning methods and limited public data can be used to build an early warning system.


## Objectives

- **Primary**: Develop a rainfall-based predictive model to detect flood-prone days in Assam.
- **Secondary**: Evaluate the potential of rainfall-only models in the absence of complex environmental data like soil moisture or river levels.

## Data Sources

- [EM-DAT International Disaster Database](https://www.emdat.be/)
- PEND-GDIS 1960–2018 Global Disaster Locations
- Indian Flood Inventory (Hydrolab, IIT Delhi)
- Daily rainfall data from [India WRIS](https://indiawris.gov.in)

## Preprocessing & Feature Engineering

- Standardized flood causes (e.g., "heavy rain")
- Binary labels created:
  - `Flood 1`: Any flood occurrence
  - `Flood 2`: Severe floods (severity > 1)
- Engineered features:
  - 3-Day Cumulative Actual Rainfall
  - Consecutive Rainy Days
  - Seasonal Indicator (Month)

## Machine Learning Models

- **Logistic Regression**: Baseline model
- **Random Forest**
- **Gradient Boosting**
- **XGBoost** with SHAP for interpretability

### Balancing Techniques Used

- **Oversampling** of minority class (flood days)
- **Class weight adjustment**
- **Threshold optimization** using precision-recall curves

## Model Evaluation Metrics

- **Accuracy**
- **Precision, Recall, F1-score**
- **Confusion Matrix**
- **SHAP Analysis** for feature interpretability

## Key Findings

- **Random Forest** achieved best balance (accuracy: 82%, recall for flood days: 88%).
- SHAP revealed that:
  - **3-Day Cumulative Rainfall** and **Consecutive Rainy Days** are top predictors.
  - Seasonal patterns align with monsoon months.

## Limitations

- Relied only on rainfall data.
- Could not achieve high precision for **severe floods** (Flood 2).
- Oversampling introduced potential bias.

## Future Directions

- Include topographical, hydrological (river level), and soil moisture data.
- Collaborate with government agencies for enriched datasets.
- Explore spatiotemporal deep learning models (e.g., LSTM, CNN).
- Expand model for other monsoon-affected regions.

## Project Structure

