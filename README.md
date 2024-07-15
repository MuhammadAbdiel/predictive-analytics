# Laporan Proyek Machine Learning Terapan - Muhammad Abdiel Firjatullah

## Domain Proyek

Topik yang diangkat dari proyek ini yaitu mengenai bidang ekonomi dan bisnis, di mana suatu perusahaan akan mengadakan perekrutan karyawan baru. Oleh karena itu, perusahaan ingin mengetahui kisaran gaji yang sesuai berdasarkan tahun pengalaman kerja calon karyawannya.

### Latar Belakang

Rekrutmen adalah proses mencari dan menyeleksi calon karyawan untuk mengisi posisi atau jabatan tertentu [[1]](https://majoo.id/solusi/detail/rekrutmen-adalah#:~:text=Rekrutmen%20adalah%20proses%20mencari%20dan,mudah%20mencari%20karyawan%20yang%20berkualitas.). Proses rekrutmen ini penting dalam menentukan baik tidaknya pelamar yang melamar pekerjaan pada suatu perusahaan. Salah satu variabel yang dapat menentukan baik tidaknya seorang karyawan adalah pengalaman kerja, semakin banyak pengalaman kerja seorang karyawan akan semakin baik juga kualitasnya. Mengutip salah satu e-Jurnal Riset Manajemen Prodi Manajemen Fakultas Ekonomi Unisma _"Pengalaman kerja merupakan pengalaman seorang karyawan yang telah memiliki jam kerja yang tinggi atau pengalaman yang lama dengan adanya pengalaman dapat memecahkan berbagai macam masalah, persoalan, penyelesaian tanggung jawab yang diberikan, sesuai dengan individu karyawan"_ [[2]](http://riset.unisma.ac.id/index.php/jrm/article/view/8261).

Dalam proyek ini perusahaan akan membuat beberapa model Machine Learning yang kemudian di evaluasi untuk membandingkan model mana yang hasil prediksinya paling baik lalu diharapkan dapat memprediksi kisaran gaji yang sesuai berdasarkan pengalaman kerja calon pelamarnya.

## Business Understanding

### Problem Statements

Berdasarkan latar belakang di atas, rincian masalahnya adalah sebagai berikut:

- Algoritma apa yang cocok untuk memprediksi kisaran gaji karyawan?
- Bagaimana cara menentukan hasil prediksi suatu Algoritma Machine Learning dapat dikatakan baik?

### Goals

Untuk menjawab pertanyaan di atas, maka akan dijabarkan sebagai berikut:

- Ada banyak algoritma yang dapat menyelesaikan masalah tersebut, namun di proyek ini akan menggunakan algoritma LinearRegression dan RandomForest.
- Melakukan evaluasi terhadap metrik dari masing-masing algoritma.

### Solution Statements

Solusi yang dapat dilakukan untuk memenuhi goals proyek ini diantaranya sebagai berikut:

- Membuat 2 model Machine Learning yaitu dengan algoritma LinearRegression dan RandomForest.

  - Konsep dari algoritma LinearRegression adalah memprediksi nilai dari y dengan mengetahui nilai x dan menemukan nilai m dan b yang errornya paling minimal [[3]](https://medium.com/@adiptamartulandi/belajar-machine-learning-simple-linear-regression-di-python-e82972695eaf).
    <br><br>
    _y = mx + b + e_
    <br><br>
    _y = dependent variable_
    <br>
    _m = slope dari garis (persamaan diatas merupakan sebuah garis)_
    <br>
    _x = independent variable_
    <br>
    _b = intercept_
    <br>
    _e = error_
    <br><br>
    Adapun kelebihan dari metode ini yakni metode ini mampu digunakan untuk memprediksi nilai yang ada pada masa depan jika hubungan antara variabel independen dan dependen memiliki hubungan linear. Kekurangan dari metode ini yaitu pada keadaan sesungguhnya jarang sekali variabel dependen dan independen menunjukkan hubungan yang jelas [[4]](https://caraguna.com/apa-itu-linear-regression-dalam-machine-learning/).
    <br>  
    ![image](https://docs.microsoft.com/id-id/analysis-services/data-mining/media/linear-regression.png?view=asallproducts-allversions)

  - Konsep dari algoritma RandomForest yaitu model prediksi yang terdiri dari beberapa model dan bekerja secara bersama-sama. Kelebihan dari metode ini yakni jika dataset berjumlah banyak maka RandomForest akan bekerja secara efisien.
    <br><br>
    ![image](https://dicoding-web-img.sgp1.cdn.digitaloceanspaces.com/original/academy/dos:5e086364e59025d11dd0dfd3bc965e7c20210912094833.png)

- Perkiraan gaji adalah tujuan yang ingin dicapai. Seperti yang kita tahu, perkiraan gaji merupakan variabel kontinu. Saat membuat prediksi variabel kontinu artinya ini merupakan permasalahan regresi. Untuk kasus regresi seperti ini akan gunakan metrik Mean Squared Error (MSE).Secara umum, metrik ini mengukur seberapa jauh hasil prediksi dengan nilai yang sebenarnya. Oleh karena itu nantinya masing-masing model akan di evaluasi yang kemudian memilih algoritma yang nilai metriknya paling baik.

## Data Understanding

Dataset yang digunakan pada proyek kali ini dibuat oleh [RubyDoby](https://www.kaggle.com/rubydoby) yang di upload ke [Kaggle](https://www.kaggle.com/) pada Januari 2022. Sumber dataset: [Years of experience and employees salary](https://www.kaggle.com/datasets/rubydoby/years-of-experience-and-employees-salary).

Pada berkas yang diunduh pada [link tersebut](https://www.kaggle.com/datasets/rubydoby/years-of-experience-and-employees-salary) yaitu [employee_salaries.csv](https://www.kaggle.com/datasets/rubydoby/years-of-experience-and-employees-salary?select=employee_salaries.csv) terdapat 1500 baris dan 2 kolom.

### Variabel-variabel pada Years of Experience and Employee Salary Dataset adalah sebagai berikut:

- Years of Experience: merupakan total tahun pengalaman kerja.
- Salary: merupakan total gaji karyawan per tahun dalam kurs dollar.
