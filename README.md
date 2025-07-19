# Telecom Customer Churn Prediction ###

# 1. Business Understanding
Overview
Customer churn (or the loss of customers) is a major challenge for telecom companies like SyriaTel because acquiring new customers is far more expensive than retaining existing ones. High churn rates negatively impact profitability and market share.

This project leverages historical customer data to predict churn, enabling proactive measures to improve retention and customer satisfaction.

Business Problem
- SyriaTel is experiencing customer churn, directly impacting revenue.
- Lack of understanding of churn drivers prevents effective retention strategies.
- Goal: Predict which customers are likely to churn and identify key influencing factors.

Project Objectives
- Predict customer churn using machine learning models.
- Identify important features contributing to churn.
- Provide actionable business recommendations for retention.

# 2. Data Understanding

Dataset: Kaggle - Churn in Telecoms Dataset

- Rows: 3,333
- Target Variable: churn (binary: True = customer left)
- Features: Customer demographics, usage patterns, service plans, and customer service interactions.

Feature Types

- Numeric: Account length, total day/evening/night minutes, charges, calls, etc.
- Categorical: State, Area code, International plan, Voice mail plan.

# 3. Data Preparation
Steps performed:

- Removed irrelevant features (phone number).
- Checked and handled:Duplicates: None, Missing values: None.
- Outlier treatment: Removed points beyond 3 standard deviations.
- Feature correlation: Dropped highly correlated variables (correlation > 0.9).
- Encoding: One-hot encoding applied to categorical features.
- Target transformation: churn mapped to binary (0/1).

# 4. Exploratory Data Analysis (EDA)

Key Insights
- Churn Distribution:
- Only 14.5% of customers churned → highly imbalanced dataset.
- Customer Service Calls: Churned customers often make 4+ service calls, non-churn typically 1–2 calls.
- International Plan:Customers with an international plan show higher churn rates.
- Area Code 415: Shows slightly higher churn percentage compared to others.
- Correlation Analysis:Day/evening/night charges are perfectly correlated with their respective minutes → dropped redundant features.

Visuals
- Churn distribution plots.
- Numeric feature histograms.
- Pairplot showing feature relationships by churn.
- Heatmap for correlations.
- Categorical feature distributions by churn.

# 5. Handling Class Imbalance
Applied SMOTE (Synthetic Minority Oversampling Technique) on training set.

Result: Balanced class distribution (50-50).

# 6. Feature Scaling
Applied StandardScaler to normalize numeric features (important for Logistic Regression and KNN).

# 7. Model Building
Models implemented:
- Logistic Regression (Baseline Model)
- Random Forest Classifier
- Decision Tree Classifier
- K-Nearest Neighbors (KNN) (added for comparison)
- Train-Test Split
- 70% Training, 30% Testing.
- Stratified split to maintain class ratio.

# 8. Model Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1-Score
- ROC Curve & AUC Score
- Confusion Matrix

# 9. Results Summary
- Model	Accuracy	F1-Score	Recall	AUC
- Logistic Regression	0.736	0.386	0.345	0.81
- Random Forest	0.875	0.71	0.67	0.94
- Decision Tree	0.835	0.62	0.58	0.87
- KNN	0.78	0.50	0.46	0.84

✅ Random Forest is the best performing model, achieving:

- Accuracy: 87.5%
- F1-score: 0.71
- AUC: 0.94

# 10. Key Feature Importance (Random Forest)
Top predictors of churn:
- Customer Service Calls
- Total Day Charge
- International Plan (Yes)

# 11. Business Implications
- Customers with frequent service calls are at high churn risk → Improve customer support quality and reduce resolution time.
- High day usage customers may need better value plans → Offer tailored packages.
- Customers with international plans show higher churn → Review pricing or provide loyalty benefits.

# 12. Recommendations
- Implement predictive churn scoring for customers weekly/monthly.
- Proactively engage customers with >3 service calls.
- Offer personalized retention offers to high-risk customers.
- Track A/B tests on retention campaigns to measure impact.

# 13. Next Steps
- Deploy Random Forest model via API for real-time scoring.
- Collect more granular data (customer feedback, payment behavior).
- Experiment with advanced models like XGBoost, LightGBM, Neural Networks.
- Explore threshold tuning to maximize recall (reduce false negatives).

# 14. Project Files
- notebook.ipynb – Complete analysis and modeling.
- README.md – Project summary.
- data/ – Dataset files.
- images/ – Visualization outputs.

# 15. Tools & Libraries
- Python: pandas, numpy, scikit-learn, imbalanced-learn, seaborn, matplotlib, plotly.
- SMOTE for class imbalance.
- itHub for version control.

