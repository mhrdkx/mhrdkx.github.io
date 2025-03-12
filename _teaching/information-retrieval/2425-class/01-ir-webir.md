---
title: "Introduction to Information Retrieval"
# collection: teaching
type: "Undergraduate course"
permalink: /teaching/information-retrieval/2425-class/01-ir-webir
venue: "Universitas Sam Ratulangi, Sistem Informasi"
date: 2025-01-01
location: "Manado, Indonesia"
author_profile: false
---

## **Materi 1: Pengenalan Web Information Retrieval**

#### **Tujuan Pembelajaran**

Setelah mempelajari materi ini, mahasiswa diharapkan:

1. Memahami konsep dasar **Web Information Retrieval (Web IR)**.
2. Mengetahui perbedaan antara **Information Retrieval (IR) tradisional** dan **Web IR**.
3. Mengenal aplikasi nyata dari Web IR dalam kehidupan sehari-hari.
4. Dapat menjalankan praktikum sederhana untuk mengidentifikasi contoh penggunaan Web IR.

---

### **1. Pendahuluan**

#### **Apa itu Information Retrieval?**

- **Definisi**: Information Retrieval (IR) adalah ilmu yang mempelajari cara mengambil informasi yang relevan dari kumpulan dokumen berdasarkan permintaan pengguna (query).
- **Contoh Sederhana**: Saat Anda mencari buku di perpustakaan menggunakan sistem katalog, Anda sedang melakukan IR.

#### **Apa itu Web Information Retrieval?**

- **Definisi**: Web Information Retrieval adalah cabang dari IR yang fokus pada pengambilan informasi dari **World Wide Web**.
- **Perbedaan dengan IR Tradisional**:
  - **Sumber Data**: Web IR bekerja dengan data yang tersebar di internet, sedangkan IR tradisional biasanya bekerja dengan koleksi dokumen terbatas (misalnya, database atau perpustakaan digital).
  - **Skala**: Web IR menangani data dalam skala besar dan dinamis, sedangkan IR tradisional sering kali statis.
  - **Format Data**: Web IR harus menangani berbagai format data (HTML, PDF, gambar, video), sedangkan IR tradisional biasanya berfokus pada teks.

---

### **2. Ruang Lingkup Web Information Retrieval**

Web IR melibatkan beberapa komponen utama:

1. **Crawling**: Proses mengumpulkan data dari web menggunakan robot (crawler/spider).
2. **Indexing**: Proses menyimpan data yang dikumpulkan dalam format yang mudah dicari.
3. **Query Processing**: Proses menganalisis permintaan pengguna dan mengembalikan hasil yang relevan.
4. **Ranking**: Proses mengurutkan hasil berdasarkan relevansi.

---

### **3. Pentingnya Web Information Retrieval**

- **Pencarian Informasi**: Web IR adalah inti dari mesin pencari seperti Google, Bing, dan DuckDuckGo.
- **E-commerce**: Platform seperti Amazon dan Tokopedia menggunakan Web IR untuk memberikan rekomendasi produk.
- **Media Sosial**: Instagram, Twitter, dan Facebook menggunakan Web IR untuk menampilkan konten yang relevan kepada pengguna.
- **Personalisasi**: Layanan seperti Netflix dan Spotify menggunakan Web IR untuk memberikan rekomendasi film atau musik.

---

### **4. Contoh Aplikasi Nyata**

1. **Google Search**: Mesin pencari terbesar di dunia yang menggunakan algoritma kompleks untuk mengindeks dan meranking halaman web.
2. **Amazon Product Search**: Membantu pengguna menemukan produk berdasarkan query mereka.
3. **YouTube Recommendations**: Memberikan rekomendasi video berdasarkan riwayat tontonan pengguna.
4. **Wikipedia**: Menggunakan teknologi IR untuk menyediakan artikel yang relevan berdasarkan query pengguna.

---

### **5. Praktikum: Identifikasi Contoh Nyata Penggunaan Web IR**

#### **Langkah 1: Diskusi Kelompok**

- Mahasiswa dibagi menjadi kelompok kecil (3-4 orang).
- Tugas: Identifikasi setidaknya 3 aplikasi nyata dari Web IR dalam kehidupan sehari-hari.
- Contoh diskusi:
  - "Bagaimana Google memberikan hasil pencarian yang relevan?"
  - "Bagaimana YouTube merekomendasikan video kepada pengguna?"

#### **Langkah 2: Eksplorasi Wikipedia API**

- Gunakan API Wikipedia untuk mendapatkan informasi tentang "Web Information Retrieval".
- **Tujuan**: Memahami bagaimana mesin pencari bekerja dalam mengambil informasi dari web.

```python
# In-Class Activity: Menggunakan Wikipedia API
import wikipedia

# Cari artikel tentang "Web Information Retrieval"
print(wikipedia.summary("Information retrieval"))
```

#### **Langkah 3: Simulasi Pencarian Sederhana**

- Buat simulasi pencarian sederhana menggunakan Python.
- **Tujuan**: Memahami bagaimana query diproses dan hasil ditampilkan.

```python
# In-Class Activity: Simulasi Pencarian Sederhana
def simple_search(query, documents):
    results = []
    for doc in documents:
        if query.lower() in doc.lower():
            results.append(doc)
    return results

# Kumpulan dokumen
documents = [
    "Web Information Retrieval is important for search engines.",
    "Machine Learning is used in Web IR.",
    "Big Data and Cloud Computing are related to Web IR."
]

# Query dari pengguna
query = input("Masukkan query Anda: ")
results = simple_search(query, documents)

print("Hasil Pencarian:")
for result in results:
    print("- ", result)
```

---

### **6. Penutup**

#### **Kesimpulan**

- Web Information Retrieval adalah cabang ilmu yang sangat penting dalam era digital.
- Web IR memiliki aplikasi luas di berbagai bidang, mulai dari mesin pencari hingga e-commerce.
- Dengan memahami konsep dasar Web IR, mahasiswa dapat membangun sistem pencarian yang lebih baik di masa depan.

#### **Tugas Individu**

- Carilah satu aplikasi nyata dari Web IR (selain yang telah dibahas di kelas).
- Jelaskan bagaimana aplikasi tersebut bekerja dan manfaatnya bagi pengguna.
- Kirimkan hasilnya dalam bentuk laporan singkat (1-2 halaman).

---

### **7. Referensi**

- Buku: _"Introduction to Information Retrieval"_ oleh Christopher D. Manning, Prabhakar Raghavan, dan Hinrich Schütze.
- Artikel: "The Anatomy of a Large-Scale Hypertextual Web Search Engine" oleh Sergey Brin dan Lawrence Page.
- Website: [Wikipedia API Documentation](https://wikipedia.readthedocs.io/en/latest/)
