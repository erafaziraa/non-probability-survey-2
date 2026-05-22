# Analisis Tingkat Kepuasan Pengguna Layanan Keuangan Digital (E-Wallet dan Mobile Banking) dalam Mendukung Kebutuhan Sehari-hari Mahasiswa FMIPA Universitas Mataram
## Latar Belakang
Perkembangan teknologi digital telah membawa perubahan besar dalam sistem transaksi keuangan melalui hadirnya layanan seperti E-Wallet dan Mobile Banking. Layanan ini memberikan kemudahan dalam melakukan transaksi secara cepat, praktis, dan efisien sehingga penggunaannya terus meningkat di berbagai kalangan masyarakat, terutama mahasiswa yang cenderung adaptif terhadap perkembangan teknologi. Kemudahan akses melalui smartphone menjadikan layanan keuangan digital semakin diminati dalam aktivitas sehari-hari.

Mahasiswa memanfaatkan layanan keuangan digital untuk berbagai kebutuhan, seperti pembayaran makanan, transportasi, pembelian pulsa dan paket data, pembayaran tagihan, hingga transaksi akademik. Selain praktis, layanan E-Wallet dan Mobile Banking juga menawarkan berbagai fitur pendukung seperti kemudahan top up saldo, integrasi dengan berbagai layanan, serta proses transaksi yang cepat. Hal tersebut membuat layanan keuangan digital menjadi alternatif utama dibandingkan penggunaan uang tunai.

Di lingkungan FMIPA Universitas Mataram, penggunaan layanan keuangan digital juga berkembang cukup pesat untuk menunjang aktivitas sehari-hari mahasiswa. Namun, tingkat kepuasan pengguna terhadap layanan tersebut dapat berbeda-beda, dipengaruhi oleh aspek kemudahan penggunaan, keamanan, kecepatan transaksi, dan kenyamanan aplikasi. Tingkat kepuasan pengguna menjadi indikator penting dalam menilai kualitas layanan keuangan digital karena dapat memengaruhi keberlanjutan penggunaan layanan tersebut dalam kehidupan sehari-hari mahasiswa.

Penelitian ini bertujuan untuk mengetahui tingkat kepuasan mahasiswa FMIPA Universitas Mataram terhadap penggunaan layanan keuangan digital, khususnya E-Wallet dan Mobile Banking. Selain itu, penelitian ini juga memberikan gambaran mengenai peran layanan tersebut dalam mendukung kebutuhan harian mahasiswa. Data diperoleh melalui survei daring dengan teknik non probability sampling dengan metode purposive sampling, sehingga hasil penelitian diharapkan mampu memberikan informasi deskriptif terkait perilaku serta tingkat kepuasan pengguna layanan keuangan digital di lingkungan mahasiswa FMIPA Universitas Mataram.

## Tujuan
1.	Mengetahui tingkat kepuasan mahasiswa FMIPA Universitas Mataram terhadap penggunaan layanan keuangan digital.  
2.	Menentukan jumlah sampel penelitian menggunakan rumus Slovin. 
3.	Menguji validitas dan reliabilitas instrumen kuisioner yang digunakan dalam penelitian.
4.	Membandingkan hasil estimasi menggunakan metode naive estimator dan weighted estimator dalam mengukur tingkat kepuasan responden.

## Metode
Penelitian ini merupakan penelitian kuantitatif dengan pendekatan survei online. Data diperoleh melalui penyebaran kuesioner menggunakan Google Form kepada mahasiswa FMIPA Universitas Mataram mengenai penggunaan layanan keuangan digital, seperti E-Wallet dan Mobile Banking.

Teknik sampling yang digunakan adalah non probability sampling dengan metode convenience sampling, yaitu pengambilan sampel berdasarkan kemudahan dalam memperoleh responden. Penentuan jumlah sampel dilakukan menggunakan rumus Slovin dengan tingkat kesalahan sebesar 15%. Jumlah responden yang digunakan dalam penelitian ini sebanyak 44 mahasiswa.

Instrumen penelitian yang digunakan berupa kuesioner dengan beberapa item pertanyaan terkait tingkat kepuasan dan penggunaan layanan keuangan digital. Sebelum dilakukan analisis data, instrumen penelitian diuji terlebih dahulu menggunakan uji validitas dan uji reliabilitas untuk memastikan bahwa kuesioner layak digunakan dalam penelitian. 

