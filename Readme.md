# Laporan Proyek Machine Learning - Novandri Sitinjak

## Domain Proyek
Bank merupakan lembaga intermediasi yang bertugas menerima simpanan dari nasabah dan meminjamkannya kepada nasabah (unit ekonomi) lain yang membutuhkan dana. Atas simpanan masyarakat, bank memberikan imbalan berupa bunga. Demikian pula, atas pemberian pinjaman (kredit) bank mengenakan bunga kepada para peminjam. Dengan kata lain bank sebagai lembaga keuangan yang berfungsi menghimpun dan menyalurkan dana dari dan ke masyarakat untuk meningkatkan pelayanan kepada para nasabah tanpa mengabaikan etika perbankan[1].

Salah satu kegiatan utama bank adalah menyalurkan dana kepada masyarakat dalam bentuk kredit. Hal ini didasarkan pada kenyataan bahwa perkreditan merupakan aktivitas terbesar pada perbankan. Besarnya jumlah kredit yang disalurkan akan menentukan keuntungan bank. Jika bank tidak mampu menyalurkan kredit sementara dana dari masyarakat banyak disimpan, maka alternative lain bank bisa menyalurkan dananya melalui pasar uang maupun pasar modal. Hal ini dilakukan untuk memperoleh keuntungan yang maksimal. Apabila bank tidak melakukan alternative lain selaain menyalurkan kredit maka bank akan mengalami kerugian, karena harus membayar bunga simpanan kepada masyarakat.

Perkembangan ekonomi yang semakin global tentu membawa peluang dan risiko yang semakin besar. Risiko kredit merupakan masalah besar bagi dunia perbankan, dan lembaga keuangan pada umumnya. Dengan demikian, risiko kredit perlu mendapatkan perhatian yang khusus. Setiap rupiah yang tidak tertagih menjadi kredit macet, yang kemudian menimbulkan biaya penyisihan dalam laporan laba/rugi.

Kredit disamping memberikan sumbangan terbesar terhadap laba, kredit juga merupakan salah satu faktor yang menyebabkan rapuhnya usaha perbankan yaitu dengan tingginya risiko kredit. Risiko terkait dengan adanya ketidakpastian. Risiko kredit ditimbulkan oleh debitur yang secara kredit tidak dapat membayar utang dan memenuhi kewajiban seperti tertuang dalam kesepakatan atau turunnya kualitas debitur atau pembeli sehingga persepsi mengenai kemungkinan gagal bayar semakin tinggi. Risiko kredit perlu dikelola dengan baik karena apabila tidak dikelola dengan baik maka akan mengakibatkan proposi kredit yang bermasalah semakin besar, sehingga akan berdampak pada kondisi perbankan

Pengendalian pada Risiko kredit tentu dilakukan oleh setiap bank. Pengendalian tersebut diantisipasi oleh kualitas suatu sistem manajemen risiko kredit yang baik untuk meminimalkan risiko kredit. Evaluasi kredit yang akurat menjadi sangat penting dan berguna sebagai salah satu input alternative dalam mempertahankan kondisi perbankan agar tetap stabil.

## Business Understanding

Implementasi model klasifikasi risiko kredit yang akurat dapat membantu institusi keuangan mengidentifikasi peluang risiko yang tinggi dan mengambil tindakan yang sesuai untuk mengelola portofolio pinjaman mereka. Dengan memiliki prediksi yang lebih baik tentang risiko kredit, institusi keuangan dapat mengurangi risiko gagal bayar, meningkatkan keuntungan, dan menjaga stabilitas keuangan mereka.

Selain itu, model klasifikasi yang dapat memprediksi risiko kredit dengan akurasi tinggi juga dapat membantu dalam pengambilan keputusan yang lebih baik dan efisien. Institusi keuangan dapat menggunakan hasil prediksi model untuk menentukan tingkat bunga, persyaratan pinjaman, atau memutuskan apakah suatu pengajuan pinjaman harus disetujui atau ditolak.

