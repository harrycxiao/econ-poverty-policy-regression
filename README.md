# Poverty and Federal Policy: Statistical Analysis in R

## Overview
This project analyzes how federal monetary policy and government spending relate to the U.S. poverty rate. 

Using historical economic data, I built and compared several regression models to study the effects of:
- Federal funds rate
- Discount rate
- Government spending

The project focuses on statistical modeling, multicollinearity diagnosis, transformations, and bootstrap-based inference.

---

## Data
Variables used:
- Poverty rate
- Federal funds rate
- Discount rate
- Government spending

Data source: U.S. economic indicators compiled into a single dataset.

---

## Methodology

### 1. Simple linear regressions
Tested each predictor separately:
- Poverty vs federal funds rate
- Poverty vs discount rate
- Poverty vs government spending

Findings:
- Interest rates showed statistically significant relationships
- Government spending alone was not significant

---

### 2. Multiple regression
Built a full model with all three predictors.

Result:
- Loss of significance in interest rates
- Evidence of multicollinearity between:
  - Federal funds rate
  - Discount rate

---

### 3. Multicollinearity diagnostics
Regression between the two interest rates showed:
- R² ≈ 0.93
- Strong collinearity

---

### 4. Reduced models
Built two-predictor models:
- Government spending + federal funds rate
- Government spending + discount rate

These performed better than the full model.

---

### 5. Transformations
Applied a log transformation to the federal funds rate:

PRate ~ GovSpend + log(FFrate)

Results:
- Higher R²
- Both predictors statistically significant

---

### 6. Interaction and nonlinear models
Tested second-order and interaction models:
- Added squared terms
- Included interaction between predictors

These improved model fit further.

---

### 7. Randomization and bootstrap inference
Used:
- Randomization tests
- Bootstrap sampling

Results:
- Strong statistical evidence against the null hypothesis
- 95% confidence intervals for coefficients and R²

---

## Key Insight
Interest rate variables show stronger statistical relationships with poverty than government spending alone, but multicollinearity between interest rates must be handled carefully. Transformations and bootstrap inference improved model reliability.

---

## Tools Used
- R
- Linear regression
- Residual diagnostics
- Randomization tests
- Bootstrap confidence intervals

---

## Files
- `poverty_analysis.Rmd` – main analysis file with code, plots, and explanations
- `EconData.csv` – dataset used for regression analysis
- `jsr_paper.pdf` – published research paper based on this analysis

---

## How to Run
Open the R Markdown file in RStudio and run all chunks:

1. Install required packages if needed
2. Open `poverty_analysis.Rmd`
3. Click **Knit** or run all code cells
