# Tweet Classification for Disaster Information

*Natural Language Processing Project – Naive Bayes & Logistic Regression*

This project was developed for academic purposes (NLP midterm) and can be used as a learning resource.

## Project Description

Twitter is often a primary source of real-time information during disasters. However, not all tweets containing words such as “ablaze” or “fire” actually refer to real disaster events.

Examples:

* "The concert was ablaze!" → Not a disaster
* "The entire forest is ablaze." → Disaster

This project aims to build **Naive Bayes** and **Logistic Regression** models to classify whether a tweet truly contains disaster-related information.

---

## Dataset

* Source: Kaggle – *Real or Not? Disaster Tweets*
* Total data: 10,876 English tweets

  * 7,613 training data (used in the analysis)
  * 3,263 test data (not used because labels are unavailable)

Labels:

* **1** → Tweet references a real disaster
* **0** → Tweet does not reference a disaster

---

## Methodology

1. **Exploratory Data Analysis (EDA)** – tweet distribution, text length, frequent words
2. **Preprocessing** – lowercase, removing URLs, numbers, punctuation; stopword removal; lemmatization; tokenization
3. **Vectorization** – TF-IDF with `ngram_range=(1,2)` and `max_features=10,000`
4. **Feature Selection** – Chi-Square (SelectKBest, top 3,000 features)
5. **Modeling** – Naive Bayes and Logistic Regression with GridSearchCV (5-fold cross-validation)
6. **Evaluation** – confusion matrix, precision, recall, F1-score, accuracy
7. **Interpretability** – error analysis, POS tagging, Named Entity Recognition (NER)

---

## Results

| Model               | Precision | Recall | F1-Score | Accuracy  |
| ------------------- | --------- | ------ | -------- | --------- |
| Logistic Regression | 0.84      | 0.83   | 0.83     | 83.7%     |
| Naive Bayes         | 0.86      | 0.85   | 0.86     | **85.9%** |

* Naive Bayes outperforms Logistic Regression on all evaluation metrics.
* Both models perform well for short-text classification tasks such as tweets.

---

## Insights

* Preprocessing is crucial to reduce noise commonly found in social media text.
* Naive Bayes performs strongly on short, sparse text due to its independence assumptions.
* Logistic Regression is more stable on balanced feature distributions.
* POS tagging and NER help identify recurring locations, times, and organizations mentioned in disaster-related tweets.

---

## How to Run

1. Clone the repository

   ```bash
   git clone https://github.com/username/tweet-disaster-classification.git
   cd tweet-disaster-classification
   ```