Pengolahan data dilakukan menggunakan bahasa pemrograman R. Tahapan analisis meliputi penentuan jumlah sampel menggunakan rumus Slovin, uji validitas, dan uji reliabilitas terhadap instrumen penelitian yang digunakan.

## Tahap Analisis Data
###	Menentukan Jumlah Sampel dengan Rumus Slovin
Tahap ini dilakukan untuk menentukan jumlah sampel penelitian berdasarkan jumlah populasi dan tingkat kesalahan tertentu. Perhitungan dilakukan menggunakan rumus Slovin dengan tingkat kesalahan sebesar 15%.
 ```r
N <- 1693
e <- 0.15
n <- ceiling(N / (1 + N * e^2))
cat("Jumlah sampel berdasarkan rumus Slovin =", n)
 ```
###	Import Data Kuesioner
Tahap ini dilakukan untuk memasukkan data hasil kuesioner ke dalam R. Data diimport dari file yang telah disiapkan agar dapat digunakan pada proses analisis selanjutnya.

```r
library(readxl)
data_kuesioner <- read_excel("C:/Users/ACER/OneDrive/Documents/DATA TEKSAM.xlsx")
View(data_kuesioner)
```
###	Uji Validitas Instrumen Penelitian
Uji validitas dilakukan untuk mengetahui apakah setiap item pertanyaan pada kuesioner mampu mengukur variabel penelitian dengan baik. Pengujian dilakukan dengan melihat nilai corrected item-total correlation (r.drop) pada setiap item pertanyaan.

```r
install.packages("psych")
library(psych)
hasil <- alpha(data_kuisioner)
hasil
hasil$item.stats
```
###	Uji Reliabilitas Instrumen Penelitian
Uji reliabilitas dilakukan untuk mengetahui tingkat konsistensi instrumen penelitian. Pengujian dilakukan menggunakan metode Cronbach’s Alpha untuk melihat apakah kuesioner reliabel atau tidak.

```r
hasil_baru$total$raw_alpha
```
### Analisis Deskriptif
Tahap ini dilakukan untuk analisis deskriptif menggunakan R dengan menghitung frekuensi dan persentase pada variabel data responden guna mengetahui sebaran data responden.
```r
table(data$`Jenis Kelamin`)
prop.table(table(data$`Jenis Kelamin`)) * 100
```
### Tabel Distribusi Frekuensi dan Persentase
Tahap ini dilakukan untuk menyajikan hasil analisis dalam bentuk tabel distribusi frekuensi dan persentase agar memudahkan dalam melihat sebaran data pada setiap kategori variabel.
```r
frekuensi <- table(data_kuesioner1$`Jenis Kelamin`)
frekuensi

persentase <- prop.table(frekuensi) * 100
persentase

tabel_jenis_kelamin <- data.frame(
  Jenis_Kelamin = names(frekuensi),
  Frekuensi = as.vector(frekuensi),
  Persentase = round(as.vector(persentase), 2)
)
tabel_jenis_kelamin
```
### Grafik Distribusi Responden
Tahap ini dilakukan untuk menyajikan data dalam bentuk grafik distribusi responden agar sebaran setiap kategori variabel dapat terlihat lebih jelas dan mudah dipahami.
```r
barplot(
  table(data_kuesioner1$`Jenis Kelamin`),
  main = "Distribusi Responden Berdasarkan Jenis Kelamin"
)

frekuensi_usia <- table(data_kuesioner1$Usia)

barplot(
  frekuensi_usia,
  main = "Distribusi Responden Berdasarkan Usia",
  xlab = "Usia",
  ylab = "Frekuensi",
  col = "grey"
)
```
### Naive Estimation
Tahap ini dilakukan untuk menghitung naive estimation sebagai nilai pembanding dasar dalam pemodelan, yaitu dengan mengasumsikan kelas mayoritas sebagai hasil prediksi utama tanpa mempertimbangkan variabel lain.
```r
kepuasan_total <- rowMeans(data_kuesioner1[, c("P1","P2","P3","P4","P5","P6","P7","P8","P9","P10")], na.rm = TRUE)

puas <- sum(kepuasan_total >= 4, na.rm = TRUE)
puas

n <- sum(!is.na(kepuasan_total))

estimasi_puas <- puas / n
estimasi_puas
estimasi_puas * 100
```
### Weighting Sederhana Berdasarkan Jenis Kelamin
Tahap ini dilakukan untuk memberikan pembobotan sederhana berdasarkan variabel jenis kelamin guna menyeimbangkan pengaruh masing-masing kategori dalam analisis data.
```r
proporsi_laki <- 0.5
proporsi_perempuan <- 0.5

sampel_laki <- 0.2727273
sampel_perempuan <- 0.7272727

w_laki <- proporsi_laki / sampel_laki
w_perempuan <- proporsi_perempuan / sampel_perempuan

w_laki
w_perempuan

# Jumlah responden puas berdasarkan jenis kelamin
table(data_kuesioner1$`Jenis Kelamin`, kepuasan_total >= 4)

puas_laki <- 11
puas_perempuan <- 22

# Perhitungan weighted estimation
weighted_laki <- puas_laki * w_laki
weighted_perempuan <- puas_perempuan * w_perempuan

total_weighted <- weighted_laki + weighted_perempuan

weighted_estimation <- total_weighted / n

weighted_estimation
weighted_estimation * 100
```
### Perbandingan Naive dan Weighted Estimation
Tahap ini dilakukan untuk membandingkan hasil naive estimation dengan weighted estimation guna melihat perbedaan hasil sebelum dan sesudah pemberian pembobotan pada data.
```r
naive <- puas / n

estimasi <- c(
  Naive = naive * 100,
  Weighted = weighted_estimation * 100
)

barplot(
  estimasi,
  main = "Perbandingan Hasil Estimasi",
  ylab = "Persentase",
  col = c("skyblue", "blue")
)
```

