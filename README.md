# Sistem Rekomendasi Film - Husnan

## Project Overview

Industri film berkembang demikian pesat. Banyak jenis film yang beredar dan siap untuk disaksikan. Oleh sebab itu banyak orang kebingunan akan film apa yang ingin disaksikan. Maka, dibutuhkan sistem untuk merekomendasikan film agar sesuai dengan yang calon penonton inginkan. Proyek ini menggunakan metode Collaborative Filtering (CF). metode yang digunakan untuk memprediksi kegunaan item berdasarkan penilaian pengguna sebelumnya.

## Business Understanding

### Problem Statements
- Bagaimana merekomendasikan film ke penonton sesuai dengan yang calon penonton inginkan ?

### Goals
- Menggunakan Collaborative Filtering untuk merekomendasikan film ke penonton

## Data Understanding
Saya menggunakan MovieLens 20M Dataset oleh Grouplens yang memiliki lebih dari 20 juta peringkat film sejak 1995 dengan title, genre, dan rating yang diberikan oleh pengguna. Bisa di unduh di [sini](https://grouplens.org/datasets/movielens/), Hanya file movie.csv dan rating.csv yang digunakan pada proyek ini

Berikut pratinjau `movie.csv`
|movieId |title                    |genres                                           |
|--------|-------------------------|-------------------------------------------------|
|1       |Toy Story (1995)         | Adventure, Animation, Children, Comedy, Fantasy |
|2       |Jumanji (1995)           | Adventure, Children, Fantasy                    |
|3       |Grumpier Old Men (1995)  | Comedy, Romance   	                             |
|4       |Waiting to Exhale (1995) | Comedy, Drama, Romance  	                       |

Berikut pratinjau `rating.csv`
|userId |movieId |rating |timestamp           |
|-------|--------|-------|--------------------|
|1      |2       |3.5    |2005-04-02 23:53:47 |
|1      |29      |3.5    |2005-04-02 23:31:16 |
|1      |32      |3.5    |2005-04-02 23:33:39 |
|1      |47      |3.5    |2005-04-02 23:32:07 |
|1      |50      |3.5    |2005-04-02 23:29:40 |

## Data Preparation
Data preparation yang dilakukan pada proyek ini adalah sebagai berikut:
- Import library yang akan digunakan
- Membaca dataset yang kita miliki
- Membuat kolom Tahun di movie dataframe
- Menghapus tahun di kolom Judul.
- Menghapus kolom genre
- Menghapus kolom timestamp pada dataframe rating
- Membuatan sistem rekomendasi Berbasis User:
  - Pilih pengguna dengan film yang telah ditonton pengguna
  - Mendapatkan rekaman film yang ditonton dari pengguna
  - Menghitung similarity score
  - Merekomendasikan item dengan skor tertinggi
- Memfilter film berdasarkan judul, Kemudian gabungkan, Sehingga kita bisa mendapatkan movieId. Menghapus informasi yang tidak digunakan 
- Memfilter pengguna yang telah menonton film yang telah ditonton oleh input dan menyimpannya

## Modeling
Modeling yang dilakukan pada proyek ini adalah sebagai berikut:
- Membuat beberapa sub dataframes di mana semuanya memiliki nilai yang sama di kolom yang ditentukan sebagai parameter
- Menunjukkan satu contoh grup dengan mendapatkan semua pengguna userId tertentu
- Menyortirnya sehingga pengguna dengan film yang paling mirip dengan input akan diprioritaskan
- Menyimpan Pearson Correlation dalam dictionary, di mana keynya user Id pengguna dan value adalah coefficient
- Menyortir input dan user group saat ini sehingga nilainya tidak tercampur nanti
- Mendapatkan review scores untuk film
- Menyimpan dalam variabel buffer sementara untuk memfasilitasi perhitungan di masa mendatang
- Meletakkan ulasan grup pengguna saat ini dalam format list
- Menghitung pearson correlation antara dua pengguna, yang disebut, x dan y
- Mengambil weighted average dari peringkat film menggunakan Pearson Correlation sebagai bobot. 
- Mengalikan similarity dengan user's ratings
- Menerapkan sum ke topUsers setelah mengelompokkannya berdasarkan userId
- Membuat empty dataframe, Terus mengambil weighted average
- Mendapatkan 10 film teratas dengan skor rekomendasi tertinggi. Berikut adalah 10 rekomendasi teratas untuk pengguna input berdasarkan apa yang ditonton orang lain

<p align="center">
<img width="381" alt="chrome_UCiULMXqGR" src="https://user-images.githubusercontent.com/57633103/190485615-31d27cf4-0a91-454a-b441-1af69105084f.png">
</p>
  
## Evaluation
Evaluation yang dilakukan pada proyek ini adalah sebagai berikut:
- Proyek ini menggunakan pendekatan Memory-based, yaitu menggunakan teknik statistik seperti Pearson Correlation
- Dengan menerapkan Pearson Correlation, kita bisa mendapatkan weighted average recommendation score yang bagus yaitu 5.0, berikut hasilnya

<p align="center">
<img width="358" alt="chrome_JFq4Ir1dBk" src="https://user-images.githubusercontent.com/57633103/190490989-1441896b-187f-4d46-aea7-0c5dccb0e8f2.png">
</p>

## Conclusion
Dari gambar sebelumnya, kita dapat melihat film teratas dengan skor rekomendasi tertinggi. Hal ini menunjukkan efektivitas metode Collaborative Filtering (CF) dalam merekomendasikan sesuatu, yang mana pada kasus ini merekomendasikan film.
