# 📘 Klasifikasi Diagnosis Penyakit (Exasens Dataset)

### 👤 Informasi

* **Nama:** Ardha Ferbian Muqorrobin
* **Repo:** [UAS_Exasens_Classification](https://github.com/asammanis89/UAS_Exasens_Classification)
* **Video:** (https://youtu.be/FN3RWlT5N1Y)

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
├── images/                 # Hasil Visualisasi & Plot Evaluasi
│   ├── Deep_Learning_(MLP).jpg
│   ├── Distribusi_Kelas_Diagnosis.jpg
│   ├── Matriks_Korelasi_Antar_Fitur.jpg
│   ├── TABEL_PERBANDINGAN_MODEL.jpg
│   └── Visual_Sebaran_Umur_Berdasarkan_Diagnosis.jpg
│
├── models/                 # Model yang sudah dilatih (Saved Models)
│   ├── model_exasens_knn.pkl    # Baseline Model
│   ├── model_exasens_rf.pkl     # Random Forest Model
│   └── model_exasens_mlp.h5     # Deep Learning Model
│
├── notebooks/              # Jupyter Notebook eksperimen utama
│   └── UAS_DATASIENCE.ipynb
│
├── Laporan Proyek Machine Learning.pdf
├── requirements.txt        # Daftar library python
└── README.md
```

---

### 3. 📊 Dataset

* **Nama Dataset:** Exasens (Exhaled Breath Condensate)
* **File:** `data/Exasens.csv`
* **Sumber:** [UCI Machine Learning Repository - Exasens](https://archive.ics.uci.edu/dataset/523/exasens)
* **Jumlah Data:** 399 Sampel
* **Tipe Masalah:** Multiclass Classification (4 Kelas)

**Fitur Utama yang Digunakan:**

| Nama Fitur | Deskripsi | Tipe Data |
| :--- | :--- | :--- |
| **Diagnosis** | Label Target (COPD, Asthma, Infected, HC/Healthy) | Categorical |
| **Imaginary Part** | Nilai permitivitas imajiner (sifat dielektrik saliva) | Float |
| **Real Part** | Nilai permitivitas riil (sifat dielektrik saliva) | Float |
| **Age** | Usia pasien | Integer |
| **Gender** | Jenis Kelamin (Dikonversi ke 0/1) | Integer |
| **Smoking** | Status Merokok (1=Ya, 0=Tidak) | Integer |

---

### 4. 🔧 Data Preparation

Langkah-langkah preprocessing yang dilakukan dalam `UAS_DATASIENCE.ipynb`:

1.  **Cleaning:** Menghapus kolom `ID` yang tidak relevan.
2.  **Encoding:** Mengubah label *Diagnosis* dan *Gender* menjadi format numerik (Label Encoding).
3.  **Splitting:** Membagi data menjadi **80% Training** dan **20% Testing** (`random_state=42`).
4.  **Scaling:** Melakukan normalisasi data menggunakan **MinMaxScaler** agar rentang nilai fitur seragam (0-1), yang sangat penting untuk performa model KNN dan Neural Network.

---

### 5. 🤖 Modeling

Saya membangun tiga model dengan pendekatan berbeda:

**Model 1: K-Nearest Neighbors (Baseline)**
* Algoritma berbasis jarak.
* Parameter: `n_neighbors=5`.
* *Keunggulan:* Sederhana dan cepat untuk dataset kecil.

**Model 2: Random Forest (Advanced)**
* Algoritma *Ensemble Learning* (Bagging).
* Parameter: `n_estimators=100`.
* *Keunggulan:* Stabil dan tahan terhadap overfitting.

**Model 3: Deep Learning (MLP)**
* Arsitektur Neural Network (TensorFlow/Keras).
* Layer: 3 Hidden Layers (64, 32, 16 neuron) + Output Layer (Softmax).
* Optimizer: Adam.

---

### 6. 🧪 Evaluation

Berdasarkan hasil pengujian pada data test:

| Model | Accuracy | Training Time (s) | Analisis |
| :--- | :--- | :--- | :--- |
| **KNN (Baseline)** | **70%** | **0.006s** | **Terbaik.** Akurasi tinggi dengan waktu komputasi tercepat. |
| **Random Forest** | **70%** | 0.180s | Akurasi setara KNN, namun waktu training sedikit lebih lama. |
| **Deep Learning** | 60% | 14.16s | Underperformance. Kemungkinan karena jumlah data (399 baris) terlalu sedikit untuk Deep Learning. |

---

### 7. 🏁 Kesimpulan

* **Model Terbaik:** **K-Nearest Neighbors (KNN)** dipilih sebagai model terbaik untuk kasus ini.
* **Alasan:** KNN memberikan akurasi tertinggi (70%) yang setara dengan Random Forest, namun dengan efisiensi waktu yang jauh lebih baik (0.006 detik vs 0.18 detik).
* **Insight:** Untuk dataset medis berukuran kecil seperti Exasens, algoritma klasik (Traditional ML) seringkali mengungguli algoritma Deep Learning yang kompleks.

---

### 8. 🔮 Future Work

* **Data Augmentation:** Menambah jumlah data sampel untuk meningkatkan performa Deep Learning.
* **Hyperparameter Tuning:** Melakukan GridSearch pada Random Forest untuk mencari parameter yang lebih optimal.
* **Advanced Deep Learning:** Mencoba arsitektur CNN 1D jika data dianggap sebagai sinyal.

---

### 9. 🔁 Reproducibility

Untuk menjalankan proyek ini di lokal komputer Anda:

1. **Clone Repository:**
   ```bash
   git clone [https://github.com/asammanis89/UAS_Exasens_Classification.git](https://github.com/asammanis89/UAS_Exasens_Classification.git)
   ```

2. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Jalankan Notebook:**
   Buka `notebooks/UAS_DATASIENCE.ipynb` menggunakan Jupyter Notebook atau VS Code.
