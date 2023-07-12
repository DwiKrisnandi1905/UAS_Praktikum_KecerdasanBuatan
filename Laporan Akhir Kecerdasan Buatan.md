# Laporan Akhir Kecerdasan Buatan

**Anggota Kelompok :**

1. Dwi Krisnandi NIM. 3.34.21.3.08
2. Nandya Nurmala NIM. 3.34.21.3.17

## Domain Proyek

Asuransi sangat penting saat ini karena banyak profesi datang dengan tanggung jawab dan risiko tinggi. Badan Pusat Statistik (BPS) menyatakan pada tahun 2022 akan ada 152 perusahaan asuransi di Indonesia. Jumlah tersebut meningkat 2,01% dibandingkan tahun lalu yang berjumlah 149 perusahaan asuransi. Harga premi asuransi merupakan parameter yang mempengaruhi seseorang yang ingin naik kelas ke asuransi premi. Oleh karena itu, kemampuan machine learning untuk memprediksi harga premi menjadi sangat penting bagi masyarakat yang ingin beralih ke asuransi premi. Kami mencoba untuk mengekstrak beberapa wawasan dari kumpulan data yang berisi detail tentang latar belakang seseorang yang membeli asuransi kesehatan beserta berapa besar premi yang dibebankan kepada individu tersebut.

Terdapat beberapa parameter untuk memprediksi harga premi asuransi. Salah satu parameter tersebut adalah jenis kelamin (sex), usia (age), bmi dan lainya. Di penelitian kami, kami menggunkan prediksi regresi. Algoritma regresi dapat memprediksi nilai dari sebuah variable target berdasarkan nilai dari beberapa variabel fitur. Pada proyek kami dilakukan prediksi harga premi dengan menggunakan beberapa algoritma machine learning. Sebelum pelatihan model, terlebih dahulu dilakukan manipulasi data, dan pembersihan data agar model machine learning yang dihasilkan memiliki akurasi yang tinggi.

## Business Understanding

Setiap tahunnya, harga asuransi mengalami kenaikan sesuai dengan latar belakang dan tujuan. Setiap perusahaan memiliki harga premium yang berbeda. Semakin besar risiko pekerjaan, semakin tinggi asuransinya. Oleh karena itu calon konsumen harus memahami premi asuransi yang akan dibeli dengan latar belakang kontrak asuransi. Kami membutuhkan model machine learning yang dapat memprediksi harga asuransi kesehatan secara akurat. Agar calon konsumen dengan latar belakang yang relevan dapat menganggarkan pembelian premi asuransi kesehatan.

#### Problem Statements

Problem Statements
Berdasarkan permasalahan yang telah dijelaskan, problem statements dari pryek ini adalah

1. Fitur-fitur apa saja yang paling berpengaruh terhadap harga asuransi ?
2. apa hubungan antara fitur-fitur independen yaitu bagaimana yang satu mempengaruhi yang lain?
3. Bagaimana proses Pre-Processing yang dilakukan agar menghasilkan model machine learning yang akurat ?
4. Bagaimana membuat atau memilih model machine learning yang memiliki akurasi terbaik dalam memprediksi harga asuransi ?

#### Goals

Tujuan yang hendak dicapai dari proyek ini adalah sebagai berikut 
1. Mengetahui fitur yang paling berkorelasi dengan penentuan harga asuransi.
2. mengetahui sebaran/distribusi dari data yang ada.
3. Membuat model machine learning yang dapat memprediksi harga asuransi.
4. Memilih model machine learning yang menghasilkan prediksi paling akurat berdasarkan proses yang dilakukan

####  Solution Statements

Solusi yang diajukan untuk menyelesaikan masalah yang telah diuraikan adalah sebagai berikut.
1.  Melakukan analisis deskriptif untuk mengetahui pola dan informasi yang tersimpan di data mengenai fitur atau spesifikasi yang mempengaruhi harga asuransi.
2. Melakukan  Proses Preprocessing seperti :
   - Mengecek missing value dan duplikasi data. pada projek kami dataset yang digunakan tidak ada missing value tetapi terdapat duplikasi data. sehingga kami menghapus terlebih dahulu data yang duplicate
   - Melakukan visualisasi data untuk melihat persebaran dan korelasi antar kolom
   - Membagi data menjadi training dan validation. validasi akan memiliki ukuran 20% dari keseluruhan dataset dan training 80%
   - Melakukan Encoding terhadap kolom yang bertipe objek / kategorikal menggunakan fungsi `Map`.