Namun, penting untuk diingat bahwa meskipun model klasifikasi dapat memberikan panduan dan rekomendasi yang berharga, keputusan akhir harus didasarkan pada evaluasi yang cermat oleh analis risiko yang berkualifikasi. Model hanya menjadi alat bantu untuk menginformasikan keputusan, dan manusia tetap memiliki peran penting dalam proses pengambilan keputusan.

Dengan pemahaman yang baik tentang kebutuhan bisnis dan implementasi yang tepat, pengembangan model klasifikasi risiko kredit yang efektif dapat memberikan manfaat yang signifikan bagi institusi keuangan dalam pengelolaan risiko dan pengambilan keputusan yang lebih baik.

### Problem Statements
1. Bagaimana mengembangkan model klasifikasi yang dapat memprediksi risiko kredit dengan akurasi, presisi, _recall_, dan _f1-score_ minimal 88% ?

### Goals
1. mengembangkan model klasifikasi yang dapat memprediksi risiko kredit dengan akurasi, presisi, _recall_, dan _f1-score_ minimal 88% .

### Solution Statement
   Ketiga model klasifikasi yang dipilih, yaitu _K-Nearest Neighbor_ (KNN), _Random Forest_, dan _Support Vector Classifier_ (SVC).
   - _K-Nearest Neighbor_ (KNN):
   KNN adalah algoritma yang menggunakan data latihan terdekat dalam ruang fitur untuk memprediksi kelas dari data uji. Dalam konteks risiko kredit, KNN dapat digunakan untuk mencari pola atau kemiripan antara pengajuan pinjaman baru dengan pinjaman yang sudah ada. Model KNN dapat mengklasifikasikan pengajuan pinjaman baru sebagai risiko kredit tinggi jika memiliki tetangga yang sebagian besar memiliki riwayat kredit yang buruk.
   - _Random Forest_:
   _Random Forest_ adalah algoritma _ensemble_ yang menggabungkan beberapa pohon keputusan untuk menghasilkan prediksi akurat. Dalam kasus risiko kredit, Random Forest dapat mengevaluasi berbagai fitur seperti usia, pendapatan, riwayat kredit, dan lainnya untuk mengklasifikasikan pengajuan pinjaman baru sebagai risiko kredit rendah atau tinggi. Keunggulan _Random Forest_ adalah dapat menangani variabel numerik dan kategorikal, serta mampu mengatasi _overfitting_.
   - _Support Vector Classifier_ (SVC):
   SVC adalah algoritma yang membangun _hyperplane_ atau sekumpulan hyperplane untuk melakukan klasifikasi. Dalam kasus risiko kredit, SVC dapat membangun pemisah antara pengajuan pinjaman yang berpotensi risiko tinggi dan rendah berdasarkan fitur-fitur yang relevan. Keunggulan SVC adalah dapat mengatasi masalah data yang tidak linier, sehingga cocok untuk mengklasifikasikan risiko kredit yang kompleks.

 KNN dapat mengidentifikasi pola berdasarkan kemiripan data, _Random Forest_ memiliki kemampuan untuk menangani variabel numerik dan kategorikal serta menghindari _overfitting_, dan SVC dapat mengatasi masalah data yang tidak linier.
 
 Dengan menggunakan kombinasi ketiga model ini, dapat dimanfaatkan keunggulan masing-masing model dan meningkatkan akurasi serta kinerja dalam mengidentifikasi risiko kredit.

