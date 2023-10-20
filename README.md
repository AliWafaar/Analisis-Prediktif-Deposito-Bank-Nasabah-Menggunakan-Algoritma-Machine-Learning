# README

Dalam Repisitories ini saya membuat machine learning yang akan memprediksi nasabah apakah ingin melakukan deposito atau tidak berdasarkan data historis nya

## **Latar Belakang**

Dalam dunia perbankan dan industri keuangan, manajemen nasabah dan pengembangan produk adalah dua aspek kunci yang sangat penting.

Produk keuangan seperti deposito berjangka adalah salah satu alat yang digunakan oleh bank untuk mengumpulkan dana dan meningkatkan keuntungan mereka. 

Dalam data ini, kita ingin mengetahui data historis nasabah: apakah nasabah ini akan melakukan deposito atau tidak jika kita tawarkan campaign melalui telemarketing.


Target: 

0 atau Negative : Tidak Deposit

1 atau Positive : Deposit

## **Masalah**

Salah satu bank swasta di Washington,USA ingin melakukan campaign deposito pada tahun depan, yang dimana campaign ini harus dioptimalkan berdasarkan data historis campaign yang sudah berjalan pada tahun ini .

Salah satu tantangan utama yang dihadapi oleh bank adalah bagaimana memprediksi perilaku nasabah, terutama apakah mereka akan melakukan deposito atau tidak dalam campaign yang di tawarkan melalui telemarketing. 

Kesalahan dalam memprediksi perilaku nasabah dapat mengakibatkan kerugian finansial dan kehilangan peluang bisnis yang berharga. 

Oleh karena itu, untuk mengatasi tantangan ini, penggunaan teknologi machine learning menjadi semakin relevan.

## **Tujuan**

Tujuan dari project ini adalah mengembangkan model machine learning yang dapat membantu bank dalam memprediksi apakah seorang nasabah akan melakukan deposito berjangka atau tidak. 

**Konsukuensi False Positive**: Hilang nya waktu dan resource yang digunakan untuk menawarkan campaign ini.

**Konsukuensi False Negative**: Hilang **`Potential Profit`** serta **`Potential Nasabah`** yang akan melakukan deposit.

Dari konsukensi diatas maka fokus utama dari penelitian ini adalah untuk mereduksi **`False Negative`**, yaitu kasus di mana model memprediksi bahwa seorang nasabah tidak akan melakukan deposito padahal seharusnya ia akan melakukannya. 

Hal ini dilakukan karena salah menebak nasabah yang seharusnya akan melakukan deposito dapat mengakibatkan kerugian bagi bank dalam hal kehilangan potensi pendapatan dari deposito berjangka.

Langkah-langkah yang akan diambil untuk mencapai tujuan ini termasuk:

1. Pengumpulan Data: Mengumpulkan data historis tentang nasabah, termasuk informasi pekerjaan, sejarah transaksi, dan riwayat deposito sebelumnya.

2. Preprocessing Data: Membersihkan dan memproses data untuk menghilangkan nilai yang hilang atau tidak relevan, serta melakukan encoding kategori data.

3. Pembagian Data: Membagi data menjadi dua bagian, yaitu data pelatihan (training data) dan data pengujian (testing data).

4. Pengembangan Model: Mengembangkan model machine learning yang mampu memprediksi apakah seorang nasabah akan melakukan deposito berjangka atau tidak.

5. Evaluasi Model: Mengukur kinerja model, dengan penekanan khusus pada pengurangan False Negative, yang merupakan kesalahan yang ingin dihindari.

6. Implementasi: Mengintegrasikan model ke dalam sistem perbankan untuk membantu dalam pengambilan keputusan dan manajemen nasabah.

Dengan demikian, project ini akan memberikan panduan langkah demi langkah untuk mengembangkan model machine learning yang efektif dalam mengurangi **`False Negative`** dan meningkatkan prediksi nasabah yang berpotensi melakukan deposito berjangka, sehingga bank dapat memaksimalkan potensi pendapatan mereka dan memberikan layanan yang lebih baik kepada nasabahnya.

## Data Info

Dataset set ini memuat informasi historis nasabah berikut selengkapnya:

| No. | Kolom      | Deskripsi                                                                               |
|-----|------------|-----------------------------------------------------------------------------------------|
| 1   | Age        | Umur Nasabah                                                                            |
| 2   | Job        | Pekerjaan Nasabah                                                                      |
| 3   | Balance    | Saldo Nasabah (USD)                                                                          |
| 4   | Housing    | Pinjaman Rumah                                                                         |
| 5   | Loan       | Pinjaman Dana                                                                            |
| 6   | Contact    | Jenis Komunikasi Kontak (e.g., telepon, HP)                                           |
| 7   | Month      | Bulan terakhir kontak dalam tahun (e.g., Januari, Februari)                            |
| 8   | Campaign   | Jumlah kontak yang dilakukan selama kampanye ini berlangsung                      |
| 9   | Pdays      | Jumlah hari setelah klien dihubungi dari kampanye sebelumnya (jika -1 berarti belum pernah di hubungi)                           |
| 10  | Poutcome   | Hasil kampanye pemasaran sebelumnya                                                    |
| 11  | Deposit    | Apakah nasabah melakukan deposito atau tidak (Ya/Tidak)                                |