3. . Melakukan pemilihan model terbaik menggunakan LazyPredict
   - Memilih 6 algoritma yang menghasilkan model dengan performa terbaik
   - Dalam evaluasi model regresi, tujuan utamanya adalah untuk mencapai training error dan validation error yang lebih rendah. Semakin rendah error yang diperoleh, semakin baik model tersebut dalam memprediksi nilai target.

## Data Understanding

- Dataset berisi daftar faktor yang mempengaruhi berapa besar biaya premi asuransi kesehatan. Dataset dapat di download pada tautan berikut : https://www.kaggle.com/datasets/mirichoi0218/insurance
- Memberikan informasi seperti jumlah data, missing value, duplikasi data, korelasi antar kolom, dan sebaran data.
- Melakukan data manipulation untuk mendapatkan variabel atau fitur baru
- Melakukan beberapa tahapan yang diperlukan untuk memahami data contohnya teknik visualisasi data atau exploratory data analysis.

Adapun variabel yang terdapat pada dataset adalah sebagai berikut :

1. **age**: Usia penerima manfaat utama
2. **sex**: Jenis kelamin pemegang polis asuransi, perempuan atau laki-laki
3. **bmi**: Memberikan pemahaman tentang berat badan yang relatif tinggi atau rendah dibandingkan tinggi badan, indeks objektif berat badan (kg/m^2) dengan menggunakan rasio tinggi badan terhadap berat badan, idealnya antara 18,5 hingga 24,9
4. **childern**: Jumlah anak yang ditanggung oleh asuransi kesehatan/jumlah tanggungan
5. **smoker**: Merokok atau tidak
6. **region**: Tempat tinggal penerima manfaat di Amerika Serikat, timur laut, tenggara, barat daya, barat laut
7. **charges**: biaya asuransi

Pada dataset, terdapat 4 fitur numerikal dan 3 fitur kategorikal. Ringkasan statistik dari data-data numerikal dapat dilihat pada Tabel 1.

<div style="text-align:center">Tabel 1. Ringkasan Statistik Data-Data Numerikal Pada Dataset</div>

|       |     age     | bmi         | children    | charges      |
| :---: | :---------: | ----------- | ----------- | ------------ |
| count | 1338.000000 | 1338.000000 | 1338.000000 | 1338.000000  |
| mean  |  39.207025  | 30.663397   | 1.094918    | 13270.422265 |
|  std  |  14.049960  | 6.098187    | 1.205493    | 12110.011237 |
|  min  |  18.000000  | 15.960000   | 0.000000    | 1121.873900  |
|  25%  |  27.000000  | 26.296250   | 0.000000    | 4740.287150  |
|  50%  |  39.000000  | 30.400000   | 1.000000    | 9382.033000  |
|  75%  |  51.000000  | 34.693750   | 2.000000    | 16639.912515 |
|  max  |  64.000000  | 53.130000   | 5.000000    | 63770.428010 |

Pada tahap Data Understanding dilakukan analisis data eksploratif untuk mendapatkan wawasan tentang karakteristik data, memahami struktur data, dan mengidentifikasi potensi masalah atau kesalahan yang mungkin terjadi. Kegiatan Data Understanding yang dilakukan pada Proyek ini antara lain :

- Memberikan informasi seperti jumlah data, missing value, duplikasi data, korelasi antar kolom, dan sebaran data.

- Melakukan visualisasi data untuk mengetahui korelasi dan sebaran data. Visualisasi korelasi antar kolom digambarkan dalam heatmap seperti ditunjukan Gambar 1. Berdasarkan diagaram heatmap Gambar 1 diketahui bahawa terdapat beberapa kolom seperti age, bmi, childern, dll yang berkorelasi dengan kolom 'charges'.  Semakin mendekati nilai 1 maka korelasi semakin tinggi. Kemudian hasil visualisasi heatmap hanya menampilkan korelasi pada kolom yang memberikan data numerikal, sedangkan kolom yang memberikan hasil kategorikal tidak dapat diketahui korelasinya.



