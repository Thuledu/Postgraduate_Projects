# Lung Cancer Risk Prediction - PDAN8411 (Part 2)

## 📌 Project Overview
This project is part of the Postgraduate Diploma in Data Analytics (PDAN8411).  
The objective was to build a **classification model** to predict lung cancer risk using the *Lung Cancer Dataset* from Kaggle.  

Dataset: 284 patient records, 15 features (demographics + risk factors), binary target (Lung_Cancer: YES/NO).  
Client: Prominent medical aid scheme in South Africa.  
GitHub: [vc-online-pdan8411-part2-2025-Thuledu](https://github.com/VCONLINE/vc-online-pdan8411-part2-2025-Thuledu)

---

## ⚙️ Methodology
1. **Data Cleaning**
   - Removed 33 duplicate records → final dataset: 276 rows × 16 columns.
   - No missing/null values.
   - One-hot encoding for categorical variables.
   - Target mapped: NO → 0, YES → 1.

2. **Exploratory Data Analysis (EDA)**
   - Class imbalance: 86% YES vs 14% NO.
   - Age distribution: peak around 60 years, realistic range 50–80.
   - Correlation heatmap showed no multicollinearity.

3. **Feature Engineering**
   - Selected features based on importance ranking.
   - Top predictors: Age, Allergy, Alcohol Consumption, Yellow Fingers, Peer Pressure.

4. **Model Training**
   - Compared Random Forest vs KNN.
   - Random Forest chosen (Accuracy: 100% on training, 87.5% on test).
   - Train/test split: 80/20, stratified.

5. **Evaluation Metrics**
   - Accuracy: **0.875**
   - Precision: **0.878**
   - Recall: **0.977**
   - F1 Score: **0.925**
   - AUC-ROC: **0.984**

---

## 📊 Key Findings
- **Age** and **smoking-related features** are the strongest predictors of lung cancer risk.  
- High recall (97.7%) ensures minimal false negatives, critical for medical diagnostics.  
- Confusion matrix shows strong classification ability with very few misclassifications.  

---

## 🚧 Limitations
- Small dataset size (276 records) limits generalizability.  
- Class imbalance may bias predictions toward the majority class.  
- Dataset is Kaggle-based; requires validation with **local South African medical data**.  

---

## ✅ Recommendations
- Apply **SMOTE** or other resampling techniques for class imbalance.  
- Collect larger, diverse datasets for improved robustness.  
- Explore hyperparameter tuning (e.g., n_estimators, max_depth).  
- Compare with Gradient Boosting or SVM models.  
- Adjust classification threshold to further improve recall.  

---

## 📂 References
- Kaggle (mysarahmadbhat, 2023) – Lung Cancer Dataset  
- WHO (2020) – Global Lung Cancer Statistics  
- Scikit-learn, Imbalanced-learn, Seaborn, Matplotlib  

---

## 👤 Author
**Thuledu M. Tshabalala**  
Postgraduate Diploma in Data Analytics (PDAN8411)  
GitHub: [vc-online-pdan8411-part2-2025-Thuledu](https://github.com/VCONLINE/vc-online-pdan8411-part2-2025-Thuledu)
