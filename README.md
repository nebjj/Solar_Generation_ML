# Solar_Generation_ML
Project Overview: This project develops a machine learning-based system for solar AC power estimation and forecasting using operational and environmental data collected from photovoltaic (PV) plants. The study focuses on building accurate predictive models that assist in monitoring solar power generation and forecasting future power output.

Three predictive models were developed and evaluated:

Model 1: Current AC Power Estimation
Model 2A: Future AC Power Forecasting
Model 2B: Forecasting with Time-Series Lag Features

After extensive experimentation, XGBoost (Model 2B) was selected as the final forecasting model due to its superior predictive performance.

Objectives
1. Predict current solar AC power generation.
2. Forecast future AC power using weather parameters.
3. Improve forecasting accuracy using lag-based time-series features.
4. Compare multiple machine learning algorithms.
5. Develop interactive Tableau dashboards for visualization and analysis.

Dataset

The project uses the Solar Power Generation Data containing:

1. Plant operational data
2. Weather sensor measurements
3. Inverter information
4. Time-series power generation records

Features Used
	Plant ID
	Inverter ID
	Irradiation
	Ambient Temperature
	Module Temperature
	DC Power (Model 1)
	Hour, Day, Month
	Day of Week
	Hour (Sin/Cos Encoding)
	Temperature Difference
	Lag Features (Model 2B)
	AC_POWER_LAG_1
	AC_POWER_LAG_2
	AC_POWER_LAG_4
	Rolling Mean
	Rolling Standard Deviation

Technologies Used
	Python
	Pandas
	NumPy
	Scikit-learn
	XGBoost
	CatBoost
	LightGBM
	Random Forest
	Matplotlib
	Tableau

Exploratory Data Analysis

	Performed:
	
		Missing value analysis
		Duplicate removal
		Feature engineering
		Correlation analysis
		Distribution analysis
		Scatter plots
		Time-series visualization

Feature Engineering

	Implemented:

		Hour, Day, Month extraction
		Day of Week
		Cyclical encoding (Hour Sin & Hour Cos)
		Temperature Difference
		Time-series lag features
		Rolling statistics

Machine Learning Models
	Model 1 – Current AC Power Estimation
		
		Predicts the current AC Power using operational measurements including DC Power.
			
		Algorithms Evaluated
			Linear Regression
			Decision Tree
			Random Forest 
			XGBoost
			LightGBM
			CatBoost
		Best Model: Random Forest

		Performance:

			R² : 0.9999
			RMSE : 3.30
			MAE : 0.57

	Model 2A – Future AC Power Forecasting

		Forecasts future AC Power without using DC Power.

		Algorithms Evaluated
			Linear Regression
			Decision Tree
			Random Forest
			XGBoost
			LightGBM
			CatBoost 

		Best Model: CatBoost

		Performance:

			R² : 0.8636
			RMSE : 119.73
			MAE : 41.05

	Model 2B – Forecasting with Lag Features

		Enhanced forecasting using previous AC power values and rolling statistics.

		Algorithms Evaluated
			Linear Regression
			Decision Tree
			Random Forest
			XGBoost 
			LightGBM
			CatBoost
		
		Best Model: XGBoost
		
		Performance:
		
			R² : 0.9589
			RMSE : 64.81
			MAE : 26.41
		
Model Comparison
		Model	Best Algorithm	R²	RMSE	MAE
		Model 1	Random Forest	0.9999	3.30	0.57
		Model 2A	CatBoost	0.8636	119.73	41.05
		Model 2B	XGBoost	0.9589	64.81	26.41

Observation

	Model 1 achieved the highest accuracy because it uses DC Power, which is highly correlated with AC Power.
	Model 2A demonstrates baseline forecasting performance without historical power information.
	Model 2B significantly improves forecasting accuracy by incorporating lag-based time-series features, making it the preferred model for practical forecasting.

Tableau Dashboards

Three interactive dashboards were developed.

1. Solar Plant Overview

	Includes:
	
	Total AC Power
	Maximum AC Power
	Average AC Power
	Average Irradiation
	Daily AC Power Generation
	Hourly AC Power Generation
	Plant-wise Average AC Power

2. Environmental Analysis

	Visualizations include:
	
	Irradiation vs AC Power
	Ambient Temperature vs AC Power
	Module Temperature vs AC Power

3. Machine Learning Dashboard

	Contains:
	
	Actual vs Predicted AC Power
	Prediction Error Distribution
	Top 10 Inverters
	Model Performance KPIs
		MAE
		RMSE
		R² Score

Future Improvements

	Deep Learning models (LSTM, GRU, Transformer)
	Multi-step forecasting
	Hyperparameter optimization using Optuna
	Explainable AI using SHAP values
	Real-time prediction using APIs
	Deployment with Streamlit or Flask
	Cloud deployment (AWS/Azure/GCP)

Results
	Successfully developed three machine learning models for solar power estimation and forecasting.
	Achieved 95.89% forecasting accuracy (R²) using XGBoost with lag features.
	Built interactive Tableau dashboards for operational monitoring, environmental analysis, and prediction evaluation.
	Demonstrated that incorporating historical power information significantly improves forecasting performance.
