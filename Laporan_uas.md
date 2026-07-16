# LAPORAN UAS KECERDASAN BUATAN
ANALISIS SENTIMEN KOMENTAR YOUTUBE TERHADAP SAMSUNG GALAXY A17 PADA KANAL GADGETIN MENGGUNAKAN COMPLEMENT NAIVE BAYES DAN SUPPORT VECTOR MACHINE

# Anggota Kelompok
    Nama           : Anwar Ibrahim | 2406017 |
                     Rahmat Apandi | 2406006 |
    Kelas          : A Informatika
    Mata Kuliah    :
    Dosen Pengampu :

# 1. Judul Proyek

# Analisis Sentimen Komentar YouTube terhadap Samsung Galaxy A17 pada Kanal GadgetIn Menggunakan Complement Naive Bayes dan Support Vector Machine

Proyek ini merupakan penerapan kecerdasan buatan dalam bidang **Natural Language Processing**, khususnya analisis sentimen pada komentar media sosial. Data yang digunakan berupa komentar pengguna pada salah satu video ulasan smartphone di kanal YouTube GadgetIn.

Komentar pengguna dianalisis dan dikelompokkan menjadi tiga kelas sentimen, yaitu **positif**, **netral**, dan **negatif**. Pengelompokan tersebut bertujuan untuk mengetahui kecenderungan opini pengguna terhadap produk smartphone yang dibahas dalam video.

Pada tahap pemodelan, proyek ini membandingkan dua algoritma klasifikasi, yaitu **Complement Naive Bayes** dan **Support Vector Machine dengan kernel linear**. Kedua algoritma tersebut dipilih karena sesuai untuk klasifikasi teks yang memiliki jumlah fitur besar setelah proses transformasi menggunakan metode Term Frequency–Inverse Document Frequency atau TF-IDF.

Hasil kedua model kemudian dibandingkan menggunakan metrik accuracy, precision, recall, F1-score, dan confusion matrix untuk menentukan algoritma dengan kinerja terbaik.

# 2. Business Understanding

# 2.1 Latar Belakang

YouTube merupakan salah satu media yang banyak digunakan masyarakat untuk mencari informasi sebelum membeli suatu produk. Dalam video ulasan smartphone, penonton dapat memberikan komentar mengenai harga, desain, kamera, baterai, performa, prosesor, serta pengalaman penggunaan produk. Komentar-komentar tersebut dapat menunjukkan bagaimana respons masyarakat terhadap produk yang sedang dibahas.

Jumlah komentar pada video YouTube dapat mencapai ratusan hingga ribuan. Apabila komentar tersebut dianalisis secara manual, prosesnya akan membutuhkan waktu yang lama dan berpotensi menghasilkan penilaian yang tidak konsisten. Selain itu, komentar pengguna sering menggunakan bahasa tidak baku, singkatan, emoji, kata gaul, dan campuran bahasa sehingga lebih sulit dianalisis secara langsung.

Salah satu solusi yang dapat digunakan adalah analisis sentimen dengan memanfaatkan kecerdasan buatan. Analisis sentimen merupakan proses untuk mengidentifikasi kecenderungan opini dalam suatu teks, seperti opini positif, netral, atau negatif. Melalui analisis sentimen, komentar dalam jumlah besar dapat diproses secara otomatis sehingga kecenderungan pendapat pengguna dapat diketahui dengan lebih cepat.

Pada proyek ini, komentar pengguna pada video ulasan Samsung Galaxy A17 di kanal YouTube GadgetIn dianalisis menggunakan dua algoritma klasifikasi, yaitu Complement Naïve Bayes dan Support Vector Machine. Teks komentar terlebih dahulu dibersihkan dan diubah menjadi data numerik menggunakan metode TF-IDF. Selanjutnya, performa kedua algoritma dibandingkan untuk mengetahui model yang memberikan hasil klasifikasi terbaik.

# 2.2 Permasalahan Dunia Nyata

Komentar pengguna pada video ulasan smartphone mengandung banyak informasi yang dapat digunakan untuk mengetahui tanggapan konsumen terhadap suatu produk. Namun, jumlah komentar yang besar menyebabkan proses pembacaan dan pengelompokan komentar secara manual menjadi tidak efektif.

Permasalahan lain yang ditemukan adalah bentuk komentar yang tidak terstruktur. Pengguna sering menulis komentar dengan singkatan, kesalahan penulisan, bahasa informal, emoji, serta kata-kata yang tidak memiliki makna penting dalam proses klasifikasi. Kondisi tersebut membuat data komentar harus melalui tahap preprocessing sebelum digunakan untuk membangun model.

Selain itu, distribusi jumlah komentar pada setiap kelas sentimen tidak selalu seimbang. Ketidakseimbangan data dapat menyebabkan model lebih banyak memprediksi kelas yang memiliki jumlah data paling besar. Oleh karena itu, diperlukan proses pengolahan data dan pemilihan algoritma yang sesuai agar model dapat mengenali setiap kelas sentimen dengan lebih baik.

Berdasarkan permasalahan tersebut, rumusan masalah dalam proyek ini adalah:

1. Bagaimana distribusi sentimen positif, netral, dan negatif pada komentar pengguna?
2. Bagaimana proses pembersihan komentar bahasa Indonesia agar siap digunakan dalam pemodelan?
3. Bagaimana kinerja algoritma Complement Naïve Bayes dalam mengklasifikasikan sentimen komentar?
4. Bagaimana kinerja algoritma Support Vector Machine dalam mengklasifikasikan sentimen komentar?
5. Algoritma manakah yang menghasilkan performa klasifikasi terbaik?

