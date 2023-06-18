# Laporan Proyek Machine Learning - Novandri Sitinjak

## Latar Belakang
Bank merupakan lembaga intermediasi yang bertugas menerima simpanan dari nasabah dan meminjamkannya kepada nasabah (unit ekonomi) lain yang membutuhkan dana. Atas simpanan masyarakat, bank memberikan imbalan berupa bunga. Demikian pula, atas pemberian pinjaman (kredit) bank mengenakan bunga kepada para peminjam. Dengan kata lain bank sebagai lembaga keuangan yang berfungsi menghimpun dan menyalurkan dana dari dan ke masyarakat untuk meningkatkan pelayanan kepada para nasabah tanpa mengabaikan etika perbankan.

Salah satu kegiatan utama bank adalah menyalurkan dana kepada masyarakat dalam bentuk kredit. Hal ini didasarkan pada kenyataan bahwa perkreditan merupakan aktivitas terbesar pada perbankan. Besarnya jumlah kredit yang disalurkan akan menentukan keuntungan bank. Jika bank tidak mampu menyalurkan kredit sementara dana dari masyarakat banyak disimpan, maka alternative lain bank bisa menyalurkan dananya melalui pasar uang maupun pasar modal. Hal ini dilakukan untuk memperoleh keuntungan yang maksimal. Apabila bank tidak melakukan alternative lain selaain menyalurkan kredit maka bank akan mengalami kerugian, karena harus membayar bunga simpanan kepada masyarakat.

Perkembangan ekonomi yang semakin global tentu membawa peluang dan risiko yang semakin besar. Risiko kredit merupakan masalah besar bagi dunia perbankan, dan lembaga keuangan pada umumnya. Dengan demikian, risiko kredit perlu mendapatkan perhatian yang khusus. Setiap rupiah yang tidak tertagih menjadi kredit macet, yang kemudian menimbulkan biaya penyisihan dalam laporan laba/rugi.

Kredit disamping memberikan sumbangan terbesar terhadap laba, kredit juga merupakan salah satu faktor yang menyebabkan rapuhnya usaha perbankan yaitu dengan tingginya risiko kredit. Risiko terkait dengan adanya ketidakpastian. Risiko kredit ditimbulkan oleh debitur yang secara kredit tidak dapat membayar utang dan memenuhi kewajiban seperti tertuang dalam kesepakatan atau turunnya kualitas debitur atau pembeli sehingga persepsi mengenai kemungkinan gagal bayar semakin tinggi. Risiko kredit perlu dikelola dengan baik karena apabila tidak dikelola dengan baik maka akan mengakibatkan proposi kredit yang bermasalah semakin besar, sehingga akan berdampak pada kondisi perbankan

Pengendalian pada Risiko kredit tentu dilakukan oleh setiap bank. Pengendalian tersebut diantisipasi oleh kualitas suatu sistem manajemen risiko kredit yang baik untuk meminimalkan risiko kredit. Evaluasi kredit yang akurat menjadi sangat penting dan berguna sebagai salah satu input alternative dalam mempertahankan kondisi perbankan agar tetap stabil.

## Problem Statements
1. Bagaimana kita dapat mengidentifikasi risiko kredit dengan akurat dan efektif untuk mengurangi tingkat kredit bermasalah dan meningkatkan kinerja Bank?
2. Bagaimana kita dapat mengembangkan model klasifikasi yang dapat memprediksi risiko kredit secara efektif?

## Goals
1. Mengembangkan model klasifikasi dengan akurasi minimal 90% untuk mengidentifikasi risiko kredit.
2. Meningkatkan performa model klasifikasi dalam memprediksi risiko kredit.

