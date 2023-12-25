# Laporan Proyek Machine Learning - Rahmad Ramadhan Laska

## Domain Proyek
Diabetes adalah kondisi di mana pankreas tidak dapat memproduksi atau tubuh manusia tidak dapat menggunakan insulin dengan efektif. Insulin, yang dihasilkan oleh pankreas, berfungsi sebagai kunci untuk memungkinkan glukosa dari makanan masuk ke dalam sel-sel tubuh, yang kemudian digunakan untuk menghasilkan energi.

Makanan yang mengandung karbohidrat diubah menjadi glukosa dalam darah, dan insulin membantu glukosa masuk ke dalam sel. Ketidakmampuan tubuh untuk memproduksi atau menggunakan insulin dengan baik menyebabkan peningkatan kadar glukosa dalam darah. Kondisi ini, jika berlangsung dalam jangka panjang, dapat merusak organ dan menyebabkan kegagalan fungsi organ dan jaringan.

Diabetes dibagi menjadi beberapa jenis, termasuk diabetes tipe 1, tipe 2, dan diabetes gestasional yang terjadi selama kehamilan karena perubahan hormonal [1]. Gejala umum diabetes meliputi poliuria, polidipsia, polifagia, penurunan berat badan mendadak (biasanya pada diabetes tipe 1), kelemahan, obesitas (biasanya pada diabetes tipe 2), penyembuhan luka yang tertunda, penglihatan kabur, gatal, iritabilitas, sariawan genital, paresis parsial, otot kaku, alopecia, dan sebagainya [2].

Dalam era industri 4.0, teknologi komputer dan penambangan data menjadi kunci penting dalam mendeteksi penyakit secara akurat dan efisien. Penambangan data, sebagai bidang ilmu komputer, digunakan untuk menganalisis dan memprediksi penyakit dengan memanfaatkan data yang sudah diketahui [3]. Untuk prediksi penyakit seperti diabetes, data gejala dan data klinis diperlukan. Gejala menjadi faktor penting untuk prediksi tahap awal penyakit, sementara data klinis digunakan untuk analisis lebih lanjut.

## Business Understanding

### Problem Statements

Berdasarkan latar belakang yang telah dijelaskan diatas, terdapat beberapa masalah yaitu:
- Bagaimana kita dapat memprediksi risiko seseorang terkena diabetes berdasarkan data klinis seperti kadar glukosa darah, tekanan darah, dan BMI?
- Apakah terdapat pola atau kombinasi fitur tertentu yang dapat digunakan untuk mengidentifikasi individu dengan risiko tinggi terkena diabetes?

### Goals

Untuk menjawab masalah yang ada, akan dibuat model prediksi dengan tujuan sebagai berikut:
- Membangun model klasifikasi yang dapat memprediksi risiko diabetes dengan akurasi tinggi.
- Mengidentifikasi fitur-fitur yang paling berpengaruh dalam prediksi risiko diabetes.

### Solution statements
Solusi yang dapat dilakukan berupa:
- Menggunakan algoritma klasifikasi, yaitu Support Vector Machine (SVM).
- Melakukan improvement pada model baseline dengan melakukan hyperparameter tuning untuk meningkatkan performa model.

