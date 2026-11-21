# Best-Seller Prediction with Logistic Regression – PDAN8412 (Part 2)

## 📌 Project Overview
This project forms part of the Postgraduate Diploma in Data Analytics (PDAN8412).
The objective was to apply **logistic regression** to Amazon book review data to predict whether a book is likely to be a best-seller, and to evaluate how well review-based features can support that prediction.

Logistic regression was implemented **from scratch in NumPy** (sigmoid, regularised cost function, gradient and mini-batch gradient descent) and compared with scikit-learn's `LogisticRegression`.

Dataset: [Amazon Books Reviews (Kaggle)](https://www.kaggle.com/datasets/mohamedbakhet/amazon-books-reviews) – `Books_rating.csv` and `books_data.csv`
Size: 3,000,000 reviews × 19 columns after merging on book title
Modelling unit: ~212,000 books after aggregating reviews per title
Target: `isBestseller` (1 if a book's review count is above the 75th percentile, otherwise 0)

---

## ⚙️ Methodology
1. **Data Loading & Inspection**
   - Downloaded the dataset via the Kaggle API and merged review and book metadata on `Title`.
   - Checked data types, summary statistics, missing values and duplicates (8,774 duplicate rows identified).

2. **Feature Engineering**
   - Aggregated reviews per book: `review_count`, `avg_score`, `avg_helpful_votes`, `avg_total_votes`, `avg_review_length` and `helpful_ratio`.
   - Missing aggregated values filled with 0.
   - Model features: `avg_score`, `helpful_ratio` and `avg_review_length`, standardised with `StandardScaler`.

3. **Exploratory Data Analysis (EDA)**
   - Histograms showed highly skewed review counts: most books have very few reviews, while a small number (e.g. *The Hobbit*, *Pride and Prejudice*) have over 20,000.
   - Correlation heatmaps and box plots compared features across best-seller and non-best-seller books.

4. **Model Training**
   - Train/test split: 80/20 (169,922 training and 42,481 test books).
   - **From-scratch model:** mini-batch gradient descent with L2 regularisation; the cost curve converged after roughly 50 iterations.
   - **Hyperparameter tuning:** grid search over learning rate (0.001, 0.01, 0.1), iterations (200, 400, 800) and regularisation strength (0.1, 1, 10). Best cost: 0.529.
   - **Benchmark:** scikit-learn `LogisticRegression` (liblinear solver, including C = 5000).

5. **Evaluation**
   - Metrics: accuracy, precision, recall, F1-score, confusion matrix, ROC curve, precision-recall curve and calibration curve.
   - SHAP explainability was explored on a subset of test data.

---

## 📊 Results
| Metric | Value |
|---|---|
| Accuracy (test) | 0.7725 |
| Precision (best-seller class) | 0.00 |
| Recall (best-seller class) | 0.00 |
| F1-score (best-seller class) | 0.00 |
| ROC-AUC (from-scratch model) | 0.50 |

- Test set class split: 77.25% non-best-sellers and 22.75% best-sellers.
- Both the from-scratch and scikit-learn models predicted **every book as a non-best-seller**. The 77% accuracy therefore equals the share of the majority class, and the model did not learn to identify best-sellers.
- By absolute coefficient size, **helpful_ratio** had the largest influence, followed by **avg_score** and **avg_review_length**.

---

## 💡 Key Learnings
- **Accuracy alone is misleading on imbalanced data.** The confusion matrix, recall and ROC-AUC exposed that the model was only predicting the majority class.
- The three review-quality features carry little signal for a label defined by review volume, so a linear model at the default 0.5 threshold cannot separate the classes.
- Building logistic regression from scratch made the effect of the learning rate, regularisation and convergence on the cost function concrete.

---

## 🚧 Limitations
- Strong class imbalance (≈77/23) pushed the model toward the majority class.
- Best-seller status is a proxy based on review count, not actual sales.
- Only three features were used.

---

## ✅ Next Steps
- Handle imbalance with `class_weight='balanced'`, resampling (e.g. SMOTE) or a lower decision threshold.
- Add features such as price, category, publication date and ratings count.
- Compare non-linear models such as Random Forest and XGBoost.

---

## 🛠️ Tools
Python, NumPy, pandas, scikit-learn, Matplotlib, seaborn, SHAP, Jupyter Notebook

---

## 📂 References
- Mohamedbakhet. 2023. *Amazon Books Reviews*, Kaggle.
- Banerjee, P. 2020. *Logistic Regression Classifier Tutorial*, Kaggle.

---

## 👤 Author
**Thuledu Tshabalala**
Postgraduate Diploma in Data Analytics (PDAN8412)
