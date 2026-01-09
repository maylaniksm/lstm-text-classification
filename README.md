# 📘 Implementasi Arsitektur LSTM untuk Klasifikasi Teks

![NLP](https://img.shields.io/badge/Domain-NLP-blue)
![Model](https://img.shields.io/badge/Model-LSTM-green)
![Framework](https://img.shields.io/badge/Framework-TensorFlow%20%7C%20PyTorch-orange)
![Status](https://img.shields.io/badge/Status-Selesai-success)

---

## 🧑‍🎓 Informasi Mahasiswa
- **Nama**: Maylani Kusuma Wardhani  
- **NIM**: 202210370311123  
- **Kelas**: NLP C  

📌 **Google Colab**:  
🔗 https://colab.research.google.com/drive/1Vb_xGd4YjgmcyQKq16sseF_ZAjiDqK-7  

📌 **Dataset**:  
🔗 https://huggingface.co/datasets/MrbBakh/Twitter_Sentiment  

---

## 📖 Pendahuluan
Natural Language Processing (NLP) merupakan cabang kecerdasan buatan yang berfokus pada pemrosesan dan pemahaman bahasa manusia. Salah satu permasalahan penting dalam NLP adalah **klasifikasi teks**, khususnya klasifikasi sentimen.

Pada proyek ini, digunakan **Long Short-Term Memory (LSTM)** untuk mengklasifikasikan teks berdasarkan sentimen. LSTM dipilih karena kemampuannya dalam memahami **urutan kata dan konteks jangka panjang**, yang sangat penting dalam data teks.

---

## 🧠 Arsitektur LSTM dan Cara Kerja
**Long Short-Term Memory (LSTM)** adalah pengembangan dari Recurrent Neural Network (RNN) yang dirancang untuk mengatasi masalah *vanishing gradient*.

### 🔑 Komponen Utama LSTM:
- **Forget Gate**  
  Menentukan informasi yang perlu dihapus dari memori sebelumnya.
- **Input Gate**  
  Menentukan informasi baru yang akan disimpan.
- **Output Gate**  
  Menentukan output yang dihasilkan berdasarkan memori sel.

Dengan mekanisme ini, LSTM mampu menangkap hubungan kata dalam kalimat secara lebih efektif.

---

## ⚖️ Kelebihan dan Kekurangan LSTM

### ✅ Kelebihan
- Mampu menangkap konteks jangka panjang
- Stabil saat proses pelatihan
- Sangat cocok untuk data sekuensial seperti teks

### ❌ Kekurangan
- Waktu pelatihan relatif lebih lama
- Membutuhkan sumber daya komputasi lebih besar
- Performa kalah dibanding Transformer (misalnya BERT) pada dataset besar

---

## 🎯 Alasan Pemilihan LSTM
LSTM dipilih karena:
- Mempertahankan urutan kata dalam kalimat
- Efektif untuk klasifikasi sentimen
- Cocok untuk dataset kecil hingga menengah
- Lebih sederhana dibanding Transformer namun tetap powerful

---

## 🛠️ Tahapan Implementasi

### 1️⃣ Preprocessing Data
- Tokenisasi menggunakan `Tokenizer` dari `tensorflow.keras`
- Jumlah maksimum kata: **10.000**
- Padding sequence hingga panjang **100 kata**

---

### 2️⃣ Pembuatan Dataset & Dataloader
- Pembagian data:
  - **80%** data latih
  - **20%** data validasi
- Dataset dibuat secara custom menggunakan:
  - `torch.utils.data.Dataset`
  - `DataLoader`

---

### 3️⃣ Arsitektur Model
Model LSTM yang digunakan terdiri dari:
- **Embedding Layer**
- **LSTM Layer**
  - Hidden size: **64**
- **Fully Connected Layer**
  - Output: **2 kelas sentimen**

---

### 4️⃣ Pelatihan Model
- **Optimizer**: Adam  
- **Loss Function**: CrossEntropyLoss  
- **Epoch**: 5  

---

### 5️⃣ Evaluasi & Visualisasi
Evaluasi model dilakukan menggunakan:
- 📊 **Confusion Matrix**
- 📈 **Classification Report**
  - Precision
  - Recall
  - F1-Score
- 📉 **Grafik Loss dan Akurasi** per epoch

---

## 📊 Hasil dan Analisis
Model LSTM menunjukkan performa yang cukup baik dalam mengklasifikasikan teks.  
Hasil pelatihan menunjukkan:
- Akurasi validasi meningkat secara konsisten
- Loss menurun secara stabil
- Confusion Matrix menunjukkan klasifikasi dua kelas berjalan efektif

Model mampu membedakan sentimen dengan tingkat akurasi yang memadai untuk dataset sederhana.

---

## 🏁 Kesimpulan
LSTM merupakan solusi yang efektif untuk tugas klasifikasi teks, terutama ketika **konteks dan urutan kata** berperan penting.  
Walaupun kalah populer dibanding model Transformer modern, LSTM tetap relevan dan andal untuk:
- Dataset kecil hingga menengah
- Lingkungan dengan keterbatasan komputasi
- Pembelajaran konsep NLP sekuensial

---

## 📌 Catatan
Repositori ini dibuat sebagai bagian dari tugas mata kuliah **Natural Language Processing (NLP)** dan bertujuan untuk pembelajaran serta eksplorasi model LSTM pada klasifikasi teks.

✨ *Feel free to explore, modify, and improve!*
