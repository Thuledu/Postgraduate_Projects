# Sentiment Classification with LSTM-RNN

## 📌 Project Overview
This project applies **Natural Language Processing (NLP)** techniques using a **Recurrent Neural Network (RNN) with Long Short-Term Memory (LSTM)** units to classify sentiment in consumer food reviews.  
Dataset: [Amazon Fine Food Reviews](https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews) (~568,000 entries).  
Objective: Predict whether a review expresses **positive** or **negative** sentiment.

---

## ⚙️ Methodology
1. **Data Wrangling**
   - Filtered reviews to binary sentiment (positive vs. negative).
   - Applied text cleaning: lowercasing, punctuation removal, HTML tag removal.
   - Tokenization and stopword removal.
   - Sequence padding to ensure uniform input length.

2. **Exploratory Data Analysis (EDA)**
   - Identified class imbalance (majority positive reviews).
   - Visualized distributions with word clouds and histograms.
   - Assessed average text length and feature diversity.

3. **Model Development**
   - Built an LSTM-based RNN using TensorFlow/Keras.
   - Incorporated dropout layers (0.2–0.5) to reduce overfitting.
   - Trained with 5–15 epochs, using class weights to address imbalance.

4. **Evaluation**
   - Metrics: Accuracy, Precision, Recall, F1-score.
   - Confusion matrix analysis revealed challenges with sarcastic/ambiguous texts.
   - Target performance: ~90–92% accuracy, precision, and recall.

---

## 📊 Key Findings
- **Word order matters**: Phrases like *“not great”* vs. *“great product”* highlight the need for sequential models.  
- **Age of reviews and imbalance**: Positive reviews dominate (~63.9% score 5).  
- **LSTM advantage**: Captures long-term dependencies better than simple RNNs, improving sentiment classification accuracy.  

---

## 🚧 Limitations
- Imbalanced dataset skewed toward positive reviews.  
- Sarcasm and nuanced language reduce precision.  
- Requires further tuning and semantic embeddings for improvement.  

---

## ✅ Recommendations
- Integrate **GloVe embeddings** for richer semantic representation.  
- Apply **SMOTE** or resampling techniques to balance classes.  
- Experiment with alternative architectures (e.g., GRU, Transformer-based models).  
- Deploy model for real-time sentiment monitoring in e-commerce platforms.  

---

## 👤 Author
**Thuledu Tshabalala**  
Postgraduate Diploma in Data Analytics (PDAN8412)  
GitHub: [vc-online-pdan8412-part-one-Thuledu](https://github.com/VCONLINE/pdan8412-part-one-Thuledu)
