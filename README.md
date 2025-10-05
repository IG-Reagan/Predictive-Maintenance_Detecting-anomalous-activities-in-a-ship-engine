# Case Study: Predictive Maintenance — Detecting the Anomalous Activity of a Ship Engine

## Overview
This project developed a machine-learning-based predictive maintenance framework to detect anomalous behaviour in ship engine performance. The goal was to identify early warning signs of mechanical faults to reduce downtime, improve safety, and optimise operational efficiency across a commercial shipping fleet.

## Data Source
The dataset, provided by **Devabrat (2022)**, captures real-world sensor readings from a ship’s main engine. It consists of **19,535 records** with **six continuous features**: engine rpm, lubrication oil pressure, fuel pressure, coolant pressure, lubrication oil temperature, and coolant temperature. These variables reflect the mechanical and thermal conditions of the engine under different operating states.

## Methods
The anomaly-detection pipeline integrated both **statistical** and **machine learning** techniques:  
- **Exploratory Data Analysis (EDA):** Distribution inspection, outlier detection, and percentile analysis of sensor readings.  
- **Statistical approach:** Interquartile Range (IQR) method to flag outliers across all features, with criteria for multi-feature anomalies (≥3 outlying values).  
- **Machine-learning models:**  
  - **One-Class SVM** – modelled normal engine behaviour using standardised features and identified anomalies via deviations in feature space.  
  - **Isolation Forest** – isolated anomalous observations through random feature-split trees; visualised with PCA-reduced 2D scatter plots.  
- **Dimensionality Reduction:** PCA applied for visualisation and model interpretability.  

## Results
- **IQR method:** Detected 11 clear anomalies across multiple engine parameters.  
- **One-Class SVM:** Identified ~1,043 potential anomalies after tuning gamma and nu hyperparameters.  
- **Isolation Forest:** Detected **977 anomalies**, offering the best balance between sensitivity and computational efficiency.  
- The models confirmed that extreme deviations in coolant temperature and lubrication pressures were the strongest indicators of potential malfunction.  
- The **Isolation Forest** outperformed other methods in scalability, interpretability, and precision under minimal distributional assumptions.  

## Insights & Business Impact
- Provided a scalable framework for real-time anomaly detection in maritime operations.  
- Enables predictive maintenance scheduling, reducing unexpected failures and maintenance costs.  
- Supports improved engine health monitoring and fuel efficiency, contributing to safer, greener shipping operations.  

## Skills Demonstrated
- Data cleaning, feature scaling, and exploratory data analysis  
- Statistical anomaly detection (IQR)  
- Unsupervised machine learning (One-Class SVM, Isolation Forest)  
- Dimensionality reduction and visualisation (PCA)  
- Model evaluation and interpretability  
