# Laporan Proyek Machine Learning - Novandri Sitinjak

## Latar Belakang

        Perkembangan perekonomian suatu negara dipengaruhi kondisi industri pendukung. Industri perbankan merupakan salah satu industri yang sangat berperan dalam mendukung perkembangan ekonomi, yaitu menghimpun dan menyalurkan dana. Penyaluran dana dalam bentuk kredit akan meningkatkan perkem bangan industri pada sektor riil yang mendukung pertumbuhan perekonomian negara dan mengurangi tingkat pengangguran.
        Risiko yang dihadapi dalam kegiatan penyaluran kredit adalah terjadinya kredit bermasalah Kredit berkembang menjadi bermasalah dapat disebabkan oleh berbagai hal yang berasal dari nasabah, kondisi eksternal, dan pemberi kredit. Evaluasi kredit yang akurat menjadi sangat penting untuk meminimalkan risiko kredit yang tidak menguntungkan bagi lembaga keuangan. Oleh karena itu, pengembangan model klasifikasi yang dapat mengidentifikasi risiko kredit dengan tepat sangatlah relevan dan penting.

Referensi :
- [Manajemen Risiko 2](https://himia.umj.ac.id/wp-content/uploads/2019/12/manajemen-resiko-2.pdf)
- [Analisis Penerapan Manajemen Risiko Kredit Dalam Meminimalisir Kredit Bermasalah Pada PT. BPR Swadaya Anak Nagari Bandarejo Simpang Empat Periode 2013-2018](https://media.neliti.com/media/publications/279976-analisis-penerapan-manajemen-risiko-kred-40cf48b0.pdf).

## Problem Statements
1. Bagaimana kita dapat mengidentifikasi risiko kredit dengan akurat?
2. Bagaimana kita dapat mengembangkan model klasifikasi yang dapat memprediksi risiko kredit secara efektif?

## Goals
1. Mengembangkan model klasifikasi yang dapat mengidentifikasi risiko kredit dengan akurat.
2. Meningkatkan performa model klasifikasi dalam memprediksi risiko kredit.

## Solution Statement
1. Menggunakan empat model klasifikasi antara lain KNN, Random Forest, Boosting, dan SVC.
2. Memilih model terbaik berdasarkan hasil evaluasi.

## Data Understanding
Data yang digunakan dalam proyek ini adalah dataset Credit Risk yang berisi informasi tentang pengajuan pinjaman dan status kredit. Dataset ini dapat diunduh dari [kaggle](https://www.kaggle.com/datasets/laotse/credit-risk-dataset/download?datasetVersionNumber=1.).

Variabel-variabel dalam dataset Credit Risk meliputi:
| Variabel | Deskripsi |
|-----|-----------|
|person_age| Usia peminjam|
|person_income| Pendapatan tahunan peminjam|
|person_home_ownership| Status kepemilikan rumah peminjam|
|person_emp_length| Lama pekerjaan yang telah dilalui peminjam (dalam tahun)|
|loan_intent | Tujuan pinjaman|
|loan_grade| Tingkat kualitas pinjaman|
|loan_amnt| Jumlah pinjaman|
|loan_int_rate| Suku bunga pinjaman|
|loan_status|Status pinjaman (0 artinya tidak menunggak dan 1 artinya menunggak)|
|loan_percent_income | Presentasi pendapatan tahunan peminjam terhadap cicilan pinjaman|
|cb_person_default_on_file| Riwayat kredit peminjam (pernah menunggak atau tidak)|
|cb_preson_cred_hist_length| Durasi sejak peminjam memiliki catatan kredit yang tercatat|

## Data preparation
1. Data Cleaning : Menghapus baris dengan nilai yang hilang atau tidak valid.
2. Handling Outlier : Mendeteksi data outlier menggunakan IQR method dan menghapus baris yang mengandung outlier.
3. Feature Encoding : Mengubah variabel kategori menjadi representasi numerik menggunakan teknik One-Hot Encoding untuk fitur yang tidak memiliki atau Label Encoding untuk fitur yang memiliki tingkatan.
4. Balancing Dataset : Menyeimbangkan data, karena perbandingan kolom target yaitu loan_status memiliki perbandingan yang sangat jauh antara yang menunggak dan tidak menunggak.
5. Train-Test Splitting : Memisahkan data menjadi data latihan (train) dan data uji (test) dengan perbandingan 90:10.

## Modeling
Pada tahap ini, kami menggunakan dua algoritma untuk mengklasifikasikan loan status, yaitu K-Nearest Neighbor, Random Forest Classifier, Boosting Algorithm, dan Support Vector Classifier.
1. K-Nearest Neighbor:
   - Jumlah tetangga (n_neighbors) : 10
2. Random Forest Classifier
   - Jumlah pohon (n_estimators) : 50
   - Kedalaman maksimum pohon (max_depth): 16
   - Random State (random_state) : 55
   - Jumlah job (n_jobs) : 1
3. Boosting Algorithm
   - Tingkat pembelajaran (learning_rate)
   - Random State (random_state) : 55
4. Support Vector Classifier

## Evaluation
Metrik evaluasi yang digunakan dalam proyek ini adalah akurasi (accuracy). Metode evaluasi ini mengukur nilai akurasi yang didapatkan dari jumlah data bernilai positif yang diprediksi positif dan data bernilai negatif yang diprediksi negatif dibagi dengan jumlah seluruh data di dalam dataset.

Hasil proyek berdasarkan metrik evaluasi yang digunakan:
1. K-Nearest Neighbor:
   - Train Accuracy : 0.92
   - Test Accuracy : 0.91
2. Random Forest Classifier
   - Train Accuracy : 0.97
   - Test Accuracy : 0.94
3. Boosting Algorithm
   - Train Accuracy : 0.79
   - Test Accuracy : 0.79
4. Support Vector Classifier
   - Train Accuracy : 0.93
   - Test Accuracy : 0.92

    Berdasarkan metrik evaluasi yang digunakan, kesimpulan yang dapat diambil adalah model Boosting memiliki tingkat akurasi yang lebih rendah dibandingkan dengan model lainnya. Di sisi lain, model Random Forest menunjukkan tingkat akurasi yang lebih tinggi. Oleh karena itu, disarankan untuk menggunakan model Random Forest untuk membuat model machine learning klasifikasi yang dapat digunakan untuk mengidentifikasi risiko kredit.

