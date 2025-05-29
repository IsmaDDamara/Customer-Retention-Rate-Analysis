# 📊 Customer Retention Rate Analysis

## 📌 Latar Belakang
Dalam bisnis ritel yang kompetitif, **retention rate** menjadi metrik penting untuk menilai keberhasilan strategi pemasaran dan layanan. Mempertahankan pelanggan lama lebih efisien dan menguntungkan dibandingkan menarik pelanggan baru. Namun, banyak bisnis menghadapi penurunan retensi, yang meningkatkan **churn rate** dan menurunkan pendapatan. Karena itu, diperlukan pendekatan berbasis data untuk memahami perilaku pelanggan dan merancang strategi retensi yang efektif.

## 🎯 Tujuan Proyek
Proyek ini bertujuan untuk:

- Menghitung customer retention rate secara periodik berdasarkan data transaksi yang tersedia.
- Mengidentifikasi faktor-faktor penting yang memengaruhi loyalitas dan perilaku pembelian pelanggan.
- Menganalisis cohort pelanggan untuk melihat pola retensi dalam periode waktu tertentu.
- Memberikan insight bisnis strategis untuk meningkatkan retensi pelanggan dan menurunkan churn rate.
- Menyediakan visualisasi interaktif untuk mempermudah pemantauan kinerja retensi pelanggan secara berkala.

## 🧭 Langkah-langkah Analisis
Berikut adalah tahapan analisis yang dilakukan dalam proyek ini:
1. Persiapan & Pembersihan Data
Konversi order_date ke datetime, tambah kolom year_month.
- Hapus data kosong pada customer_id/product_name, dan produk uji (mengandung "test").
 - Tambah kolom order_status (identifikasi pembatalan).
- Normalisasi nilai quantity (harus positif), hapus price negatif.
- Buat kolom amount = quantity × price.
- Standarisasi nama produk via product_code.
- Ubah customer_id jadi string, bersihkan tanda koma.
- Hapus outlier (Z-score) dari quantity dan amount.
2. Transformasi Data Retensi
- Hitung jumlah pesanan per pelanggan per bulan.
- Tentukan bulan pertama transaksi sebagai cohort.
- Hitung selisih bulan dari transaksi ke cohort (period_num).
- Buat pivot cohort (baris: cohort, kolom: bulan ke-n, isi: jumlah pelanggan unik).
3. Perhitungan Retention Rate
- Hitung retention rate = jumlah pelanggan bulan ke-n ÷ jumlah bulan cohort.
- Visualisasi tren retensi & churn per cohort dan agregat.

## 📈 Dashboard
Dashboard interaktif dapat diakses melalui tautan berikut:

👉 [Lihat Dashboard Retail Analysis](https://lookerstudio.google.com/s/n8j-5g6Qxac)

## ▶️ Cara Menjalankan
Clone repositori ini:

```bash
git clone https://github.com/IsmaDDamara/Retail-Sales-Product-Performance-and-Retention-Analysis.git
cd notebook
```

Jalankan analisis:
```bash
jupyter notebook retentionrate_analysis.ipynb
```