# Dataset Indonesia Palm Oil

## Informasi Dataset

- Nama dataset: Indonesia Palm Oil Supply Chain Dataset
- File: `indonesia_palm_oil_v1_2_5.csv`
- Format: CSV
- Jumlah baris: 1,694,907
- Jumlah kolom: 34
- Ukuran file: 721.83 MB
- Periode data: 2013–2022
- Negara produksi: Indonesia

## Sumber

Dataset bersumber dari Trase Earth dan berisi informasi
mengenai rantai pasok kelapa sawit Indonesia.

## Variabel Utama

Beberapa variabel yang digunakan dalam analisis:

- `year` — tahun data
- `product_type` — jenis produk
- `province_of_production` — provinsi produksi
- `kabupaten_of_production` — kabupaten produksi
- `mill` — pabrik kelapa sawit
- `refinery` — refinery
- `exporter` — eksportir
- `importer` — importir
- `country_of_first_import` — negara tujuan impor pertama
- `volume` — volume
- `oil_palm_ha` — luas kelapa sawit
- `fob` — nilai FOB
- variabel paparan deforestasi dan emisi

## Karakteristik Data

Dataset memiliki lebih dari 1 juta baris sehingga memenuhi
persyaratan skala dataset untuk Tugas 1 Analisis Big Data.

Hasil profiling awal menunjukkan terdapat missing values
pada beberapa variabel lingkungan dan terdapat beberapa
kolom yang perlu diperiksa tipe datanya pada tahap cleaning.

## Penyimpanan Dataset

Dataset berukuran besar tidak disimpan dalam repository GitHub.

File dataset ditempatkan secara lokal pada:

```text
data/raw/indonesia_palm_oil_v1_2_5.csv