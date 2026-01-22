# 📩 SMS Spam Detector (Bahasa Indonesia)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Ryonandha/sms-spam-detector-indonesia/blob/main/SMS_Spam_Detector_Indonesia.ipynb)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Library-Scikit_Learn-orange)
![License](https://img.shields.io/badge/License-MIT-green)

Proyek *Machine Learning* untuk mengklasifikasikan pesan SMS dalam Bahasa Indonesia ke dalam tiga kategori: **Normal**, **Penipuan (Fraud)**, dan **Promo**. Model ini dibangun menggunakan algoritma **Multinomial Naive Bayes** dengan ekstraksi fitur **TF-IDF**.

## 📌 Daftar Isi
- [Tentang Proyek](#-tentang-proyek)
- [Dataset](#-dataset)
- [Teknologi yang Digunakan](#-teknologi-yang-digunakan)
- [Hasil & Performa](#-hasil--performa)
- [Cara Menjalankan](#-cara-menjalankan)
- [Contoh Penggunaan](#-contoh-penggunaan)

## 📖 Tentang Proyek
Sistem ini dibuat untuk memfilter pesan spam yang sering mengganggu pengguna seluler di Indonesia. Model dilatih untuk membedakan konteks bahasa Indonesia (termasuk bahasa gaul/singkatan) untuk menentukan apakah sebuah pesan aman atau berbahaya.

**Metode:**
1. Text Preprocessing (pembersihan data).
2. Feature Extraction menggunakan **TF-IDF (Term Frequency-Inverse Document Frequency)**.
3. Modeling menggunakan **Multinomial Naive Bayes**.

## 📊 Dataset
Dataset yang digunakan merupakan koleksi publik yang terdiri dari **1.143 data SMS** dengan label sebagai berikut:

| Label | Deskripsi | Jumlah Data |
| :--- | :--- | :--- |
| **Normal** | Percakapan pribadi atau informasi wajar | 569 |
| **Penipuan** | Modus penipuan (minta pulsa, menang undian) | 335 |
| **Promo** | Iklan operator atau penawaran produk | 239 |

*Sumber Dataset: [Gist GitHub - dataset_sms_spam_v2.csv](https://gist.githubusercontent.com/agtbaskara/a1a7017027cc1df9d35cf06e1e5575b7/raw/59870e27ca217d77ac0d8d8dc100551c0dcd14b3/dataset_sms_spam_v2.csv)*

## 🛠 Teknologi yang Digunakan
* **Python** (Bahasa Pemrograman utama)
* **Pandas & NumPy** (Analisis & Manipulasi Data)
* **Scikit-Learn** (Pembuatan Model Machine Learning)
* **Matplotlib & Seaborn** (Visualisasi Data/Confusion Matrix)

## 📈 Hasil & Performa
Berdasarkan pengujian menggunakan data *testing* (20% dari total data), model mencapai performa berikut:

* **Akurasi Model:** `91.70%`

**Classification Report:**
```text
              precision    recall  f1-score   support

      normal       0.94      0.93      0.93        99
    penipuan       0.97      0.89      0.93        82
       promo       0.80      0.94      0.87        48

    accuracy                           0.92       229

```

## 🚀 Cara Menjalankan
### Opsi 1: Google Colab (Direkomendasikan)
Klik badge "Open In Colab" di bagian paling atas README ini untuk menjalankan kode langsung di browser tanpa instalasi.

### Opsi 2: Jalankan di Lokal (Local Machine)
1. **Clone Repository**
```bash
git clone [https://github.com/Ryonandha/sms-spam-detector-indonesia.git](https://github.com/Ryonandha/sms-spam-detector-indonesia.git)
cd sms-spam-detector-indonesia
```
2. **Install Library**
Pastikan Python sudah terinstall, lalu jalankan:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

3. **Jalankan Notebook**
Buka file `.ipynb` menggunakan Jupyter Notebook atau VS Code.

## 📝 Contoh Penggunaan
Di dalam notebook terdapat fungsi `cek_sms()` untuk mendeteksi teks baru secara *real-time*.
```python
# Contoh Input
teks1 = "Selamat siang, apakah hari ini ada kuliah?"
teks2 = "Selamat! Anda menang undian 100jt dr Shopee. Klik link bit.ly/xxx"
print(cek_sms(teks1))
print(cek_sms(teks2))
```

**Output:**
```text
Hasil: normal (Yakin 85.7%)
Hasil: penipuan (Yakin 79.2%)
```

**Author:** [Ryonandha](https://www.google.com/search?q=https://github.com/Ryonandha)

*Project ini dibuat untuk tujuan edukasi dan eksperimen NLP Sederhana.*
