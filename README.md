# 🚀 Future Sales Prediction - 6 Months Forecast

**Author:** Ankit Jha  
**Date:** July 2026  
**Institution:** IDEAS - Institute of Data Engineering, Analytics and Science Foundation, ISI Kolkata  
**Guide:** Dr. Dipasree Pal

---

## 📌 Project Overview

This project presents a complete time-series machine learning pipeline for forecasting daily retail sales in the Indian retail sector over a **6-month (180-day) horizon**. Retail sales fluctuate due to seasonal trends, customer behavior, and market dynamics, creating the risk of overstocking (tying up capital in unsold inventory) or understocking (losing revenue due to stockouts).

The pipeline supports data-driven decision making for:
- 📦 **Inventory Management** - Order the right quantity of products
- 👥 **Staff Scheduling** - Align workforce with expected footfall
- 💰 **Financial Planning** - Project revenue for cash-flow management
- 📢 **Promotional Strategy** - Plan marketing campaigns strategically

---

## 📊 Dataset Used

| Property | Details |
|----------|---------|
| **Name** | Indian Store Dataset |
| **Size** | 100,000+ transactions |
| **Time Period** | January 2019 - December 2023 (1,796 days) |
| **Data Coverage** | 100% complete (no missing dates) |
| **Features** | Order Date, Sales, Discount, Segment, City Type, Region, Product Category, etc. |
| **Source** | Public dataset from Kaggle |

### Dataset Statistics
| Metric | Value |
|--------|-------|
| Minimum Daily Sales | ₹815,302.96 |
| Maximum Daily Sales | ₹2,143,603.46 |
| Mean Daily Sales | ₹1,373,701.17 |
| Median Daily Sales | ₹1,364,909.24 |
| Standard Deviation | ₹213,211.17 |
| Total Sales (All Days) | ₹2,467,167,298.46 |

---

## 🛠️ Technologies & Libraries Used

### Core Libraries
- **Python** (Pandas, NumPy, Matplotlib, Seaborn) - Data processing & visualization
- **Scikit-learn** - Linear Regression, Random Forest, preprocessing
- **XGBoost** - Gradient boosting implementation
- **TensorFlow/Keras** - LSTM deep learning model
- **Prophet** - Facebook's dedicated time-series model
- **Plotly** - Interactive dashboard creation

### Development Environment
- **Google Colab** - Cloud-based Jupyter notebook environment with GPU support

---

## 🧠 Methodology

### Phase 1: Data Preparation
- Parsed order dates to datetime format and sorted chronologically
- Removed records with missing sales values (100,000+ records available)
- Removed outliers using the **IQR (Interquartile Range) method**
- Identified 9 outlier days (0.50% of total data)

### Phase 2: Feature Engineering
Created 15 engineered features organized into three categories:

#### 📊 Lag Features (5 features)
- Lag_1, Lag_3, Lag_7, Lag_14, Lag_30
- Captures short-term dependencies and weekly/monthly seasonality

#### 📈 Rolling Statistics (6 features)
- Rolling_Mean_7, Rolling_Mean_14, Rolling_Mean_30
- Rolling_Std_7, Rolling_Std_14, Rolling_Std_30
- Captures underlying trend and volatility

#### 📅 Calendar Features (4 features)
- Year, Month, Day, DayOfWeek, WeekOfYear, Quarter, IsWeekend
- Enables learning of calendar-based sales patterns

### Phase 3: Data Splitting & Scaling
- **Chronological split** - 80% training, 20% testing (no random shuffling to prevent data leakage)
- **StandardScaler** applied to all features for model convergence

### Phase 4: Model Selection
Five diverse models trained and compared:
1. **Linear Regression** - Simple baseline model
2. **Random Forest Regressor** - Ensemble of decision trees
3. **XGBoost Regressor** - Gradient boosting
4. **LSTM (Long Short-Term Memory)** - Deep learning for sequential data
5. **Prophet** - Dedicated time-series forecasting model

### Phase 5: Evaluation Metrics
- **MAE** (Mean Absolute Error) - Interpretable average error
- **RMSE** (Root Mean Squared Error) - Penalizes large errors
- **R² Score** - Proportion of variance explained by the model

---

## 📈 Key Results

### Model Performance Comparison