## Solution Statement
   Keempat model klasifikasi yang dipilih, yaitu K-Nearest Neighbor (KNN), Random Forest, Boosting Algorithm, dan Support Vector Classifier (SVC).
   - K-Nearest Neighbor (KNN):
   KNN adalah algoritma yang menggunakan data latihan terdekat dalam ruang fitur untuk memprediksi kelas dari data uji. Dalam konteks risiko kredit, KNN dapat digunakan untuk mencari pola atau kemiripan antara pengajuan pinjaman baru dengan pinjaman yang sudah ada. Model KNN dapat mengklasifikasikan pengajuan pinjaman baru sebagai risiko kredit tinggi jika memiliki tetangga yang sebagian besar memiliki riwayat kredit yang buruk.
   - Random Forest:
   Random Forest adalah algoritma ensemble yang menggabungkan beberapa pohon keputusan untuk menghasilkan prediksi akurat. Dalam kasus risiko kredit, Random Forest dapat mengevaluasi berbagai fitur seperti usia, pendapatan, riwayat kredit, dan lainnya untuk mengklasifikasikan pengajuan pinjaman baru sebagai risiko kredit rendah atau tinggi. Keunggulan Random Forest adalah dapat menangani variabel numerik dan kategorikal, serta mampu mengatasi overfitting.
   - Boosting Algorithm:
   Boosting Algorithm, seperti Gradient Boosting atau AdaBoost, adalah algoritma ensemble yang memadukan beberapa model kelemahan menjadi model yang kuat. Dalam konteks risiko kredit, Boosting Algorithm dapat memberikan bobot yang lebih besar kepada pengajuan pinjaman yang memiliki risiko kredit tinggi. Model Boosting dapat memperkuat kemampuan dalam mengklasifikasikan pengajuan pinjaman baru dengan risiko kredit yang lebih tinggi berdasarkan pengalaman belajar dari model sebelumnya.
   - Support Vector Classifier (SVC):
   SVC adalah algoritma yang membangun hyperplane atau sekumpulan hyperplane untuk melakukan klasifikasi. Dalam kasus risiko kredit, SVC dapat membangun pemisah antara pengajuan pinjaman yang berpotensi risiko tinggi dan rendah berdasarkan fitur-fitur yang relevan. Keunggulan SVC adalah dapat mengatasi masalah data yang tidak linier, sehingga cocok untuk mengklasifikasikan risiko kredit yang kompleks.

 KNN dapat mengidentifikasi pola berdasarkan kemiripan data, Random Forest memiliki kemampuan untuk menangani variabel numerik dan kategorikal serta menghindari overfitting, Boosting Algorithm dapat memperkuat kemampuan klasifikasi dengan penggabungan model, dan SVC dapat mengatasi masalah data yang tidak linier.
 
 Dengan menggunakan kombinasi keempat model ini, dapat dimanfaatkan keunggulan masing-masing model dan meningkatkan akurasi serta kinerja dalam mengidentifikasi risiko kredit.

