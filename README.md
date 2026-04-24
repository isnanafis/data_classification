# 💧 Water Potability Prediction: Analisis Klasifikasi Kualitas Air

Proyek ini berfokus pada pengembangan model *machine learning* untuk memprediksi apakah air layak dikonsumsi atau tidak berdasarkan parameter kualitas air. Proyek ini menggunakan dataset [Water Potability](https://www.kaggle.com/datasets/adityakadiwal/water-potability) dari Kaggle.

## 📌 Deskripsi Proyek
Tujuan utama dari analisis ini adalah membangun sistem deteksi dini (*early warning system*) yang handal dalam menyaring air yang tidak layak konsumsi (Kelas 0). Mengingat pentingnya aspek kesehatan, model ini dioptimalkan untuk meminimalkan risiko air berbahaya lolos sebagai air aman.

## 📊 Kamus Variabel
* **pH:** Tingkat keasaman air (WHO: 6.5 - 8.5).
* **Hardness:** Kandungan kalsium dan magnesium.
* **Solids (TDS):** Total padatan terlarut dalam air.
* **Chloramines & Sulfate:** Kandungan desinfektan dan mineral alami.
* **Conductivity:** Kemampuan air menghantarkan arus listrik.
* **Organic Carbon & Trihalomethanes:** Senyawa organik dan hasil sampingan klorinasi.
* **Turbidity:** Tingkat kekeruhan air.
* **Potability (Target):** 1 (Layak), 0 (Tidak Layak).

## 🛠️ Metodologi & Preprocessing
Data dalam proyek ini memiliki tantangan berupa data kosong (*missing values*) dan banyak pencilan (*outliers*). Langkah penanganannya meliputi:
1. **Imputasi:** Menggunakan `KNNImputer` untuk mengisi data kosong berdasarkan kemiripan pola sampel.
2. **Scaling:** Menggunakan `RobustScaler` untuk menormalisasi fitur agar tahan terhadap pengaruh nilai ekstrem.
3. **Balancing:** Menerapkan teknik `SMOTE` pada data latih untuk menangani ketidakseimbangan kelas target.

## 🚀 Perbandingan Model (Benchmarking)
Eksperimen dilakukan terhadap 7 algoritma untuk mencari daya diskriminasi terbaik (ROC-AUC):
* **Terbaik** `Random Forest` 
* **Kedua** `Neural Network (ANN)` 
* **Model Lain:** XGBoost, SVM, KNN, Decision Tree, dan Logistic Regression.

## 📈 Evaluasi Model Final
Setelah dilakukan *Hyperparameter Tuning*, model Random Forest memberikan performa sebagai berikut:
* **ROC-AUC Score:** **0.67** (Menunjukkan kemampuan pemisahan kelas yang baik).
* **Recall (Kelas 0):** **75%** (Efektif dalam mendeteksi air yang tidak layak konsumsi).



## 💡 Insights
Berdasarkan analisis *Feature Importance*, variabel **Sulfate** dan **pH** merupakan indikator paling krusial dalam menentukan kelayakan air. Temuan ini menyarankan bahwa pemantauan kualitas air secara real-time sebaiknya diprioritaskan pada kedua parameter tersebut.



---
**Dataset:** [Kaggle - Water Potability](https://www.kaggle.com/datasets/adityakadiwal/water-potability)