![png](output_17_0.png)

<div style="text-align:center">Gambar 1. Visualisasi Korelasi Data dengan Heatmap</div>

Sedangkan contoh visualisasi dari sebaran data ditunjukan pada Gambar 2. Visualisasi yang ditunjukan pada Gambar 2 menunjukan bahwa ada ketidakseimbangan data pada kolom female male, children, smoker, dan region.

![png](output_21_0.png)

<div style="text-align:center">Gambar 2. Visualisasi Data pada Dataset</div>

## Data Preparation

Data Preparation

Teknik data preparation yang dilakukan pada proyek ini adalah sebagai berikut : 

1. Feature Selection : Melakukan seleksi fitur untuk menyeleksi kolom yang berperan sebagai data fitur dan kolom yang menjadi data label.

2. Data Splitting: Membagi dataset menjadi data training dan validation. Pada proyek ini perbandingan training dan data validation adalah 80 : 20.

3. Menampilkan informasi jumlah data training dan validation. Jumlah data latih adalah 1054, sedangkan data validation terdat 264 data. jumlah data fitur yang dipakai untuk pelatihan adalah 6.


## Modelling

Pada tahap ini dilakukan proses pelatihan untuk mendapatkan model dengan performa terbaik. Tahapan yang dilakukan pada proses Modelling adalah sebagai berikut.

