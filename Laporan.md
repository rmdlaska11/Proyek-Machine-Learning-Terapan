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

### Goals

Untuk menjawab masalah yang ada, akan dibuat model prediksi dengan tujuan sebagai berikut:
- Membangun model klasifikasi yang dapat memprediksi risiko diabetes dengan akurasi tinggi.

### Solution statements
Solusi yang dapat dilakukan berupa:
- Menggunakan algoritma klasifikasi, yaitu Support Vector Machine (SVM).
- Melakukan improvement pada model baseline dengan melakukan hyperparameter tuning untuk meningkatkan performa model.

## Data Understanding
Data atau dataset yang digunakan pada proyek *machine learning* ini adalah data diabetes yang didapat dari situs kaggle. 
- Terdapat 768 baris dalam dataset 
- Ada 9 Kolom yaitu: Pregnancies, Glucose, BloodPressure, SkinThickness, Insulin, BMI, DiabetesPedigreeFunction, Age, dan Outcome. 
- Link dataset dapat dilihat dari tautan berikut : [Diabetes Dataset](https://www.kaggle.com/datasets/whenamancodes/predict-diabities/data).


### Variabel-variabel pada Diabetes dataset adalah sebagai berikut:  
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


| # | Column                   | Non-Null Count | Dtype   |
|---|--------------------------|----------------|---------|
| 0 | Pregnancies              | 768 non-null   | int64   |
| 1 | Glucose                  | 768 non-null   | int64   |
| 2 | BloodPressure            | 768 non-null   | int64   |
| 3 | SkinThickness            | 768 non-null   | int64   |
| 4 | Insulin                  | 768 non-null   | int64   |
| 5 | BMI                      | 768 non-null   | float64 |
| 6 | DiabetesPedigreeFunction | 768 non-null   | float64 |
| 7 | Age                      | 768 non-null   | int64   |
| 8 | Outcome                  | 768 non-null   | intt64  |

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

Pada tahap pemodelan, dua algoritma klasifikasi utama digunakan, yaitu Support Vector Machine.  Hyperparameter tuning juga dilakukan untuk meningkatkan performa model. Support Vector Machine (SVM) adalah algoritma pembelajaran mesin yang digunakan untuk tugas klasifikasi dan regresi. Tujuannya adalah untuk menemukan batas keputusan (decision boundary) yang optimal untuk memisahkan dua kelas dalam ruang fitur. SVM berfokus pada pemilihan vektor dukungan (support vectors), yaitu titik-titik data yang paling dekat dengan batas keputusan.

Keunggulan SVM dibandingkan dengan Algoritma Klasifikasi Lain:

- Kemampuan Menangani Ruang Fitur Tinggi: SVM efektif dalam ruang fitur yang memiliki dimensi tinggi, bahkan ketika jumlah fitur melebihi jumlah sampel.
- Mengatasi Overfitting: SVM dapat mengatasi masalah overfitting dengan mengatur parameter seperti C (cost), yang mengontrol tingkat kompleksitas model.
- Kemampuan Menangani Data yang Tidak Linier: SVM dapat mengatasi masalah klasifikasi non-linier melalui penggunaan kernel, seperti kernel polinomial atau radial basis function (RBF).

Proses Membuat Model SVM:

- Pemilihan Kernel: Pilih jenis kernel yang sesuai dengan karakteristik data. Misalnya, kernel linear untuk data yang linier terpisah, kernel polinomial untuk data yang tidak linier, dan kernel RBF untuk kasus umum.
- Pemilihan Parameter: Tentukan parameter kernel dan parameter C (cost) dengan menggunakan teknik validasi silang (cross-validation) atau pencarian grid untuk mencari kombinasi parameter terbaik.
- Pelatihan Model: Latih model SVM pada data pelatihan menggunakan parameter yang telah dipilih.
- Evaluasi Model: Evaluasi kinerja model pada data uji untuk memastikan bahwa model dapat melakukan prediksi dengan baik pada data yang belum pernah dilihat sebelumnya.

Tabel 2. Perbandingan SVM sebelum dan Sesudah Tuning Hyperparameter

|              |   **Sebelum Tuning**   |    **Setelah Tuning**   |
|--------------|:----------------------:|:-----------------------:|
|    **SVM**   | 0.82                   | 0.93                    |

## Evaluation
Metrik evaluasi yang digunakan meliputi akurasi, presisi, recall, dan F1 score. Hasil model dievaluasi berdasarkan metrik-metrik ini untuk mengukur sejauh mana model dapat memprediksi risiko diabetes dengan baik.

![Confusion Matrix](https://github.com/rmdlaska11/Proyek-Machine-Learning-Terapan/assets/121273531/e1c16e47-e283-4c04-a237-a67c9eeffa97)

Gambar 3. Hasil Confusion Matrix

Tabel 3. Hasil Classification Report

|              |  Precision  |  Recall | f1-score  |  Support |
|--------------|:-----------:|:-------:|:---------:|---------:|
| 0            |      0.88   |    1.00 | 0.93      |    91    |
| 1            |      1.00   |    0.85 | 0.92      |    85    |
| accuracy     |             |         |   0.93    |   176    |
| macro avg    |    0.94     |   0.92  |   0.93    |    176   |
| weighted avg |    0.94     |   0.93  |   0.93    |     176  |

Berdasarkan hasil classification report di atas:

- Kelas 0:
  * Precision: 0.88
    Dari prediksi positif yang dilakukan untuk kelas 0, 88% di antaranya benar.
  * Recall: 1.00
    Model berhasil mendeteksi semua instance positif yang sebenarnya dari kelas 0.
  * F1-Score: 0.93
    F1-score adalah rata-rata harmonik dari precision dan recall, dan nilai ini mencapai 0.93.
  * Support: 91
    Terdapat 91 instance dalam kelas 0 pada dataset.

- Kelas 1:
  * Precision: 1.00
            Dari prediksi positif yang dilakukan untuk kelas 1, 100% di antaranya benar.
  * Recall: 0.85
            Model berhasil mendeteksi 85% dari instance positif yang sebenarnya dari kelas 1.
  * F1-Score: 0.92
            F1-score adalah rata-rata harmonik dari precision dan recall, dan nilai ini mencapai 0.92.
  * Support: 85
            Terdapat 85 instance dalam kelas 1 pada dataset.

- Akurasi (Accuracy):
  Akurasi adalah ukuran keseluruhan kinerja model, yang mencapai 0.93. Ini mengukur sejauh mana model dapat memprediksi keseluruhan kelas dengan benar.

- Rata-rata Makro (Macro Avg):
  Rata-rata makro adalah rata-rata aritmatika dari metrik-metrik (precision, recall, f1-score) untuk setiap kelas. Nilai precision, recall, dan f1-score rata-rata makro adalah 0.94, 0.92, dan 0.93, secara berturut-turut.

- Rata-rata Terimbang (Weighted Avg):
  Rata-rata terimbang adalah rata-rata tertimbang berdasarkan jumlah instance dalam setiap kelas. Nilai precision, recall, dan f1-score rata-rata terimbang adalah 0.94, 0.93, dan 0.93, secara berturut-turut.

**Kesimpulan** :  Proyek ini bertujuan untuk mengembangkan model klasifikasi yang dapat membantu dalam prediksi risiko diabetes pada individu berdasarkan data klinis. Dengan menggunakan algoritma klasifikasi dan melakukan hyperparameter tuning, diperolehlah akurasi sebesar 93% menggunakan algoritma *support vector machine* dengan C =1 dan Gamma = 10.

**Referensi** :

[1]	World Health Organization, “Global Report on Diabetes,” Isbn, 2016, doi: ISBN 978 92 4 156525 7.

[2]	American Diabetes Association, “2016 American Diabetes Association (ADA) Diabetes Guidelines Summary Recommendation from NDEI,” Natl. Diabetes Educ. Initiat., 2016.

[3] D. T. Larose, Data Mining Methods and Models. 2006.
