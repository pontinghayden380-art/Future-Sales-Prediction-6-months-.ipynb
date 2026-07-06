# 🚀 Future Sales Prediction - 6 Months Forecast

[![Open In Colab][![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pontinghayden380-art/Future-Sales-Prediction-6-months-.ipynb/blob/main/Future_Sales_Prediction(6_months).ipynb)

**Author:** Ankit Jha  
**Date:** 06/07/2026

---

## 📌 Project Overview
This project focuses on predicting future sales for Indian retail stores using the "Indian Store Dataset" containing over 100,000 transactions. We implemented and compared five forecasting models to forecast sales for the next 6 months (180 days).

## 📊 Dataset Used
- **Name:** Indian Store Data
- **Size:** 100,000+ transactions
- **Features:** Order Date, Sales, Discount, Segment, City Type, Region, etc.
- **Source:** Public dataset from Kaggle

## 🛠️ Technologies & Libraries Used
- **Python** (Pandas, NumPy, Matplotlib, Seaborn)
- **Scikit-learn** (Linear Regression, Random Forest)
- **XGBoost**
- **LSTM** (Deep Learning with TensorFlow/Keras)
- **Prophet** (Facebook's Time Series Model)
- **Plotly** (Interactive Dashboard)

## 🧠 Models Implemented & Compared
1.  **Linear Regression**
2.  **Random Forest Regressor**
3.  **XGBoost Regressor**
4.  **LSTM (Long Short-Term Memory)**
5.  **Prophet (Time Series)**

## 📈 Key Results
| Model               | MAE        | RMSE       | R² Score   |
|---------------------|------------|------------|------------|
| Linear Regression   | 156,691.09 | 195,692.08 | **0.2176** |
| Random Forest       | 162,756.71 | 202,572.94 | 0.1616     |
| XGBoost             | 165,311.24 | 206,007.85 | 0.1329     |
| LSTM                | 1,372,876.10 | 1,390,569.39 | -38.5070 |
| Prophet             | 180,180.99 | 223,459.03 | -0.0202   |

### 🏆 Best Performing Model
**Linear Regression** performed best with an **R² Score of 0.2176**, indicating it can explain approximately 21.76% of the variance in sales data.

## 🔍 Key Observations
- **Linear Regression outperformed** all other models, including complex ones like XGBoost and LSTM.
- **LSTM performed poorly** with a negative R² score, indicating overfitting or insufficient data.
- The overall weak performance suggests that the dataset may need additional features (like holidays, promotions, weather data) for better predictions.

## 🔮 Future Predictions
Despite the weak model performance, the Linear Regression model was used to generate sales predictions for the **next 6 months (180 days)**. These predictions can serve as a baseline for future improvements.

## 📊 Dashboard
An interactive Plotly dashboard was created to visualize:
- Historical sales trends
- 6-month future sales predictions
- Seasonal patterns

## 🚀 How to Run This Project in Google Colab
1.  Click on the **"Open In Colab"** badge above.
2.  Run all cells sequentially.
3.  Upload the dataset when prompted.
4.  View the model comparison and future predictions.

## 📂 Repository Structure





## 🔧 Future Improvements
- Add external features (holidays, weather, promotions)
- Collect more historical data
- Try different aggregation levels (weekly instead of daily)
- Feature engineering with product categories
