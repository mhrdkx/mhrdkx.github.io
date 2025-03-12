---
title: "Information Retrieval"
collection: teaching
type: "Undergraduate course"
permalink: /teaching/information-retrieval-2425-4
venue: "University 1, Department"
date: 2014-01-01
location: "City, Country"
---

## **Materi 4: Indexing dan Representasi Dokumen**

---

#### **Tujuan Pembelajaran**

Setelah mempelajari materi ini, mahasiswa diharapkan:

1. Memahami konsep **indexing** dalam Web Information Retrieval.
2. Mengetahui teknik representasi dokumen seperti **Inverted Index**, **Vector Space Model**, **Term Frequency (TF)**, dan **Inverse Document Frequency (IDF)**.
3. Dapat menjalankan praktikum sederhana untuk membuat inverted index dan menghitung skor TF-IDF.

---

### **1. Pendahuluan**

#### **Apa itu Indexing?**

- **Definisi**: Indexing adalah proses menyimpan data yang telah dikumpulkan (dari crawling) dalam format yang mudah dicari.
- **Tujuan**: Mempercepat proses pencarian dengan mengorganisasi data secara sistematis.

#### **Mengapa Indexing Penting?**

- Tanpa indexing, mesin pencari harus memindai seluruh koleksi dokumen setiap kali pengguna melakukan query, yang sangat lambat.
- Indexing memungkinkan mesin pencari menemukan dokumen yang relevan dalam waktu singkat.

---

### **2. Teknik Indexing**

#### **1. Inverted Index**

- **Definisi**: Struktur data yang memetakan kata-kata ke dokumen yang mengandungnya.
- **Contoh**:
  - Kata "information" ada di dokumen 1, 2, dan 3.
  - Kata "retrieval" ada di dokumen 1 dan 2.
- **Keuntungan**: Memungkinkan pencarian cepat berdasarkan kata kunci.

#### **2. Vector Space Model**

- **Definisi**: Representasi dokumen sebagai vektor berdasarkan frekuensi kata.
- **Cara Kerja**:
  - Setiap kata menjadi dimensi dalam ruang vektor.
  - Frekuensi kata dalam dokumen menjadi nilai vektor.
- **Keuntungan**: Memungkinkan perhitungan kesamaan antar dokumen menggunakan metrik seperti cosine similarity.

#### **3. Term Frequency (TF)**

- **Definisi**: Jumlah kemunculan sebuah kata dalam dokumen.
- **Rumus**:
  $$
  \text{TF}(t, d) = \frac{\text{Jumlah kemunculan kata } t \text{ dalam dokumen } d}{\text{Total jumlah kata dalam dokumen } d}
  $$

#### **4. Inverse Document Frequency (IDF)**

- **Definisi**: Mengukur seberapa penting sebuah kata dalam koleksi dokumen.
- **Rumus**:
  $$
  \text{IDF}(t) = \log\left(\frac{\text{Total jumlah dokumen}}{\text{Jumlah dokumen yang mengandung kata } t}\right)
  $$

#### **5. TF-IDF**

- **Definisi**: Kombinasi TF dan IDF untuk memberikan bobot pada kata dalam dokumen.
- **Rumus**:
  $$
  \text{TF-IDF}(t, d) = \text{TF}(t, d) \times \text{IDF}(t)
  $$
- **Keuntungan**: Memberikan skor lebih tinggi untuk kata-kata yang jarang muncul tetapi penting.

---

### **3. Praktikum: Membuat Inverted Index dan Menghitung TF-IDF**

#### **Langkah 1: Diskusi Kelompok**

- Mahasiswa dibagi menjadi kelompok kecil (3-4 orang).
- Tugas: Identifikasi cara mesin pencari seperti Google menggunakan indexing untuk mempercepat pencarian.
- Contoh diskusi:
  - "Bagaimana Google bisa menemukan hasil pencarian dalam hitungan detik?"
  - "Apa yang terjadi jika tidak ada indexing?"

#### **Langkah 2: Membuat Inverted Index**

- Buat inverted index sederhana dari kumpulan dokumen.
- **Tujuan**: Memahami cara kerja inverted index.

```python
# In-Class Activity: Membuat Inverted Index
documents = {
    1: "information retrieval is important",
    2: "web information retrieval is useful",
    3: "retrieval systems are complex"
}

# Membuat inverted index
inverted_index = {}
for doc_id, text in documents.items():
    for word in text.split():
        if word not in inverted_index:
            inverted_index[word] = []
        inverted_index[word].append(doc_id)

# Menampilkan inverted index
print("Inverted Index:")
for word, doc_ids in inverted_index.items():
    print(f"{word}: {doc_ids}")
```

#### **Langkah 3: Menghitung TF-IDF**

- Hitung skor TF-IDF untuk setiap kata dalam dokumen.
- **Tujuan**: Memahami cara representasi dokumen menggunakan TF-IDF.

```python
# In-Class Activity: Menghitung TF-IDF
import math

# Data dokumen
documents = [
    "information retrieval is important",
    "web information retrieval is useful",
    "retrieval systems are complex"
]

# Membuat dictionary untuk menyimpan TF dan IDF
word_count = {}
doc_count = len(documents)

# Menghitung TF
def compute_tf(text):
    words = text.split()
    tf_dict = {}
    total_words = len(words)
    for word in words:
        tf_dict[word] = tf_dict.get(word, 0) + 1 / total_words
    return tf_dict

# Menghitung IDF
def compute_idf():
    idf_dict = {}
    for doc in documents:
        words = set(doc.split())
        for word in words:
            idf_dict[word] = idf_dict.get(word, 0) + 1
    for word, count in idf_dict.items():
        idf_dict[word] = math.log(doc_count / count)
    return idf_dict

# Menghitung TF-IDF
tf_dicts = [compute_tf(doc) for doc in documents]
idf_dict = compute_idf()

# Menampilkan hasil TF-IDF
print("\nTF-IDF Scores:")
for i, tf_dict in enumerate(tf_dicts):
    print(f"Dokumen {i+1}:")
    for word, tf in tf_dict.items():
        tf_idf = tf * idf_dict[word]
        print(f"  {word}: {tf_idf:.4f}")
```

---

### **4. Penutup**

#### **Kesimpulan**

- Indexing adalah langkah penting dalam Web Information Retrieval untuk mempercepat pencarian.
- Teknik seperti inverted index dan TF-IDF membantu mesin pencari menemukan dokumen yang relevan dengan cepat.
- Dengan memahami teknik indexing, mahasiswa dapat membangun sistem pencarian yang lebih efisien.

#### **Tugas Individu**

- Pilih satu dataset teks (misalnya, artikel berita atau blog) dan buat inverted index serta hitung skor TF-IDF.
- Kirimkan hasilnya dalam bentuk laporan singkat (1-2 halaman).

---

### **5. Referensi**

- Buku: _"Introduction to Information Retrieval"_ oleh Christopher D. Manning, Prabhakar Raghavan, dan Hinrich Schütze.
- Artikel: "Vector Space Model and TF-IDF Explained" oleh Stanford University.
- Website: [Scikit-Learn TF-IDF Documentation](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html)

---

> Written with [StackEdit](https://stackedit.io/).
