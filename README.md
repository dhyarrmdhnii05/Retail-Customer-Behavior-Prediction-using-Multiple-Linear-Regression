# Retail Customer Behavior Prediction: Linear Regression Analysis 📊🛒

Proyek ini bertujuan untuk menganalisis perilaku pelanggan dan memprediksi rata-rata nilai transaksi (`Average_Transaction_Amount`) pada data retail menggunakan algoritma **Linear Regression**. Proyek ini disusun sebagai tugas besar untuk mata kuliah Kecerdasan Buatan (AI).

## 📋 Ringkasan Proyek
Dataset yang digunakan berasal dari **DQLab** yang berisi riwayat transaksi pelanggan. Fokus utama penelitian ini adalah memahami hubungan antara frekuensi transaksi (`Count_Transaction`) dan waktu transaksi pertama (`First_Transaction`) terhadap nilai rata-rata pengeluaran pelanggan.

* **Dataset Source:** [DQLab Retail Data](https://storage.googleapis.com/dqlab-dataset/data_retail.csv)
* **Key Findings:** Penambahan variabel `First_Transaction` secara signifikan meningkatkan performa model dari yang awalnya lemah menjadi sangat kuat ($R^2 = 0.814$).

## 🛠️ Tech Stack
* **Language:** Python
* **Libraries:** * `Pandas` (Data Manipulation)
    * `Matplotlib` (Data Visualization)
    * `Scikit-Learn` (Machine Learning Modeling)
    * `Statsmodels` (Statistical OLS Summary)

## 🚀 Metodologi Pelatihan Model

### 1. Simple Linear Regression
Menggunakan satu variabel penjelas (`Count_Transaction`) untuk memprediksi `Average_Transaction_Amount`.
* **Slope (b1):** 271.33
* **Intercept (b0):** 1,369,983.14
* **Interpretasi:** Setiap kenaikan 1 transaksi diprediksi meningkatkan nilai rata-rata transaksi sebesar 271.33 unit.

### 2. Multiple Linear Regression (Optimization)
Model dikembangkan dengan menambahkan variabel `First_Transaction`.
* **Persamaan Regresi:**
    $$Y = 271.33(X_1) + 0.05(X_2) + 1,369,983.1$$
* **Kecocokan Model:** **Adjusted R-Squared sebesar 0.814**, artinya model mampu menjelaskan 81.4% variasi data pengeluaran pelanggan.

## 📈 Hasil Evaluasi Statistik
<img width="580" height="318" alt="image" src="https://github.com/user-attachments/assets/41a182ee-2154-4ae8-9925-6da2ae70f650" />

Model divalidasi menggunakan metode **Ordinary Least Squares (OLS)** dengan hasil sebagai berikut:
* **P-Value Count_Transaction:** 0.049 (< 0.05) → Signifikan secara statistik.
* **P-Value First_Transaction:** < 0.05 → Signifikan secara statistik.
* **R-Squared:** Menunjukkan tingkat akurasi prediksi yang tinggi setelah optimasi variabel.

## 🧮 Perhitungan Manual vs Python
Proyek ini juga memvalidasi hasil komputasi Python dengan perhitungan manual untuk memastikan akurasi rumus regresi:

| Count_Transaction (X) | Perhitungan Manual | Hasil Prediksi Model |
| :--- | :--- | :--- |
| 20 | 1,369,983.14 + (271.33 × 20) | 1,375,409.74 |
| 50 | 1,369,983.14 + (271.33 × 50) | 1,383,549.64 |
| 100 | 1,369,983.14 + (271.33 × 100) | 1,397,116.14 |

## 💡 Kesimpulan
Meskipun jumlah transaksi berpengaruh, waktu transaksi pertama pelanggan memiliki peran krusial dalam menentukan pola pengeluaran. Model regresi ini kini siap digunakan untuk memprediksi pengeluaran pelanggan di masa depan berdasarkan profil loyalitas mereka.