| Model | MAE | RMSE | R² Score |
|-------|-----|------|----------|
| **Linear Regression** | 156,691.09 | 195,692.08 | **0.2176** |
| Random Forest | 162,756.71 | 202,572.94 | 0.1616 |
| XGBoost | 165,311.24 | 206,007.85 | 0.1329 |
| LSTM | 1,372,876.10 | 1,390,569.39 | -38.4995 |
| Prophet | 180,180.99 | 223,459.03 | -0.0202 |

### 🏆 Best Performing Model
**Linear Regression** achieved the best performance with an **R² Score of 0.2176**, outperforming more complex models like XGBoost and LSTM. This indicates that:
- Carefully engineered features captured most predictable patterns
- Added complexity of ensemble/deep learning models was not justified
- Simpler, more interpretable models can be equally effective

### Key Observations
- ✅ **No Weekend Effect** - Weekday mean (1,374,250.58) vs Weekend mean (1,372,330.85) difference of just -0.1% (p = 0.863)
- ✅ **Complete Data Coverage** - 100% of expected days present (1,796/1,796 days)
- ✅ **Minimal Outliers** - Only 9 outlier days identified (0.50% of data)
- ✅ **Top Features** - Rolling_Mean_7 (correlation: 0.372, importance: 0.231)

### Feature Importance Analysis
| Rank | Feature | Importance |
|------|---------|------------|
| 1 | Rolling_Mean_7 | 0.2310 |
| 2 | Lag_3 | 0.1174 |
| 3 | Lag_1 | 0.1074 |
| 4 | Lag_30 | 0.0794 |
| 5 | Lag_14 | 0.0756 |
| 6 | Lag_7 | 0.0747 |
| 7 | Rolling_Mean_30 | 0.0717 |
| 8 | Rolling_Mean_14 | 0.0683 |
| 9 | Day | 0.0544 |
| 10 | WeekOfYear | 0.0394 |

### Feature Category Importance
- **Lag Features**: 45.5% of total importance
- **Rolling Features**: 37.1% of total importance
- **Time/Calendar Features**: 17.5% of total importance

---

## 🔮 Future Predictions

The Linear Regression model was used to generate sales predictions for the **next 6 months (180 days)** from January 1, 2024 to June 28, 2024.

### Key Insights for Business Planning
- 📊 Sales follow consistent daily patterns with minimal weekend effect
- 📈 Strongest predictor is the 7-day rolling mean (recent trend)
- 📉 No significant seasonality detected (based on low time feature importance)
- 💡 Simpler models are sufficient given current feature set

---

## 📊 Dashboard & Visualizations

An interactive Plotly dashboard was created showing:
- 📈 **Historical Sales Trends** (2019-2023)
- 🔮 **6-Month Future Sales Predictions**
- 📊 **Distribution Analysis** with outlier boundaries
- 🎯 **Weekend vs Weekday Sales Comparison**
- 📈 **Feature Correlation & Importance Visualizations**

### Key Visualizations Included
1. **Sales Range Analysis** - Time series with min/max boundaries
2. **Weekend Effect Analysis** - Day-wise sales patterns
3. **Outlier Analysis** - IQR-based outlier detection
4. **Clean Data Analysis** - After outlier removal
5. **Feature Importance** - Correlation heatmap & RF importance
6. **Monthly Patterns** - Monthly, yearly, and day-of-week averages

---

## 🚀 How to Run This Project in Google Colab

### Option 1: Open in Colab (Recommended)
Click the badge below to open the notebook directly:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/17ToxlxLwMoi2OKtuVPsGl1kVhv_wIZqU)

> **Note:** If the badge doesn't work, make sure the notebook is publicly accessible (Share → "Anyone with the link" → "Viewer").

