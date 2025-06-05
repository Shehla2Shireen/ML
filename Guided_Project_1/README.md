# Global Tech University Admissions Optimizer

## Project Overview
This project aims to develop a decision-support tool to predict admission probabilities for Global Tech University (GTU) applicants and assist in merit scholarship allocation. The challenge is to handle a surge in applications efficiently while balancing accuracy, fairness, and budget constraints.

## Data Description
- Dataset includes 5 admission cycles (2019-2023) exported from Slate CRM.
- Features:
  - Academic signals: GRE, TOEFL, CGPA
  - Subjective ratings: SOP quality, LOR strength
  - Institutional prestige: University rating (1–5)
  - Research indicator: binary (0/1)
- Target variable: Admission probability

## Approach
1. **Exploratory Data Analysis (EDA)**  
   Explored feature distributions, correlations, and data quality.

2. **Modeling**  
   - Baseline: Multiple Linear Regression for interpretability  
   - Decision Tree to model human-reviewer logic and for transparent decision paths  
   - Random Forest for improved accuracy and robustness via ensemble learning  
   - Hyperparameter tuning using `RandomizedSearchCV` for Random Forest and GridSearchCV for Decision Tree  
   - Feature importance analysis to identify top predictive features  
   - Retraining models using only top 5 important features for efficiency and performance comparison  

3. **Multicollinearity Check**  
   - Calculated Variance Inflation Factor (VIF) and correlation matrix  
   - Addressed multicollinearity to improve linear regression model reliability

4. **Evaluation Metrics**  
   - R² (coefficient of determination)  
   - RMSE (root mean squared error)  
   - MAE (mean absolute error)

## Results
- Random Forest achieved the highest test R² (~0.80) and lowest RMSE, outperforming Linear Regression and Decision Tree models.  
- Top features influencing admission decisions included CGPA, GRE Score, TOEFL Score, SOP, and University Rating.  
- Multicollinearity was present among academic signals; addressed to enhance linear model stability.  
- Visualizations (scatter plots of predicted vs actual probabilities) confirmed model accuracy and reliability.

## Insights
- Ensemble models like Random Forest effectively capture nonlinear relationships and improve prediction accuracy.  
- Feature selection reduces model complexity without significantly sacrificing performance, aiding interpretability.  
- Multicollinearity handling is crucial for trustworthy linear regression results.  
- The model can support admissions by flagging high-probability admits and projecting scholarship budgets under constraints.

## Usage
- Load trained models from provided scripts.  
- Input applicant features to obtain admission probability predictions.  
- Use visualizations and model explanations to support admission and scholarship decisions.

## Future Work
- Incorporate fairness and bias assessment across demographic groups.  
- Explore additional data sources for enhanced prediction.  
- Develop user-friendly dashboards for admissions staff.

---
