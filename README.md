<p align="center">
  <img src="Images\image.png" alt="Customer Churn Infographic" width="700"/>
</p>

# Telecom Churn Prediction  

Predicting customer churn for SyriaTel using machine learning and providing actionable business insights to improve retention strategies.

**Author:** [Judah Odida](https://github.com/jodida01)
---

## Table of Contents
- [1. Business Understanding](#1-business-understanding)  
- [2. Data Understanding](#2-data-understanding)  
- [3. Data Preparation](#3-data-preparation)  
- [4. Exploratory Data Analysis (EDA)](#4-exploratory-data-analysis-eda)  
- [5. Feature Engineering](#5-feature-engineering)  
- [6. Modeling](#6-modeling)  
- [7. Model Evaluation](#7-model-evaluation)  
- [8. Business Insights](#8-business-insights)  
- [9. Recommended Actions](#9-recommended-actions)  
- [10. How to Run](#10-how-to-run)  

---

## 1. Business Understanding
Customer churn is a major challenge for telecom companies because **acquiring new customers costs more than retaining existing ones**.  
This project predicts churn and identifies **key factors influencing churn** to help SyriaTel **implement proactive retention strategies**.

**Problem Statement:**
- SyriaTel is experiencing **high customer churn**, impacting revenue.
- Lack of insights into churn drivers prevents effective retention.
- Goal: **Predict customers likely to churn** and identify actionable factors.

**Objectives:**
- Build **machine learning models** to predict churn.
- Identify **top churn drivers** for strategic interventions.
- Recommend **data-driven business actions**.

**Key KPI:**
- Focus on **Recall > Precision**, because **False Negatives (missed churners) are more costly**.

---

## 2. Data Understanding
- Dataset: [Kaggle – Churn in Telecom Dataset](https://www.kaggle.com/datasets/becksddf/churn-in-telecoms-dataset)  
- Records: **3,333 customers**  
- Features: **Numeric & Categorical** (usage stats, plans, calls, churn)  

---

## 3. Data Preparation
Steps:
- Removed duplicates & irrelevant columns (e.g., phone number).
- Handled missing values (none found).
- Encoded categorical features using **One-Hot Encoding**.
- Scaled numeric features using **StandardScaler**.
- Handled class imbalance using **SMOTE** (oversampling minority class).

---

## 4. Exploratory Data Analysis (EDA)
Key findings:
- **14.5% churn rate** → Imbalanced dataset.
- **Churners make more customer service calls**.
- **International Plan customers churn more**.
- High correlation between `minutes` and `charges` → dropped redundant features.

**Visuals:**
- Distribution plots
- Correlation heatmap
- Pairplots for churn patterns  
*(See notebook for detailed visuals)*  

---

## 5. Feature Engineering
- Removed highly correlated features (r > 0.9).
- Created dummy variables for categorical features.
- Converted churn column into binary (0 = No Churn, 1 = Churn).

---

## 6. Modeling
Models implemented:
- **Logistic Regression** (Baseline)
- **Random Forest Classifier** (Best performance)
- **Decision Tree Classifier**

---

## 7. Model Evaluation
| Model               | Accuracy | Precision | Recall | F1    | ROC-AUC |
|----------------------|----------|-----------|--------|-------|---------|
| Logistic Regression  | 0.86     | 0.47      | 0.32   | 0.38  | 0.79    |
| Random Forest       | **0.91** | 0.54      | **0.64** | **0.59** | **0.88** |
| Decision Tree       | 0.89     | 0.52      | 0.61   | 0.56  | 0.84    |

**Best Model:**  **Random Forest**  
- Highest ROC-AUC (0.88)
- Best recall for catching churners  

---

## 8. Business Insights
- **Top churn drivers**:
  1. Customer service calls (more calls = dissatisfaction)
  2. International plan (high churn rate)
  3. High usage (total day minutes)

- **Actionable patterns**:
  - Customers with multiple service calls are at **high churn risk**.
  - International plan pricing or service issues likely causing churn.

---

## 9. Recommended Actions
 **Immediate Actions:**
- Prioritize retention for customers with **>3 service calls**.
- Review **international plan pricing & quality**.
- Offer **loyalty perks** for high-usage customers.

 **KPIs to Track:**
- **Churn Rate** (target ↓ by 10%)
- **Customer Service Call Volume** (track dissatisfaction)
- **Retention Campaign ROI**
- **Customer Lifetime Value (CLV)**

##  How to Run

1. **Clone the repository:**
   ```bash
   git clone https://github.com/jodida01/Telecom-Churn-Prediction.git
   cd Telecom-Churn-Prediction

2. Install dependencies:
    ```
    pip install -r requirements.txt

3. Run the notebook:
    ```
    jupyter notebook churn.ipynb

# License

This project is licensed under the MIT License