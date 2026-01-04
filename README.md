# 📊 Employee Attrition Analytics & Predictive Limitations Study

This repository contains an end-to-end HR analytics project focused on understanding employee attrition patterns, extracting business insights, and evaluating the limitations of predictive machine learning models when key organizational drivers are missing.

The project demonstrates **real-world data science thinking**, including data cleaning, SQL analytics, advanced EDA, visualization, and honest evaluation of machine learning performance.

---

## 🔍 Table of Contents

- [📁 Project Overview](#-project-overview)  
- [📦 Folder Structure](#-folder-structure)  
- [🛠 Tech Stack](#-tech-stack)  
- [📊 Dataset](#-dataset)  
- [📌 Key Features & Engineering](#-key-features--engineering)  
- [📈 Exploration & Insights](#-exploration--insights)  
- [🤖 Machine Learning Models](#-machine-learning-models)  
- [🧠 Limitations & Analysis](#-limitations--analysis)  
- [📌 Business Recommendations](#-business-recommendations)  
- [📁 How to Run](#-how-to-run)  
- [📄 Authors / Acknowledgements](#-authors--acknowledgements)  

---

## 📁 Project Overview

Employee attrition (voluntary or involuntary) is a major concern for organizations. Identifying patterns and predicting which employees may leave provides valuable insight for HR strategy.

This project aims to:
1. Clean and preprocess a real-world messy HR dataset  
2. Explore attrition patterns through SQL and visual analysis  
3. Evaluate if machine learning models can predict attrition  
4. Understand why models succeed or fail  
5. Provide actionable business recommendations

> **Important Note:** This project highlights that *sometimes predictive models do not perform well because the available data lacks key causal factors*. Knowing when not to use machine learning is as important as knowing how to use it.

---

## 📦 Folder Structure

```
employee-attrition-analytics/
│
├── data/
│ ├── raw/
│ │ └── Messy_HR_Dataset_Detailed.csv
│ └── processed/
│ └── hr_cleaned.csv
│
├── models/
│ ├── logistic_regression.pkl
│ ├── random_forest.pkl
│ └── scaler.pkl
│
├── sql/
│ └── hr_analytics.db
│
├── notebooks/
│ └── employee_attrition_analysis.ipynb
│
├── README.md
├── requirements.txt
├── .gitignore
└── LICENSE
```

---

## 🛠 Tech Stack

- **Programming:** Python  
- **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, SciPy, Scikit-Learn, SQLite  
- **Database:** SQLite  
- **Environment:** Jupyter Notebook / Colab

---

## 📊 Dataset

The original dataset (`Messy_HR_Dataset_Detailed.csv`) contains 3,150 rows and 39 features including employee personal details, job data, training information, and engagement scores.

After cleaning and deduplication, the final dataset contains **3,000 unique employee records**.

Key columns include:
- StartDate, ExitDate (dates of hire/exit)  
- Engagement Score, Satisfaction Score, Work-Life Balance  
- Training Type, Training Cost, Training Duration  
- Employee Rating

---

## 📌 Key Features & Engineering

This project performs:
- Date formatting & logical checks  
- Deduplication with latest survey records  
- Tenure calculation (active vs exited)  
- Composite engagement metric (`engagement_proxy`)  
- Age imputation and missing flag  
- Binning tenure into human-friendly buckets  
- Outlier clipping (1st–99th percentile)

---

## 📈 Exploration & Insights

### SQL Analytics

Using `hr_analytics.db`, SQL queries reveal:

- **Attrition rates are high across all engagement levels**, suggesting engagement alone cannot predict turnover.
- **Training cost and type** show similar investment but internal training slightly correlates with better performance.
- **Production and Sales departments** show elevated attrition among high-performing employees.

### Visual Analysis

Visualizations include:
- Attrition rate by engagement
- Attrition distribution by department
- Training cost vs performance
- Tenure distribution

These figures provide interpretable business insights beyond raw metrics.

---

## 🤖 Machine Learning Models

Two models were trained using clean numeric features:

| Model               | ROC-AUC |
|--------------------|---------|
| Logistic Regression | ~0.49   |
| Random Forest       | ~0.48   |

Despite strong preprocessing, **models perform nearly at random**, indicating weak predictive power from available features.

---

## 🧠 Limitations & Analysis

This project underscores that:
- **Machine learning is limited by data quality and content**
- Key HR drivers (salary, raises, promotions, manager effectiveness) were missing
- Numeric engagement and training metrics alone do not sufficiently explain attrition

This outcome is *a valuable finding*, demonstrating critical evaluation rather than just model building.

---

## 📌 Business Recommendations

**1. Target Production Department Retention**  
High performer exits in operations should be addressed through focused HR strategies.

**2. Audit Training ROI**  
Training cost alone does not guarantee retention — evaluate outcomes over spending.

**3. Collect richer HR signals**  
In future work, incorporate managerial ratings, compensation history, and promotion timelines to improve insight and prediction.

---

## 📁 How to Run

### 1. Clone Repository

```
git clone https://github.com/<your-username>/employee-attrition-analytics.git
cd employee-attrition-analytics
```

### 2. Install Dependencies

```
pip install -r requirements.txt
```

### 3. Open Notebook

```
notebooks/employee_attrition_analysis.ipynb
```