Link Dataset: [Click Here](https://github.com/AliWafaar/Analisis-Prediktif-Deposito-Bank-Nasabah-Menggunakan-Algoritma-Machine-Learning/blob/main/data_bank_marketing_campaign.csv).

##  Explorasi Mendalam dalam Pemodelan Machine Learning

Dalam membuat dan mengembangkan machine learning ini kita akan melakukan: 

1. Data Understanding
2. Data Cleaning
3. EDA
4. Feature Selection
5. Train Test Split
6. Model Benchmarking
7. Model Hyperparameter Tuning
8. Fit To test
9. PCA Analysis
10. Feater Importance

## Conclusion And Reccomendation

**Conclusion:**

Berdasarkan hasil classification report dari model Random Forest yang kita kembangkan:

- Melihat dari nilai F2 sebesar 0.66 yang berarti dalam model machine learning kita bisa melakukan prediksi dengan tingkat kebenaran sebesar `66%` 

- Jika kita menggunakan model ini untuk menawarkan campaign kepada nasabah, model ini dapat mengurangi `77%` nasabah yang sebenarnya tidak tertarik sehingga kita tidak perlu mendekati mereka. Sementara itu, model kita dapat mengidentifikasi `62%` nasabah yang sebenarnya tertarik dari keseluruhan nasabah yang tertarik (berdasarkan recall untuk label 1).


- Jika kita menggunakan model kita bisa menekan angka `Acquisition Cost` dan meningkatkan `ROI (Return Over Investment)` dengan penjabaran seperti ini:

Acquisition Cost = $10/Nasabah

Profit= $50/Nasabah

True Positive (TP) = 457 Nasabah

False Positive (FP) = 172 Nasabah

True Negative (TN) = 643 Nasabah

False Negative (FN) = 289 Nasabah

Jika tidak menggunakan model, accusition cost akan dialokasikan ke semua nasabah dengan rumus:

$$
\text{Acquisition Cost} = (TP + FP + TN + FN) \times 10
$$

$$
\text{Acquisition Cost} = (457 + 172 + 643 + 289) \times 10
$$

$$
\text{Acquisition Cost} = 15,160
$$

Jika kita menggunakan model, accusition cost akan dialokasikan ke nasabah yang kita prediksi ingin melakukan deposit dengan rumus:

$$
\text{Acquisition Cost} = (TP + FP) \times 10
$$

$$
\text{Acquisition Cost} = (457 + 172) \times 10
$$

$$
\text{Acquisition Cost} = 6,290
$$

Dengan menggunakan model ini, kita dapat menghemat accusition cost sebesar `$8,870` atau sekitar `58.5%.`, Dan untuk `ROI` nya:

ROI tanpa Model:

$$
\text{ROI = (Total Profit  - Acquisition Cost) / Acquisition Cost}
$$

$$
\text {ROI} = (37,300 - 15,610) / 15,610
$$

$$
\text {ROI} = 1.39
$$

ROI dengan Model:

$$
\text{ROI = (Total Profit  - Acquisition Cost) / Acquisition Cost}
$$

$$
\text {ROI} = (22,850 - 6,290) / 6,290
$$

$$
\text {ROI} = 2.63
$$

Dengan menggunakan model ini kita bisa meningkatkan angka ROI dari `139%` menjadi `263%` yang dimana peningkatan tersebut sebesar `124%`
  
- Namun, perlu dicatat bahwa model ini belum sepenuhnya optimal. Karena keterbatasan waktu dan sumber daya, beberapa model saat dituning tidak menggunakan banyak parameter, dan beberapa lainnya memakai metode RandomizedCV sebagai pendekatan yang lebih cepat, contohnya pada VotingClassifier. Oleh karena itu, ada potensi untuk peningkatan kinerja dengan melakukan tuning lebih mendalam dan pengoptimalan model

**Reccomendation:**

1. **Fokus pada Recall**: Mengingat tujuan kita adalah mereduksi `False Negative`, kita mungkin ingin meningkatkan recall untuk label 1 (nasabah yang tertarik) lebih lanjut. Meskipun recall untuk label 1 saat ini sudah cukup baik `(62%)`, meningkatkannya akan memastikan lebih sedikit nasabah potensial yang terlewatkan.
  
2. **Optimasi Model**: Coba teknik seperti hyperparameter tuning lebih lanjut, cross-validation, atau bahkan mencoba model lain untuk meningkatkan performa.

3. **Penambahan Fitur**: Salah satu cara untuk meningkatkan performa model adalah dengan menambahkan fitur-fitur baru yang relevan. Misalnya, menambahkan fitur 'Status Pernikahan' (Marital Status) atau 'Kepuasan Pelanggan' (Customer Satisfaction) bisa memberikan informasi tambahan mengenai nasabah dan berpotensi meningkatkan akurasi prediksi.

4. **Pertimbangkan Feature Importance**: Dengan mengetahui Feature Importance, kita dapat melakukan intervensi atau strategi pemasaran yang lebih tepat sasaran,seperti menargetkan campaign ini kepada nasabah dengan `balance` yang besar dan bisa kita lihat orang sebelum nya melakukan deposit `(poutcome)` cendurung melakukan deposit kembali.

5. **Evaluasi Bisnis**: Pertimbangkan biaya dan manfaat dalam implementasi model. Seberapa banyak biaya yang bisa dihemat dengan menghindari nasabah yang tidak tertarik? Seberapa banyak pendapatan tambahan yang bisa diperoleh dengan menargetkan nasabah yang sebenarnya tertarik?

### **Pipeline**

Untuk akses pipeline nya kalian bisa download disini: [Click Here](https://github.com/AliWafaar/Analisis-Prediktif-Deposito-Bank-Nasabah-Menggunakan-Algoritma-Machine-Learning/blob/main/pipeline_predict_bank.pkl)

