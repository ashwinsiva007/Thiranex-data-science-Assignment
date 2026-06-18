# 🚀 Thiranex Data Science Internship — Assignments Portfolio

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-1.x-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.x-11557C?style=for-the-badge&logo=matplotlib&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-0.13.x-4C72B0?style=for-the-badge)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Google Colab](https://img.shields.io/badge/Google_Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)

**Author:** Ashwin S &nbsp;|&nbsp; **Internship:** Thiranex Data Science Internship &nbsp;|&nbsp; **Assignments:** 4

</div>

---

## 📌 Overview

This repository contains all **four data science assignments** completed as part of the **Thiranex Data Science Internship**. Each assignment covers a distinct and progressively advanced area of data science — from data cleaning and exploratory analysis to machine learning and predictive modeling. All work was done using **Python** in **Google Colab / Jupyter Notebooks**.

---

## 📂 Repository Structure

```
Thiranex-data-science-Assignment/
│
├── 📁 Assignment 1/          ← Data Cleaning & EDA (Titanic Dataset)
│   ├── Dataclean_Pro_01.ipynb
│   ├── Titanic-Dataset.csv
│   └── titanic_dashboard.png
│
├── 📁 Assignment 2/          ← Machine Learning Prediction (Titanic Survival)
│   └── ML_prediction_pro_2.ipynb
│
├── 📁 Assignment 3/          ← EDA on Hotel Booking Demand
│   ├── Assignment_EDA_pro3.ipynb
│   └── hotel_bookings.csv
│
├── 📁 Assignment 4/          ← Retail Sales Forecasting (Walmart)
│   ├── Sales_predict_pro4.ipynb
│   ├── train.csv
│   ├── test.csv
│   ├── features.csv
│   ├── stores.csv
│   └── sales_forecasting_banner.jpg
│
└── README.md
```

---

## 📘 Assignment 1 — Data Cleaning & Exploratory Data Analysis (Titanic)

### 🎯 Objective
Perform **data cleaning** and **basic EDA** on the classic Titanic dataset to understand the structure, handle missing values, and uncover initial patterns.

### 📦 Dataset
- **File:** `Titanic-Dataset.csv`
- **Rows:** 891 passengers
- **Columns:** 12 features (PassengerId, Survived, Pclass, Name, Sex, Age, SibSp, Parch, Ticket, Fare, Cabin, Embarked)

### 🔧 Steps Performed

| Step | Description |
|------|-------------|
| 📥 Load Data | Loaded the Titanic CSV using Pandas |
| 🔍 Missing Value Detection | Identified 177 missing `Age`, 687 missing `Cabin`, 2 missing `Embarked` values |
| 🧹 Data Cleaning | Filled numeric columns with **mean**, dropped duplicates |
| 📊 Descriptive Statistics | Computed mean, std, min, max, percentiles for all numeric columns |
| 📈 Visualizations | Age Distribution histogram, Survival Count bar chart, Correlation Heatmap |

### 📊 Key Visualizations
- **Age Distribution** — KDE histogram to visualize passenger age spread (mean age ≈ 29.7 years)
- **Survival Count** — Bar chart showing ~62% did not survive (0=No, 1=Yes)
- **Correlation Heatmap** — Revealed relationships between Pclass, Fare, Survived, and other features

### 🛠️ Libraries Used
`pandas` · `matplotlib` · `seaborn`

---

## 📗 Assignment 2 — Machine Learning Prediction (Titanic Survival)

### 🎯 Objective
Build a **supervised machine learning model** (Decision Tree Classifier) to predict whether a passenger survived the Titanic disaster based on their features.

### 📦 Dataset
- Same Titanic dataset (891 rows, 12 columns)

### 🔧 Steps Performed

| Step | Description |
|------|-------------|
| 📥 Load Data | Loaded Titanic-Dataset.csv into a Pandas DataFrame |
| 🧹 Preprocessing | Filled missing `Age` with **median**, `Embarked` with **mode**, dropped `Cabin` column |
| 🔢 Feature Encoding | Encoded `Sex` (male → 0, female → 1), `Embarked` (S → 0, C → 1, Q → 2) |
| 🎯 Feature Selection | Selected features: `Pclass`, `Sex`, `Age`, `Fare`, `SibSp`, `Parch` |
| ✂️ Train-Test Split | 80% training / 20% testing (`random_state=42`) |
| 🌳 Model Training | Trained a `DecisionTreeClassifier` from scikit-learn |
| 📏 Model Evaluation | Accuracy Score + Confusion Matrix (with ConfusionMatrixDisplay) |

### 🧠 Model Architecture
```
Input Features: Pclass, Sex, Age, Fare, SibSp, Parch (6 features)
Model: DecisionTreeClassifier (scikit-learn)
Train Split: 80% (712 samples)
Test Split:  20% (179 samples)
```

### 🛠️ Libraries Used
`pandas` · `numpy` · `matplotlib` · `scikit-learn` (DecisionTreeClassifier, train_test_split, accuracy_score, confusion_matrix)

---

## 📙 Assignment 3 — Exploratory Data Analysis on Hotel Booking Demand

### 🎯 Objective
Perform a **comprehensive EDA** on a real-world hotel bookings dataset to uncover booking patterns, cancellation trends, seasonal demand, and customer behavior insights.

### 📦 Dataset
- **File:** `hotel_bookings.csv`
- **Rows:** 66,478 booking records
- **Columns:** 32 features
- **Hotels:** Resort Hotel & City Hotel
- **Time Period:** 2015–2017

### 🏨 Dataset Features

| Category | Features |
|----------|----------|
| Hotel Info | `hotel`, `reservation_status`, `deposit_type` |
| Booking Details | `lead_time`, `arrival_date_year/month/day`, `stays_in_weekend_nights`, `stays_in_week_nights` |
| Guest Info | `adults`, `children`, `babies`, `customer_type`, `country` |
| Financials | `adr` (Average Daily Rate), `required_car_parking_spaces` |
| Booking Channel | `market_segment`, `distribution_channel`, `agent`, `company` |
| Outcome | `is_canceled`, `reservation_status_date` |

### 🔧 Steps Performed

| Step | Description |
|------|-------------|
| 📥 Load Data | Loaded `hotel_bookings.csv` with 66,478 rows × 32 columns |
| 🔍 Data Inspection | `.shape()`, `.info()`, `.describe(include='all')` for full profiling |
| 📊 Distribution Analysis | Examined cancellation rates (47.8%), lead times, ADR, stay durations |
| 📅 Seasonal Trends | Identified **August** as the peak booking month |
| 🌍 Country Analysis | Analyzed guest countries and booking origins |
| 📈 EDA Visualizations | Multiple plots using Matplotlib and Seaborn (`whitegrid` style) |

### 📊 Key Insights
- **~47.8%** of all bookings were cancelled
- **Resort Hotels** dominate the dataset (40,060 out of 66,478 records)
- **August** is the busiest month (7,714 bookings)
- Average Daily Rate (ADR) ≈ **$96.33**, with outliers up to $5,400
- Most customers are **Transient** type (49,965 records)
- Average lead time is **104 days** (how far in advance bookings are made)

### 🛠️ Libraries Used
`pandas` · `numpy` · `matplotlib` · `seaborn`

---

## 📕 Assignment 4 — Retail Sales Forecasting (Walmart Dataset)

### 🎯 Objective
Build a **Random Forest Regression model** to forecast **weekly retail sales** for Walmart stores using historical sales data, store features, and economic indicators.

### 📦 Datasets (Multi-table)

| File | Description | Shape |
|------|-------------|-------|
| `train.csv` | Historical weekly sales per store & department | 421,570 × 5 |
| `features.csv` | Economic indicators per store & date | 8,190 × 12 |
| `stores.csv` | Store metadata (type, size) | 45 × 3 |
| `test.csv` | Test data for predictions | — |

### 📐 Feature Details

**train.csv:**
- `Store`, `Dept`, `Date`, `Weekly_Sales`, `IsHoliday`

**features.csv:**
- `Temperature`, `Fuel_Price`, `MarkDown1-5`, `CPI`, `Unemployment`, `IsHoliday`

**stores.csv:**
- `Store`, `Type` (A/B/C), `Size` (sq. ft.)

### 🔧 Steps Performed

| Step | Description |
|------|-------------|
| 📥 Load Data | Loaded all three datasets (train, features, stores) |
| 🔗 Data Merging | Merged train ← features on `Store`, `Date`, `IsHoliday` then merged ← stores on `Store` |
| 🧹 Preprocessing | Handled missing values in MarkDown columns, feature engineering |
| 📊 EDA | Visualized weekly sales distributions, seasonal trends, holiday impact |
| 🌲 Model Training | Trained `RandomForestRegressor` from scikit-learn |
| 📏 Model Evaluation | MAE, RMSE, and R² Score metrics |
| 📈 Visualization | Actual vs. Predicted sales plots |

### 🧠 Model Architecture
```
Algorithm:  Random Forest Regressor (scikit-learn)
Target:     Weekly_Sales
Features:   Store, Dept, Temperature, Fuel_Price, MarkDown1-5, 
            CPI, Unemployment, IsHoliday, Type, Size
Evaluation: MAE · RMSE · R² Score
```

### 📊 Key Insights
- 45 Walmart stores across types A, B, and C
- Store sizes range from **34,875 to 205,863 sq. ft.**
- Training data spans 421,570 rows from **Feb 2010 onward**
- **Holiday weeks** show significantly higher sales spikes
- MarkDown promotions are key drivers of sales during peak periods

### 🛠️ Libraries Used
`pandas` · `numpy` · `matplotlib` · `seaborn` · `scikit-learn` (RandomForestRegressor, train_test_split, MAE, RMSE, R²)

---

## 🧰 Tech Stack & Tools

| Tool | Purpose |
|------|---------|
| 🐍 Python 3.10+ | Core programming language |
| 📓 Google Colab | Cloud-based Jupyter notebook environment |
| 🐼 Pandas | Data manipulation and analysis |
| 🔢 NumPy | Numerical computing |
| 📊 Matplotlib | Data visualization |
| 🌊 Seaborn | Statistical data visualization |
| 🤖 Scikit-learn | Machine learning (classification & regression) |

---

## 📈 Skills Demonstrated

```
✅ Data Loading & Inspection           ✅ Missing Value Treatment
✅ Data Cleaning & Preprocessing       ✅ Feature Engineering & Encoding
✅ Exploratory Data Analysis (EDA)     ✅ Statistical Summaries
✅ Data Visualization                   ✅ Correlation Analysis
✅ Supervised ML — Classification       ✅ Supervised ML — Regression
✅ Model Evaluation (Accuracy, MAE,     ✅ Multi-dataset Merging
   RMSE, R², Confusion Matrix)         ✅ Real-world Dataset Handling
```

---

## 🚀 Getting Started

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### Run Locally
```bash
# Clone this repository
git clone https://github.com/ashwinsiva007/Thiranex-data-science-Assignment.git
cd Thiranex-data-science-Assignment

# Open any assignment notebook
jupyter notebook "Assignment 1/Dataclean_Pro_01.ipynb"
```

### Open in Google Colab
Click the notebook `.ipynb` file in this repo → GitHub renders it → Use **"Open in Colab"** button.

---

## 👤 About

**Ashwin S** — Data Science Intern at **Thiranex**

Completed 4 progressive assignments covering the full data science pipeline from raw data to predictive models.

---

<div align="center">

⭐ **If you find this repository useful, please star it!** ⭐

Made with ❤️ during the Thiranex Data Science Internship

</div>
