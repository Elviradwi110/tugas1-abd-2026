# Tugas 1 Analisis Big Data 2026

## Analisis Data Produksi dan Rantai Pasok Kelapa Sawit Indonesia

Repository ini merupakan implementasi **Tugas 1 Analisis Big Data 2026** pada mata kuliah Analisis Big Data.

Project ini berfokus pada proses pengolahan dataset berukuran besar mulai dari data profiling, data cleaning, exploratory data analysis (EDA), visualisasi interaktif, hingga penarikan insight berdasarkan data produksi dan rantai pasok kelapa sawit Indonesia.

Pengolahan data dilakukan menggunakan **Polars** sebagai library utama untuk data processing, **DuckDB** untuk analisis SQL dan profiling, serta **Plotly** untuk menghasilkan visualisasi interaktif.

Project juga menggunakan **Docker** untuk mendukung reproducibility environment sehingga notebook dapat dijalankan pada environment yang telah didefinisikan melalui Dockerfile.

---

# 1. Informasi Project

| Informasi | Keterangan |
|---|---|
| Mata Kuliah | Analisis Big Data |
| Tugas | Tugas 1 Analisis Big Data 2026 |
| Topik | Produksi dan Rantai Pasok Kelapa Sawit Indonesia |
| Bahasa Pemrograman | Python |
| Data Processing | Polars |
| SQL Analytics | DuckDB |
| Visualisasi | Plotly |
| Notebook | Jupyter Notebook / JupyterLab |
| Containerization | Docker |
| Version Control | Git |
| Repository | GitHub |

---

# 2. Dataset

Dataset yang digunakan dalam project ini adalah dataset produksi dan rantai pasok kelapa sawit Indonesia.

Dataset memiliki ukuran yang cukup besar sehingga sesuai dengan karakteristik tugas Big Data.

## Karakteristik Dataset

| Karakteristik | Nilai |
|---|---:|
| Jumlah baris | 1.694.907 |
| Jumlah kolom | 34 |
| Ukuran file CSV | ±721,83 MB |
| Periode data | 2013–2022 |
| Negara produksi | Indonesia |
| Format data awal | CSV |
| Format data hasil cleaning | Parquet |

Dataset memenuhi persyaratan ukuran data karena memiliki:

- lebih dari **1.000.000 baris**;
- ukuran file lebih dari **500 MB**.

File dataset mentah berada pada:

**data/raw/indonesia_palm_oil_v1_2_5.csv**

Dataset mentah tidak disimpan di repository GitHub karena ukuran file cukup besar.

Informasi mengenai sumber dataset dan petunjuk untuk memperoleh dataset tersedia pada:

**data/README.md**

---

# 3. Tujuan Analisis

Project ini bertujuan untuk:

1. Melakukan profiling terhadap dataset berukuran besar.
2. Mengidentifikasi struktur dan karakteristik dataset.
3. Menganalisis kualitas data.
4. Melakukan proses data cleaning menggunakan Polars.
5. Menggunakan DuckDB untuk profiling dan validasi data.
6. Menganalisis tren produksi berdasarkan tahun.
7. Menganalisis distribusi produksi berdasarkan provinsi.
8. Menganalisis volume berdasarkan jenis produk.
9. Menganalisis hubungan volume produksi dengan FOB.
10. Menganalisis deforestation exposure berdasarkan provinsi.
11. Menganalisis emission exposure.
12. Menghasilkan visualisasi interaktif menggunakan Plotly.
13. Menghasilkan insight berdasarkan hasil exploratory data analysis.
14. Membuat environment yang dapat direproduksi menggunakan Docker.

---

# 4. Struktur Repository

Struktur repository project adalah sebagai berikut:

TUGAS 1 ANALISIS BIG DATA/
├── data/
│   ├── raw/
│   │   └── indonesia_palm_oil_v1_2_5.csv
│   ├── processed/
│   │   └── indonesia_palm_oil_cleaned.parquet
│   └── README.md
├── notebooks/
│   ├── 01_data_profiling.ipynb
│   ├── 02_data_cleaning.ipynb
│   └── 03_eda_and_insights.ipynb
├── output/
│   └── figures/
├── src/
├── .github/
│   └── workflows/
│       └── lint_check.yml
├── .dockerignore
├── .gitignore
├── Dockerfile
├── README.md
└── requirements.txt

