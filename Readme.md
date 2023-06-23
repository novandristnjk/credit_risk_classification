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
   Keempat model klasifikasi yang dipilih, yaitu _K-Nearest Neighbor_ (KNN), _Random Forest_, _Boosting Algorithm_, dan _Support Vector Classifier_ (SVC).
   - K-Nearest Neighbor (KNN):
   KNN adalah algoritma yang menggunakan data latihan terdekat dalam ruang fitur untuk memprediksi kelas dari data uji. Dalam konteks risiko kredit, KNN dapat digunakan untuk mencari pola atau kemiripan antara pengajuan pinjaman baru dengan pinjaman yang sudah ada. Model KNN dapat mengklasifikasikan pengajuan pinjaman baru sebagai risiko kredit tinggi jika memiliki tetangga yang sebagian besar memiliki riwayat kredit yang buruk.
   - _Random Forest_:
   _Random Forest_ adalah algoritma _ensemble_ yang menggabungkan beberapa pohon keputusan untuk menghasilkan prediksi akurat. Dalam kasus risiko kredit, Random Forest dapat mengevaluasi berbagai fitur seperti usia, pendapatan, riwayat kredit, dan lainnya untuk mengklasifikasikan pengajuan pinjaman baru sebagai risiko kredit rendah atau tinggi. Keunggulan _Random Forest_ adalah dapat menangani variabel numerik dan kategorikal, serta mampu mengatasi _overfitting_.
   - _Boosting Algorithm_:
   _Boosting Algorithm_, seperti _Gradient Boosting_ atau _AdaBoost_, adalah algoritma _ensemble_ yang memadukan beberapa model kelemahan menjadi model yang kuat. Dalam konteks risiko kredit, _Boosting Algorithm_ dapat memberikan bobot yang lebih besar kepada pengajuan pinjaman yang memiliki risiko kredit tinggi. Model _Boosting_ dapat memperkuat kemampuan dalam mengklasifikasikan pengajuan pinjaman baru dengan risiko kredit yang lebih tinggi berdasarkan pengalaman belajar dari model sebelumnya.
   - _Support Vector Classifier_ (SVC):
   SVC adalah algoritma yang membangun _hyperplane_ atau sekumpulan hyperplane untuk melakukan klasifikasi. Dalam kasus risiko kredit, SVC dapat membangun pemisah antara pengajuan pinjaman yang berpotensi risiko tinggi dan rendah berdasarkan fitur-fitur yang relevan. Keunggulan SVC adalah dapat mengatasi masalah data yang tidak linier, sehingga cocok untuk mengklasifikasikan risiko kredit yang kompleks.

 KNN dapat mengidentifikasi pola berdasarkan kemiripan data, _Random Forest_ memiliki kemampuan untuk menangani variabel numerik dan kategorikal serta menghindari _overfitting_, _Boosting Algorithm_ dapat memperkuat kemampuan klasifikasi dengan penggabungan model, dan SVC dapat mengatasi masalah data yang tidak linier.
 
 Dengan menggunakan kombinasi keempat model ini, dapat dimanfaatkan keunggulan masing-masing model dan meningkatkan akurasi serta kinerja dalam mengidentifikasi risiko kredit.