## Data Understanding
Data atau dataset yang digunakan pada proyek *machine learning* ini adalah data diabetes yang didapat dari situs kaggle. 
- Terdapat 768 baris dalam dataset 
- Ada 9 Kolom yaitu: Pregnancies, Glucose, BloodPressure, SkinThickness, Insulin, BMI, DiabetesPedigreeFunction, Age, dan Outcome. 
- Link dataset dapat dilihat dari tautan berikut : [Diabetes Dataset](https://www.kaggle.com/datasets/whenamancodes/predict-diabities/data).


### Variabel-variabel pada Motorcycle dataset adalah sebagai berikut:  
* Pregnancies   : menyatakan jumlah kehamilan
* Glucose       : menyatakan kadar Glukosa dalam darah
* BloodPressure : menyatakan pengukuran tekanan darah
* SkinThickness :	menyatakan ketebalan kulit
* Insulin       :	menyatakan kadar Insulin dalam darah
* BMI 	        : menyatakan indeks massa tubuh
* DiabetesPedigreeFunction : menyatakan persentase Diabetes
* Age                      : menyatakan usia
* Outcome : menyatakan hasil akhir 1 adalah Ya dan 0 adalah Tidak

Tahapan Data Understanding
- Data loading
- Exploratory Data Analysis - Deskripsi Variabel
- Exploratory Data Analysis - Menangani Missing Value dan Outliers
- Exploratory Data Analysis - Univariate Analysis

Untuk memahami Diabetes dataset akan menggunakan beberapa tahapan dari teknik *Explanatory Data Analysis* (EDA) sebagai berikut:

1.   Deskripsi Variabel

![Tabel info](https://github.com/rmdlaska11/Proyek-Machine-Learning-Terapan/assets/121273531/48c5b1b3-6985-4b57-861b-969a22756c32)

Tabel 1. Info dataset

Pada Tabel 1, dapat dilihat bahwa:
* Terdapat 2 kolom numerik dengan tipe data float64 yaitu: BMI dan DiabetesPedigreeFunction. 
* Terdapat 7 kolom numerik dengan tipe data int64, yaitu: Pregnancies,Glucose, BloodPressure, SkinThickness, Insulin, Age , dan Outcome.

2.   Menangani *missing value & outliers*

Langkah selanjutnya menggunakan salah satu teknik untuk mendeteksi adanya *missing value*. Kemudian menangani *outlier*, *outliers* adalah sampel yang nilainya sangat jauh dari cakupan umum data utama. Pada kasus ini, *outliers* akan dideteksi dengan teknik visualisasi data (boxplot). Kemudian, *ouliers* akan ditangani dengan teknik *IQR method*.

3.   Analisis *Univariate*
Fitur Numerik

![Univariate Numerik](https://github.com/rmdlaska11/Proyek-Machine-Learning-Terapan/assets/121273531/3f88bd94-01e1-4c9a-a894-015d541d9f9e)

Gambar 1. Analisis Fitur Numerik

Berdasarkan gambar 1 di atas, jumlah orang yang memiliki penyakit diabetes berjumlah 200, sedangkan yang tidak terkena sebanyak 439 orang.


## Data Preparation
1. Mengatasi data tidak seimbang menggunakan *RandomOverSampler*

![Visualisasi Data Seimbang](https://github.com/rmdlaska11/Proyek-Machine-Learning-Terapan/assets/121273531/10925724-4ee8-4767-a647-dd9d9f6c1079)

Gambar 2. Plot Data Setelah diseimbangkan

Berdasarkan gambar 2, dapat dilihat variabel outcome telah seimbang dengan jumlah masing-masing 439.

2. Pembagian dataset (train-test split) dengan proposri 80:20
3. Normalisasi data menggunakan *StandardScaler*

## Modeling

Pada tahap pemodelan, dua algoritma klasifikasi utama digunakan, yaitu Support Vector Machine. SVM cenderung lebih tangguh terhadap overfitting, terutama dalam situasi di mana jumlah sampel relatif kecil. Hyperparameter tuning juga dilakukan untuk meningkatkan performa model.

Tabel 2. Perbandingan SVM sebelum dan Sesudah Tuning Hyperparameter

|              |   **Sebelum Tuning**   |    **Setelah Tuning**   |
|--------------|:----------------------:|:-----------------------:|
|    **SVM**   | 0.82                   | 0.93                    |

## Evaluation
Metrik evaluasi yang digunakan meliputi akurasi, presisi, recall, dan F1 score. Hasil model dievaluasi berdasarkan metrik-metrik ini untuk mengukur sejauh mana model dapat memprediksi risiko diabetes dengan baik.

![metrik evaluasi](https://github.com/rmdlaska11/Proyek-Machine-Learning-Terapan/assets/121273531/79c68252-17aa-4b01-b0a8-15e998342940)

Gambar 3. Hasil Confusion Matrix dan metriks evaluasi

**Kesimpulan** :  Proyek ini bertujuan untuk mengembangkan model klasifikasi yang dapat membantu dalam prediksi risiko diabetes pada individu berdasarkan data klinis. Dengan menggunakan algoritma klasifikasi dan melakukan hyperparameter tuning, diperolehlah akurasi sebesar 93%.

**Referensi** :

[1]	World Health Organization, “Global Report on Diabetes,” Isbn, 2016, doi: ISBN 978 92 4 156525 7.

[2]	American Diabetes Association, “2016 American Diabetes Association (ADA) Diabetes Guidelines Summary Recommendation from NDEI,” Natl. Diabetes Educ. Initiat., 2016.

[3] D. T. Larose, Data Mining Methods and Models. 2006.