### Keterangan Folder dan File

| Folder/File | Keterangan |
|---|---|
| `data/raw/` | Menyimpan dataset mentah |
| `data/processed/` | Menyimpan dataset hasil cleaning |
| `data/README.md` | Dokumentasi sumber dan petunjuk dataset |
| `notebooks/` | Notebook untuk proses analisis |
| `output/figures/` | Folder untuk output visualisasi |
| `src/` | Source code tambahan |
| `.github/workflows/` | Konfigurasi GitHub Actions |
| `.dockerignore` | Mengecualikan file tertentu dari Docker build context |
| `.gitignore` | Mengecualikan file tertentu dari Git |
| `Dockerfile` | Konfigurasi environment Docker |
| `requirements.txt` | Daftar dependency Python |
| `README.md` | Dokumentasi utama project |

---

# 5. Alur Analisis

Proses analisis dilakukan secara bertahap mulai dari dataset mentah hingga menghasilkan insight.

Dataset CSV
↓
01_data_profiling.ipynb
↓
Data Profiling
↓
02_data_cleaning.ipynb
↓
Data Cleaning & Validation
↓
Cleaned Parquet
↓
03_eda_and_insights.ipynb
↓
Exploratory Data Analysis
↓
Visualisasi Interaktif
↓
Insights

Notebook dijalankan secara berurutan:

1. **01_data_profiling.ipynb**  
   Digunakan untuk memahami karakteristik awal dataset, struktur data, statistik, dan kualitas data.

2. **02_data_cleaning.ipynb**  
   Digunakan untuk melakukan proses cleaning, validasi, konversi tipe data, pemeriksaan missing values, duplicate, outlier, dan menghasilkan dataset Parquet.

3. **03_eda_and_insights.ipynb**  
   Digunakan untuk melakukan exploratory data analysis, analisis temporal dan spasial, membuat visualisasi interaktif, serta menghasilkan insight.

Alur utama project adalah:

**Dataset CSV → Profiling → Cleaning → Validasi → Parquet → EDA → Visualisasi → Insights**

---

# 6. Milestone 1 - Data Profiling

Notebook yang digunakan:

**notebooks/01_data_profiling.ipynb**

Tahap profiling dilakukan untuk memahami karakteristik awal dataset sebelum proses cleaning.

Analisis yang dilakukan meliputi:

- jumlah baris dan kolom;
- ukuran dataset;
- struktur kolom;
- tipe data;
- statistik deskriptif;
- missing values;
- distribusi tahun;
- distribusi volume;
- profiling menggunakan Polars;
- profiling menggunakan DuckDB.

## Hasil Profiling

Hasil profiling menunjukkan:

- Jumlah baris: **1.694.907**
- Jumlah kolom: **34**
- Ukuran file CSV: **±721,83 MB**
- Periode data: **2013–2022**

Dataset memenuhi kriteria data berukuran besar karena memiliki lebih dari satu juta baris dan ukuran file lebih dari 500 MB.

---

# 7. Struktur Kolom Dataset

Dataset memiliki 34 kolom, yaitu:

- `year`
- `country_of_production`
- `product_type`
- `forest_500_palm_oil`
- `zero_deforestation_indonesia_palm_oil`
- `province_of_production`
- `kabupaten_of_production`
- `mill`
- `mill_trase_id`
- `mill_group`
- `refinery`
- `refinery_trase_id`
- `refinery_group`
- `exporter`
- `exporter_group`
- `port_of_export`
- `importer`
- `importer_group`
- `country_of_first_import`
- `economic_bloc`
- `province_of_production_trase_id`
- `kabupaten_of_production_trase_id`
- `country_of_production_trase_id`
- `country_of_first_import_trase_id`
- `palm_oil_deforestation_10_year_total_exposure`
- `palm_oil_deforestation_annual_exposure`
- `total_emission_exposure`
- `net_emission_luc_exposure`
- `emission_subsidence_exposure`
- `gross_emission_luc_exposure`
- `emissions_fire_on_peat_exposure`
- `volume`
- `oil_palm_ha`
- `fob`

