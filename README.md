# Analisis Ulasan Aplikasi Moovit Menggunakan Natural Language Processing (NLP)

Repositori ini berisi dokumentasi dan implementasi dari proyek analisis ulasan pengguna aplikasi Moovit. Proyek ini merupakan bagian dari tugas mata kuliah **Pemodelan Bahasa Alami (PBA)** dan mencakup keseluruhan *pipeline* NLP, mulai dari pengumpulan data hingga analisis dan ekstraksi wawasan.

**Author**: [Qoyyimil](https://github.com/qoyyimil)

---

### **Deskripsi Proyek**

Tujuan utama dari proyek ini adalah untuk mengolah data tekstual tidak terstruktur dari ulasan pengguna menjadi wawasan yang dapat ditindaklanjuti. Proses ini melibatkan tiga tahap utama yang diuraikan di bawah ini, masing-masing terdapat dalam *notebook* Jupyter yang terpisah.

---

### **Pipeline Proyek: Tahapan & Hasil**

| Tahap | Notebook | Deskripsi Utama | Output Utama |
| :---: | :--- | :--- | :--- |
| **1** | `1_Scraping_Moovit_Reviews.ipynb` | Mengambil data mentah dari Google Play Store. | `moovit_reviews_raw.csv` |
| **2** | `2_Preprocessing_Moovit_Reviews.ipynb`| Membersihkan dan menormalisasi teks ulasan. | `moovit_reviews_cleaned.csv` |
| **3** | `3_EDA_BoW_Regex_Analysis_Moovit.ipynb`| Melakukan EDA, BoW, dan analisis sentimen. | Wawasan & Visualisasi |

---

### 🚀 Tech Stack

<p align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas">
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-learn">
  <img src="https://img.shields.io/badge/NLTK-3776AB?style=for-the-badge&logo=nltk&logoColor=white" alt="NLTK">
  <img src="https://img.shields.io/badge/Seaborn-3776AB?style=for-the-badge&logo=seaborn&logoColor=white" alt="Seaborn">
</p>

---

### **Panduan Eksekusi**

Untuk mereplikasi hasil dari analisis ini, ikuti langkah-langkah berikut:

1.  **Clone Repositori**:
    ```bash
    git clone https://github.com/qoyyimil/pba.git
    cd pba
    ```
2.  **Instalasi Dependensi**:
    Pastikan semua *library* yang tercantum di atas sudah terinstal di lingkungan Python Anda.
    ```bash
    pip install pandas google-play-scraper sastrawi nltk scikit-learn seaborn matplotlib wordcloud emoji
    ```
3.  **Eksekusi Notebook**:
    Jalankan *notebook* secara berurutan untuk memastikan alur data yang benar:
    -   `1_Scraping_Moovit_Reviews.ipynb`
    -   `2_Preprocessing_Moovit_Reviews.ipynb`
    -   `3_EDA_BoW_Regex_Analysis_Moovit.ipynb`
