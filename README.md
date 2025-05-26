# Laporan Proyek Machine Learning - Evi Afiyatus Solihah

## Domain Proyek

Domain yang dipilih untuk proyek machine learning ini adalah Kesehatan, dengan judul Predictive Analytics: Klasifikasi Obesitas (Underweight, Normal, Overweight, Obese)

# Latar Belakang

Obesitas adalah masalah kesehatan masyarakat yang semakin meningkat secara global dan berkontribusi pada berbagai penyakit kronis seperti diabetes, penyakit jantung, dan hipertensi. Identifikasi dini terhadap kategori obesitas seseorang sangat penting untuk intervensi dan pencegahan yang efektif. Dengan menggunakan data demografi dan karakteristik fisik, proyek ini bertujuan untuk membangun model klasifikasi yang dapat memprediksi kategori obesitas (Underweight, Normal weight, Overweight, Obese) secara akurat. Riset terkait telah menunjukkan bahwa analisis machine learning dapat digunakan untuk mengklasifikasikan status obesitas dengan memanfaatkan berbagai data karakteristik individu (Sitanggang, D. et al., 2022). Proyek ini mengacu pada dataset yang diambil dari Kaggle.

Obesitas adalah masalah kesehatan masyarakat yang semakin meningkat secara global dan berkontribusi pada berbagai penyakit kronis seperti diabetes, penyakit jantung, dan hipertensi. Identifikasi dini terhadap kategori obesitas seseorang sangat penting untuk intervensi dan pencegahan yang efektif, terutama untuk mengurangi beban sistem kesehatan dan meningkatkan kualitas hidup masyarakat. Sayangnya, diagnosis obesitas secara konvensional sering kali memerlukan proses manual dan tidak selalu mempertimbangkan kombinasi berbagai faktor yang saling berkaitan.
Dengan menggunakan data demografi dan karakteristik fisik, proyek ini bertujuan untuk membangun model klasifikasi berbasis machine learning yang dapat memprediksi kategori obesitas (Underweight, Normal weight, Overweight, Obese) secara akurat. Model ini diharapkan dapat menjadi alat bantu yang efisien dan objektif dalam mendukung tenaga medis atau instansi terkait dalam melakukan deteksi dini. Riset terkait telah menunjukkan bahwa analisis machine learning dapat digunakan untuk mengklasifikasikan status obesitas dengan memanfaatkan berbagai data karakteristik individu (Sitanggang, D. et al., 2022). Proyek ini mengacu pada dataset yang diambil dari Kaggle.

## Business Understanding

### Problem Statements

- Bagaimana mengklasifikasikan status obesitas individu berdasarkan data fisik dan aktivitas?
- Bagaimana meningkatkan akurasi prediksi kategori obesitas dengan metode machine learning?

### Goals

- Membangun model klasifikasi untuk mengkategorikan status obesitas dengan akurasi tinggi.
- Mengidentifikasi fitur yang paling berpengaruh dalam prediksi obesitas.

**Rubrik/Kriteria Tambahan (Opsional)**:

- Menambahkan bagian “Solution Statement” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut:

  ### Solution statements

- Menerapkan algoritma klasifikasi seperti Random Forest dan Support Vector Machine.
- Menggunakan evaluasi metrik akurasi, precision, recall, dan F1 score untuk mengukur hasil.

## Data Understanding

Dataset yang digunakan berisi data fisik dan demografi dari individu yang telah diberi label kategori obesitas. Dataset ini dapat diunduh dari UCI Kaggle. Contoh: [Kaggle](https://www.kaggle.com/datasets/mrsimple07/obesity-prediction/).

### Variabel-variabel pada dataset adalah sebagai berikut:

- Age : Usia individu (tahun)
- Gender : Jenis kelamin (Laki-laki/Perempuan)
- Height : Tinggi badan (cm)
- Weight : Berat badan (kg)
- BMI : Indeks Massa Tubuh
- PhysicalActivityLevel : Tingkat aktivitas fisik harian
- ObesityCategory : Kategori obesitas (Underweight, Normal weight, Overweight, Obese)

Selain itu, dilakukan exploratory data analysis untuk memeriksa distribusi data, nilai hilang, outlier, dan korelasi antar fitur. Juga dilakukn visualisasi data

## Data Preparation

Data dibersihkan dengan menghapus baris yang mengandung nilai hilang dan duplikat. Outlier pada fitur numerik diidentifikasi menggunakan boxplot dan dihapus untuk menjaga kualitas data. Variabel kategorikal seperti Gender dan ObesityCategory diubah menjadi variabel numerik menggunakan teknik encoding. Selanjutnya, fitur yang memiliki korelasi tinggi seperti Weight dan BMI direduksi menggunakan Principal Component Analysis (PCA) untuk mengurangi multikolinearitas.

**Rubrik/Kriteria Tambahan (Opsional)**:

- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling

Model klasifikasi yang digunakan adalah Random Forest dan Support Vector Machine (SVM). Kedua model dilatih menggunakan data training dengan parameter default awal. Selanjutnya, dilakukan hyperparameter tuning menggunakan Grid Search untuk mencari kombinasi parameter terbaik, seperti jumlah pohon pada Random Forest dan kernel pada SVM.

Kelebihan Random Forest adalah kemampuannya menangani data yang kompleks dan outlier, sedangkan SVM efektif untuk klasifikasi dengan margin yang jelas. Kelemahan Random Forest adalah kompleksitas komputasi yang tinggi, sedangkan SVM sensitif terhadap pemilihan kernel dan parameter.

**Rubrik/Kriteria Tambahan (Opsional)**:

- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

## Evaluation

- Metrik evaluasi yang digunakan meliputi:
- Akurasi: Proporsi prediksi benar terhadap total data.
- Precision: Ketepatan prediksi positif.
- Recall: Kemampuan menemukan semua kasus positif.
- F1 Score: Harmonik rata-rata precision dan recall.

Hasil evaluasi menunjukkan model Random Forest mencapai akurasi sebesar 92%, precision dan recall yang seimbang, serta F1 score tinggi, menjadikannya pilihan terbaik dibandingkan SVM. Evaluasi ini mengindikasikan model mampu memprediksi kategori obesitas dengan baik, sehingga dapat digunakan sebagai alat bantu dalam deteksi dini risiko obesitas.

Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:

- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**:

- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_

- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.

Setiyani, L., Indahsari, A. N., & Roestam, R. (2023). Analisis Prediksi Level Obesitas Menggunakan Perbandingan Algoritma Machine Learning dan Deep Learning. JTERA (Jurnal Teknol. Rekayasa), 8(1), 139.
