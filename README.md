# Smart Customer Segmentation for Personalized Retail Marketing
## OUR TIM A25-CS284
(M006D5Y1670) - (Rega Ardana)- (Machine Learning)

(M269D5X1545) - (Nyoman Arini Trirahayu)- (Machine Learning) 

(M269D5X1956) - (Widia Saputri)- (Machine Learning)

## 📊 Customer Segmentation & Business Insights Dashboard

Dashboard ini menampilkan analisis lengkap terkait perilaku pelanggan, performa penjualan, serta strategi bisnis yang dapat diterapkan berdasarkan hasil clustering, analisis RFM, dan rekomendasi produk menggunakan algoritma Apriori. Tujuan utama proyek ini adalah membantu bisnis memahami siapa pelanggan mereka, bagaimana mereka berbelanja, dan strategi apa yang paling efektif untuk meningkatkan penjualan dan loyalitas.

## Deployment Dashboard
# 📘 1. Dashboard: Elbow Method & Dataset Overview

Dashboard pertama memberikan gambaran umum dataset dan proses penentuan jumlah cluster optimal.

<img width="990" height="739" alt="Screenshot 2025-12-05 213102" src="https://github.com/user-attachments/assets/e68ec14c-0fe9-4c52-bb82-d78588e23871" />


### 🔹 Distortion Score – Elbow Method
- Model diuji dari k=2 hingga k=9.
- Titik elbow ditemukan pada **k = 4** (nilai optimal untuk clustering).
- Distortion score menurun signifikan sampai k=4, lalu stabil → menunjukkan segmentasi 4 cluster paling representatif.

### 🔹 Ringkasan Data
- **Total Data:** 51.290 baris transaksi  
- **Total Customer:** 796  
- **Total Sales:** 12.642.501,91  
- **Total Profit:** 1.467.457  
- Visualisasi PCA 2D digunakan untuk melihat persebaran cluster setelah reduksi dimensi.

Dashboard ini memastikan segmentasi berbasis data akurat sebelum masuk ke analisis berikutnya.

---

# 📗 2. Dashboard: Customer Cluster Characteristics

Dashboard kedua fokus pada karakterisasi setiap cluster menggunakan RFM (Recency, Frequency, Monetary).

<img width="992" height="742" alt="Screenshot 2025-12-05 213200" src="https://github.com/user-attachments/assets/44b702cf-1ea6-4316-a090-c3af0b89f165" />


### 🔹 Karakteristik 4 Cluster
| Cluster | Karakter Utama | Recency | Frequency | Monetary |
|--------|------------------|---------|-----------|----------|
| **0 – Active Low Spender** | Aktif, namun nilai belanja rendah | Aktif | Rendah | Rendah |
| **1 – High-Frequency Mid Spender** | Sering belanja, nilai sedang | Aktif | Tinggi | Menengah |
| **2 – Dormant Low Buyer** | Jarang belanja, nilai kecil | Tidak aktif | Rendah | Rendah |
| **3 – Premium High-Value Buyer** | Pembeli VIP dengan nilai tinggi | Aktif | Tinggi | Sangat tinggi |

### 🔹 Performa Cluster
- **Cluster 3**: Profit & sales tertinggi, pelanggan premium.
- **Cluster 0**: Jumlah pelanggan terbanyak namun nilai transaksinya kecil.
- **Cluster 2**: Perlu strategi reaktivasi karena hampir tidak aktif.
- **Cluster 1**: Loyal & sering transaksi, kandidat untuk loyalty program.

### 🔹 Visualisasi Tambahan
- Total customer tiap cluster  
- Rata-rata profit per cluster  
- Rata-rata sales per cluster  
- Rata-rata biaya shipping per cluster  

Dashboard ini memetakan prioritas pelanggan dan potensi bisnis.

---

# 📙 3. Dashboard: Customer Insight & RFM Summary

Dashboard ketiga memberikan insight mendalam terkait kualitas pelanggan.

<img width="988" height="738" alt="Screenshot 2025-12-05 213313" src="https://github.com/user-attachments/assets/9945c1e8-8c7c-4acc-b3c9-1ac6a6580bd8" />


### 🔹 Rata-Rata Nilai RFM per Cluster
- **Cluster 3** mendominasi Frequency & Monetary → pelanggan paling berharga.
- **Cluster 2** memiliki Recency tertinggi → paling jarang kembali.
- **Cluster 0 & 1** stabil namun dengan behavior berbeda (low vs mid spender).

### 🔹 PCA Clustering (Advanced)
- Visualisasi memperjelas bahwa 4 cluster terpisah jelas secara pola pembelian.
- Menunjukkan validitas segmentasi KMeans.

### 🔹 Insight Utama
- Cluster high-value kecil tetapi menyumbang pendapatan besar.
- Active low spender berpotensi dinaikkan nilainya dengan promo kecil.
- Dormant buyer harus ditarget dengan strategi comeback.

Dashboard ini menjawab:  
> “Bagaimana kualitas pelanggan dalam setiap cluster?”
---

# 📒 4. Dashboard: Business Performance & Yearly Sales Insights

Dashboard keempat fokus pada performa bisnis secara keseluruhan.

<img width="989" height="740" alt="Screenshot 2025-12-05 213344" src="https://github.com/user-attachments/assets/fdd9c4f1-5e65-4601-a20b-d6b793b7cedd" />


### 🔹 Tren Sales & Profit per Tahun (2012–2015)
- Penjualan terus naik setiap tahun.  
- Profit tertinggi pada **tahun 2015**.  
- Menunjukkan pertumbuhan bisnis positif.

### 🔹 Sales menurut Sub-Category
Kategori dengan kontribusi terbesar:
1. Phones  
2. Copiers  
3. Chairs  
4. Bookcases  
5. Storage  

Insight: produk teknologi & office supplies mendominasi pendapatan.

### 🔹 Ship Mode Analysis
- **Standard Class** mendominasi 59% pengiriman.  
- Same Day hanya 5.3% → cocok untuk strategi upsell berdasarkan urgensi.

Dashboard ini menjawab:  
> “Apa yang paling banyak dijual? Tahun mana paling untung? Bagaimana pola pengiriman?”
---

# 🧠 Apriori Product Recommendations & Cluster Strategies

Selain clustering, sistem juga menghasilkan **rekomendasi produk otomatis** untuk meningkatkan cross-selling.

### 🔹 Top Association Rules
| Bundle | Lift | Confidence | Insight |
|--------|------|------------|---------|
| Art + Furnishings → Binders | 1463 | 0.3089 | Cocok jadi paket workstation |
| Phones + Storage → Binders | 1462 | 0.3086 | Pelanggan perangkat → butuh dokumen |
| Accessories + Binders → Storage | 1442 | 0.2558 | Cocok bundle office organization |

### 🔹 Strategi Setiap Cluster
**Cluster 0:** micro-promo, bundling kebutuhan rutin  
**Cluster 1:** loyalty program, upselling berdasarkan histori  
**Cluster 2:** kampanye reaktivasi, diskon besar  
**Cluster 3:** VIP service, early access, event eksklusif  

---

# 🎯 Kesimpulan Akhir

Keempat dashboard memberikan insight lengkap:
- Penentuan cluster yang optimal  
- Profil dan kualitas tiap cluster  
- Insight perilaku pelanggan  
- Performansi bisnis tahunan  
- Rekomendasi berbasis mesin (Apriori)

Proyek ini dapat digunakan untuk:
- CRM (Customer Relationship Management)  
- Segmentasi pelanggan e-commerce  
- Analisis marketing berbasis data  
- Business decision support  

---
