# IoT-Based Animal Monitoring and Milk Yield Prediction

## Project Overview

This project explores the use of **IoT-based animal monitoring data and machine learning to predict milk production**.

Animal-related measurements collected over time are used as input features for regression models. Multiple machine learning algorithms are compared to evaluate how effectively the available variables can predict milk yield.

The project combines concepts from **IoT, data analysis, and machine learning**.

---

## Dataset


The dataset contains **240 observations**.

The main variables used for modelling are:

| Variable | What It Represents | Likely Unit | Realistic Data Collection |
|----------|--------------------|-------------|---------------------------|
| `TMR` | Total Mixed Ration/feed consumed by the cow | kg/day | RFID identifies the cow and a weight sensor measures feed consumed |
| `GRASS` | Grass/fodder consumed or grazing activity | kg/day | Smart collar/accelerometer monitors grazing behaviour |
| `WATER` | Water consumed by the cow | litres/day | RFID identifies the cow and a flow meter measures water consumption |
| `BATH` | Number of bathing/cooling events | events/day | RFID/proximity sensor records visits to the cooling or bathing area |
| `MILK` | Daily milk production - prediction target | litres/day | Electronic milk meter records milk produced during milking |

The original data also contains animal identification and date information for tracking measurements over time.


---

## Machine Learning Objective

The objective of the project is to predict **milk production (`MILK`)** using four input variables:

```text
TMR + GRASS + WATER + BATH → MILK
```

The dataset was divided into:

- **80% training data**
- **20% testing data**

---

## Models Evaluated

Six regression models were evaluated:

- Linear Regression
- Decision Tree Regression
- Support Vector Regression (SVR)
- Random Forest Regression
- XGBoost Regression
- Neural Network

---

## Model Performance

| Model | MAE | RMSE | R² |
|------|----:|-----:|---:|
| Support Vector Regression | **1.734** | **1.905** | **0.4040** |
| Linear Regression | 1.757 | 1.909 | 0.4013 |
| XGBoost | 1.873 | 2.048 | 0.3110 |
| Decision Tree | 1.876 | 2.080 | 0.2894 |
| Random Forest | 1.961 | 2.162 | 0.2321 |
| Neural Network | 2.577 | 3.114 | -0.5926 |

**Support Vector Regression (SVR)** achieved the best performance among the evaluated models, with an **R² of 0.404** and **RMSE of 1.905**.

Linear Regression produced very similar results.

---

## IoT Concept

The broader animal-monitoring system uses IoT technologies to collect animal-related information through sensors and connected devices.

A simplified data flow is:

```text
Animal Sensors
      ↓
IoT Network
      ↓
IoT Gateway
      ↓
Cloud / Database
      ↓
Data Processing
      ↓
Machine Learning
      ↓
Milk Yield Prediction
```

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- TensorFlow / Keras
- Jupyter Notebook
- Machine Learning
- IoT Concepts

---

## Evaluation Metrics

The regression models were evaluated using:

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R² Score

---

## Key Finding

The results indicate that the available animal-monitoring variables contain useful information for predicting milk production.

The best-performing model, **Support Vector Regression**, achieved an **R² of approximately 0.40**.

This also indicates that the four available predictors do not explain all variation in milk production. Additional animal, environmental, behavioural, and historical production variables could potentially improve prediction performance.

---

## Future Improvements

Future improvements could include:

- Collecting data from more animals over longer periods
- Adding animal-specific characteristics
- Adding environmental sensor data
- Adding behavioural and activity measurements
- Including previous milk-production measurements
- Feature engineering
- Hyperparameter tuning
- Cross-validation and time-based validation
- Developing a real-time IoT prediction pipeline

---

## Project Purpose

This project demonstrates the application of **machine learning regression techniques to IoT-based livestock data**, including data preparation, model development, performance evaluation, and comparison of multiple regression algorithms.
