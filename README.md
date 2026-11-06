# IoT-Based Streaming Data for Traffic Intensity Prediction using AdReSaR

## Overview

This project explores the use of IoT streaming data and machine learning techniques to predict traffic conditions. It focuses on forecasting three key traffic parameters:

- **Traffic Intensity**
- **Occupancy**
- **Traffic Load**

The pipeline combines data preprocessing, interpolation, sampling techniques, and regression models to evaluate prediction accuracy and support near-real-time traffic forecasting.

## Objectives

- Develop a traffic prediction pipeline using IoT-based traffic data.
- Forecast traffic intensity, occupancy, and load using machine learning regression models.
- Investigate the impact of data interpolation on prediction accuracy.
- Apply Reservoir Sampling to reduce the volume of data while retaining representative observations.
- Explore adaptive prediction windows to support near-real-time forecasting.

## Methodology

### 1. Data Preprocessing and Interpolation

The traffic dataset contains time-series observations recorded at 15-minute intervals. Linear and cubic interpolation techniques were explored to generate observations at finer resolutions, including 5-minute and 1-minute intervals.

### 2. Reservoir Sampling

Reservoir Sampling was applied to reduce the dataset size while retaining representative samples. This helped investigate the effect of sampling on model performance and prediction accuracy.

### 3. Machine Learning Models

The following regression models were implemented and evaluated:

- **Support Vector Regression (SVR):** Used with an RBF kernel to model nonlinear relationships in traffic data.
- **Stochastic Gradient Descent (SGD) Regressor:** Evaluated as a regression approach for traffic parameter prediction.
- **Gaussian Process Regression (GPR):** Implemented with a Matérn kernel to model traffic patterns and generate predictions.

### 4. Adaptive Prediction Window

An adaptive prediction-window strategy was explored using Mean Absolute Percentage Error (MAPE) as a feedback measure.

- If MAPE exceeded 10%, the prediction window was reduced.
- If MAPE was below 5%, the prediction window was increased.
- The prediction window was bounded between 3 and 6 intervals.

This approach was used to investigate how prediction intervals could adapt to changing forecasting accuracy.

## Prediction Workflow

1. Collect and prepare traffic time-series data.
2. Apply interpolation to generate finer-grained observations.
3. Perform Reservoir Sampling to reduce the dataset size.
4. Train and evaluate regression models.
5. Generate predictions using sliding training and prediction windows.
6. Compare predicted values with actual traffic observations.
7. Calculate MAPE and adjust the prediction window based on forecasting performance.

## Technologies and Techniques

- **Programming Language:** Python
- **Machine Learning:** Scikit-learn
- **Data Processing:** Pandas, NumPy
- **Streaming Technology:** Apache Kafka
- **Techniques:** Linear Interpolation, Cubic Interpolation, Reservoir Sampling, Time-Series Forecasting
- **Models:** SVR, SGD Regressor, Gaussian Process Regression

## Results and Observations

- Evaluated the effect of different interpolation intervals on forecasting accuracy.
- Compared regression models across traffic intensity, occupancy, and load.
- Investigated the impact of Reservoir Sampling on model performance.
- Gaussian Process Regression with a Matérn kernel produced the best results among the evaluated models in the reported experiments.
- One-minute interpolation generally achieved lower MAPE than five-minute interpolation.

## Project Scope

This project investigates machine learning approaches for traffic prediction using IoT-based time-series data, with an emphasis on data preprocessing, efficient sampling, model evaluation, and adaptive forecasting.