## Data Understanding
Data yang digunakan dalam proyek ini adalah dataset Credit Risk yang berisi informasi tentang pengajuan pinjaman dan status kredit. Dataset ini dapat diunduh dari [kaggle](https://www.kaggle.com/datasets/laotse/credit-risk-dataset)

Variabel-variabel dalam dataset Credit Risk meliputi:
| Variabel | Deskripsi |
|-----|-----------|
|person_age| Usia peminjam|
|person_income| Pendapatan tahunan peminjam|
|person_home_ownership| Status kepemilikan rumah peminjam|
|person_emp_length| Lama pekerjaan yang telah dilalui peminjam (dalam tahun)|
|loan_intent | Tujuan pinjaman|
|loan_grade| Tingkat kualitas pinjaman (Grade A pinjaman dengan risiko rendah atau sangat baik, Grade B pinjaman dengan risiko sedang atau baik, Grade C pinjaman dengan risiko moderat atau cukup baik, Grade D pinjaman dengan risiko agak tinggi atau cukup baik, Grade E pinjaman dengan risiko tinggi atau perlu diperhatikan, Grade F pinjaman dengan risiko sangat tinggi atau perlu pengawasan ketat, dan Grade G pinjaman dengan risiko sangat tinggi atau perlu tindakan segera.|
|loan_amnt| Jumlah pinjaman|
|loan_int_rate| Suku bunga pinjaman|
|loan_status|Status pinjaman (Nilai 0 menunjukkan bahwa pinjaman tidak dalam keadaan menunggak atau lancar. Artinya, peminjam telah membayar pinjaman sesuai dengan ketentuan yang telah disepakati. Nilai 1 Menunjukkan bahwa pinjaman dalam keadaan menunggak atau tidak lancar. Ini mengindikasikan bahwa peminjam tidak dapat atau belum membayar pinjaman sesuai dengan ketentuan yang telah disepakati, biasanya melebihi batas waktu pembayaran yang ditentukan.)|
|loan_percent_income | Presentase pendapatan tahunan peminjam terhadap cicilan pinjaman|
|cb_person_default_on_file| Riwayat kredit peminjam ("Y" menunjukkan bahwa peminjam memiliki riwayat gagal membayar kredit atau menunggak dalam catatan kreditnya. "N" menunjukkan bahwa peminjam tidak memiliki riwayat gagal membayar kredit atau menunggak dalam catatan kreditnya.)|
|cb_preson_cred_hist_length| Durasi sejak peminjam memiliki catatan kredit yang tercatat|

## Data preparation
1. Data Cleaning

![Data null](https://github.com/novandristnjk/laporan/assets/110597813/429c0c08-1f04-4fdc-82dc-b2f729c55663)

Terdapat data yang bernilai null pada kolom person_emp_length dan loan_int_rate sehingga perlu menghapus baris yang bernilai null.

![describe](https://github.com/novandristnjk/laporan/assets/110597813/b36b4dfc-8225-4e01-8007-490adb2ff3ce)

Dari hasil fungsi describe(), nilai minimum untuk kolom "loan_percent_income" adalah 0. "loan_percent_income" merupakan presentase pendapatan tahunan peminjam terhadap cicilan pinjaman sehingga tidak mungkin ada yang bernilai 0 jika tidak ada "loan_amnt" atau jumlah pinjaman yang bernilai 0. Dilakukan pengecekan ada berapa missing value pada kolom "loan_percent_income":

```
loan_percent_income = (df.loan_percent_income == 0).sum()

print("Nilai 0 di kolom loan_percent_income ada: ", loan_percent_income)
```

Output:

![output missing value](https://github.com/novandristnjk/laporan/assets/110597813/cc2f4cf2-88e7-4ac4-8eed-3ac38627946d)

Terdapat 8 sampel missing value yang merupakan jumlah yang kecil dibandingkan total sampel. Oleh karena itu missing value tersebut dihapus. Setelah baris bernilai 0 dihapus, jumlah sampel atau baris data berubah menjadi 28638.

2. Handling Outlier

![Outlier 1](https://github.com/novandristnjk/laporan/assets/110597813/cead662c-bd53-436e-b500-6c998c81e0fc)

![Outlier 2](https://github.com/novandristnjk/laporan/assets/110597813/61929f64-9e4b-433a-b892-7ad2b4d6cfc2)

![Outlier 3](https://github.com/novandristnjk/laporan/assets/110597813/ab21d406-3221-441a-b247-30b4776ee11d)

![Outlier 4](https://github.com/novandristnjk/laporan/assets/110597813/5c666cfa-8b89-4143-a7aa-f88bda0b089c)

![Outlier 5](https://github.com/novandristnjk/laporan/assets/110597813/bc156cba-4027-4fce-a776-8b77bb869485)

dapat dilihat, pada beberapa fitur numerik di atas terdapat outliers. Outliers diidentifikasi menggunakan metode IQR  dan dihapus baris yang mengandung outliers.

3. Feature Encoding
Terdapat empat variabel kategori dalam dataset, yaitu "person_home_ownership", "loan_grade", "loan_intent", dan "cb_person_default_on_file". Pada variabel "loan_grade" dan "cb_person_default_on_file" digunakan teknik LabelEncoding, karena kedua variabel tersebut memiliki tingkatan atau urutan yang terkait. Pada variabel "person_home_ownership" dan  "loan_intent" digunakan teknik OneHotEncoding, karena kedua variabel tersebut tidak memiliki tingkatan atau urutan yang terkait.

4. Balancing Dataset

![Imballance Dataset](https://github.com/novandristnjk/laporan/assets/110597813/6f7ecc05-6591-432d-a468-1eccef08aac7)

Dapat dilihat bahwa terjadi ketidakseimbangan data pada fitur target "loan_status", dimana nilai sangat jauh lebih banyak dibanding nilai 1. Ketidakseimbangan dataset dapat menghasilkan model yang tidak optimal dan bias terhadap kelas mayoritas. Untuk menyeimbangkan dataset dilakukan oversampling menggunakan metode SMOTE dengan menggandakan sampel pada fitur "loan_status"  yang bernilai 1. SMOTE bekerja dengan menciptakan sampel sintetis baru untuk kelas minoritas dengan menggunakan teknik interpolasi antara sampel yang sudah ada dalam kelas minoritas. Oversampling dipilih karena jika menggunakan metode undersampling, maka jumlah akan berkurang sangat besar sehingga dapat kehilangan informasi dari data yang dihilangkan.

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

$(\text{True Positive} + \text{True Negative})$ dengan jumlah total prediksi $(\text{True Positive} + \text{True Negative} + \text{False Positive} + \text{False Negative})$.