1. Memprediksi algoritma dengan performa terbaik menggunakan Lazy Predict

   Lazy Predict adalah library Python yang membantu dalam membuat model *machine learning* dengan cepat dan mudah. Library ini dikembangkan untuk mempercepat proses eksplorasi data dan pemodelan awal. Hasil dari proses pelatihan yang dilakukan Lazy Predict ditunjukan pada Tabel 2.

   <div style="text-align:center">Tabel 2. Hasil Perbandingan model menggunakan Lazy Predict</div>

   <table border="1" class="dataframe">
     <thead>
       <tr style="text-align: right;">
         <th></th>
         <th>Adjusted R-Squared</th>
         <th>R-Squared</th>
         <th>RMSE</th>
         <th>Time Taken</th>
       </tr>
       <tr>
         <th>Model</th>
         <th></th>
         <th></th>
         <th></th>
         <th></th>
       </tr>
     </thead>
     <tbody>
       <tr>
         <th>GradientBoostingRegressor</th>
         <td>0.87</td>
         <td>0.88</td>
         <td>4509.71</td>
         <td>0.15</td>
       </tr>
       <tr>
         <th>LGBMRegressor</th>
         <td>0.87</td>
         <td>0.87</td>
         <td>4596.34</td>
         <td>0.18</td>
       </tr>
       <tr>
         <th>HistGradientBoostingRegressor</th>
         <td>0.87</td>
         <td>0.87</td>
         <td>4640.92</td>
         <td>1.28</td>
       </tr>
       <tr>
         <th>RandomForestRegressor</th>
         <td>0.87</td>
         <td>0.87</td>
         <td>4641.06</td>
         <td>0.47</td>
       </tr>
       <tr>
         <th>AdaBoostRegressor</th>
         <td>0.85</td>
         <td>0.86</td>
         <td>4849.66</td>
         <td>0.14</td>
       </tr>
       <tr>
         <th>BaggingRegressor</th>
         <td>0.85</td>
         <td>0.85</td>
         <td>4889.92</td>
         <td>0.13</td>
       </tr>
       <tr>
         <th>XGBRegressor</th>
         <td>0.85</td>
         <td>0.85</td>
         <td>4942.43</td>
         <td>0.73</td>
       </tr>
       <tr>
         <th>ExtraTreesRegressor</th>
         <td>0.84</td>
         <td>0.85</td>
         <td>4991.68</td>
         <td>0.43</td>
       </tr>
       <tr>
         <th>DecisionTreeRegressor</th>
         <td>0.81</td>
         <td>0.81</td>
         <td>5546.72</td>
         <td>0.04</td>
       </tr>
       <tr>
         <th>PoissonRegressor</th>
         <td>0.78</td>
         <td>0.79</td>
         <td>5904.18</td>
         <td>0.04</td>
       </tr>
       <tr>
         <th>ExtraTreeRegressor</th>
         <td>0.76</td>
         <td>0.77</td>
         <td>6127.42</td>
         <td>0.05</td>
       </tr>
       <tr>
         <th>LinearRegression</th>
         <td>0.76</td>
         <td>0.76</td>
         <td>6212.26</td>
         <td>0.04</td>
       </tr>
       <tr>
         <th>TransformedTargetRegressor</th>
         <td>0.76</td>
         <td>0.76</td>
         <td>6212.26</td>
         <td>0.04</td>
       </tr>
       <tr>
         <th>Lars</th>
         <td>0.76</td>
         <td>0.76</td>
         <td>6212.26</td>
         <td>0.02</td>
       </tr>
       <tr>
         <th>Lasso</th>
         <td>0.76</td>
         <td>0.76</td>
         <td>6212.57</td>
         <td>0.03</td>
       </tr>
       <tr>
         <th>SGDRegressor</th>
         <td>0.76</td>
         <td>0.76</td>
         <td>6212.96</td>
         <td>0.02</td>
       </tr>
       <tr>
         <th>LassoCV</th>
         <td>0.76</td>
         <td>0.76</td>
         <td>6214.20</td>
         <td>0.09</td>
       </tr>
       <tr>
         <th>BayesianRidge</th>
         <td>0.76</td>
         <td>0.76</td>
         <td>6214.64</td>
         <td>0.04</td>
       </tr>
       <tr>
         <th>Ridge</th>
         <td>0.76</td>
         <td>0.76</td>
         <td>6214.67</td>
         <td>0.03</td>
       </tr>
       <tr>
         <th>RidgeCV</th>
         <td>0.76</td>
         <td>0.76</td>
         <td>6214.67</td>
         <td>0.02</td>
       </tr>
       <tr>
         <th>KernelRidge</th>
         <td>0.76</td>
         <td>0.76</td>
         <td>6215.62</td>
         <td>0.06</td>
       </tr>
       <tr>
         <th>LassoLars</th>
         <td>0.76</td>
         <td>0.76</td>
         <td>6218.46</td>
         <td>0.03</td>
       </tr>
       <tr>
         <th>OrthogonalMatchingPursuitCV</th>
         <td>0.76</td>
         <td>0.76</td>
         <td>6228.74</td>
         <td>0.03</td>
       </tr>
       <tr>
         <th>LassoLarsIC</th>
         <td>0.75</td>
         <td>0.76</td>
         <td>6265.16</td>
         <td>0.03</td>
       </tr>
       <tr>
         <th>LassoLarsCV</th>
         <td>0.75</td>
         <td>0.76</td>
         <td>6284.89</td>
         <td>0.07</td>
       </tr>
       <tr>
         <th>LarsCV</th>
         <td>0.75</td>
         <td>0.76</td>
         <td>6284.89</td>
         <td>0.03</td>
       </tr>
       <tr>
         <th>KNeighborsRegressor</th>
         <td>0.74</td>
         <td>0.75</td>
         <td>6386.31</td>
         <td>0.03</td>
       </tr>
       <tr>
         <th>PassiveAggressiveRegressor</th>
         <td>0.72</td>
         <td>0.73</td>
         <td>6633.46</td>
         <td>0.06</td>
       </tr>
       <tr>
         <th>HuberRegressor</th>
         <td>0.69</td>
         <td>0.70</td>
         <td>6984.39</td>
         <td>0.08</td>
       </tr>
       <tr>
         <th>RANSACRegressor</th>
         <td>0.64</td>
         <td>0.65</td>
         <td>7552.34</td>
         <td>0.08</td>
       </tr>
       <tr>
         <th>OrthogonalMatchingPursuit</th>
         <td>0.62</td>
         <td>0.63</td>
         <td>7769.23</td>
         <td>0.03</td>
       </tr>
       <tr>
         <th>ElasticNet</th>
         <td>0.48</td>
         <td>0.50</td>
         <td>9082.85</td>
         <td>0.05</td>
       </tr>
       <tr>
         <th>TweedieRegressor</th>
         <td>0.34</td>
         <td>0.35</td>
         <td>10285.33</td>
         <td>0.03</td>
       </tr>
       <tr>
         <th>GammaRegressor</th>
         <td>0.31</td>
         <td>0.33</td>
         <td>10467.05</td>
         <td>0.04</td>
       </tr>
       <tr>
         <th>ElasticNetCV</th>
         <td>0.12</td>
         <td>0.14</td>
         <td>11852.77</td>
         <td>0.10</td>
       </tr>
       <tr>
         <th>DummyRegressor</th>
         <td>-0.03</td>
         <td>-0.00</td>
         <td>12802.37</td>
         <td>0.04</td>
       </tr>
       <tr>
         <th>NuSVR</th>
         <td>-0.08</td>
         <td>-0.06</td>
         <td>13147.00</td>
         <td>0.14</td>
       </tr>
       <tr>
         <th>SVR</th>
         <td>-0.14</td>
         <td>-0.12</td>
         <td>13507.94</td>
         <td>0.16</td>
       </tr>
       <tr>
         <th>QuantileRegressor</th>
         <td>-0.14</td>
         <td>-0.12</td>
         <td>13515.04</td>
         <td>21.50</td>
       </tr>
       <tr>
         <th>LinearSVR</th>
         <td>-0.87</td>
         <td>-0.83</td>
         <td>17290.44</td>
         <td>0.08</td>
       </tr>
       <tr>
         <th>MLPRegressor</th>
         <td>-1.03</td>
         <td>-0.99</td>
         <td>18025.50</td>
         <td>1.27</td>
       </tr>
       <tr>
         <th>GaussianProcessRegressor</th>
         <td>-4680.36</td>
         <td>-4573.56</td>
         <td>864690.45</td>
         <td>0.17</td>
       </tr>
     </tbody>
   </table>

   Algoritma dengan performa terbaik dilihat dari nilai R-Square dan RMSE. Semakin besar nilai R-Square (mendekati 1) maka model semakin akurat. Sedangkan pada RMSE, apabila nilai semain kecil (mendekati 0), maka akurasi model akan semakin tinggi. Berdasarkan hasil R-Square dan RMSE menggunakan Lazy Predict pada Tabel 1, disimpulkan bahwa 3 algoritma terbaik yang akan digunakan untuk mempredikasi harga adalah **GradientBoostingRegressor**, **RandomForestRegressor**, dan **BaggingRegressor**.

