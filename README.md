# 📘 Klasifikasi Diagnosis Penyakit (Exasens Dataset)

### 👤 Informasi

* **Nama:** Ardha Ferbian Muqorrobin
* **Repo:** [UAS_Exasens_Classification](https://github.com/asammanis89/UAS_Exasens_Classification)
* **Video:** [Link Video Demo/Penjelasan Anda Di Sini]

---

### 1. 🎯 Ringkasan Proyek

Proyek ini bertujuan untuk menyelesaikan permasalahan klasifikasi medis menggunakan dataset **Exasens** (Exhaled Breath Condensate). Proyek ini mencakup tahapan data preparation, visualisasi, hingga pembangunan model machine learning untuk memprediksi diagnosis penyakit pernapasan.

**Aktivitas Utama:**
* Melakukan *data cleaning* dan preprocessing pada dataset Exasens.
* Membangun 3 model perbandingan: **KNN (Baseline)**, **Random Forest (Advanced)**, dan **Deep Learning (MLP)**.
* Melakukan evaluasi performa berdasarkan akurasi dan waktu komputasi.

---

### 2. 📄 Problem & Goals

**Problem Statements:**
* Diagnosis penyakit pernapasan (seperti COPD dan Asma) seringkali membutuhkan waktu lama dan peralatan mahal.
* Diperlukan metode komputasi yang efisien untuk membantu diagnosis awal berdasarkan sampel *saliva* (air liur) dan data demografis.

**Goals:**
* Mengembangkan model machine learning yang dapat mengklasifikasikan 4 kondisi pasien: *COPD, Asthma, Infected, dan Healthy*.
* Menganalisis fitur mana yang paling berpengaruh terhadap diagnosis.
* Menemukan model dengan keseimbangan terbaik antara akurasi dan efisiensi waktu.

---

### 📁 Struktur Folder

```text
UAS_Exasens_Classification/
│
├── data/
│   └── Exasens.csv         # Dataset utama (399 baris data pasien)
│
├── images/                 # Hasil Visualisasi & Plot
│   ├── Deep_Learning_(MLP).jpg
│   ├── Distribusi_Kelas_Diagnosis.jpg
│   ├── Matriks_Korelasi_Antar_Fitur.jpg
│   ├── TABEL_PERBANDINGAN_MODEL.jpg
│   └── Visual_Sebaran_Umur_Berdasarkan_Diagnosis.jpg
│
├── models/                 # Model yang sudah dilatih
│   ├── model_exasens_knn.pkl
│   ├── model_exasens_rf.pkl
│   └── model_exasens_mlp.h5
│
├── notebooks/
│   └── UAS_DATASIENCE.ipynb
│
├── Laporan Proyek Machine Learning.md
├── requirements.txt
└── README.md