## Data Understanding
Data yang digunakan dalam proyek ini adalah dataset Credit Risk yang berisi informasi tentang pengajuan pinjaman dan status kredit. Dataset ini dapat diunduh dari [kaggle](https://www.kaggle.com/datasets/laotse/credit-risk-dataset).

Tabel 1 variabel dan deskripsi data.

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
1. _Data Cleaning_

![Data null](https://github.com/novandristnjk/laporan/assets/110597813/429c0c08-1f04-4fdc-82dc-b2f729c55663)


Gambar 1. Data bernilai null sebelum dibersihkan

Terdapat data yang bernilai null pada kolom person_emp_length dan loan_int_rate sehingga perlu menghapus baris yang bernilai null.

![describe](https://github.com/novandristnjk/laporan/assets/110597813/b36b4dfc-8225-4e01-8007-490adb2ff3ce)

Gambar 2. Deskripsi data

Dari hasil fungsi describe(), nilai minimum untuk kolom "loan_percent_income" adalah 0. "loan_percent_income" merupakan presentase pendapatan tahunan peminjam terhadap cicilan pinjaman sehingga tidak mungkin ada yang bernilai 0 jika tidak ada "loan_amnt" atau jumlah pinjaman yang bernilai 0. Dilakukan pengecekan ada berapa missing value pada kolom "loan_percent_income":

```
loan_percent_income = (df.loan_percent_income == 0).sum()

print("Nilai 0 di kolom loan_percent_income ada: ", loan_percent_income)
```

Output:

![output missing value](https://github.com/novandristnjk/laporan/assets/110597813/cc2f4cf2-88e7-4ac4-8eed-3ac38627946d)

Terdapat 8 sampel missing value yang merupakan jumlah yang kecil dibandingkan total sampel. Oleh karena itu missing value tersebut dihapus. Setelah baris bernilai 0 dihapus, jumlah sampel atau baris data berubah menjadi 28638.

2. _Handling Outlier_

![Outlier 1](https://github.com/novandristnjk/laporan/assets/110597813/cead662c-bd53-436e-b500-6c998c81e0fc)

Gambar 3. _Boxplo_t variabel "person_age"

![Outlier 2](https://github.com/novandristnjk/laporan/assets/110597813/61929f64-9e4b-433a-b892-7ad2b4d6cfc2)

Gambar 4. _Boxplot_ variabel "person_emp_length"

![Outlier 3](https://github.com/novandristnjk/laporan/assets/110597813/ab21d406-3221-441a-b247-30b4776ee11d)

Gambar 5. _Boxplot_ variabel "loan_amnt"

![Outlier 4](https://github.com/novandristnjk/laporan/assets/110597813/5c666cfa-8b89-4143-a7aa-f88bda0b089c)

Gambar 6. _Boxplo_t variabel "loan_percent_income"

dapat dilihat, pada beberapa fitur numerik di atas terdapat outliers. Outliers diidentifikasi menggunakan metode IQR  dan dihapus baris yang mengandung outliers.

3. _Feature Encoding_
Terdapat empat variabel kategori dalam dataset, yaitu "person_home_ownership", "loan_grade", "loan_intent", dan "cb_person_default_on_file". Pada variabel "loan_grade" dan "cb_person_default_on_file" digunakan teknik LabelEncoding, karena kedua variabel tersebut memiliki tingkatan atau urutan yang terkait. Pada variabel "person_home_ownership" dan  "loan_intent" digunakan teknik OneHotEncoding, karena kedua variabel tersebut tidak memiliki tingkatan atau urutan yang terkait.

4. Balancing Dataset

![Imballance Dataset](https://github.com/novandristnjk/laporan/assets/110597813/6f7ecc05-6591-432d-a468-1eccef08aac7)

Gambar 7. Perbandingan nilai 0 dan 1 pada fitur targer "loan_status"

Dapat dilihat bahwa terjadi ketidakseimbangan data pada fitur target "loan_status", dimana nilai sangat jauh lebih banyak dibanding nilai 1. Ketidakseimbangan dataset dapat menghasilkan model yang tidak optimal dan bias terhadap kelas mayoritas. Untuk menyeimbangkan dataset dilakukan oversampling menggunakan metode SMOTE dengan menggandakan sampel pada fitur "loan_status"  yang bernilai 1. SMOTE bekerja dengan menciptakan sampel sintetis baru untuk kelas minoritas dengan menggunakan teknik interpolasi antara sampel yang sudah ada dalam kelas minoritas. Oversampling dipilih karena jika menggunakan metode undersampling, maka jumlah akan berkurang sangat besar sehingga dapat kehilangan informasi dari data yang dihilangkan.

5. Train-Test Splitting : Memisahkan data menjadi data latihan (train) dan data uji (test) dengan perbandingan 90:10.

## Modeling
Pada tahap ini digunakan empat model untuk mengklasifikasikan loan status, yaitu K-Nearest Neighbor, Random Forest Classifier, Boosting Algorithm, dan Support Vector Classifier.
1. K-Nearest Neighbor:
   - Jumlah tetangga : 10
  Jumlah tetangga dalam K-Nearest Neighbors (KNN) adalah parameter yang digunakan untuk menentukan jumlah tetangga terdekat yang akan digunakan dalam proses klasifikasi atau regresi. KNN adalah sebuah algoritma pembelajaran mesin yang digunakan untuk melakukan klasifikasi atau regresi berdasarkan kumpulan data yang ada di sekitarnya. Dalam KNN, ketika akan mengklasifikasikan atau meramalkan label dari sebuah sampel data yang belum diketahui, algoritma mencari k-nearest neighbors (k-tetangga terdekat) dari sampel tersebut berdasarkan jarak euclidean atau metrik jarak lainnya. Jumlah tetangga menentukan berapa banyak tetangga terdekat yang akan digunakan dalam proses ini.

2. Random Forest Classifier
   - Jumlah pohon : 50
   Jumlah pohon pada Random Forest adalah parameter yang menentukan berapa banyak pohon keputusan yang akan digunakan dalam ensemble. Random Forest adalah sebuah algoritma pembelajaran mesin yang menggabungkan beberapa pohon keputusan untuk melakukan klasifikasi atau regresi. Dalam Random Forest, setiap pohon keputusan dibangun secara independen dengan menggunakan subset acak dari data pelatihan. Jumlah pohon mengontrol berapa banyak pohon keputusan yang akan dibangun dalam ensemble. Semakin banyak pohon yang digunakan, semakin kompleks modelnya. Jumlah pohon yang lebih besar cenderung memberikan model yang lebih kuat dan lebih mampu menangkap hubungan yang kompleks dalam data. Namun, terlalu banyak pohon juga dapat menyebabkan overfitting, di mana model "menghafal" data pelatihan tetapi tidak umum untuk data yang tidak dilihat sebelumnya.
   - Kedalaman maksimum pohon : 16
   Kedalaman maksimum pohon adalah parameter yang digunakan dalam pohon keputusan dan beberapa algoritma berbasis pohon lainnya, seperti Random Forest. Max_depth menentukan seberapa dalam pohon keputusan dapat tumbuh dengan membatasi jumlah tingkat atau simpul dalam pohon.
    Ketika membangun pohon keputusan, algoritma akan membagi setiap simpul berdasarkan fitur dan ambil keputusan berdasarkan kriteria yang ditentukan, seperti gain informasi atau gini impurity. Dengan setiap pembagian, pohon tumbuh lebih dalam dengan menambahkan tingkat baru. Kedalaman maksimum pohon mengatur seberapa banyak tingkat yang diizinkan dalam pohon tersebut.
    Membatasi kedalaman maksimum pohon adalah langkah yang penting untuk mencegah overfitting. Jika pohon memiliki kedalaman yang sangat besar, ia dapat dengan mudah "menghafal" data pelatihan dengan sangat spesifik, tetapi akan cenderung tidak mampu melakukan generalisasi dengan baik pada data baru. Dalam kasus tersebut, model akan terlalu kompleks dan sensitif terhadap noise atau variasi kecil dalam data pelatihan.
   - Random State : 55
   Random State adalah parameter yang digunakan dalam algoritma pembelajaran mesin untuk mengontrol randomization atau keacakan yang terkait dengan model. Ketika model menggunakan algoritma yang melibatkan elemen keacakan, seperti inisialisasi bobot, pembagian data, atau pembangunan model, random_state memungkinkan pengguna untuk menetapkan nilai awal yang tetap sehingga model dapat menghasilkan hasil yang konsisten setiap kali dijalankan dengan nilai random_state yang sama.
    Dalam konteks algoritma pembelajaran mesin, seperti pemisahan data menjadi set pelatihan dan pengujian, pengacakan urutan data, atau inisialisasi bobot dalam beberapa model, penggunaan random_state memungkinkan replikabilitas atau reproduktibilitas yang diinginkan. Dengan menetapkan nilai random_state yang sama, kita dapat memastikan bahwa model akan menghasilkan hasil yang serupa setiap kali dijalankan.
    Random_state biasanya dinyatakan dalam bentuk bilangan bulat, dan nilai yang digunakan tidak terlalu penting. Yang penting adalah bahwa nilai random_state yang sama akan menghasilkan hasil yang sama. Namun, penting untuk dicatat bahwa mengubah nilai random_state dapat menghasilkan model yang berbeda, dan dengan demikian, penting untuk melakukan eksperimen dan validasi model menggunakan variasi nilai random_state untuk memahami stabilitas dan performa model secara menyeluruh.
   - Jumlah job : 1
   Jumlah job (n_jobs) adalah parameter yang digunakan dalam Random Forest untuk mengontrol paralelisasi atau penggunaan multiple core atau CPU dalam proses pembangunan pohon keputusan. Random Forest dapat membangun pohon keputusan secara independen dan paralel untuk mempercepat proses pelatihan.
    Nilai n_jobs menentukan berapa banyak pekerjaan yang akan dijalankan secara paralel. Jika n_jobs diatur sebagai -1, maka semua core atau CPU yang tersedia akan digunakan untuk melatih model secara paralel. Jika n_jobs diatur sebagai nilai positif, maka jumlah core atau CPU yang digunakan akan sesuai dengan nilai n_jobs yang ditentukan.
3. Boosting Algorithm
   - Tingkat pembelajaran : 0.05
   Tingkat pembelajaran (learning_rate) adalah parameter yang digunakan dalam algoritma boosting untuk mengontrol seberapa banyak setiap model kecil atau pohon keputusan berkontribusi terhadap model ensemble akhir. Algoritma boosting seperti Gradient Boosting dan AdaBoost membangun model secara iteratif dengan menambahkan model kecil berulang kali ke ensemble.
    Learning rate menentukan seberapa banyak bobot yang diberikan kepada model kecil yang baru ditambahkan ke ensemble pada setiap iterasi. Semakin tinggi learning rate, semakin besar pengaruh model baru dalam memperbaiki kesalahan model sebelumnya. Namun, nilai learning rate yang terlalu tinggi dapat menyebabkan model overfitting pada data pelatihan.
   - Random State : 55
   Random State pada algoritma boosting mengacu pada parameter yang digunakan untuk mengontrol inisialisasi keacakan dalam algoritma. Algoritma boosting, seperti Gradient Boosting dan AdaBoost, melibatkan penggunaan beberapa model kecil yang diiterasi untuk meningkatkan performa model ensemble.
    Random State digunakan untuk menetapkan nilai awal yang tetap dalam inisialisasi keacakan yang terkait dengan algoritma boosting. Dengan menetapkan random_state dengan nilai tertentu, kita dapat memastikan bahwa proses inisialisasi yang melibatkan pengacakan nilai, misalnya dalam memilih subset data atau menentukan inisialisasi bobot, akan menghasilkan hasil yang konsisten setiap kali algoritma dijalankan dengan nilai random_state yang sama.
4. Support Vector Classifier

## Evaluation
Metrik evaluasi yang digunakan dalam proyek ini adalah akurasi, presisi (precision), recall, dan F1-score.

1. Akurasi
Kelebihan utama akurasi adalah memberikan gambaran umum tentang sejauh mana model dapat melakukan prediksi yang benar secara keseluruhan. Metrik ini cocok digunakan ketika kelas positif dan kelas negatif memiliki bobot yang seimbang dalam dataset. Namun, akurasi tidak memberikan informasi rinci tentang jenis kesalahan yang dibuat oleh model. Jika terdapat ketidakseimbangan antara jumlah sampel dalam kelas positif dan kelas negatif, akurasi mungkin menjadi tidak representatif. Dalam kasus tersebut, metrik evaluasi lain seperti presisi, recall, dan F1-score bisa memberikan informasi yang lebih bermanfaat.

Rumus:

Akurasi = $\frac{{\text{{True Positive}} + \text{{True Negative}}}}{{\text{{True Positive}} + \text{{True Negative}} + \text{{False Positive}} + \text{{False Negative}}}}$

2. Presisi(Precision)
Presisi menggambarkan sejauh mana model dapat mengidentifikasi dengan benar kasus positif dari prediksi positif yang dilakukan. Metrik ini penting ketika fokus utama adalah mengurangi kesalahan positif palsu (misclassification yang mengatakan bahwa suatu sampel adalah positif ketika sebenarnya negatif).
Presisi berguna dalam kasus di mana kesalahan positif palsu memiliki konsekuensi yang lebih serius, misalnya dalam sistem deteksi penyakit di mana kesalahan diagnosis positif palsu dapat menyebabkan kecemasan yang tidak perlu atau pengobatan yang tidak perlu.

Rumus:

Precision = $\frac{{\text{{True Positive}}}}{{\text{{True Positive}} + \text{{False Positive}}}}$

3. Recall
Recall (juga dikenal sebagai sensitivitas atau true positive rate) menggambarkan sejauh mana model dapat menemukan atau mengenali kasus positif secara keseluruhan dari semua kasus positif yang ada. Metrik ini penting ketika fokus utama adalah mengurangi kesalahan negatif palsu (misclassification yang mengatakan bahwa suatu sampel adalah negatif ketika sebenarnya positif).
Recall berguna dalam kasus di mana kesalahan negatif palsu memiliki konsekuensi yang lebih serius, misalnya dalam sistem deteksi kejahatan atau deteksi penyakit serius, di mana kesalahan mengabaikan kasus positif dapat berdampak besar.

Rumus:

Recall = $\frac{{\text{{True Positive}}}}{{\text{{True Positive}} + \text{{False Negative}}}}$

4. F1-Score
F1-score adalah harmonik rata-rata presisi dan recall, yang memberikan kompromi antara keduanya. Metrik ini berguna ketika kita ingin menyeimbangkan presisi dan recall secara seimbang, terutama dalam kasus di mana kelas positif dan kelas negatif memiliki distribusi yang tidak seimbang dalam dataset.
F1-score berguna ketika ada ketidakseimbangan antara presisi dan recall yang diinginkan. Misalnya, dalam kasus deteksi spam email, di mana kita ingin meminimalkan kesalahan positif palsu (presisi tinggi) dan kesalahan negatif palsu (recall tinggi) secara bersamaan.

Rumus:

F1-Score = $\frac{{2 \times (\text{{Precision}} \times \text{{Recall}})}}{{\text{{Precision}} + \text{{Recall}}}}$


Tabel 2. Hasil evaluasi

|          | Accuracy Train | Precision Train | Recall Train | F1-Score Train | Accuracy Test | Precision Test | Recall Test | F1-Score Test |
|----------|----------------|-----------------|--------------|----------------|---------------|----------------|-------------|---------------|
| KNN      | 0.926517       | 0.946743        | 0.903595     | 0.924666       | 0.915429      | 0.931892       | 0.899322    | 0.915317      |
| RF       | 0.977048       | 0.998089        | 0.955842     | 0.976509       | 0.946182      | 0.984729       | 0.90819     | 0.944912      |
| Boosting | 0.799057       | 0.826736        | 0.755771     | 0.789662       | 0.800106      | 0.838278       | 0.751695    | 0.792629      |
| SVC      | 0.933854       | 0.979569        | 0.885944     | 0.930407       | 0.927359      | 0.97568        | 0.878978    | 0.924808      |

Dalam analisis model berdasarkan evaluasi yang diberikan, terdapat beberapa metrik yang dipertimbangkan, yaitu akurasi (Accuracy), presisi (Precision), recall (Recall), dan f1-score.

Jika kita fokus pada akurasi, model Random Forest (RF) memiliki akurasi tertinggi pada data train dan data test. Ini menunjukkan kemampuan model untuk secara konsisten melakukan klasifikasi yang akurat pada data train dan test. Jika kita mempertimbangkan presisi dan recall pada data train dan data test, Random Forest memiliki nilai presisi dan recall yang seimbang baik pada data latih maupun data uji. Dalam konteks klasifikasi risiko kredit, penting untuk memiliki presisi yang tinggi (menghindari banyak kesalahan positif) dan recall yang tinggi (menghindari banyak kesalahan negatif). RF memberikan keseimbangan yang baik antara kedua metrik ini.
Selain itu, Random Forest juga memiliki nilai f1-score yang paling tinggi. F1-Score menggabungkan presisi dan recall menjadi satu metrik. RF memberikan skor F1-Score yang baik pada data latih maupun data uji, menunjukkan kemampuannya dalam mengklasifikasikan risiko kredit secara akurat dan seimbang.

Random Forest adalah model ensemble yang menggabungkan beberapa pohon keputusan. Kelebihan dari model ensemble adalah kemampuannya dalam menangani kompleksitas data dan mengurangi overfitting. Dalam klasifikasi risiko kredit, di mana terdapat banyak faktor yang mempengaruhi keputusan, model ensemble seperti RF dapat memberikan performa yang lebih baik daripada model lain yang lebih sederhana. Oleh karena itu lebih baik untuk menggunakan model Random Forest untuk membuat model machine learning klasifikasi yang dapat digunakan untuk mengidentifikasi risiko kredit.

