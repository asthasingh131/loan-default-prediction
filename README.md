# Loan Default Prediction

Built a machine learning model to predict which borrowers are likely 
to default, helping lenders catch high-risk cases early before they 
turn into losses.

## Problem Statement
MSME lenders lose significant revenue due to undetected loan defaults. 
This project predicts high risk borrowers 60-90 days before they default, 
enabling early intervention and revenue protection.

## Dataset
- **Source:** Give Me Some Credit — Kaggle
- **Size:** 149,986 borrower records, 11 features
- **Target:** SeriousDlqin2yrs (1 = Defaulted, 0 = Not Defaulted)

## Tools Used
- Python — Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, XGBoost
- SQL — SQLite for business query analysis
- Jupyter Notebook — end to end project workflow

## Key EDA Findings
- Only 6.68% borrowers defaulted — highly imbalanced dataset
- Defaulters had 11.7x more late payments than non defaulters
- Youngest borrowers (18-30) default at 3.87x rate of oldest (60+)
- Late payment history is the single strongest default predictor

## Feature Engineering
Created 4 new business driven features:
- debt_burden — total financial stress score
- income_per_person — income after family obligations
- credit_utilization — aggressiveness of credit usage
- is_young — binary flag for high risk age group

## ML Model Results

| Model | AUC Score |
|-------|-----------|
| Logistic Regression | 0.648 |
| Random Forest | 0.836 |
| XGBoost | 0.850 ✅ Champion |

## Business Impact
- Model correctly identified 395 high risk borrowers in test set
- Projected revenue saved: ₹8.29 Crores
- High Risk borrowers default at 44.93% — 16.5x higher than Low Risk
- 2,941 borrowers flagged as immediately high risk (48.76% default rate)

## Risk Tier System
| Risk Tier | Borrowers | Default Rate |
|-----------|-----------|--------------|
| Low Risk | 119,625 | 2.73% |
| Medium Risk | 23,183 | 15.25% |
| High Risk | 7,178 | 44.93% |

## SQL Business Insights
- 2,941 borrowers flagged as immediately high risk (48.76% default rate)
- Risk tier system created: Low / Medium / High
- Full financial profile comparison of defaulters vs non defaulters

## Future Improvements
- Apply SMOTE to handle class imbalance and improve recall
- Deploy model as a Streamlit web application
- Integrate bureau data for richer feature set
