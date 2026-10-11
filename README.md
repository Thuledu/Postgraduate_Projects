# Linear Regression Analysis - PDAN8411 (Part 1)

## 📌 Project Overview
This project forms part of the Postgraduate Diploma in Data Analytics (PDAN8411).  
The objective was to apply **Linear Regression** to the *Medical Cost Personal Dataset* to predict medical aid charges based on demographic and lifestyle features.

Dataset: [Medical Cost Personal Dataset (Kaggle)](https://www.kaggle.com/datasets/mirichoi0218/insurance)  
Records: 1,338  
Features: Age, Sex, BMI, Children, Smoker, Region  
Target: Charges (continuous variable)

---

## ⚙️ Methodology
1. **Dataset Evaluation**
   - Verified suitability for Linear Regression.
   - Checked assumptions: linearity, homoscedasticity, independence, multicollinearity, normality.

2. **Exploratory Data Analysis (EDA)**
   - No missing values; one duplicate removed.
   - Visualizations: box plots, scatter plots, histograms.
   - Correlation matrix highlighted strong relationships (smoker status, age).

3. **Feature Engineering**
   - One-hot encoding for categorical variables.
   - Standardization of numerical features.

4. **Model Training**
   - Train/test split: 80/20.
   - Applied Linear Regression with default hyperparameters.

5. **Model Evaluation**
   - Metrics: RMSE (~$5,000–$6,000), MAE, R² (~0.81).
   - Diagnostics: residual plots, Q-Q plots, correlation checks.

---

## 📊 Key Findings
- **Smoker status** and **age** are the most influential predictors of medical costs.
- Residuals show near-normal distribution, though outliers affect tails.
- No multicollinearity detected.
- Charges distribution improved after log transformation.

---

## 🚧 Limitations
- Dataset is US-based; regional features (e.g., "northeast") do not align with South African contexts.
- Model requires validation with **local South African data** for accurate application.

---

## ✅ Recommendations
- Map US regions to South African equivalents (urban vs. rural, provinces).
- Collect South African medical aid data for improved accuracy.
- Consider interaction terms or regularization techniques to refine predictions.

---

## 📂 References
- Choi, M. (2018). *Medical Cost Personal Dataset, Kaggle.*
- Kumar, S. (2020). *Linear Regression Tutorial, Kaggle.*
- Fernando, J. (2024). *R-Squared: Definition, Calculation, and Interpretation, Investopedia.*
- GeeksforGeeks (2025). *Linear Regression Formula.*
- Waskom, M. (2024). *Seaborn Tutorials.*

---

## 👤 Author
**Thuledu Maggie Tshabalala**  
Postgraduate Diploma in Data Analytics (PDAN8411)  
GitHub: [vc-online-pdan8411-part1-2025-Thuledu](https://github.com/VCONLINE/vc-online-pdan8411-part1-2025-Thuledu)
