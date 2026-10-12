# Best-Seller Prediction with Logistic Regression

## 📌 Project Overview
This project applies **Logistic Regression** to the **Amazon Kindle Books Dataset 2023** to predict whether a book is likely to be a best seller.  
The goal was to evaluate dataset suitability, engineer meaningful features, and iteratively refine the model to improve accuracy and address data limitations.

---

## ⚙️ Methodology
1. **Data Evaluation & Cleaning**
   - Dataset: ~3,000,000 rows × 19 columns.
   - Handled missing values using median imputation.
   - One-hot and ordinal encoding applied to categorical variables.
   - Removed duplicates and ensured all predictors were numeric/boolean.

2. **Exploratory Data Analysis (EDA)**
   - Histograms revealed skewed distributions (few books dominate reviews).
   - Correlation heatmaps highlighted strong predictors (review count, average score).
   - Boxplots identified outliers and imbalances.

3. **Feature Engineering**
   - Aggregated features per book: review_count, avg_score, helpful_ratio, avg_review_length.
   - Feature importance analysis showed **helpful_ratio**, **avg_score**, and **avg_review_length** as top predictors.

4. **Model Training**
   - Logistic Regression baseline model trained with L2 regularization.
   - Train/test split: 80/20, stratified.
   - Hyperparameter tuning (alpha, iterations, lambda) via grid search.
   - Compared Logistic Regression, Random Forest, and XGBoost.

5. **Evaluation**
   - Metrics: Accuracy, Precision, Recall, F1-score, ROC-AUC.
   - Logistic Regression baseline achieved ~77% accuracy.
   - XGBoost outperformed with ROC-AUC = **0.92** and F1-score = **0.88**.
   - Calibration curves confirmed well-calibrated probability outputs.

---

## 📊 Key Findings
- Logistic Regression provided a strong baseline but struggled with minority class imbalance.  
- XGBoost emerged as the best model, balancing accuracy, recall, and interpretability.  
- Features like **helpful_ratio** and **average score** are strong indicators of bestseller potential.  

---

## 🚧 Limitations
- Logistic Regression assumes linearity in log-odds, limiting performance with complex interactions.  
- Dataset imbalance reduced recall for true bestsellers.  
- Reliance on review-based features may introduce bias toward popular genres.  

---

## ✅ Recommendations
- Use Logistic Regression or Naive Bayes for quick sentiment classification.  
- Apply Random Forests or Boosting methods to capture non-linearities.  
- Incorporate collaborative filtering for personalized recommendations.  
- Collect localized datasets for improved generalization.  
- Explore hybrid models combining logistic regression with deep learning.  

---

## 👤 Author
**Thuledu M. Tshabalala**  
Postgraduate Diploma in Data Analytics (PDAN8412)  
GitHub: [pdan8412-part-two-Thuledu](https://github.com/VCONLINE/pdan8412-part-two-Thuledu)