# 2.3 Tujuan Proyek

Proyek ini bertujuan untuk:

1. Mengumpulkan komentar pengguna dari video YouTube menggunakan YouTube Data API.
2. Membersihkan dan menormalisasi komentar berbahasa Indonesia.
3. Mengelompokkan komentar ke dalam sentimen positif, netral, dan negatif.
4. Mengetahui distribusi dan pola awal pada data komentar.
5. Mengubah teks komentar menjadi fitur numerik menggunakan TF-IDF.
6. Membangun model klasifikasi menggunakan Complement Naïve Bayes.
7. Membangun model klasifikasi menggunakan Support Vector Machine.
8. Membandingkan kedua model berdasarkan accuracy, precision, recall, F1-score, dan confusion matrix.
9. Menentukan algoritma yang memberikan hasil terbaik dalam klasifikasi sentimen komentar.

# 2.4 Pengguna Sistem

Sistem analisis sentimen ini dapat digunakan oleh beberapa pihak, yaitu:

# 1. Konsumen

Konsumen dapat menggunakan hasil analisis untuk mengetahui kecenderungan tanggapan pengguna lain terhadap suatu produk sebelum melakukan pembelian.

# 2. Kreator Konten

Kreator konten dapat mengetahui respons penonton terhadap produk yang diulas serta memahami topik yang paling banyak dibahas dalam kolom komentar.

# 3. Produsen atau Tim Pemasaran

Produsen dapat memanfaatkan hasil analisis untuk mengetahui tanggapan konsumen mengenai kelebihan dan kekurangan produk. Informasi tersebut dapat digunakan sebagai bahan evaluasi dan pengembangan produk.

# 4. Peneliti

Peneliti dapat menggunakan proyek ini sebagai contoh penerapan Natural Language Processing dan machine learning dalam analisis sentimen bahasa Indonesia.

# 5. Pengembang Sistem

Pengembang dapat menggunakan hasil proyek ini sebagai dasar untuk membuat aplikasi atau dashboard yang dapat memantau opini pengguna secara otomatis.

# 2.5 Solusi yang Ditawarkan

Solusi yang ditawarkan dalam proyek ini adalah sistem klasifikasi sentimen otomatis terhadap komentar YouTube. Sistem bekerja melalui beberapa tahapan, yaitu:

1. Mengambil komentar menggunakan YouTube Data API.
2. Membersihkan teks komentar.
3. Melakukan normalisasi kata dan stemming.
4. Memberikan label sentimen awal.
5. Mengubah teks menjadi representasi TF-IDF.
6. Membagi data menjadi data training dan data testing.
7. Menangani ketidakseimbangan kelas menggunakan oversampling.
8. Melatih model Complement Naïve Bayes dan Support Vector Machine.
9. Mengevaluasi dan membandingkan kedua model.
10. Menentukan model dengan performa terbaik.

# 2.6 Manfaat Implementasi Kecerdasan Buatan

Implementasi kecerdasan buatan dalam proyek ini memberikan beberapa manfaat, yaitu:

1. Mempercepat proses analisis komentar dalam jumlah besar.
2. Mengurangi kebutuhan pengelompokan komentar secara manual.
3. Menghasilkan klasifikasi sentimen secara lebih konsisten.
4. Membantu mengetahui kecenderungan opini konsumen.
5. Mempermudah identifikasi respons positif, netral, dan negatif.
6. Mendukung pengambilan keputusan berbasis data.
7. Menjadi dasar pengembangan sistem pemantauan opini secara otomatis.

# 2.7 Tinjauan Literatur Singkat

Analisis sentimen merupakan salah satu penerapan Natural Language Processing yang digunakan untuk menentukan kecenderungan opini dalam teks. Dalam klasifikasi teks, dokumen atau komentar harus diubah menjadi bentuk numerik agar dapat diproses oleh algoritma machine learning.

Metode TF-IDF digunakan untuk memberikan bobot pada kata berdasarkan frekuensi kemunculannya dalam suatu dokumen dan keseluruhan kumpulan dokumen. Kata yang penting dalam suatu komentar akan memperoleh bobot yang lebih tinggi, sedangkan kata yang terlalu sering muncul pada seluruh komentar akan memperoleh bobot yang lebih rendah.

Complement Naïve Bayes merupakan pengembangan dari algoritma Naïve Bayes yang banyak digunakan dalam klasifikasi teks. Algoritma ini relatif sederhana, memiliki waktu pelatihan yang cepat, dan dapat digunakan pada data dengan jumlah fitur yang besar. Complement Naïve Bayes juga dirancang untuk membantu mengurangi kelemahan Naïve Bayes pada dataset dengan distribusi kelas yang tidak seimbang.

Support Vector Machine merupakan algoritma klasifikasi yang bekerja dengan mencari batas pemisah terbaik antar kelas. Pada data teks, Support Vector Machine sering digunakan karena mampu bekerja dengan baik pada data berdimensi tinggi, seperti hasil transformasi TF-IDF.

Dalam proyek ini, kedua algoritma dibandingkan untuk mengetahui perbedaan performanya dalam mengklasifikasikan komentar menjadi sentimen positif, netral, dan negatif.