Kolom-kolom tersebut mencakup informasi mengenai tahun, wilayah produksi, jenis produk, rantai pasok, volume, nilai FOB, deforestation exposure, dan emission exposure.

---

# 8. Profiling Menggunakan DuckDB

DuckDB digunakan untuk melakukan profiling tambahan menggunakan SQL.

Fungsi `SUMMARIZE` digunakan untuk memperoleh informasi mengenai:

- tipe data;
- jumlah nilai;
- minimum;
- maksimum;
- rata-rata;
- jumlah NULL;
- statistik lainnya.

Penggunaan DuckDB membantu melakukan pemeriksaan dataset menggunakan pendekatan SQL tanpa harus menggunakan Pandas.

---

# 9. Milestone 2 - Data Cleaning

Notebook yang digunakan:

**notebooks/02_data_cleaning.ipynb**

Data cleaning dilakukan menggunakan **Polars Lazy API** dan validasi dilakukan menggunakan Polars serta DuckDB.

Tahapan cleaning meliputi:

1. Pemeriksaan missing values.
2. Pemeriksaan duplicate.
3. Pemeriksaan tipe data.
4. Konversi data numerik.
5. Pemeriksaan nilai negatif.
6. Pemeriksaan nilai nol.
7. Pemeriksaan outlier.
8. Pemeriksaan nilai `UNKNOWN`.
9. Validasi hasil cleaning.
10. Penyimpanan dataset dalam format Parquet.

---

# 10. Missing Value Analysis

Hasil pemeriksaan missing values menunjukkan bahwa beberapa kolom memiliki nilai kosong.

Lima kolom yang berkaitan dengan emission exposure memiliki sekitar:

**1.025.290 missing values**

atau sekitar:

**60,49%**

Kolom tersebut adalah:

- `total_emission_exposure`
- `net_emission_luc_exposure`
- `emission_subsidence_exposure`
- `gross_emission_luc_exposure`
- `emissions_fire_on_peat_exposure`

Selain itu terdapat missing values pada:

- `palm_oil_deforestation_10_year_total_exposure`
- `palm_oil_deforestation_annual_exposure`
- `oil_palm_ha`
- `fob`

---

# 11. Missing Value Berdasarkan Tahun

Analisis berdasarkan tahun menunjukkan bahwa data emission exposure tidak tersedia secara lengkap untuk seluruh periode.

Data emission exposure pada tahun **2013–2020** tidak tersedia.

Data emission exposure tersedia pada:

- **2021**
- **2022**

Missing values tersebut tidak diubah menjadi nilai nol karena missing value menunjukkan data yang tidak tersedia, bukan berarti nilai sebenarnya adalah nol.

Oleh karena itu:

- missing value tidak diimputasi menjadi nol;
- baris tidak dihapus hanya karena memiliki missing value;
- nilai asli tetap dipertahankan.

---

# 12. Duplicate Analysis

Pemeriksaan duplicate dilakukan terhadap keseluruhan baris dataset.

Hasil pemeriksaan menunjukkan tidak ditemukan duplicate baris penuh yang perlu dihapus.

Jumlah baris setelah proses cleaning tetap:

**1.694.907**

---

# 13. Data Type Conversion

Beberapa kolom awalnya terbaca sebagai string walaupun berisi data numerik.

Kolom yang dikonversi menjadi tipe `Float64` antara lain:

- `oil_palm_ha`
- `fob`
- `palm_oil_deforestation_10_year_total_exposure`
- `palm_oil_deforestation_annual_exposure`
- `total_emission_exposure`
- `net_emission_luc_exposure`
- `emission_subsidence_exposure`
- `gross_emission_luc_exposure`
- `emissions_fire_on_peat_exposure`

Pemeriksaan juga dilakukan untuk memastikan tidak terdapat nilai non-numerik yang menghambat proses konversi.

---

# 14. Negative Value Analysis

Pemeriksaan nilai negatif dilakukan pada variabel numerik.

Nilai negatif ditemukan pada:

- `total_emission_exposure`
- `net_emission_luc_exposure`

Nilai negatif terutama terdapat pada data tahun:

- **2021**
- **2022**

