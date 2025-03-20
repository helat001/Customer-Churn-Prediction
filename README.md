# Customer Churn Prediction Analysis


## Project Overview
This project analyzes customer churn patterns using exploratory data analysis, machine learning (XGBoost), and Tableau visualizations. We identify key drivers of churn and provide actionable business recommendations to improve customer retention.

**Key Findings**:
- 27% churn rate with significant class imbalance
- Tenure and contract type are strongest churn predictors
- High monthly charges correlate with churn risk
- SHAP values reveal interpretable feature impacts

## 📂 Repository Structure
.
├── data/
│ ├── telco_churn.csv # Raw dataset
│ └── cleaned_churn_data.csv # Processed data
├── notebooks/
│ └── churn_analysis.ipynb # Jupyter notebook with full analysis
├── images/
│ ├── churn_distribution.png # Class distribution (Fig 1)
│ ├── tenure_vs_churn.png # Tenure vs churn boxplot (Fig 2)
│ ├── correlation_matrix.png # Feature correlations (Fig 3)
│ ├── shap_summary.png # SHAP values plot (Fig 5)
│ └── Tableau_*.png # Tableau visualizations
├── tableau/
│ └── Customer_Churn.twbx # Tableau workbook
└── videos/
└── walkthrough.mp4 # Screen recording & voice memo

## 🔍 Analysis Highlights

### 1. Churn Distribution
![Churn Distribution](images/churn_distribution.png)
- Imbalanced dataset: 27% churn (1) vs 73% non-churn (0)
- Key consideration: Use F1-score/AUC instead of accuracy
- Mitigation: Class weighting during model training

### 2. Tenure vs Churn
![Tenure Analysis](images/tenure_vs_churn.png)
- Median tenure: 10mo (churned) vs 40mo (retained)
- Critical period: First 12 months
- Recommendation: Enhanced onboarding program

### 3. Feature Correlations
![Correlation Matrix](images/correlation_matrix.png)
- Strong correlations: 
  - Tenure ↔ TotalCharges (0.83)
  - Contract type → Churn (+0.4)
- Multicollinearity handled via feature selection

### 4. Model Insights (XGBoost + SHAP)
![SHAP Values](images/shap_summary.png)
**Top Predictors**:
1. Contract type (month-to-month → +churn)
2. Tenure (short → +churn)
3. Monthly charges (high → +churn)

**Interpretation**:
- Red points (right): Increase churn probability
- Blue points (left): Decrease churn probability

## 🎯 Business Recommendations
1. **Contract Incentives**
   - Offer discounts for 1/2-year contracts
   - Auto-renewal benefits

2. **High-Risk Customer Program**
   - Target customers with:
     - Month-to-month contracts
     - <12mo tenure
     - Above-average monthly charges

3. **Service Improvements**
   - Bundle security/tech support
   - Fiber optic service audit
   - Auto-pay incentives ($5/month discount)

4. **Proactive Retention**
   - 30/60/90-day check-ins
   - Predictive churn scoring
   - Personalized retention offers

## 📊 Tableau Visualizations
| Churn Distribution | Key Drivers | Tenure Analysis |
|--------------------|-------------|-----------------|
| ![Tableau1](images/Tableau%20Churn%20Distribution%20(Screenshot).png) | ![Tableau2](images/Tableau%20Key%20Drivers%20of%20Churn(Screenshot).png) | ![Tableau3](images/Tableau%20Tenure%20vs%20Churn(Screenshot).png) |

## 🎥 Video Walkthrough
[Screen Recording & Voice Memo](videos/walkthrough.mp4) demonstrating:
- Data exploration process
- Model training workflow
- Tableau dashboard features
- Key findings walkthrough