### Option 2: Manual Setup from GitHub
1. Go to [Google Colab](https://colab.research.google.com/)
2. Click on the **"GitHub"** tab
3. Enter the repository URL:  
   `https://github.com/pontinghayden380-art/Future-Sales-Prediction-6-months-.ipynb`
4. Select the notebook and run all cells

### Option 3: Upload File
1. Download the `.ipynb` file from this repository
2. Go to [Google Colab](https://colab.research.google.com/)
3. Click **"Upload"** and select the file
4. Run all cells sequentially

### Step-by-Step Instructions
1. **Open in Colab** using any of the above methods
2. **Upload the dataset** when prompted (the notebook handles file upload automatically)
3. **Run all cells** sequentially (Runtime → Run all)
4. **View results** - Model comparison, visualizations, and 6-month forecast will be displayed
5. **Download outputs** - All graphs and predictions are automatically saved and downloadable

---

## 📂 Repository Structure
Future-Sales-Prediction-6-months-.ipynb/
├── Future_Sales_Prediction(6_months).ipynb # Complete Jupyter Notebook
├── README.md # Project documentation
├── Final_Report_July_2026.pdf # Detailed project report
├── visualizations/
│ ├── sales_range_analysis.png
│ ├── weekend_effect_analysis.png
│ ├── outlier_analysis.png
│ ├── clean_data_analysis.png
│ ├── before_after_comparison.png
│ ├── monthly_patterns_cleaned.png
│ ├── feature_correlation_analysis.png
│ ├── feature_importance_analysis.png
│ ├── feature_pair_relationships.png
│ └── categorical_feature_analysis.png
└── data/
└── sample_data.csv (if included)

text

---

## 📚 How to Use This Repository

### For Business Stakeholders
- Review the **Executive Summary** in the report for business implications
- Explore the **interactive dashboard** for visual insights
- Understand **forecast limitations** and improvement areas

### For Data Scientists
- Clone the repository and run the notebook in Colab
- Modify **feature engineering** to improve model performance
- Add **external features** (holidays, weather, promotions)
- Try **different aggregation levels** (weekly instead of daily)

### For Students/Researchers
- Use as a **reference implementation** for time-series forecasting
- Study the **methodology** and feature engineering approaches
- Understand **model comparison** and evaluation techniques
- Learn about **time-series best practices** (chronological split, no data leakage)

---

## 🔧 Future Improvements

Based on insights from this project, future work can focus on:

### Feature Enhancement
- ➕ Add **holiday calendars** (Indian festivals, national holidays)
- ➕ Include **weather data** (rainfall, temperature)
- ➕ Integrate **promotion/marketing** campaign data
- ➕ Add **product category-specific** features

### Modeling Improvements
- 🔄 Implement **recursive multi-step forecasting**
- 🎯 Try **ensemble methods** combining multiple models
- 📊 Test **weekly aggregation** instead of daily
- 🧪 Experiment with **ARIMA/SARIMA** models for comparison

### Data Expansion
- 📈 Collect **more historical data** (5+ years)
- 🏪 Include **store-level** data (different locations)
- 🛒 Add **product-level** sales data for granular predictions

### Technical Enhancements
- 🚀 Deploy as **web application** using Flask/Streamlit
- 💾 Implement **database integration** for real-time predictions
- 📱 Create **mobile dashboard** for on-the-go access

---

## 📋 Project Deliverables

### Final Deliverables
1. ✅ **Complete Jupyter Notebook** - All code in one place
2. ✅ **Interactive Dashboard** - Plotly-based sales visualization
3. ✅ **Comprehensive Report** - Detailed methodology and results
4. ✅ **All Visualizations** - 10+ quality PNG images
5. ✅ **6-Month Forecast** - CSV file with daily predictions

### Report Sections
- Abstract
- Introduction
- Project Objectives
- Methodology (5 phases)
- Data Analysis & Results (6 sub-sections)
- Conclusion & Future Work
- Appendices with GitHub & Drive links

---

## 📞 Contact & Support

**Author:** Ankit Jha  

**Project Guide:** Dr. Dipasree Pal  
**Institution:** IDEAS, ISI Kolkata  

**Links:**
- 🔗 GitHub Repository: [https://github.com/pontinghayden380-art/Future-Sales-Prediction-6-months-.ipynb](https://github.com/pontinghayden380-art/Future-Sales-Prediction-6-months-.ipynb)
- 🔗 Colab Notebook: [https://colab.research.google.com/drive/17ToxlxLwMoi2OKtuVPsGl1kVhv_wIZqU](https://colab.research.google.com/drive/17ToxlxLwMoi2OKtuVPsGl1kVhv_wIZqU)

---

## 📜 License

This project is for educational and research purposes. Feel free to use, modify, and distribute with proper attribution.

---












## 🔧 Future Improvements
- Add external features (holidays, weather, promotions)
- Collect more historical data
- Try different aggregation levels (weekly instead of daily)
- Feature engineering with product categories