## Hasil dan Pembahasan
### Jumlah Sampel dengan Rumus Slovin
Penentuan jumlah sampel dalam penelitian ini dilakukan menggunakan rumus Slovin dengan bantuan software R. Jumlah populasi dalam penelitian ini adalah sebanyak 1.693 mahasiswa FMIPA Universitas Mataram, dengan tingkat kesalahan (error) yang digunakan sebesar 0,15.

Berdasarkan hasil perhitungan, diperoleh jumlah sampel penelitian sebanyak 44 responden. Dengan demikian, jumlah sampel yang digunakan dalam penelitian ini adalah 44 responden, dan jumlah tersebut dinilai telah representatif untuk mewakili populasi penelitian.
### Uji Validitas Instrumen Penelitian
Uji validitas instrumen penelitian dilakukan menggunakan corrected item-total correlation (r.drop) dengan kriteria pengambilan keputusan yaitu item dinyatakan valid apabila memiliki nilai r.drop ≥ 0,30. Hasil pengujian validitas setiap item pertanyaan dapat dilihat pada tabel berikut.
| Item | r.drop | Keterangan |
|---|---|---|
| P1 | 0,67 | Valid |
| P2 | 0,64 | Valid |
| P3 | 0,30 | Valid |
| P4 | 0,30 | Valid |
| P5 | 0,59 | Valid |
| P6 | 0,31 | Valid |
| P7 | 0,53 | Valid |
| P8 | 0,75 | Valid |
| P9 | 0,70 | Valid |
| P10 | 0,78 | Valid |

Berdasarkan hasil uji validitas tersebut, seluruh item pertanyaan 1 sampai pertanyaan 10 dinyatakan valid karena memiliki nilai r.drop ≥ 0,30. Dengan demikian, tidak terdapat item yang perlu dieliminasi, sehingga seluruh item kuesioner dapat digunakan dalam analisis data selanjutnya.

### Uji Reliabilitas Instrumen Penelitian
Uji reliabilitas instrumen penelitian dilakukan untuk mengetahui tingkat konsistensi instrumen dalam mengukur variabel penelitian. Pengujian reliabilitas dalam penelitian ini menggunakan Cronbach’s Alpha dengan dasar pengambilan keputusan bahwa instrumen dinyatakan reliabel apabila memiliki nilai Cronbach’s Alpha > 0,70.

Uji reliabilitas dilakukan setelah proses eliminasi item tidak valid, sehingga hanya item yang telah memenuhi kriteria validitas yang digunakan dalam pengujian ini. Hal ini dilakukan agar hasil reliabilitas yang diperoleh mencerminkan kualitas instrumen penelitian secara lebih akurat.

