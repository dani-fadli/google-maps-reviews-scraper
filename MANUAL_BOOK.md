# Manual Book
**Analisis Sentimen Tempat Wisata Air Terjun Di Bandung Raya Berdasarkan Ulasan Google Maps Menggunakan Algoritma Support Vector Machine**

## Struktur Folder
- `Count_Reviews.ipynb`
- `Scrape_Reviews.ipynb`
- `SVM_IndoBERT.ipynb`
- `datasets/All_Reviews.csv`, `id-tourism-sentimentanalysis.tsv`, `train_preprocess.tsv`
- `results/classification/classified_reviews.csv`
- `results/scraping/*.csv`

---

## 1. Scrape Reviews Count
**File:** `Count_Reviews.ipynb`

### Deskripsi
Program ini digunakan untuk mengambil jumlah ulasan dari berbagai tempat wisata air terjun di Bandung Raya melalui Google Maps.

### Cara Penggunaan
1. Buka `Count_Reviews.ipynb` di Google Colab atau Jupyter Notebook.
2. Jalankan seluruh sel.
3. Program akan mengekstrak jumlah ulasan dari URL Google Maps yang telah ditentukan.
4. Hasil akan disimpan dalam bentuk dataframe dan dapat diekspor ke CSV.

### Output
- File CSV berisi jumlah ulasan tiap tempat wisata (dapat disimpan manual oleh user).

---

## 2. Scrape Reviews
**File:** `Scrape_Reviews.ipynb`

### Deskripsi
Program ini digunakan untuk mengambil seluruh ulasan Google Maps dari tempat wisata air terjun yang telah dipilih.

### Cara Penggunaan
1. Buka `Scrape_Reviews.ipynb` di Google Colab.
2. Jalankan seluruh sel.
3. Program akan melakukan scraping ulasan dari daftar URL tempat wisata.
4. Setiap hasil scraping akan disimpan dalam file CSV dengan format:
	`results/scraping/{Nama_Tempat}_reviews_{Tanggal_Jam}.csv`
	Contoh:
	- `results/scraping/Curug_Cilengkrang_reviews_20250620_153957.csv`
	- `results/scraping/Curug_Cinulang_reviews_20250620_135116.csv`

### Output
- File CSV berisi ulasan tiap tempat wisata di folder `results/scraping`.

---

## 3. Predict Sentiment Using SVM IndoBERT-large
**File:** `SVM_IndoBERT.ipynb`

### Deskripsi
Program ini digunakan untuk melakukan analisis sentimen pada ulasan yang telah dikumpulkan, menggunakan model SVM dengan embedding IndoBERT-large.

### Cara Penggunaan
1. Buka `SVM_IndoBERT.ipynb` di Google Colab.
2. Jalankan seluruh sel secara berurutan.
3. Program akan:
	- Memuat dataset ulasan (`datasets/All_Reviews.csv`)
	- Melakukan preprocessing dan ekstraksi embedding IndoBERT
	- Melatih model SVM atau memuat model yang sudah disimpan (`svm_model.joblib`)
	- Melakukan prediksi sentimen pada ulasan
	- Menyimpan hasil klasifikasi ke file CSV:
	  `results/classification/classified_reviews.csv`
	- Menampilkan visualisasi distribusi sentimen dan wordcloud

### Output
- File CSV hasil klasifikasi sentimen: `results/classification/classified_reviews.csv`
- Model SVM terlatih: `svm_model.joblib`
- Visualisasi distribusi sentimen dan wordcloud (ditampilkan di notebook)

---

## Alur Data
1. `Count_Reviews.ipynb` → Mendapatkan jumlah ulasan tiap tempat wisata.
2. `Scrape_Reviews.ipynb` → Mengambil seluruh ulasan dan menyimpannya dalam CSV.
3. `SVM_IndoBERT.ipynb` → Melakukan analisis sentimen pada ulasan, menyimpan hasil klasifikasi, dan visualisasi.

---

## Catatan
- Dataset hasil scraping dapat digabungkan secara manual menjadi `datasets/All_Reviews.csv` untuk analisis sentimen.
- Semua output file dapat digunakan sebagai lampiran hasil penelitian skripsi.