Nilai tersebut tidak langsung dihapus karena belum terdapat bukti bahwa nilai tersebut merupakan kesalahan input.

Oleh karena itu, nilai negatif tetap dipertahankan sebagai bagian dari dataset.

---

# 15. Zero Value Analysis

Pemeriksaan nilai nol dilakukan pada beberapa variabel numerik.

Nilai nol ditemukan pada beberapa variabel seperti:

- `oil_palm_ha`
- `fob`
- `palm_oil_deforestation_10_year_total_exposure`
- `palm_oil_deforestation_annual_exposure`

Nilai nol dipertahankan karena dapat merupakan nilai yang valid dan tidak dapat langsung dianggap sebagai kesalahan.

---

# 16. Outlier Analysis

Outlier dianalisis menggunakan metode **Interquartile Range (IQR)**.

Variabel yang diperiksa meliputi:

- `volume`
- `oil_palm_ha`
- `fob`
- `palm_oil_deforestation_10_year_total_exposure`
- `palm_oil_deforestation_annual_exposure`

Beberapa variabel memiliki jumlah outlier yang cukup besar.

Outlier tidak otomatis dihapus karena:

1. Distribusi beberapa variabel sangat skewed.
2. Nilai ekstrem dapat merepresentasikan aktivitas produksi atau perdagangan dalam jumlah besar.
3. Penghapusan otomatis dapat menyebabkan kehilangan informasi.
4. Tidak terdapat bukti yang cukup bahwa seluruh nilai ekstrem merupakan kesalahan input.

Dengan demikian, nilai outlier dipertahankan.

---

# 17. UNKNOWN Value Analysis

Beberapa kolom memiliki kategori `UNKNOWN`.

Contohnya:

- `province_of_production`
- `kabupaten_of_production`
- `mill`
- `refinery`
- `exporter`
- `importer`

Nilai `UNKNOWN` dipertahankan karena merupakan bagian dari data asli.

Pada analisis spasial, baris dengan wilayah `UNKNOWN` dikeluarkan dari agregasi tertentu agar hasil berdasarkan provinsi dapat diinterpretasikan dengan lebih baik.

---

# 18. Hasil Cleaning

Setelah proses cleaning dan validasi, dataset memiliki:

- Jumlah baris: **1.694.907**
- Jumlah kolom: **34**

Dataset hasil cleaning disimpan dalam format Parquet:

**data/processed/indonesia_palm_oil_cleaned.parquet**

Ukuran file hasil Parquet sekitar **47,5 MB**.

Format Parquet digunakan untuk proses analisis berikutnya karena lebih efisien dibandingkan membaca CSV mentah secara berulang.

---

# 19. Milestone 3 - Exploratory Data Analysis

Notebook yang digunakan:

**notebooks/03_eda_and_insights.ipynb**

EDA dilakukan menggunakan:

- Polars;
- DuckDB;
- Plotly Express;
- Plotly Graph Objects.

Analisis mencakup aspek temporal, spasial, produk, perdagangan, deforestasi, dan emisi.

---

# 20. Analisis Temporal

Analisis temporal dilakukan dengan mengagregasikan total volume berdasarkan tahun.

Hasil agregasi volume:

| Tahun | Total Volume |
|---|---:|
| 2013 | ±27,14 juta |
| 2014 | ±29,27 juta |
| 2015 | ±31,07 juta |
| 2016 | ±31,73 juta |
| 2017 | ±37,97 juta |
| 2018 | ±42,88 juta |
| 2019 | ±47,11 juta |
| 2020 | ±44,76 juta |
| 2021 | ±45,03 juta |
| 2022 | ±46,69 juta |

Visualisasi yang digunakan adalah line chart interaktif.

---

# 21. Analisis Spasial

Analisis spasial dilakukan berdasarkan:

`province_of_production`

Wilayah `UNKNOWN` tidak digunakan dalam agregasi utama provinsi.

Sepuluh provinsi dengan total volume terbesar adalah:

1. RIAU
2. KALIMANTAN TENGAH
3. SUMATERA UTARA
4. KALIMANTAN BARAT
5. KALIMANTAN TIMUR
6. SUMATERA SELATAN
7. JAMBI
8. KALIMANTAN SELATAN
9. SUMATERA BARAT
10. ACEH

