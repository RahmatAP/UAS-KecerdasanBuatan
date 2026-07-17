# LAPORAN UAS KECERDASAN BUATAN

## ANALISIS SENTIMEN KOMENTAR YOUTUBE TERHADAP SAMSUNG GALAXY A17 MENGGUNAKAN COMPLEMENT NAÏVE BAYES DAN SUPPORT VECTOR MACHINE


## Identitas Kelompok
Nama        : Anwar Ibrahim   
            : Rahmat Apandi 


---

# 1. Judul Proyek

**Analisis Sentimen Komentar YouTube terhadap Samsung Galaxy A17 Menggunakan Complement Naïve Bayes dan Support Vector Machine**.

Proyek menerapkan Natural Language Processing untuk mengelompokkan komentar pengguna menjadi tiga kelas sentimen, yaitu positif, netral, dan negatif. Dua algoritma yang dibandingkan adalah Complement Naïve Bayes dan Linear Support Vector Machine.

---

# 2. Business Understanding

## 2.1 Latar Belakang

YouTube menjadi salah satu media yang digunakan masyarakat untuk mencari ulasan sebelum membeli smartphone. Komentar pada video ulasan dapat memberikan informasi mengenai tanggapan pengguna terhadap harga, kamera, desain, prosesor, baterai, dan performa produk.

Jumlah komentar yang besar membuat proses analisis secara manual membutuhkan waktu lama. Oleh karena itu, diperlukan sistem analisis sentimen otomatis untuk mengelompokkan komentar menjadi positif, netral, dan negatif.

## 2.2 Rumusan Masalah

1. Bagaimana distribusi sentimen komentar pengguna?
2. Bagaimana proses pengolahan komentar bahasa Indonesia?
3. Bagaimana performa Complement Naïve Bayes dan Linear SVM?
4. Model mana yang menghasilkan performa terbaik?

## 2.3 Tujuan

1. Mengumpulkan komentar menggunakan YouTube Data API.
2. Membersihkan dan mengolah komentar bahasa Indonesia.
3. Mengelompokkan komentar menjadi positif, netral, dan negatif.
4. Membangun model Complement Naïve Bayes dan Linear SVM.
5. Membandingkan performa kedua model.

## 2.4 Manfaat

Hasil analisis dapat digunakan oleh konsumen, kreator konten, produsen, dan peneliti untuk mengetahui kecenderungan opini pengguna terhadap suatu produk.

---

# 3. Data Understanding

## 3.1 Sumber Data

Data berasal dari komentar salah satu video pada kanal YouTube GadgetIn. Pengambilan data dilakukan menggunakan YouTube Data API v3.

|   Keterangan   |   Informasi   |
|---|---|
| Sumber | Komentar YouTube |
| Kanal | GadgetIn |
| Video ID | `ZGbp60qeIUM` |
| Jumlah data | 2.970 komentar |
| Format | CSV |
| Bahasa | Bahasa Indonesia |
| Jenis data | Teks tidak terstruktur |

Dataset disimpan dalam tiga tahap:

1. `1_komentar_raw.csv`
2. `2_komentar_clean.csv`
3. `3_komentar_labeled.csv`

## 3.2 Atribut Dataset

| Atribut | Deskripsi |
|---|---|
| `Komentar_Asli` | Komentar sebelum preprocessing |
| `Komentar_Bersih` | Komentar setelah preprocessing |
| `Sentimen` | Label positif, netral, atau negatif |
| `Confidence_Score` | Tingkat keyakinan hasil pelabelan |

Variabel input yang digunakan adalah `Komentar_Bersih`, sedangkan target klasifikasinya adalah `Sentimen`.

## 3.3 Distribusi Sentimen

| Sentimen | Jumlah | Persentase |
|---|---:|---:|
| Negatif | 1.243 | 41,85% |
| Netral | 1.067 | 35,93% |
| Positif | 660 | 22,22% |
| **Total** | **2.970** | **100%** |

Distribusi tersebut menunjukkan bahwa dataset tidak seimbang karena jumlah komentar positif lebih sedikit dibandingkan kelas lainnya.

---

# 4. Exploratory Data Analysis

EDA dilakukan untuk memahami karakteristik awal dataset. Analisis meliputi pemeriksaan data kosong, data duplikat, distribusi sentimen, panjang komentar, dan kata yang sering muncul.

## 4.1 Panjang Komentar

| Statistik | Nilai |
|---|---:|
| Rata-rata | 77,72 karakter |
| Median | 49 karakter |
| Minimum | 1 karakter |
| Maksimum | 1.161 karakter |
| Standar deviasi | 91,69 karakter |

Mayoritas komentar memiliki panjang relatif pendek, tetapi terdapat beberapa komentar yang sangat panjang.

## 4.2 Insight EDA

Hasil EDA menunjukkan bahwa:

1. Sentimen negatif merupakan kelas terbesar.
2. Sentimen positif merupakan kelas terkecil.
3. Panjang komentar sangat bervariasi.
4. Banyak komentar menggunakan singkatan dan bahasa tidak baku.
5. Dataset memerlukan preprocessing dan penanganan ketidakseimbangan kelas.

Tambahkan visualisasi berikut ke dalam laporan:

```md
![Distribusi Sentimen](images/eda_distribusi_sentimen.png)

![Kata yang Sering Muncul](images/eda_kata_populer.png)

![Distribusi Panjang Komentar](images/eda_panjang_komentar.png)