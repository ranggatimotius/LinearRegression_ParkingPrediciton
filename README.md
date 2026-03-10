# 🚗 Parking Occupancy Prediction using Linear Regression

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-lightgrey)
![Status](https://img.shields.io/badge/Project-Completed-brightgreen)

## 📌 Overview
This project predicts **parking space occupancy** using a **Linear Regression machine learning model**.  
The model analyzes several features such as parking capacity, vehicle type, traffic conditions, queue length, and time-related variables to estimate the number of occupied parking spaces.

The project demonstrates a complete **machine learning workflow**, including:
- Data preprocessing
- Feature engineering
- Model training
- Model evaluation
- Data visualization

---

## 📂 Project Structure
Parking-Occupancy-Prediction/
│
├── PrediksiKebutuhanParkir_RegresiLinear.ipynb
├── parkingStream.csv
└── README.md


---

## 📊 Dataset
The dataset contains **18,368 parking usage records** with multiple attributes related to parking availability and environmental factors.

### Features

| Feature | Description |
|------|------|
| SystemCodeNumber | Parking location identifier |
| Capacity | Maximum parking capacity |
| Latitude / Longitude | Geographic coordinates |
| Occupancy | Number of occupied parking spaces (target variable) |
| VehicleType | Type of vehicle |
| TrafficConditionNearby | Nearby traffic conditions |
| QueueLength | Number of vehicles waiting |
| IsSpecialDay | Indicator of special days |
| Timestamp | Observation time |

---

## ⚙️ Data Preprocessing
To ensure data quality and improve model performance, the following steps were performed:

- Removed duplicate records
- Converted columns to correct numeric types
- Removed invalid or negative values
- Ensured **Occupancy does not exceed Capacity**
- Converted `Timestamp` into datetime format

### Feature Engineering
New time-based features were created:

- `hour`
- `dayofweek`
- `month`
- `is_weekend`
- `hour_sin` and `hour_cos` (cyclical time encoding)
- `is_rush_hour`

Rare categories in categorical variables were grouped into **"Other"** to reduce noise during encoding.

---

## 🤖 Machine Learning Pipeline

The project uses a **Scikit-learn Pipeline** to integrate preprocessing and modeling.

Pipeline components:

1. **StandardScaler** → Normalizes numerical features  
2. **OneHotEncoder** → Encodes categorical features  
3. **LinearRegression** → Predictive model  

Dataset split:
- **80% Training Data**
- **20% Testing Data**

A **square root transformation** was applied to the target variable during training to stabilize variance.

---

## 📈 Model Performance

| Metric | Value |
|------|------|
| R² | 0.8859 |
| MAE | 132.06 |
| RMSE | 213.39 |

### Interpretation
- The model explains **~88.6% of variance** in parking occupancy.
- Average prediction error is around **132 parking spaces**.

---

## 📉 Visualizations
The notebook includes several visual analyses to understand model performance:

- Correlation matrix of numerical features
- Error vs Capacity scatter plot
- Actual vs Predicted occupancy comparison
- Residual analysis
- Prediction scatter plot

---

## 🛠 Technologies Used

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Scikit-learn**
- **Google Colab**

---

## 🚀 Future Improvements
Possible improvements for this project:

- Implement **more advanced models** (Random Forest, XGBoost)
- Perform **hyperparameter tuning**
- Add **time-series modeling**
- Build a **real-time parking prediction dashboard**

---

## 📚 References
- Scikit-learn Documentation  
- Machine Learning with Python resources  
- Public parking occupancy datasets

---

## 📌 Author
Developed as part of a **machine learning project on parking demand prediction**.