2. Membuat pipeline untuk menggabungkan data numerik dan kategorik

   Hasil penggunakan teknik `ColumnTransformer` disimpan dalam objek feature. Selanjutnya dilakukan proses pipeline untuk menggabungkan dan meng-optimasi kolom numerikal dan kategorikan agar dapat di proses oleh algoritma machine learning. 

3. Menggunakan 6 algoritma untuk di evaluasi


   - *LinearRegression*

     Linear Regression adalah metode pemodelan statistik yang digunakan untuk mempelajari hubungan linier antara variabel independen (fitur) dan variabel dependen (target). Tujuan utama Linear Regression adalah untuk menggambarkan hubungan linier antara variabel independen dan variabel dependen, serta memprediksi nilai target berdasarkan nilai fitur yang diberikan

   - *XGBRegressor*

     Algoritma XGBRegressor bekerja dengan melakukan kombinasi dari banyak pohon keputusan sederhana yang disebut "weak learners". Setiap pohon keputusan yang ditambahkan ke model berusaha untuk memperbaiki kesalahan prediksi yang dihasilkan oleh pohon sebelumnya. Proses ini dilakukan secara iteratif hingga mencapai jumlah pohon yang telah ditentukan atau ketika tidak ada peningkatan yang signifikan dalam performa model.
     
   - *RandomForestRegressor*

     RandomForestRegressor adalah sebuah algoritma pembelajaran mesin yang digunakan untuk melakukan regresi atau prediksi nilai numerik berdasarkan fitur-fitur yang diberikan. Algoritma ini merupakan bagian dari keluarga algoritma Random Forest yang dikembangkan berdasarkan konsep ensemble learning.
