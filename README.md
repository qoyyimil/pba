# Analisis Sentimen Ulasan Aplikasi Moovit

## 📜 Deskripsi Proyek

Repositori ini mendokumentasikan implementasi *pipeline* Natural Language Processing (NLP) untuk menganalisis sentimen dari ulasan pengguna aplikasi **Moovit** di Google Play Store. Proyek ini bertujuan mengolah data tekstual tidak terstruktur menjadi wawasan yang dapat ditindaklanjuti mengenai persepsi pengguna.

Proyek ini adalah bagian dari tugas mata kuliah **Pemodelan Bahasa Alami (PBA)**.

**Author**: [Qoyyimil](https://github.com/qoyyimil) | 5026221115

---

## 📁 Struktur Proyek

```
.
├── data/
│   ├── moovit_reviews_cleaned.csv
│   └── moovit_reviews_raw.csv
├── notebooks/
│   ├── 1_Scraping_Moovit_Reviews.ipynb
│   ├── 2_Preprocessing_Moovit_Reviews.ipynb
│   ├── 3_EDA_BoW_Regex_Analysis_Moovit.ipynb
│   └── 4_TFIDF_Moovit_Sentiment_Analysis.ipynb
└── README.md
```

---

## 📍 Alur Kerja Proyek: Tahapan & Hasil

Berikut adalah rincian tahapan yang dilakukan dalam setiap *notebook*:

#### 1. `1_Scraping_Moovit_Reviews.ipynb` 📥
   - Mengambil data ulasan dari Google Play Store (`google-play-scraper`).
   - Melakukan verifikasi bahasa awal (`langdetect`).
   - Menyimpan data mentah ke `moovit_reviews_raw.csv`.

#### 2. `2_Preprocessing_Moovit_Reviews.ipynb` 🧹
   - Memuat data mentah.
   - Melakukan pembersihan teks (hapus URL, emoji, tanda baca, angka).
   - Menormalisasi kata menggunakan kamus *custom* (slang, typo, singkatan Bahasa Indonesia).
   - Melakukan Tokenisasi (`nltk`).
   - Melakukan Stopword Removal (NLTK + Sastrawi + *custom list*).
   - Melakukan Stemming (`Sastrawi`).
   - Menghapus kata-kata langka (*rare words*) dan memperbarui *stopwords* secara iteratif.
   - Menyimpan data bersih ke `moovit_reviews_cleaned.csv`.

#### 3. `3_EDA_BoW_Regex_Analysis_Moovit.ipynb` 📊
   - Memuat data bersih.
   - Melakukan Exploratory Data Analysis (EDA):
     - Distribusi Skor (Rating).
     - Jumlah Ulasan per Tahun.
     - Analisis Panjang Ulasan vs. Skor.
     - Visualisasi Word Cloud.
   - Mengimplementasikan Bag of Words (BoW) (`scikit-learn`).
   - Melakukan analisis sentimen sederhana berbasis Regex (kata kunci positif/negatif).

#### 4. `4_TFIDF_Moovit_Sentiment_Analysis.ipynb` 🤖
   - Memuat data bersih.
   - Membuat label sentimen biner (Positif/Negatif) dari skor.
   - Membagi data menjadi set Latih dan Uji (`train_test_split`).
   - Mengimplementasikan TF-IDF (`scikit-learn`) dengan optimasi parameter (`min_df`, `max_df`, `ngram_range`).
   - Melatih dan mengevaluasi beberapa model klasifikasi:
     - Logistic Regression
     - Multinomial Naive Bayes
     - Linear SVC
   - Membandingkan performa model.
   - Menjalankan implementasi TF-IDF manual yang disesuaikan.

---

## 🚀 Tech Stack

<p align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas">
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-learn">
  <img src="https://img.shields.io/badge/NLTK-3776AB?style=for-the-badge&logo=nltk&logoColor=white" alt="NLTK">
  <img src="https://img.shields.io/badge/Seaborn-3776AB?style=for-the-badge&logo=seaborn&logoColor=white" alt="Seaborn">
</p>

---

## ▶️ Panduan Eksekusi

Untuk mereplikasi hasil dari analisis ini, ikuti langkah-langkah berikut:

1.  **Clone Repositori**:
    ```bash
    git clone https://github.com/qoyyimil/pba.git
    cd pba
    ```
2.  **Instalasi Dependensi**:
    Pastikan semua *library* yang tercantum di atas sudah terinstal di lingkungan Python Anda.
    ```bash
    pip install pandas google-play-scraper sastrawi nltk scikit-learn seaborn matplotlib wordcloud emoji langdetect
    ```
3.  **Eksekusi Notebook**:
    Jalankan *notebook* di dalam folder `notebooks/` secara berurutan untuk memastikan alur data yang benar:
    - `1_Scraping_Moovit_Reviews.ipynb`
    - `2_Preprocessing_Moovit_Reviews.ipynb`
    - `3_EDA_BoW_Regex_Analysis_Moovit.ipynb`
    - `4_TFIDF_Moovit_Sentiment_Analysis.ipynb`

---
