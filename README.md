# About this Project
This project was inspired by the BCG (Boston Consulting Group) Virtual Experience on Forage. I took on the role of a data scientist helping an energy provider identify customers most likely to churn.
The challenge was simple on the surface but complex in execution: use customer and pricing data to predict churn and help the client reduce potential losses. The approach combined data cleaning, exploratory analysis, feature engineering, and machine learning—all within a real-world consulting context.

# Problem Statement
The energy provider needed help understanding why customers leave and who is most at risk. With this insight, they could take proactive steps to retain high-value clients through discounts, tailored offers, or improved service.

# The Data
There were two key datasets involved in this project:
Client data included information like activation dates, energy consumption, forecasted usage, and whether or not a customer churned.
Price data provided monthly energy pricing across different tiers (peak, off-peak, fixed, variable) for each client.

The main challenge was dealing with data imbalance, as only a small fraction of customers actually churned.

# My Approach
1. Data Exploration and Cleaning
I started by checking for missing values, correcting data types, and converting date columns. I also handled class imbalance using SMOTE and merged the datasets using customer IDs and contract timelines.

2. Feature Engineering
I created new variables such as contract duration, monthly average usage, recent price fluctuations, discount ratios, margin trends, and user segmentation. These features helped capture behavioral and financial patterns related to churn.

3. Modeling and Evaluation
I trained two models—Random Forest and XGBoost. Both were tested using ROC AUC, classification reports, and precision-recall tradeoffs. I also tuned thresholds to get the best F1 scores.
XGBoost came out slightly ahead and was selected as the final model.

### 📊 Results at a Glance

| Model              | ROC-AUC  | F1 Score | Key Strength                                  |
|-------------------|----------|----------|-----------------------------------------------|
| **Random Forest** | 0.93     | 0.68     | Simplicity and interpretability               |
| **XGBoost**        | **0.94** | **0.70** | Better performance with imbalanced data (SMOTE + scale_pos_weight) |

Both models significantly outperformed a baseline and highlighted clear churn indicators.

# Insights Uncovered
Customers were more likely to churn when they had higher energy prices in recent months, shorter contract durations, or fewer active products. These insights could drive retention campaigns or pricing adjustments.

# Tools and Libraries
Python
Pandas, NumPy, Matplotlib, Seaborn
Scikit-learn
XGBoost
Imbalanced-learn (SMOTE)

# My next steps
I plan to enhance this project by adding:
1. A Streamlit app for interactive churn scoring
2. Feature importance visualizations
3. A Medium article explaining the business case and results
3. Model deployment for real-time prediction simulation