---

# 22. Analisis Jenis Produk

Dataset memiliki dua jenis produk utama:

- `PALM OIL`
- `REFINED PALM OIL`

Total volume kategori `PALM OIL` adalah:

**273.879.112,78**

Sedangkan kategori `REFINED PALM OIL` memiliki volume sekitar:

**109,76 juta**

Perbandingan dilakukan menggunakan bar chart interaktif.

---

# 23. Analisis Volume dan FOB

Analisis hubungan volume dengan FOB dilakukan menggunakan scatter plot.

Variabel yang digunakan:

- `volume`
- `fob`

Analisis dilakukan pada data yang:

- memiliki provinsi yang diketahui;
- memiliki nilai FOB;
- tidak termasuk kategori `UNKNOWN`.

Visualisasi ini digunakan untuk melihat pola hubungan antara volume produksi dengan nilai FOB berdasarkan provinsi.

---

# 24. Analisis Deforestation Exposure

Analisis deforestation exposure menggunakan:

`palm_oil_deforestation_10_year_total_exposure`

Analisis dilakukan berdasarkan provinsi.

Kalimantan Barat memiliki total deforestation exposure terbesar pada agregasi provinsi:

**1.949.347,35**

Analisis ini digunakan untuk melihat distribusi exposure deforestasi berdasarkan wilayah produksi.

---

# 25. Analisis Emission Exposure

Analisis emission exposure dilakukan berdasarkan tahun.

Karena data emission exposure tersedia terutama pada tahun 2021 dan 2022, analisis difokuskan pada kedua tahun tersebut.

Hasil agregasi:

| Tahun | Total Emission Exposure |
|---|---:|
| 2021 | ±161,20 juta |
| 2022 | 161.972.673,77 |

Data tahun 2022 memiliki total emission exposure yang lebih tinggi dibandingkan tahun 2021 pada data yang tersedia.

---

# 26. Visualisasi Interaktif

Project menghasilkan minimal enam visualisasi interaktif menggunakan Plotly.

Visualisasi yang dibuat:

1. **Tren Total Volume Produksi**  
   Menunjukkan perubahan total volume produksi dari tahun 2013 sampai 2022.

2. **Top 10 Provinsi Berdasarkan Volume**  
   Menunjukkan provinsi dengan total volume produksi terbesar.

3. **Volume Berdasarkan Jenis Produk**  
   Membandingkan total volume antara `PALM OIL` dan `REFINED PALM OIL`.

4. **Volume vs FOB**  
   Scatter plot yang membandingkan volume produksi dengan nilai FOB berdasarkan provinsi.

5. **Top 10 Provinsi Berdasarkan Deforestation Exposure**  
   Menunjukkan provinsi dengan nilai deforestation exposure terbesar.

6. **Emission Exposure 2021–2022**  
   Membandingkan total emission exposure pada tahun 2021 dan 2022.

---

# 27. Insights

Berdasarkan hasil exploratory data analysis, diperoleh beberapa insight utama.

## Insight 1 - Volume Produksi Tertinggi

Volume produksi tahunan tertinggi selama periode 2013–2022 terjadi pada tahun **2019**.

Total volume pada tahun 2019:

**47.113.546,71**

atau sekitar **47,11 juta**.

## Insight 2 - Provinsi dengan Volume Terbesar

RIAU memiliki total volume produksi terbesar dibandingkan provinsi lainnya dalam agregasi dataset.

Total volume RIAU:

**39.191.423,00**

## Insight 3 - Produk dengan Volume Terbesar

Kategori `PALM OIL` memiliki total volume terbesar.

Total volume:

**273.879.112,78**

## Insight 4 - Deforestation Exposure

Kalimantan Barat memiliki total deforestation exposure 10 tahun terbesar pada agregasi provinsi.

Total:

**1.949.347,35**

## Insight 5 - Emission Exposure Tahun 2022

Berdasarkan data emission exposure yang tersedia, total emission exposure tahun 2022 mencapai:

**161.972.673,77**

---

# 28. Teknologi yang Digunakan

