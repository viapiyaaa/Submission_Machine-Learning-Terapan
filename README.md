# Laporan Proyek Machine Learning - Evi Afiyatus Solihah

## Domain Proyek

Domain yang dipilih untuk proyek machine learning ini adalah Kesehatan, dengan judul Predictive Analytics: Klasifikasi Level Obesitas (Underweight, Normal, Overweight, Obese)

# Latar Belakang

Obesitas telah mengalami peningkatan yang signifikan dalam sepuluh tahun terakhir dan menjadi salah satu isu utama dalam bidang kesehatan masyarakat, baik secara global maupun di Indonesia (Aini, Khasanah, Ristyawan, & Diniati, 2024). Kondisi ini berkontribusi terhadap berbagai penyakit kronis, seperti diabetes, penyakit jantung, dan hipertensi. Obesitas merupakan kondisi kelebihan berat badan yang berdampak negatif terhadap kesehatan, dan dipengaruhi oleh berbagai faktor, termasuk kondisi fisik seperti tinggi badan, berat badan, dan Indeks Massa Tubuh (IMT), serta faktor lainnya seperti jenis kelamin dan tingkat aktivitas fisik  (Setiyani, Indahsari, & Roestam, 2023). Deteksi dini terhadap kategori obesitas sangat penting untuk mendukung upaya intervensi dan pencegahan yang efektif. Dengan memanfaatkan data demografis dan karakteristik fisik, proyek ini bertujuan untuk membangun model klasifikasi yang mampu memprediksi kategori obesitas—Underweight, Normal weight, Overweight, dan Obese—secara akurat. Penelitian sebelumnya menunjukkan bahwa pendekatan machine learning dapat digunakan secara efektif untuk mengklasifikasikan status obesitas berdasarkan data karakteristik individu (Sitanggang & Sherly, 2022). Dalam proyek ini, analisis dilakukan berdasarkan dataset yang diperoleh dari platform Kaggle.

## Business Understanding

Pengembangan model prediksi tingkat obesitas memiliki potensi besar untuk membantu berbagai pihak, seperti tenaga medis, lembaga kesehatan, dan individu. Model ini dapat digunakan untuk mendeteksi status obesitas secara cepat dan akurat, sehingga mendukung intervensi dini, pencegahan penyakit kronis, dan peningkatan kesadaran akan pola hidup sehat. Hasil prediksi yang tepat juga dapat membantu dalam pemantauan status kesehatan masyarakat, penyusunan kebijakan kesehatan, serta pengambilan keputusan klinis yang lebih efisien.

### Problem Statements
Mengacu pada latar belakang yang telah dijelaskan, berikut adalah sejumlah permasalahan yang dapat diselesaikan melalui proyek ini.
- Bagaimana mengklasifikasikan status obesitas individu berdasarkan data fisik dan aktivitas?
- Bagaimana meningkatkan akurasi prediksi kategori obesitas dengan metode machine learning?

### Goals
Adapun tujuan dari proyek ini adalah sebagai berikut.
- Membangun model klasifikasi untuk mengkategorikan status obesitas dengan akurasi tinggi.
- Mengidentifikasi fitur yang paling berpengaruh dalam prediksi obesitas.

  ### Solution statements
- Untuk menjawab permasalahan yang ada, dilakukan analisis univariat dan multivariat guna memahami karakteristik data. Visualisasi digunakan sebagai alat bantu dalam mengevaluasi korelasi antar fitur dan mengidentifikasi data pencilan (outlier) yang berpotensi mengganggu akurasi model.
- Dilakukan proses data cleaning dan standardisasi data untuk memastikan kualitas data yang baik.
- Beragam model dibangun dan dievaluasi guna memperoleh model paling optimal untuk prediksi kualitas apel. Di antaranya adalah:
  - Random Forest adalah algoritma berbasis pohon keputusan yang menggabungkan banyak pohon untuk menghasilkan prediksi yang lebih akurat. Cocok untuk klasifikasi obesitas karena dapat menangani banyak fitur dan hubungan non-linear antar variabel.
  - SVM bekerja dengan mencari garis pemisah terbaik antar kelas. Dalam klasifikasi obesitas, SVM efektif memisahkan level obesitas berdasarkan fitur seperti BMI, usia, dan aktivitas fisik, terutama jika data memiliki batas kelas yang jelas.
  - KNN mengklasifikasikan data berdasarkan kedekatan dengan tetangga terdekat. Untuk prediksi obesitas, KNN menilai individu berdasarkan kemiripannya dengan data yang telah diberi label sebelumnya.

