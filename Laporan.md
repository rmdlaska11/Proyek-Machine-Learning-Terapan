# Laporan Proyek Machine Learning - Rahmad Ramadhan Laska

## Domain Proyek

Latar belakang klasifikasi untuk memprediksi penyakit diabetes pada seseorang didasari oleh kompleksitas dan bahayanya penyakit diabetes mellitus. Diabetes mellitus dapat menyebabkan komplikasi serius seperti serangan jantung, stroke, gagal ginjal, dan kebutaan. Faktor penyebab diabetes mellitus meliputi faktor genetika, pola hidup tidak sehat, dan obesitas. Prevalensi diabetes mellitus terus meningkat, dan deteksi dini serta diagnosis medis diperlukan untuk mencegah komplikasi. Klasifikasi dan prediksi diabetes mellitus dapat dilakukan melalui analisis faktor-faktor risiko, termasuk data klinis dan pola hidup. Oleh karena itu, prediksi penyakit diabetes melalitus menjadi penting untuk membantu masyarakat, terutama tenaga medis, dalam melakukan diagnosis dini dan pencegahan komplikasi. 

Sumber:
* Mochamad Fajar Ismatulloh, "PREDIKSI PENYAKIT DIABETES MELLITUS MENGGUNAKAN METODE NAIVE BAYES CLASSIFIER," Universitas Komputer Indonesia.
* Eprints UMS, "PREDIKSI PENYAKIT DIABETES MELLITUS MENGGUNAKAN METODE NAIVE BAYES CLASSIFIER," Universitas Muhammadiyah Surakarta.
* Eprints UNY, "PREDIKSI PENYAKIT DIABETES MELLITUS MENGGUNAKAN METODE NAIVE BAYES CLASSIFIER," Universitas Negeri Yogyakarta.


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
 
## Data Preparation
1. Mengatasi data tidak seimbang
2. Pembagian dataset (train-test split)
3. Normalisasi data jika diperlukan.

## Modeling

Pada tahap pemodelan, dua algoritma klasifikasi utama digunakan, yaitu Support Vector Machine. Hyperparameter tuning juga dilakukan untuk meningkatkan performa model.

## Evaluation
Metrik evaluasi yang digunakan meliputi akurasi, presisi, recall, dan F1 score. Hasil model dievaluasi berdasarkan metrik-metrik ini untuk mengukur sejauh mana model dapat memprediksi risiko diabetes dengan baik.

**Kesimpulan** :  Proyek ini bertujuan untuk mengembangkan model klasifikasi yang dapat membantu dalam prediksi risiko diabetes pada individu berdasarkan data klinis. Dengan menggunakan algoritma klasifikasi dan melakukan hyperparameter tuning, diperolehlah akurasi sebesar 93%.