| Teknologi | Penggunaan |
|---|---|
| Python | Bahasa pemrograman |
| Polars | Data processing dan cleaning |
| DuckDB | SQL analytics dan profiling |
| Plotly | Visualisasi interaktif |
| NumPy | Dependensi numerik |
| Jupyter | Notebook |
| JupyterLab | Environment notebook |
| Docker | Reproducible environment |
| Git | Version control |
| GitHub | Repository |

---

# 29. Requirements

Dependencies project disimpan pada:

`requirements.txt`

Library utama yang digunakan:

- `polars`
- `duckdb`
- `plotly`
- `numpy`
- `jupyter`
- `ipykernel`

---

# 30. Instalasi Local Environment

Pastikan Python telah terinstall.

Buat virtual environment:

`python -m venv .venv`

Aktifkan virtual environment pada Windows PowerShell:

`.venv\Scripts\Activate.ps1`

Jika berhasil, terminal akan menampilkan:

`(.venv)`

Install seluruh dependencies:

`pip install -r requirements.txt`

---

# 31. Menyiapkan Dataset

Dataset mentah harus ditempatkan pada:

`data/raw/indonesia_palm_oil_v1_2_5.csv`

Pastikan nama file sesuai dengan path yang digunakan pada notebook.

Struktur folder data:

data/
├── raw/
│   └── indonesia_palm_oil_v1_2_5.csv
├── processed/
└── README.md

Dataset mentah tidak disimpan di GitHub karena memiliki ukuran sekitar 721,83 MB.

---

# 32. Menjalankan Notebook

Setelah virtual environment aktif, jalankan:

`jupyter lab`

Kemudian jalankan notebook secara berurutan.

### Notebook 1 - Profiling

`notebooks/01_data_profiling.ipynb`

Notebook ini melakukan profiling terhadap dataset mentah.

### Notebook 2 - Cleaning

`notebooks/02_data_cleaning.ipynb`

Notebook ini melakukan cleaning dan menghasilkan:

`data/processed/indonesia_palm_oil_cleaned.parquet`

### Notebook 3 - EDA

`notebooks/03_eda_and_insights.ipynb`

Notebook ini membaca dataset Parquet hasil cleaning dan melakukan EDA, visualisasi, serta menghasilkan insight.

---

# 33. Menjalankan dengan Docker

Project menyediakan `Dockerfile` untuk membuat environment yang konsisten dan reproducible.

## Build Docker Image

Jalankan dari root project:

`docker build -t tugas1-bigdata .`

## Menjalankan JupyterLab

`docker run -d --name tugas1-jupyter -p 8888:8888 -v "${PWD}:/home/jovyan/work" tugas1-bigdata`

Setelah container berjalan, buka:

`http://localhost:8888/lab`

Notebook project dapat dijalankan melalui JupyterLab.

---

# 34. Mengecek Docker Container

Untuk melihat container yang sedang berjalan:

`docker ps`

Container project menggunakan nama:

`tugas1-jupyter`

Untuk melihat log container:

`docker logs tugas1-jupyter`

Untuk menghentikan container:

`docker stop tugas1-jupyter`

Jika container sudah tidak digunakan, container dapat dihapus:

`docker rm tugas1-jupyter`

---

# 35. Reproducibility

Project dirancang agar proses analisis dapat direproduksi melalui:

- `requirements.txt` untuk dependency Python;
- `Dockerfile` untuk environment;
- `.gitignore` untuk mencegah dataset besar masuk repository;
- `.dockerignore` untuk mencegah dataset besar masuk Docker build context;
- notebook yang dijalankan secara berurutan;
- dataset hasil cleaning dalam format Parquet;
- Git untuk version control;
- GitHub sebagai repository.

Alur reproducibility:

**Clone Repository → Install Dependencies → Siapkan Dataset → Profiling → Cleaning → Parquet → EDA → Visualisasi → Insights**

---

# 36. Pengelolaan Dataset Besar

Karena dataset mentah memiliki ukuran sekitar 721,83 MB, dataset tidak disimpan pada repository GitHub.

File yang dikecualikan dari Git melalui `.gitignore`:

- `data/raw/`
- `data/processed/`

Dengan demikian:

- dataset mentah tidak masuk Git;
- dataset hasil cleaning tidak masuk Git;
- repository tetap ringan;
- pengguna dapat memperoleh dataset melalui petunjuk pada `data/README.md`.