RandomForestRegressor bekerja dengan menggabungkan prediksi dari beberapa pohon keputusan yang terbentuk secara acak. Setiap pohon keputusan dalam Random Forest diproses dengan menggunakan subset acak dari data pelatihan dan subset acak dari fitur-fitur yang tersedia. Setiap pohon menghasilkan prediksi individual, dan prediksi akhir dari RandomForestRegressor diperoleh dengan mengambil rata-rata prediksi dari semua pohon tersebut.

 - *AdaBoostRegressor*

     AdaBoostRegressor adalah sebuah algoritma pembelajaran mesin yang digunakan untuk melakukan regresi atau prediksi nilai numerik. Algoritma ini merupakan bagian dari keluarga algoritma Boosting yang dikembangkan berdasarkan konsep ensemble learning.
AdaBoostRegressor bekerja dengan menggabungkan prediksi dari beberapa model regresi yang lebih sederhana, yang disebut "weak learners". Setiap weak learner (misalnya Decision Tree) diberikan bobot yang menggambarkan sejauh mana mereka berkontribusi terhadap prediksi akhir. Pada awalnya, bobot setiap sampel dalam dataset pelatihan adalah seragam. Kemudian, dalam setiap iterasi, model regresi baru dibangun dengan memberikan bobot yang diperbarui pada sampel-sampel yang dijadikan kesalahan oleh model sebelumnya. Proses ini berlanjut hingga prediksi akhir dihasilkan dengan menggabungkan prediksi dari semua model regresi.

 - *Lasso*

     Lasso (Least Absolute Shrinkage and Selection Operator) adalah sebuah metode regularisasi yang digunakan dalam regresi untuk mengurangi variabel yang tidak signifikan dan melakukan seleksi fitur. Tujuan utama Lasso adalah memperbaiki masalah multikolinearitas dalam regresi, di mana beberapa fitur dalam model regresi memiliki korelasi yang tinggi.
Lasso bekerja dengan menambahkan istilah penalti ke dalam fungsi tujuan regresi yang menggunakan norma L1 (norma Manhattan) dari koefisien regresi. Dengan menambahkan istilah penalti ini, Lasso memperkenalkan sparsity ke dalam model, yang berarti beberapa koefisien regresi akan dikurangi menjadi nol, sehingga fitur-fitur yang kurang penting akan dieliminasi.

 - *Ridge*

     Ridge adalah sebuah metode regularisasi yang digunakan dalam regresi untuk mengurangi varians yang tinggi atau overfitting dalam model regresi. Tujuan utama Ridge adalah memperbaiki masalah multikolinearitas dalam regresi, di mana beberapa fitur dalam model regresi memiliki korelasi yang tinggi.
Ridge bekerja dengan menambahkan istilah penalti ke dalam fungsi tujuan regresi yang menggunakan norma L2 (norma Euclidean) dari koefisien regresi. Dengan menambahkan istilah penalti ini, Ridge mendorong koefisien regresi untuk mendekati nol, tetapi tidak secara tegas mengeliminasi variabel seperti yang dilakukan oleh metode Lasso.

4. menghitung dan mencetak kesalahan prediksi menggunakan metrik MAPE


## Evaluation

Dalam evaluasi model regresi, tujuan utamanya adalah untuk mencapai training error dan validation error yang lebih rendah. Semakin rendah error yang diperoleh, semakin baik model tersebut dalam memprediksi nilai target.

Berdasarkan hasil yang diberikan, terlihat bahwa Random Forest Regressor memiliki training error dan validation error yang lebih rendah dibandingkan dengan model lainnya. Oleh karena itu, model Random Forest Regressor mungkin merupakan pilihan terbaik dalam hal ini untuk melakukan prediksi.

**Di sini kami telah menggunakan MAPE yang merupakan metrik Mean Absolute Percentage Error untuk mengevaluasi kinerja model. Nilai MAPE 0,1 berarti bahwa kesalahan dalam prediksi dari nilai sebenarnya adalah sekitar 10%**

## Conclussion

1. Berdasarkan hasil pengukuran, terdapat 4 kolom atau fitur yang mempengaruhi charges yaitu age, bmi, childern.
2. Proses preprocessing yang dilakukan adalah