## Data Understanding
Dataset yang digunakan dalam proyek ini adalah Credit Risk Dataset yang berisi informasi tentang data riwayat pinjaman dan status kredit. Dataset ini dapat diunduh dari [kaggle](https://www.kaggle.com/datasets/laotse/credit-risk-dataset). Dataset ini memiliki 12 variabel dan 32581 baris data, berikut variabel-variabel yang terdapat pada dataset.

__Tabel 1 variabel dan deskripsi data.__

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

### _Data Cleaning_

__Tabel 2. Data bernilai null sebelum dibersihkan__

|          variabel          | Jumlah Baris yang Berisi Data Null |
|:--------------------------:|:----------------------------------:|
| person_age                 |                  0                 |
| person_income              |                  0                 |
| person_home_ownership      |                  0                 |
| person_emp_length          |                 895                |
| loan_intent                |                  0                 |
| loan_grade                 |                  0                 |
| loan_amnt                  |                  0                 |
| loan_int_rate              |                3116                |
| loan_status                |                  0                 |
| loan_percent_income        |                  0                 |
| cb_person_default_on_file  |                  0                 |
| cb_preson_cred_hist_length |                  0                 |

Terdapat data yang bernilai null pada kolom person_emp_length dan loan_int_rate sehingga perlu menghapus baris yang bernilai null.

__Tabel 3. Deskripsi data__

|index|person\_age|person\_income|person\_emp\_length|loan\_amnt|loan\_int\_rate|loan\_status|loan\_percent\_income|cb\_person\_cred\_hist\_length|
|---|---|---|---|---|---|---|---|---|
|count|28638\.0|28638\.0|28638\.0|28638\.0|28638\.0|28638\.0|28638\.0|28638\.0|
|mean|27\.727215587680703|66649\.37188351141|4\.788672393323556|9656\.493121028005|11\.039866610796844|0\.21660032125148404|0\.1694880927439067|5\.793735596061177|
|std|6\.310440916909462|62356\.44740470853|4\.154626670183479|6329\.683360684426|3\.2293717597794616|0\.4119351252907461|0\.10639251098884496|4\.038482503165891|
|min|20\.0|4000\.0|0\.0|500\.0|5\.42|0\.0|0\.0|2\.0|
|25%|23\.0|39480\.0|2\.0|5000\.0|7\.9|0\.0|0\.09|3\.0|
|50%|26\.0|55956\.0|4\.0|8000\.0|10\.99|0\.0|0\.15|4\.0|
|75%|30\.0|80000\.0|7\.0|12500\.0|13\.48|0\.0|0\.23|8\.0|
|max|144\.0|6000000\.0|123\.0|35000\.0|23\.22|1\.0|0\.83|30\.0|

Dari hasil fungsi describe(), nilai minimum untuk kolom "loan_percent_income" adalah 0. "loan_percent_income" merupakan presentase pendapatan tahunan peminjam terhadap cicilan pinjaman sehingga tidak mungkin ada yang bernilai 0 jika tidak ada "loan_amnt" atau jumlah pinjaman yang bernilai 0. Dilakukan pengecekan ada berapa missing value pada kolom "loan_percent_income", terdapat 8 sampel missing value yang merupakan jumlah yang kecil dibandingkan total sampel. Oleh karena itu missing value tersebut dihapus. Setelah baris bernilai 0 dihapus, jumlah sampel atau baris data berubah menjadi 28638.

### _Handling Outlier_

<img width="491" alt="person_age" src="https://github.com/novandristnjk/laporan-ml-terapan/assets/110597813/81e1e21b-0eeb-413a-bac0-453e7c7556b7">

__Gambar 1. _Boxplot_ variabel "person_age"__

<img width="491" alt="person_emp_length" src="https://github.com/novandristnjk/laporan-ml-terapan/assets/110597813/b001a497-4869-465a-896e-8b4c84dc31ff">

__Gambar 2. _Boxplot_ variabel "person_emp_length"__

<img width="491" alt="loan_amnt" src="https://github.com/novandristnjk/laporan-ml-terapan/assets/110597813/6817e0c1-0ddc-4787-99aa-9986e8fc3aaa">

__Gambar 3. _Boxplot_ variabel "loan_amnt"__

<img width="491" alt="person_income" src="https://github.com/novandristnjk/laporan-ml-terapan/assets/110597813/f27af1d0-635b-4c0d-926b-4f8ccd45f799">

__Gambar 4. _Boxplo_t variabel "loan_percent_income"___

dapat dilihat, pada beberapa fitur numerik di atas terdapat outliers. Outliers diidentifikasi menggunakan metode IQR  dan dihapus baris yang mengandung outliers.

### _Feature Encoding_
Terdapat empat variabel kategori dalam dataset, yaitu "person_home_ownership", "loan_grade", "loan_intent", dan "cb_person_default_on_file". Pada variabel "loan_grade" dan "cb_person_default_on_file" digunakan teknik LabelEncoding, karena kedua variabel tersebut memiliki tingkatan atau urutan yang terkait. Pada variabel "person_home_ownership" dan "loan_intent" digunakan teknik OneHotEncoding, karena kedua variabel tersebut tidak memiliki tingkatan atau urutan yang terkait.

### Balancing Dataset

<img width="491" alt="loan_status_distribution" src="https://github.com/novandristnjk/laporan-ml-terapan/assets/110597813/8363633a-7521-4f58-ba40-5f7c3590e36d">

__Gambar 5. Perbandingan nilai 0 dan 1 pada fitur targer "loan_status"__

Dapat dilihat bahwa terjadi ketidakseimbangan data pada fitur target "loan_status", dimana nilai sangat jauh lebih banyak dibanding nilai 1. Ketidakseimbangan dataset dapat menghasilkan model yang tidak optimal dan bias terhadap kelas mayoritas. Untuk menyeimbangkan dataset dilakukan oversampling menggunakan metode _SMOTE_ dengan menggandakan sampel pada fitur "loan_status"  yang bernilai 1. _SMOTE_ bekerja dengan menciptakan sampel sintetis baru untuk kelas minoritas dengan menggunakan teknik interpolasi antara sampel yang sudah ada dalam kelas minoritas. Oversampling dipilih karena jika menggunakan metode undersampling, maka jumlah akan berkurang sangat besar sehingga dapat kehilangan informasi dari data yang dihilangkan.

### _Train-Test Splitting_
Memisahkan data menjadi data latihan (_train_) dan data uji (_test_) dengan perbandingan 90:10.

## Modeling
Pada tahap ini digunakan tiga model untuk mengklasifikasikan loan status, yaitu _K-Nearest Neighbor_, _Random Forest Classifier_, dan _Support Vector Classifier_.
1. _K-Nearest Neighbor_:
   - Jumlah tetangga : 10
  Jumlah tetangga dalam _K-Nearest Neighbors_ (KNN) adalah parameter yang digunakan untuk menentukan jumlah tetangga terdekat yang akan digunakan dalam proses klasifikasi atau regresi. KNN adalah sebuah algoritma pembelajaran mesin yang digunakan untuk melakukan klasifikasi atau regresi berdasarkan kumpulan data yang ada di sekitarnya. Dalam KNN, ketika akan mengklasifikasikan atau meramalkan label dari sebuah sampel data yang belum diketahui, algoritma mencari _k-nearest neighbors_ dari sampel tersebut berdasarkan jarak _euclidean_ atau metrik jarak lainnya. Jumlah tetangga menentukan berapa banyak tetangga terdekat yang akan digunakan dalam proses ini.

2. _Random Forest Classifier_
   - Jumlah pohon : 50
   Jumlah pohon pada _Random Forest_ adalah parameter yang menentukan berapa banyak pohon keputusan yang akan digunakan dalam _ensemble_. _Random Forest_ adalah sebuah algoritma pembelajaran mesin yang menggabungkan beberapa pohon keputusan untuk melakukan klasifikasi atau regresi. Dalam _Random Forest_, setiap pohon keputusan dibangun secara independen dengan menggunakan subset acak dari data pelatihan. Jumlah pohon mengontrol berapa banyak pohon keputusan yang akan dibangun dalam _ensemble_. Semakin banyak pohon yang digunakan, semakin kompleks modelnya. Jumlah pohon yang lebih besar cenderung memberikan model yang lebih kuat dan lebih mampu menangkap hubungan yang kompleks dalam data. Namun, terlalu banyak pohon juga dapat menyebabkan _overfitting_, di mana model "menghafal" data pelatihan tetapi tidak umum untuk data yang tidak dilihat sebelumnya.
   - Kedalaman maksimum pohon : 16
   Kedalaman maksimum pohon adalah parameter yang digunakan dalam pohon keputusan dan beberapa algoritma berbasis pohon lainnya, seperti _Random Forest_. _Max_depth_ menentukan seberapa dalam pohon keputusan dapat tumbuh dengan membatasi jumlah tingkat atau simpul dalam pohon.
    Ketika membangun pohon keputusan, algoritma akan membagi setiap simpul berdasarkan fitur dan ambil keputusan berdasarkan kriteria yang ditentukan, seperti gain informasi atau _gini impurity_. Dengan setiap pembagian, pohon tumbuh lebih dalam dengan menambahkan tingkat baru. Kedalaman maksimum pohon mengatur seberapa banyak tingkat yang diizinkan dalam pohon tersebut.
    Membatasi kedalaman maksimum pohon adalah langkah yang penting untuk mencegah _overfitting_. Jika pohon memiliki kedalaman yang sangat besar, ia dapat dengan mudah "menghafal" data pelatihan dengan sangat spesifik, tetapi akan cenderung tidak mampu melakukan generalisasi dengan baik pada data baru. Dalam kasus tersebut, model akan terlalu kompleks dan sensitif terhadap noise atau variasi kecil dalam data pelatihan.
   - Random State : 55
   _Random State_ adalah parameter yang digunakan dalam algoritma pembelajaran mesin untuk mengontrol randomization atau keacakan yang terkait dengan model. Ketika model menggunakan algoritma yang melibatkan elemen keacakan, seperti inisialisasi bobot, pembagian data, atau pembangunan model, random_state memungkinkan pengguna untuk menetapkan nilai awal yang tetap sehingga model dapat menghasilkan hasil yang konsisten setiap kali dijalankan dengan nilai random_state yang sama.
    Dalam konteks algoritma pembelajaran mesin, seperti pemisahan data menjadi set pelatihan dan pengujian, pengacakan urutan data, atau inisialisasi bobot dalam beberapa model, penggunaan _random_state_ memungkinkan replikabilitas atau reproduktibilitas yang diinginkan. Dengan menetapkan nilai random_state yang sama, kita dapat memastikan bahwa model akan menghasilkan hasil yang serupa setiap kali dijalankan.
    _Random_state_ biasanya dinyatakan dalam bentuk bilangan bulat, dan nilai yang digunakan tidak terlalu penting. Yang penting adalah bahwa nilai _random_state_ yang sama akan menghasilkan hasil yang sama. Namun, penting untuk dicatat bahwa mengubah nilai _random_state_ dapat menghasilkan model yang berbeda, dan dengan demikian, penting untuk melakukan eksperimen dan validasi model menggunakan variasi nilai random_state untuk memahami stabilitas dan performa model secara menyeluruh.
   - Jumlah _job_ : 1
   Jumlah _job_ (_n_jobs_) adalah parameter yang digunakan dalam _Random Forest_ untuk mengontrol paralelisasi atau penggunaan _multiple core_ atau CPU dalam proses pembangunan pohon keputusan. _Random Forest_ dapat membangun pohon keputusan secara independen dan paralel untuk mempercepat proses pelatihan.
    Nilai _n_jobs_ menentukan berapa banyak pekerjaan yang akan dijalankan secara paralel. Jika _n_jobs_ diatur sebagai -1, maka semua core atau CPU yang tersedia akan digunakan untuk melatih model secara paralel. Jika n_jobs diatur sebagai nilai positif, maka jumlah core atau CPU yang digunakan akan sesuai dengan nilai n_jobs yang ditentukan.
3. _Support Vector Classifier_

   -Support Vector Classifier adalah sebuah algoritma pembelajaran mesin yang digunakan untuk melakukan klasifikasi pada data yang terstruktur. SVC adalah salah satu bentuk dari metode Support Vector Machines (SVM) yang populer.
   Pada dasarnya, model SVC membangun sebuah hiperplane dalam ruang fitur (feature space) yang memaksimalkan jarak antara dua kelas data yang berbeda. Hiperplane ini digunakan untuk memisahkan data menjadi dua kelas berdasarkan atribut atau fitur yang diberikan. Tujuan utama dari SVC adalah menemukan hiperplane yang dapat memaksimalkan margin, yaitu jarak terdekat antara hiperplane dan titik-titik data dari kelas yang berbeda.

## Evaluation
Metrik evaluasi yang digunakan dalam proyek ini adalah akurasi, presisi (_precision_), _recall_, dan _F1-score_.

### Akurasi
Kelebihan utama akurasi adalah memberikan gambaran umum tentang sejauh mana model dapat melakukan prediksi yang benar secara keseluruhan. Metrik ini cocok digunakan ketika kelas positif dan kelas negatif memiliki bobot yang seimbang dalam dataset. Namun, akurasi tidak memberikan informasi rinci tentang jenis kesalahan yang dibuat oleh model. Jika terdapat ketidakseimbangan antara jumlah sampel dalam kelas positif dan kelas negatif, akurasi mungkin menjadi tidak representatif. Dalam kasus tersebut, metrik evaluasi lain seperti presisi, _recall_, dan _F1-score_ bisa memberikan informasi yang lebih bermanfaat.

Rumus:

Akurasi = $\frac{{\text{{True Positive}} + \text{{True Negative}}}}{{\text{{True Positive}} + \text{{True Negative}} + \text{{False Positive}} + \text{{False Negative}}}}$

### Presisi(_Precision_)
Presisi menggambarkan sejauh mana model dapat mengidentifikasi dengan benar kasus positif dari prediksi positif yang dilakukan. Metrik ini penting ketika fokus utama adalah mengurangi kesalahan positif palsu (_misclassification_ yang mengatakan bahwa suatu sampel adalah positif ketika sebenarnya negatif).
Presisi berguna dalam kasus di mana kesalahan positif palsu memiliki konsekuensi yang lebih serius, misalnya dalam sistem deteksi penyakit di mana kesalahan diagnosis positif palsu dapat menyebabkan kecemasan yang tidak perlu atau pengobatan yang tidak perlu.

Rumus:

Precision = $\frac{{\text{{True Positive}}}}{{\text{{True Positive}} + \text{{False Positive}}}}$

### _Recall_
_Recall_ (juga dikenal sebagai sensitivitas atau _true positive rate_) menggambarkan sejauh mana model dapat menemukan atau mengenali kasus positif secara keseluruhan dari semua kasus positif yang ada. Metrik ini penting ketika fokus utama adalah mengurangi kesalahan negatif palsu (_misclassification_ yang mengatakan bahwa suatu sampel adalah negatif ketika sebenarnya positif).
Recall berguna dalam kasus di mana kesalahan negatif palsu memiliki konsekuensi yang lebih serius, misalnya dalam sistem deteksi kejahatan atau deteksi penyakit serius, di mana kesalahan mengabaikan kasus positif dapat berdampak besar.

Rumus:

Recall = $\frac{{\text{{True Positive}}}}{{\text{{True Positive}} + \text{{False Negative}}}}$

### _F1-Score_
_F1-score_ adalah harmonik rata-rata presisi dan _recall_, yang memberikan kompromi antara keduanya. Metrik ini berguna ketika kita ingin menyeimbangkan presisi dan _recall_ secara seimbang, terutama dalam kasus di mana kelas positif dan kelas negatif memiliki distribusi yang tidak seimbang dalam dataset.
_F1-score_ berguna ketika ada ketidakseimbangan antara presisi dan recall yang diinginkan. Misalnya, dalam kasus deteksi spam email, di mana kita ingin meminimalkan kesalahan positif palsu (presisi tinggi) dan kesalahan negatif palsu (_recall_ tinggi) secara bersamaan.

Rumus:

F1-Score = $\frac{{2 \times (\text{{Precision}} \times \text{{Recall}})}}{{\text{{Precision}} + \text{{Recall}}}}$

__Tabel 4. Hasil evaluasi__

| Model | Accuracy Train | Precision Train | Recall Train | F1 Score Train | Accuracy Test | Precision Test | Recall Test | F1 Score Test |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| KNN | 0.93 | 0.95 | 0.90 | 0.92 | 0.91 | 0.93 | 0.89 | 0.91 |
| RF | 0.98 | 0.99 | 0.96 | 0.98 | 0.95 | 0.99 | 0.91 | 0.95 |
| SVC | 0.93 | 0.98 | 0.89 | 0.93 | 0.93 | 0.98 | 0.88 | 0.92 |

Dari hasil evaluasi, dapat dilihat bahwa model klasifikasi yang dibuat sudah baik dan  sudah cukup layak digunakan. Ketiga model baik model KNN, _Random Forest_, dan _Support Vector Machine_ memiliki akurasi, presisi, recall, dan f1-score minimal 88%.

Jika fokus pada akurasi, model _Random Forest_ (RF) memiliki akurasi tertinggi pada data train dan data test. Ini menunjukkan kemampuan model untuk secara konsisten melakukan klasifikasi yang akurat pada data _train_ dan _test_. Jika kita mempertimbangkan presisi dan _recall_ pada data _train_ dan data _test_, _Random Forest_ memiliki nilai presisi dan _recall_ yang seimbang baik pada data latih maupun data uji. Dalam konteks klasifikasi risiko kredit, penting untuk memiliki presisi yang tinggi (menghindari banyak kesalahan positif) dan recall yang tinggi (menghindari banyak kesalahan negatif). RF memberikan keseimbangan yang baik antara kedua metrik ini.
Selain itu, _Random Forest juga_ memiliki nilai _f1-score_ yang paling tinggi. _F1-Score_ menggabungkan presisi dan _recall_ menjadi satu metrik. RF memberikan skor _F1-Score_ yang baik pada data latih maupun data uji, menunjukkan kemampuannya dalam mengklasifikasikan risiko kredit secara akurat dan seimbang.

_Random Forest_ adalah model ensemble yang menggabungkan beberapa pohon keputusan. Kelebihan dari model ensemble adalah kemampuannya dalam menangani kompleksitas data dan mengurangi _overfitting_. Dalam klasifikasi risiko kredit, di mana terdapat banyak faktor yang mempengaruhi keputusan, model _ensemble_ seperti RF dapat memberikan performa yang lebih baik daripada model lain yang lebih sederhana. Oleh karena itu lebih baik untuk menggunakan model _Random Forest_ untuk membuat model _machine learning_ klasifikasi yang dapat digunakan untuk mengidentifikasi risiko kredit.

## Conclusion

Bank merupakan lembaga intermediasi yang bertugas menerima simpanan dari nasabah dan meminjamkannya kepada nasabah (unit ekonomi) lain yang membutuhkan dana. Atas simpanan masyarakat, bank memberikan imbalan berupa bunga. Demikian pula, atas pemberian pinjaman (kredit) bank mengenakan bunga kepada para peminjam. Kredit disamping memberikan sumbangan terbesar terhadap laba, kredit juga merupakan salah satu faktor yang menyebabkan rapuhnya usaha perbankan yaitu dengan tingginya risiko kredit. Implementasi model klasifikasi risiko kredit yang akurat dapat membantu institusi keuangan mengidentifikasi peluang risiko yang tinggi dan mengambil tindakan yang sesuai untuk mengelola portofolio pinjaman mereka. Oleh karena itu perlu dikembangkan model klasifikasi dapat memprediksi risiko kredit dengan akurasi, presisi, recall, dan f1-score minimal 88%. Dengan memiliki prediksi yang lebih baik tentang risiko kredit, institusi keuangan dapat mengurangi risiko gagal bayar, meningkatkan keuntungan, dan menjaga stabilitas keuangan mereka.

Adapun ketiga model klasifikasi yang dipilih, yaitu K-Nearest Neighbor (KNN), Random Forest, Boosting Algorithm, dan Support Vector Classifier (SVC). KNN dapat mengidentifikasi pola berdasarkan kemiripan data, Random Forest memiliki kemampuan untuk menangani variabel numerik dan kategorikal serta menghindari overfitting, dan SVC dapat mengatasi masalah data yang tidak linier. Dengan menggunakan kombinasi ketiga model ini, dapat dimanfaatkan keunggulan masing-masing model dan meningkatkan akurasi serta kinerja dalam mengidentifikasi risiko kredit.

Dataset yang digunakan dalam proyek ini adalah Credit Risk Dataset yang berisi informasi tentang data riwayat pinjaman dan status kredit. Dataset ini dapat diunduh dari kaggle. Dataset ini memiliki 12 variabel dan 32581 baris data, dimana variabelnya terdiri dari person_age, person_income, person_home_ownership, person_emp_length, loan_intent, loan_grade, loan_amnt, loan_int_rate, loan_status, loan_percent_income, cb_person_default_on_file, dan cb_preson_cred_hist_length.

Sebelum data digunakan, terlebih dahulu dilakukan tahap dapat data preparation. Pada tahap ini ditemukan bahwa terdapat data yang bernilai null atau tidak valid, oleh karena itu data yang bernilai null atau tidak valid dihapus. selain itu dilakukan pengecekan outlier menggunakan metode IQR, ternyata data mengandung outlier dan dilakukan penghapusan outlier pada data. Selanjutnya dilakukan feature encoding untuk mengubah fitur categorical menjadi representasi numerik yang dapat dipahami oleh algoritma pemodelan. Selain itu pada fitu target loan_status ditemukan terjadi ketidakseimbangan data, dimana nilai sangat jauh lebih banyak dibanding nilai 1. ntuk menyeimbangkan dataset dilakukan oversampling menggunakan metode SMOTE dengan menggandakan sampel pada fitur "loan_status" yang bernilai 1. Selanjutnya pada tahap train-test splitting

Dalam pembentukan model, digunakan empat model untuk mengklasifikasikan loan status, yaitu K-Nearest Neighbor, Random Forest Classifier, dan Support Vector Classifier. Metrik evaluasi yang digunakan dalam proyek ini adalah akurasi, presisi (precision), recall, dan F1-score. Dari hasil evaluasi, dapat dilihat bahwa model klasifikasi yang dibuat sudah baik dan sudah cukup layak digunakan. Ketiga model baik model KNN, Random Forest, dan Support Vector Machine memiliki akurasi, presisi, recall, dan f1-score minimal 88%. Namun dari ketiga model Random Forest (RF) memiliki performa yang lebih baik dibandingkan dengan model KNN dan SVC. Model RF memiliki akurasi yang tinggi, serta precision, recall, dan f1-score yang seimbang baik pada data train maupun test.  

## Reference

[1]   IBI, "Manajemen Risiko 2 Mengidentifikasi Risiko, Likuiditas, Reputasi, Hukum, Kepatuhan, Dan Strategik Bank". _Gramedia Pustaka Utama, 2015_.

[2]   M. Desda, Yurasti "Analisis Penerapan Manajemen Risiko Kredit Dalam Meminimalisir Kredit Bermasalah Pada PT. BPR Swadaya Anak Nagari Bandarejo Simpang Empat Periode 2013-2018". _J. MBIA. Vol. 18., no. 1, 2019_.

[3]   T. Getahun, L. Anwen, dan M. S. Bari"MCredit Risk Management and Its Impact on Performance of Commercial Banks: In of Case Ethiopia ". _J. Finance. Accounting. Vol. 04., no. 16, 2016_.