File `.dockerignore` juga digunakan agar dataset besar tidak ikut masuk ke Docker build context.

---

# 37. Version Control

Pengembangan project dilakukan secara bertahap menggunakan Git.

Commit utama yang telah dibuat antara lain:

- `feat: add initial dataset profiling`
- `merge: integrate assignment template with initial profiling`
- `feat: add data cleaning pipeline`
- `feat: add EDA and insights`

Penggunaan commit bertahap bertujuan untuk menunjukkan perkembangan project dari setiap milestone.

---

# 38. Milestone Checklist

## Milestone 1 - Data Profiling

- [x] Dataset lebih dari 1 juta baris
- [x] Dataset lebih dari 500 MB
- [x] Dataset README
- [x] Data profiling
- [x] Profiling menggunakan Polars
- [x] Profiling menggunakan DuckDB
- [x] Analisis struktur dataset
- [x] Analisis missing values
- [x] Analisis statistik deskriptif

## Milestone 2 - Data Cleaning

- [x] Missing value analysis
- [x] Duplicate analysis
- [x] Data type validation
- [x] Numeric conversion
- [x] Negative value analysis
- [x] Zero value analysis
- [x] Outlier analysis
- [x] UNKNOWN value analysis
- [x] Data cleaning menggunakan Polars
- [x] Validasi menggunakan DuckDB
- [x] Export Parquet
- [x] Validasi jumlah baris
- [x] Validasi jumlah kolom

## Milestone 3 - Exploratory Data Analysis

- [x] Analisis temporal
- [x] Analisis spasial
- [x] Analisis jenis produk
- [x] Analisis volume
- [x] Analisis FOB
- [x] Analisis deforestation exposure
- [x] Analisis emission exposure
- [x] Minimal 6 visualisasi interaktif
- [x] Minimal 5 insights

## Final

- [x] Dockerfile
- [x] requirements.txt
- [x] .gitignore
- [x] .dockerignore
- [x] README.md
- [x] GitHub repository
- [x] AI Disclosure Statement
- [x] Dokumentasi reproducibility

---

# 39. AI Disclosure Statement

Dalam pengerjaan tugas ini digunakan bantuan AI sebagai alat pendukung pembelajaran dan debugging.

> **Alat AI yang digunakan:** ChatGPT.
>
> **Bagian yang dibantu:** Penjelasan konsep Big Data, bantuan debugging kode Python, Polars, DuckDB, Plotly, Jupyter, Git, GitHub, dan Docker, penyusunan langkah analisis, serta dokumentasi project.
>
> **Verifikasi yang dilakukan:** Kode dijalankan dan diuji secara langsung pada environment lokal dan Docker. Hasil profiling, cleaning, validasi, visualisasi, dan insight diperiksa berdasarkan output notebook dan dataset yang digunakan.

AI digunakan sebagai alat bantu dan bukan sebagai pengganti proses verifikasi terhadap hasil analisis.

---

# 40. Kesimpulan Project

Project ini berhasil melakukan pengolahan dataset berukuran besar dengan karakteristik:

- **1.694.907 baris**
- **34 kolom**
- **±721,83 MB**
- periode data **2013–2022**

Tahapan analisis yang dilakukan meliputi:

**Profiling → Data Quality Analysis → Data Cleaning → Data Validation → Parquet Conversion → Exploratory Data Analysis → Interactive Visualization → Insights**

Penggunaan Polars dan DuckDB memungkinkan proses pengolahan dan analisis dataset dilakukan dengan pendekatan yang sesuai untuk data berukuran besar.

Hasil EDA menunjukkan adanya pola temporal dan spasial pada data produksi kelapa sawit Indonesia, termasuk perbedaan volume antarprovinsi, perbedaan volume antarjenis produk, hubungan volume dengan FOB, serta distribusi deforestation exposure dan emission exposure.

---

# 41. Repository GitHub

Repository project tersedia pada:

**https://github.com/Elviradwi110/tugas1-abd-2026**

---

# 42. Author

**Elvira Dwi Irianty Woretma**

Program Studi Teknik Informatika  
Universitas Muhammadiyah Malang

---

## End of Documentation