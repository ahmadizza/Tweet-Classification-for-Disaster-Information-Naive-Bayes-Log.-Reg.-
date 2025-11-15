# Tweet-Classification-for-Disaster-Information-Naive-Bayes-Log.-Reg.-



# 🌀 Tweet Classification for Disaster Information  
_Natural Language Processing Project – Naive Bayes & Logistic Regression_ 

Proyek ini dibuat untuk tujuan akademik (UTS NLP) dan dapat digunakan untuk pembelajaran.

## 📌 Deskripsi Proyek  
Twitter sering menjadi sumber utama informasi saat bencana terjadi. Namun, tidak semua tweet yang mengandung kata seperti *"ablaze"* atau *"fire"* benar-benar menggambarkan bencana.  
Contoh:  
- 🔥 "The concert was ablaze!" → **bukan bencana**  
- 🔥 "The entire forest is ablaze." → **bencana**  

Proyek ini bertujuan membangun model **Naive Bayes** dan **Logistic Regression** untuk mengklasifikasikan apakah sebuah tweet benar-benar berisi informasi bencana atau tidak.  

---

## 📂 Dataset  
- Sumber: [Kaggle – Real or Not? Disaster Tweets](https://www.kaggle.com/competitions/nlp-getting-started)  
- Jumlah data: 10.876 tweet berbahasa Inggris  
  - 7.613 data train (digunakan dalam penelitian)  
  - 3.263 data test (tidak digunakan karena tidak memiliki label)  

Label:  
- **1** → Tweet tentang bencana nyata  
- **0** → Tweet tidak terkait bencana  

---

## 🔎 Metodologi  
1. **Exploratory Data Analysis (EDA)** – distribusi tweet, panjang teks, kata yang sering muncul  
2. **Preprocessing** – lowercase, hapus URL/angka/tanda baca, stopwords removal, lemmatization, tokenisasi  
3. **Vectorization** – TF-IDF dengan `ngram_range=(1,2)` dan `max_features=10.000`  
4. **Feature Selection** – Chi-Square (SelectKBest, top 3000 features)  
5. **Modeling** – Naive Bayes & Logistic Regression dengan GridSearchCV (5-fold CV)  
6. **Evaluation** – Confusion Matrix, Precision, Recall, F1-Score, Accuracy  
7. **Interpretability** – Analisis kesalahan klasifikasi, POS Tagging, Named Entity Recognition (NER)  

---

## 📊 Hasil  
| Model                | Precision | Recall | F1-Score | Accuracy |
|-----------------------|-----------|--------|----------|----------|
| Logistic Regression   | 0.84      | 0.83   | 0.83     | 83.7%    |
| Naive Bayes           | 0.86      | 0.85   | 0.86     | **85.9%** |  

- Naive Bayes lebih unggul dibanding Logistic Regression pada seluruh metrik evaluasi.  
- Kedua model terbukti efektif untuk klasifikasi teks singkat seperti tweet.  

---

## 💡 Insight  
- **Preprocessing** sangat krusial untuk mengurangi noise dalam teks sosial media.  
- **Naive Bayes** menunjukkan performa yang baik pada teks pendek karena asumsi independensi antar fitur.  
- **Logistic Regression** lebih stabil pada data dengan distribusi fitur yang seimbang.  
- **NER dan POS Tagging** memberikan insight tambahan tentang lokasi, waktu, dan organisasi yang sering muncul pada tweet bencana.  

---

## 🚀 Cara Menjalankan  
1. Clone repository ini  
   ```bash
   git clone https://github.com/username/tweet-disaster-classification.git
   cd tweet-disaster-classification