- Missing Value: Setelah melakukan pemeriksaan, tidak ditemukan missing value pada dataset yang digunakan. Ini berarti dataset tersebut sudah lengkap dan tidak ada nilai yang hilang dalam setiap kolomnya.

- Duplikasi Data: Ditemukan adanya duplikasi data dalam dataset. Untuk mengatasi ini, kami telah melakukan penghapusan data duplikat agar dataset menjadi lebih bersih dan tidak menghasilkan bias dalam analisis dan pemodelan yang akan dilakukan.

- Visualisasi Data: telah melakukan visualisasi data untuk melihat persebaran dan korelasi antar kolom. Visualisasi ini membantu kita dalam memahami karakteristik dataset, melihat pola, dan menemukan hubungan antar variabel. Visualisasi dapat memberikan wawasan yang lebih dalam tentang dataset dan membantu dalam pengambilan keputusan selanjutnya.

- Pembagian Data: kami telah membagi data menjadi data train dan val menggunakan metode tertentu. Pembagian ini penting untuk melatih model pada data train dan menguji kinerjanya pada data val. Dengan pembagian yang tepat, kami dapat menghindari overfitting dan mendapatkan perkiraan yang lebih akurat tentang seberapa baik model akan berkinerja pada data baru.

- Encoding Kolom Kategorikal: kami telah melakukan encoding pada kolom-kolom yang bertipe objek atau kategorikal menggunakan fungsi Map. Hal ini dilakukan untuk mengubah nilai-nilai kategorikal menjadi representasi numerik yang dapat digunakan dalam pemodelan. Dengan melakukan encoding, kami memungkinkan model untuk memahami dan memproses data kategorikal tersebut.

3. Model Machine Learning: Beberapa algoritma machine learning telah diuji, termasuk Linear Regression, XGBoost Regressor, Random Forest Regressor, AdaBoost Regressor, Lasso, dan Ridge. Dalam hal ini, Random Forest Regressor menunjukkan performa terbaik dengan training error dan validation error yang lebih rendah dibandingkan dengan model lainnya.

4. menggunakan MAPE yang merupakan metrik Mean Absolute Percentage Error untuk mengevaluasi kinerja model. Nilai MAPE 0,1 berarti bahwa kesalahan dalam prediksi dari nilai sebenarnya adalah sekitar 10%

## Referensi

[1]   ANALISIS MODEL PERHITUNGAN PENETAPAN BIAYA PREMI ASURANSI JIWA SYARIAH: http://repository.radenintan.ac.id/7633/1/SKRIPSI%20PUNGKY.pdf

[2]  Machine Linear untuk Analisis Regresi Linier Biaya Asuransi Kesehatan dengan Menggunakan Python Jupyter Notebook: https://jurnal.untan.ac.id/index.php/jepin/article/view/48822

[3]  Analisis Perbandingan Efisiensi pada Perusahaan Jasa Asuransi Umum Syariah dan Konvensional di Indonesia: https://journal.uir.ac.id/index.php/kiat/article/view/2799

[4]   A. Kalmaz and O. Akin, “Estimation of Mobile Phone Prices with machine learning,” 2022, doi: [10.1109/ICEET56468.2022.10007128](https://doi.org/10.1109/ICEET56468.2022.10007128).

[5]  V. Aliyev, “A hands-on explanation of Gradient Boosting Regression,” *medium.com*, 2020. https://vagifaliyev.medium.com/a-hands-on-explanation-of-gradient-boosting-regression-4cfe7cfdf9e (accessed Jun. 03, 2023).

[6]   J. H. Graw, W. T. Wood, and B. J. Phrampus, “Predicting Global Marine Sediment Density Using the Random Forest Regressor machine learning Algorithm,” *J. Geophys. Res. Solid Earth*, vol. 126, no. 1, pp. 1–14, 2021, doi: [10.1029/2020JB020135](https://doi.org/10.1029/2020JB020135).

[7]   A. Biswal, “Bagging in machine learning: Step to Perform And Its Advantages,” *simplilearn.com*, 2023. https://www.simplilearn.com/tutorials/machine-learning-tutorial/bagging-in-machine-learning (accessed Jun. 03, 2023).

**---Ini adalah bagian akhir laporan---**