Berdasarkan hasil pengujian, diperoleh nilai Cronbach’s Alpha sebesar 0,8460946. Nilai tersebut menunjukkan bahwa instrumen penelitian memiliki tingkat reliabilitas yang sangat baik, sehingga dapat disimpulkan bahwa instrumen yang digunakan bersifat konsisten dan dapat dipercaya untuk digunakan dalam analisis selanjutnya.
### Analsis Deskriptif
| Jenis Kelamin | Frekuensi | Persentase |
|---|---|---|
| Laki-laki | 12 | 27.27% |
| Perempuan | 32 | 72.73% |
| Total | 44 | 100% |

Berdasarkan hasil survei dengan jumlah responden sebanyak 44 orang, dipeproleh hasil bahwa 12 responden laki-laki (27.27%) dan 32 responden perempuan (72,73%). Data tersebut menunjukkan bahwa responden dalam penelitian ini didominasi oleh perempuan.

### Naive Estimation
Naive estimation digunakan untuk memperoleh estimasi awal tingkat kepuasan mahasiswa berdasarkan data responden secara langsung tanpa memberikan pembobotan pada data. Berdasarkan hasil analisis menggunakan R diperoleh:

Jumlah responden puas = 33 orang

Total responden = 44 orang

Hasil ini menunjukkan bahwa sebesar 75% mahasiswa merasa puas terhadap layanan keuangan digital. 

### Weighting Sederhana
Weighting sederhana digunakan untuk menyesuaikan distribusi sampel agar lebih mendekati distribusi populasi yang sebenarnya. Berdasarkan hasil analisis menggunakan R diperoleh hasil weighted estimation sebesar 80.20%. Hasil tersebut menunjukkan bahwa setelah dilakukan pembobotan berdasarkan jenis kelamin, tingkat kepuasan mahasiswa terhadap layanan keuangan digital tetap berada pada kategori cukup tinggi.

### Perbandingan Estimasi
| Metode Estimasi | Hasil | 
|---|---|
| Naive Estimation | 75.00% | 
| Weighted Estimation | 80.20% | 

## Kesimpulan
Hasil penentuan jumlah sampel menggunakan rumus Slovin, dengan jumlah populasi sebanyak 1.693 dan tingkat kesalahan sebesar 0,15, diperoleh jumlah sampel penelitian sebanyak 44 responden. Jumlah ini diperoleh sebagai representasi dari populasi yang diteliti sehingga diharapkan mampu memberikan gambaran yang akurat terhadap karakteristik responden. Selanjutnya, jumlah sampel tersebut digunakan sebagai dasar dalam proses pengumpulan data penelitian melalui penyebaran kuesioner kepada mahasiswa FMIPA Universitas Mataram.

Berdasarkan hasil uji validitas instrumen penelitian, diketahui bahwa seluruh item pertanyaan dalam kuesioner memiliki nilai r.drop ≥ 0,30 sehingga dapat dinyatakan valid. Hal ini menunjukkan bahwa setiap item pertanyaan mampu mengukur variabel yang diteliti dengan baik dan konsisten. Dengan terpenuhinya kriteria validitas tersebut, maka seluruh item kuesioner layak digunakan dalam analisis data lebih lanjut tanpa perlu dilakukan penghapusan item, sehingga kualitas pengukuran dalam penelitian ini menjadi lebih baik dan dapat dipercaya.

Selanjutnya, hasil uji reliabilitas menunjukkan nilai Cronbach’s Alpha sebesar 0,8460946, yang berada di atas batas minimal 0,70. Hal ini menunjukkan bahwa instrumen penelitian memiliki tingkat konsistensi yang sangat baik dalam mengukur variabel penelitian.
Dengan demikian, dapat disimpulkan bahwa instrumen penelitian telah memenuhi syarat validitas dan reliabilitas, sehingga layak digunakan untuk analisis data pada tahap selanjutnya sesuai dengan tujuan penelitian.

Berdasarkan hasil analisis non-probability sampling pada survei online terkait tingkat kepuasan mahasiswa FMIPA terhadap layanan keuangan digital, diketahui bahwa sebagian besar responden memberikan penilaian positif terhadap pelayanan yang diterima. Hasil distribusi responden memperlihatkan bahwa jumlah responden perempuan lebih banyak dibandingkan laki-laki. Perhitungan naive estimation menghasilkan tingkat kepuasan sebesar 75%, sedangkan hasil weighted estimation berdasarkan jenis kelamin menunjukkan nilai sebesar 80.20%. Selisih hasil yang tidak terlalu besar menandakan bahwa sampel penelitian telah cukup menggambarkan kondisi populasi.
