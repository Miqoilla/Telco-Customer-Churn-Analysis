# 📡 Telco Customer Churn Analysis & Prediction

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Library](https://img.shields.io/badge/Library-Scikit--Learn%20%7C%20XGBoost%20%7C%20Pandas-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📋 Project Overview
Customer churn (berhenti berlangganan) adalah masalah kritis dalam industri telekomunikasi yang berdampak langsung pada pendapatan perusahaan. Proyek ini bertujuan untuk membangun model **Machine Learning** yang mampu memprediksi pelanggan yang berpotensi melakukan churn, sehingga perusahaan dapat mengambil langkah retensi yang proaktif.

Pendekatan ini menggunakan algoritma **XGBoost** yang dikombinasikan dengan teknik **SMOTE** untuk menangani ketidakseimbangan data (*imbalanced class*), menghasilkan model dengan sensitivitas (*Recall*) yang tinggi dalam mendeteksi risiko churn.

## 📊 Dataset
Dataset yang digunakan adalah **Telco Customer Churn** yang diperoleh dari [Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn).
- **Total Data:** 7.043 baris.
- **Fitur:** 21 kolom (termasuk demografis, layanan, dan informasi akun).
- **Target:** `Churn` (Yes/No).

## 🛠️ Tech Stack
- **Language:** Python
- **Data Manipulation:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Machine Learning:** Scikit-Learn, XGBoost, Imbalanced-learn (SMOTE)
- **Environment:** Google Colab / Jupyter Notebook

## 🔍 Key Workflow & Methodology
1.  **Data Preprocessing:**
    - Handling missing values pada `TotalCharges` dengan imputasi median.
    - Encoding variabel kategorikal (Label Encoding & One-Hot Encoding).
    - Feature Scaling menggunakan `StandardScaler`.
2.  **Handling Imbalance:**
    - Menerapkan **SMOTE (Synthetic Minority Over-sampling Technique)** untuk menyeimbangkan kelas target dan meningkatkan performa prediksi pada kelas minoritas.
3.  **Feature Selection:**
    - Menggunakan **Mutual Information** untuk memilih 15 fitur paling relevan (Top features: *Contract, Tenure, MonthlyCharges*).
4.  **Modeling & Evaluation:**
    - Komparasi algoritma: Logistic Regression, Random Forest, dan XGBoost.
    - Evaluasi menggunakan metrik: **Recall**, **F1-Score**, dan **ROC-AUC**.

## 📈 Model Performance
Berdasarkan hasil eksperimen, model **XGBoost + SMOTE** memberikan performa terbaik:

| Metric | Score | Interpretasi |
| :--- | :--- | :--- |
| **Recall (Churn)** | **High** | Model sangat sensitif mendeteksi pelanggan yang akan pergi (meminimalisir False Negative). |
| **ROC-AUC** | **High** | Kemampuan separabilitas kelas yang sangat baik. |

> *Catatan: Detail angka akurasi dan visualisasi Confusion Matrix dapat dilihat di dalam Notebook.*

## 📂 Repository Structure

├── 📄 Customer_Churn_Analysis.ipynb # Notebook kode lengkap ├── 📄 model_churn_xgboost.pkl # Model yang sudah dilatih (siap deploy) ├── 📄 WA_Fn-UseC_-Telco-Customer-Churn.csv # Dataset (opsional) └── 📄 README.md # Dokumentasi proyek

## 🚀 How to Run
1.  Clone repository ini:
    ```bash
    git clone [https://github.com/username-anda/Telco-Customer-Churn-Analysis.git](https://github.com/username-anda/Telco-Customer-Churn-Analysis.git)
    ```
2.  Instal library yang dibutuhkan:
    ```bash
    pip install pandas numpy scikit-learn xgboost imbalanced-learn matplotlib seaborn
    ```
3.  Jalankan file notebook `Customer_Churn_Analysis.ipynb` menggunakan Jupyter atau Google Colab.

## 💡 Business Insights
- **Kontrak Bulanan:** Pelanggan dengan kontrak *Month-to-month* memiliki risiko churn tertinggi. Disarankan untuk menawarkan insentif agar beralih ke kontrak tahunan.
- **Metode Pembayaran:** Pengguna *Electronic Check* cenderung lebih mudah berpindah.
- **Layanan Fiber Optic:** Terdapat tingkat churn tinggi pada pengguna Fiber Optic, mengindikasikan perlunya evaluasi kualitas layanan atau harga.

---
**Author:** Muhammad Daffa Miqoilla  
**University:** Universitas Amikom Yogyakarta
