# Linear Regression Analysis: US Health Insurance Cost Prediction in R

## Overview
This project applies linear regression to predict insurance charges based on demographic and medical data. The dataset includes variables such as age, BMI, number of children, smoking status, and region. The goal is to analyze key factors influencing insurance costs.

## Methodology
- Data Cleaning: Handling missing values and checking for outliers.
- Exploratory Data Analysis (EDA): Visualizing distributions and correlations.
- Feature Engineering: Transforming categorical variables for regression.
- Model Training: Using `lm()` in R to build a linear regression model.
- Evaluation: Assessing model performance using R-squared and RMSE.

## Results
Key findings indicate that smokers, particularly those with obesity, experience the highest
insurance costs, with age playing a significant role in increasing charges. The final model
explained approximately 85% of the variance in insurance charges (Adjusted R2 ≈ 0.86), confirming
the strong influence of these risk factors.
### **Key Coefficients**
- **Intercept**: The baseline charge for the reference group (non-smokers) when age is zero is estimated at -2085.008. While not practical, this value sets a baseline for the model.
- **Non-obese smoker**: Associated with an increase in charges of approximately $13,588 over non-smokers, adjusting for age.
- **Obese smoker**: Smokers who are obese incur about $32,643 more in charges than non-smokers, indicating a significant impact of combined smoking and obesity on health costs.
- **Age effects**:
  - **Non-smokers**: Each additional year of age increases charges by approximately $267.
  - **Non-obese smokers**: Each year of age adds about $261 to charges, slightly less than non-smokers.
  - **Obese smokers**: Each year of age results in an approximate $281 increase in charges, the highest among the groups.

### **Model Fit**
- **Residual standard error**: 4565 on 1331 degrees of freedom.
- **Multiple R-squared**: 0.8584; **Adjusted R-squared**: 0.8579.
- The model explains approximately **85.84%** of the variance in insurance charges, indicating excellent model fit.
- **F-statistic**: 1614 on 5 and 1331 DF, p-value < 2.2e-16.
- The overall model is statistically significant, demonstrating strong explanatory power.

### **Statistical Significance**
- All predictors have **p-values < 2.2e-16**, affirming the robustness of the findings.

### **Assumptions Checking**
- **Residuals vs Fitted**: No clear patterns indicate the absence of non-linearity, and variance appears relatively consistent (homoscedasticity).
- **Q-Q Plot**: Residuals mostly follow a normal distribution, though some deviations suggest mild outliers.
- **Scale-Location Plot**: Shows relatively constant spread, supporting the assumption of equal variance.
- **Residuals vs Leverage**: A few high-leverage points suggest potential influential observations that may warrant further investigation.

## Project Structure
Insurance_Linear_Regression/
│── README.md               # Project documentation
│── Insurance_LR.Rmd        # Main R Markdown analysis
│── report/                 # Rendered PDF report
│   ├── insurance_LR.pdf
│── data/                   # Sample dataset 

## How to Run
1. Clone the repository:
```
git clone https://github.com/aidanpmitchell/Insurance_Linear_Regression.git
cd Insurance_Linear_Regression
```
2. Open **Insurance_LR.Rmd** in RStudio
3. Install required dependencies
```
install.packages(c("readr", "kableExtra", "dplyr", "ggplot2", "MASS", "gridExtra", "see", "performance"))
```
4. Run the analysis by knitting the R Markdown file to a pdf

## Dependencies
This project uses the following R packages:
- readr (reading/writing data files)
- kableExtra (enhance table formatting for better readability)
- dplyr (provides functions for data manipulation and transformation)
- ggplot2 (create visualizations and plots)
- MASS (provides support for statistical functions and linear regression analysis)
- gridExtra (allows combining multiple plots into a single visualization)
- see (supports graphical diagnostics for model evaluation)
- performance (assists in checking model performance and assumptions)

## View the Report
View the full report: 