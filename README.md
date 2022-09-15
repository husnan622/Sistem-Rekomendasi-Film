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

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data beserta insight atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model sisten rekomendasi yang Anda buat untuk menyelesaikan permasalahan. Sajikan top-N recommendation sebagai output.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menyajikan dua solusi rekomendasi dengan algoritma yang berbeda.
- Menjelaskan kelebihan dan kekurangan dari solusi/pendekatan yang dipilih.

## Evaluation
Pada bagian ini Anda perlu menyebutkan metrik evaluasi yang digunakan. Kemudian, jelaskan hasil proyek berdasarkan metrik evaluasi tersebut.

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.