## Data Understanding

Dataset yang digunakan berisi data fisik dan demografi dari individu yang telah diberi label kategori obesitas. Dataset ini dapat diunduh dari Kaggle (https://www.kaggle.com/datasets/mrsimple07/obesity-prediction/).

# EDA - Deskripsi Variabel
**Informasi Dataset**

| **Informasi**       | **Deskripsi**                                                           |
|---------------------|-------------------------------------------------------------------------|
| **Title**           | Obesity Prediction                                                      |
| **Source**          | Kaggle                                                                  |
| **Maintainer**      | MrSimple07                                                              |
| **License**         | Other (specified in description)                                        |
| **Visibility**      | Publik                                                                  |
| **Tags**            | Health, Health Conditions                                               |
| **Usability Score** | 10.00 (semakin tinggi semakin mudah digunakan, skala maksimal adalah 10)| 

Adapun isi dari dataset yang digunakan dalam proyek ini adalah Obesity Prediction yang bersumber dari platform Kaggle dan dikelola oleh pengguna dengan nama MrSimple07.

| Age | Gender | Height     | Weight     | BMI        | PhysicalActivityLevel | ObesityCategory |
|-----|--------|------------|------------|------------|----------------------|-----------------|
| 56  | Male   | 173.575262 | 71.982051  | 23.891783  | 4                    | Normal weight   |
| 69  | Male   | 164.127306 | 89.959256  | 33.395209  | 2                    | Obese           |
| 46  | Female | 168.072202 | 72.930629  | 25.817737  | 4                    | Overweight      |
| 32  | Male   | 168.459633 | 84.886912  | 29.912247  | 3                    | Overweight      |
| 60  | Male   | 183.568568 | 69.038945  | 20.487903  | 3                    | Normal weight   |
| 25  | Female | 166.405627 | 61.145868  | 22.081628  | 4                    | Normal weight   |
| 78  | Male   | 183.566334 | 92.208521  | 27.364341  | 3                    | Overweight      |
| 38  | Male   | 142.875095 | 59.359746  | 29.078966  | 1                    | Overweight      |
| 56  | Male   | 183.478558 | 75.157672  | 22.325577  | 4                    | Normal weight   |
| 75  | Male   | 182.974061 | 81.533460  | 24.353244  | 2                    | Normal weight   |

Dataset ini memiliki total 1000 entri (baris) dan mencakup 7 fitur (kolom), dengan deskripsi masing-masing kolom dijelaskan di bawah ini.

- **Age** : Usia individu (tahun)
- **Gender** : Jenis kelamin (Laki-laki/Perempuan)
- **Height** : Tinggi badan (cm)
- **Weight** : Berat badan (kg)
- **BMI** : Indeks Massa Tubuh
- **PhysicalActivityLevel** : Tingkat aktivitas fisik harian
- **ObesityCategory** : Kategori obesitas (Underweight, Normal weight, Overweight, Obese)

Selain itu, dilakukan exploratory data analysis untuk memeriksa distribusi data, nilai hilang, outlier, dan korelasi antar fitur. Juga dilakukn visualisasi data.

# EDA - Univariate Analysis

![image](https://github.com/user-attachments/assets/c067f9b3-84b3-472c-912b-6b60c2238a2b)

Gambar 1a. Analisis Univariat (Data Kategori: Gender)
Terlihat bahwa jumlah laki-laki (Male) sedikit lebih banyak dibandingkan perempuan (Female), dengan sekitar 510 laki-laki dan 460 perempuan. Perbedaan ini tidak terlalu signifikan, sehingga distribusi gender dalam data cukup seimbang.

![image](https://github.com/user-attachments/assets/b71c3b0a-89d4-4439-b6d8-200dbe81c713)

Gambar 1b. Analisis Univariat (Data Kategori: ObesityCategory)
Grafik di atas menunjukkan distribusi kategori obesitas dalam dataset. Kategori dengan jumlah tertinggi adalah Normal weight, diikuti oleh Overweight, Obese, dan yang paling sedikit adalah Underweight. Hal ini menunjukkan bahwa mayoritas individu dalam dataset memiliki berat badan normal, sedangkan jumlah penderita obesitas dan underweight relatif lebih sedikit. 

![image](https://github.com/user-attachments/assets/49177494-3ca2-489b-8399-4336b4761b02)

Gambar 2a. Analisis  Univariat (Data Numerik: Age dan Height)
Pada grafik sebelah kiri, distribusi usia tampak cukup merata dengan sedikit puncak di usia tertentu seperti sekitar 20, 30, 40, dan 70 tahun. Hal ini menunjukkan bahwa tidak ada dominasi usia tertentu, namun ada kecenderungan kelompok usia tertentu muncul lebih sering, mungkin karena faktor sampling atau karakteristik populasi yang dikaji.

Sementara itu, grafik sebelah kanan menunjukkan distribusi tinggi badan yang menyerupai bentuk distribusi normal (bell curve), dengan puncaknya berada di sekitar 165–170 cm. Ini menandakan bahwa sebagian besar individu memiliki tinggi badan di kisaran tersebut, dan jumlah individu berkurang seiring dengan tinggi yang sangat pendek maupun sangat tinggi.

![image](https://github.com/user-attachments/assets/bd8eddba-9e31-40af-a467-c1c95c596586)

Gambar 2b. Analisis  Univariat (Data Numerik: Weight dan BMI)
Histogram kiri berjudul "Weight" yang menampilkan distribusi berat badan dengan rentang sekitar 30 sampai 110 (mungkin dalam satuan kg). Distribusinya terlihat miring sedikit ke kiri dengan puncak di sekitar 75-80.

Histogram kanan berjudul "BMI" yang menunjukkan distribusi Indeks Massa Tubuh (BMI) dengan rentang dari sekitar 10 sampai 40. Distribusinya juga menyerupai distribusi normal dengan puncak sekitar 24-26.

![image](https://github.com/user-attachments/assets/de5d7457-4eaf-4103-9e8d-dad5309ccaef)

Gambar 2c. Analisis  Univariat (Data Numerik: PhysicalActivityLevel dan ObesityCategory_num)

# EDA - Multivariat Analysis
![image](https://github.com/user-attachments/assets/7d9925ae-20ca-4f7d-a9bf-3b368e9b16a4)

Gambar 3a Jumlah Obesity Category berdasarkan Gender
Grafik di atas menunjukkan distribusi kategori obesitas berdasarkan gender. Terlihat bahwa baik pada pria maupun wanita, kategori dengan jumlah individu terbanyak adalah Normal weight. Pada pria, jumlah individu dengan berat badan normal lebih tinggi dibanding wanita, dengan selisih yang cukup signifikan. Sementara itu, kategori Overweight lebih banyak ditemukan pada wanita dibandingkan pria, menunjukkan kecenderungan kelebihan berat badan yang sedikit lebih besar di kelompok wanita. Untuk kategori Obese dan Underweight, jumlahnya relatif seimbang antara pria dan wanita, meskipun tetap menunjukkan sedikit penurunan pada kelompok wanita.

![image](https://github.com/user-attachments/assets/9bc45493-9a38-447b-a87b-a20e836531db)

![image](https://github.com/user-attachments/assets/09bd8691-a53c-4b22-8088-4d043a9a222a)

Gambar 3b hubungan antar fitur numerik
Gambar pairplot menunjukkan hubungan antar fitur numerik dalam dataset. Terlihat korelasi positif yang kuat antara Weight dan BMI, serta antara BMI dan ObesityCategory_num, yang wajar karena kategori obesitas diturunkan dari nilai BMI. Sebaliknya, Height berkorelasi negatif dengan BMI. Distribusi tiap fitur juga tampak normal, terutama pada Height, Weight, dan BMI. Sementara PhysicalActivityLevel tidak menunjukkan pola korelasi yang jelas dengan fitur lain, menunjukkan pengaruhnya terhadap obesitas mungkin tidak langsung. Visualisasi ini membantu memahami data dan memilih fitur yang relevan untuk pemodelan.

![image](https://github.com/user-attachments/assets/5742a8b4-ed08-4d76-ae90-3721d6a3f367)

Gambar 3c Correlation Matrix untuk Fitur Numerik 
Berdasarkan hasil visualisasi matriks korelasi pada fitur numerik, dapat disimpulkan bahwa fitur yang paling berpengaruh dalam menentukan tingkat obesitas (ObesityCategory\_num) adalah **BMI**, dengan nilai korelasi sebesar **0.94**. Ini menunjukkan bahwa BMI sangat erat kaitannya dengan klasifikasi tingkat obesitas. Selain itu, **berat badan (Weight)** juga memiliki korelasi yang cukup tinggi terhadap tingkat obesitas, yakni **0.82**, sementara **tinggi badan (Height)** menunjukkan korelasi negatif sebesar **-0.40**, yang logis karena tinggi badan merupakan komponen dalam perhitungan BMI. Sebaliknya, fitur **usia (Age)** dan **tingkat aktivitas fisik (PhysicalActivityLevel)** menunjukkan korelasi yang sangat rendah terhadap tingkat obesitas, masing-masing sebesar **-0.06** dan **0.03**, yang mengindikasikan bahwa pengaruhnya terhadap klasifikasi obesitas dalam data ini sangat minim. Oleh karena itu, dalam studi kasus prediksi klasifikasi tingkat obesitas, fitur BMI, berat badan, dan tinggi badan merupakan variabel yang paling penting dan sebaiknya dijadikan fokus utama dalam pembangunan model prediktif.

## Data Preparation

Pada tahap Data Preparation, dilakukan beberapa langkah utama, yaitu Data Gathering, Data Assessing, dan Data Cleaning. Sedangkan pada tahap Data Gathering, data diimpor dan disusun agar dapat dibaca dengan baik menggunakan DataFrame dari library Pandas. Selanjutnya, pada tahap Data Assessing, dilakukan pengecekan terhadap:

- Duplikasi data, yaitu entri yang sama muncul lebih dari sekali,
- Missing value, yaitu nilai yang tidak tersedia dalam dataset, dan
- Outlier, yaitu data yang menyimpang jauh dari pola umum.

Pada proyek kasus ini, tidak ditemukan adanya data duplikat maupun nilai yang hilang (missing value). Namun, terdapat outlier yang akan diatasi menggunakan metode dropping berdasarkan metode Interquartile Range (IQR). IQR dihitung dengan mengurangkan kuartil ketiga (Q3) dengan kuartil pertama (Q1), sesuai rumus berikut:

**𝐼𝑄𝑅** = 𝑄3 − 𝑄1

Dimana:
𝑄1 adalah kuartil pertama
𝑄3 adalah kuartil ketiga

Setelah menerapkan metode IQR untuk menghilangkan outlier, jumlah data dalam dataset berkurang menjadi 974 dari sebelumnya 1000 data.

![image](https://github.com/user-attachments/assets/8292602a-fd09-4a99-90ac-623c23113dd0)

Selanjutnya, dilakukan analisis Principal Component Analysis (PCA), dimana ditemukan bahwa fitur weight dan ibm memiliki korelasi yang sangat tinggi, sehingga perlu diperhatikan dalam pemilihan fitur agar tidak terjadi multikolinearitas.

Pada proyek ini, digunakan metode Train Test Split dari library sklearn.model_selection untuk membagi dataset menjadi data latih dan data uji dengan perbandingan 90:10 serta menggunakan random_state sebesar 123 untuk menjaga konsistensi pembagian data. Selain itu, dilakukan proses standardisasi menggunakan StandardScaler dari library sklearn.preprocessing untuk menormalisasi dataset agar setiap fitur memiliki skala yang sama.

Semua proses ini dilakukan untuk memastikan model yang dibangun memiliki performa yang baik dan dapat menghasilkan prediksi yang akurat.

## Modeling

Dalam proyek ini, proses pemodelan dilakukan menggunakan tiga algoritma, yaitu:
1. Random Forest merupakan algoritma ensemble learning berbasis pohon keputusan yang membentuk banyak decision tree dan menggabungkan hasilnya untuk menghasilkan prediksi yang lebih akurat dan stabil. Algoritma ini bekerja dengan prinsip voting pada klasifikasi. Algoritma ini memiliki kelebihan dan kekurangan, yaitu sebagai berikut.
   
**Kelebihan:**
- Akurasi tinggi dan tahan terhadap overfitting.
- Dapat menangani data dengan fitur yang kompleks.
- Memberikan informasi pentingnya fitur (feature importance).
  
**Kekurangan:**
- Membutuhkan waktu komputasi lebih lama.
- Kurang interpretatif karena terdiri dari banyak pohon.

2. Support Vector Machine (SVM) merupakan algoritma klasifikasi yang mencari hyperplane terbaik yang memisahkan dua atau lebih kelas dalam ruang fitur. Tujuannya adalah memaksimalkan margin antara kelas-kelas tersebut. Seperti algoritma Random Forest, SVM juga memiliki kelebihan dan kekurangan, sebagai berikut.
   
**Kelebihan:**
- Efektif untuk data berdimensi tinggi dan margin antar kelas yang jelas.
- Kuat terhadap overfitting dalam kondisi tertentu.
  
**Kekurangan:**
- Tidak cocok untuk dataset besar karena waktu komputasi tinggi.
- Sensitif terhadap outlier dan membutuhkan normalisasi data.

3. K-Nearest Neighbors (KNN) merupakan algoritma terakhir yang digunakan dalam prediksi klasifikasi tingkat obesitas, dimana merupakan algoritma klasifikasi berbasis instance-based learning, yang menentukan kelas suatu data baru berdasarkan mayoritas kelas dari ‘k’ tetangga terdekatnya dalam ruang fitur. Adapun kelebihan dan kekurangn dari algorutma ini adalah sebagai berikut.
   
**Kelebihan:**
- Sederhana dan mudah diimplementasikan.
- Tidak memerlukan proses pelatihan model.
  
**Kekurangan:**
- Performa lambat pada dataset besar.
- Sangat bergantung pada pemilihan nilai k dan skala fitur.

Berdasarkan hasil evaluasi akurasi, algoritma Random Forest dipilih sebagai model terbaik karena menunjukkan akurasi tertinggi dan performa yang paling stabil dibandingkan dengan SVM dan KNN. Random Forest mampu menangani kompleksitas data klasifikasi dengan baik, terutama dalam memprediksi tingkat obesitas yang terdiri dari empat kategori, yaitu Underweight, Normal weight, Overweight, dan Obese. Model ini bekerja dengan efektif menggunakan fitur-fitur seperti berat badan, tinggi badan, indeks massa tubuh (BMI), jenis kelamin, dan usia, sehingga menjadi solusi paling optimal dalam mengklasifikasikan level obesitas. Adapun tabel hasil evaluasi berdasarkan akurasi ditampilkan pada bagian Evaluasi.

## Evaluation

Pada tahap evaluasi, digunakan metrik akurasi (accuracy) sebagai ukuran kinerja model. Metrik ini digunakan untuk mengukur sejauh mana model mampu mengklasifikasikan data secara benar secara keseluruhan.. 

Akurasi dihitung dengan rumus berikut:

**Accuracy = Jumlah prediksi benar/ Jumlah total prediksi × 100%**

Berikut adalah hasil evaluasi untuk masing-masing model.

| Model         | Accuracy   |
|---------------|------------|
| RandomForest  | 1.000000   |
| KNN           | 0.857143   |
| SVM           | 0.357143   |

Tabel Hasil Akurasi
![image](https://github.com/user-attachments/assets/236e80e3-1eb2-4379-afa7-55f505c7317e)

Dari hasil evaluasi tersebut, terlihat bahwa Random Forest memiliki akurasi paling tinggi dibandingkan KNN dan SVM, menjadikannya model terbaik dalam konteks klasifikasi tingkat obesitas pada dataset ini.

Evaluasi ini menunjukkan bahwa model Random Forest dapat memprediksi kategori obesitas dengan baik dan dapat digunakan sebagai alat bantu dalam mendeteksi risiko obesitas secara dini.

## Referensi
1. Aini, E. D. N., Khasanah, R. A., Ristyawan, A., & Diniati, E. (2024, July). Penggunaan Data Mining untuk Prediksi tingkat Obesitas di Meksiko Menggunakan Metode Random Forest. In Prosiding SEMNAS INOTEK (Seminar Nasional Inovasi Teknologi) (Vol. 8, No. 3, pp. 1256-1265).
2. Setiyani, L., Indahsari, A. N., & Roestam, R. (2023). Analisis Prediksi Level Obesitas Menggunakan Perbandingan Algoritma Machine Learning dan Deep Learning. JTERA (Jurnal Teknol. Rekayasa), 8(1), 139.
3. Sitanggang, D., & Sherly, S. (2022). Model Prediksi Obesitas dengan Menggunakan Support Vector Machine. Jurnal Sistem Informasi dan Ilmu Komputer, 5(2), 172-175.
