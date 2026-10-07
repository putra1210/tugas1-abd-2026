# Data Tugas 1

## Dataset yang Dipilih

| Item | Isi |
|---|---|
| Nama dataset | Indonesian Religious Corpus |
| Sumber | Hugging Face — dansachs/indonesian-religious-corpus |
| Lisensi/ketentuan pakai | MIT License untuk academic research purposes |
| Nama file | data.csv |
| Format | CSV |
| Ukuran file | 715.894.082 bytes (~715,89 MB / ~682,73 MiB) |
| Jumlah baris | 3.013.172 |
| Jumlah kolom | 7 |
| Periode data | Tidak tersedia secara langsung; kolom Date pada dataset hasil profiling memiliki 100% nilai NULL |
| Unit analisis | Satu baris merepresentasikan satu unit kalimat pada kolom Sentence_Unit |

## Deskripsi Dataset

Indonesian Religious Corpus merupakan dataset korpus teks Bahasa Indonesia yang berisi teks dari berbagai website keagamaan. Dataset dirancang untuk analisis teks dan klasifikasi religiolect, dengan tiga label utama yaitu Islam, Catholic, dan Protestant.

Dataset berisi sekitar 3 juta unit kalimat yang dikumpulkan dari berbagai website keagamaan yang tersedia secara publik.

Dalam dataset yang digunakan pada tugas ini, terdapat 7 kolom:

- `Label`
- `Denomination`
- `Location`
- `Date`
- `Title`
- `Sentence_Unit`
- `Link`

Kolom `Sentence_Unit` berisi teks kalimat yang menjadi unit utama analisis.

## Statistik Dataset

Berdasarkan hasil profiling menggunakan Polars dan DuckDB:

- Total baris: 3.013.172
- Total kolom: 7
- Label: 3 kategori
- Denomination: 60 kategori
- Location: 9 kategori
- Unique Sentence_Unit: 1.966.151
- Unique Link: 132.075
- Duplicate rows: 355
- Ukuran file: sekitar 715,89 MB atau 682,73 MiB

## Distribusi Label

Hasil profiling menunjukkan distribusi label sebagai berikut:

| Label | Jumlah | Persentase |
|---|---:|---:|
| Islam | 1.455.454 | 48,30% |
| Catholic | 797.131 | 26,45% |
| Protestant | 760.587 | 25,24% |

## Distribusi Location

| Location | Jumlah | Persentase |
|---|---:|---:|
| National | 2.492.876 | 82,73% |
| Java | 286.452 | 9,51% |
| Sumatra | 144.632 | 4,80% |
| Sulawesi | 30.024 | 1,00% |
| Nusa Tenggara | 23.684 | 0,79% |
| Papua | 19.199 | 0,64% |
| International | 9.369 | 0,31% |
| Maluku | 5.988 | 0,20% |
| Kalimantan | 948 | 0,03% |

## Missing Values

Berdasarkan profiling:

| Kolom | Jumlah NULL | Persentase |
|---|---:|---:|
| Label | 0 | 0% |
| Denomination | 0 | 0% |
| Location | 0 | 0% |
| Date | 3.013.172 | 100% |
| Title | 3.013.172 | 100% |
| Sentence_Unit | 0 | 0% |
| Link | 0 | 0% |

Kolom `Date` dan `Title` tidak dapat digunakan secara langsung untuk analisis karena seluruh nilainya NULL pada file yang digunakan.

## Cara Memperoleh Data

Dataset diperoleh dari Hugging Face:

`dansachs/indonesian-religious-corpus`

Unduh file dataset dari halaman dataset tersebut dan simpan sebagai:

`data/raw/data.csv`

Dataset mentah tidak disimpan di repository GitHub karena ukurannya lebih dari 500 MB dan aturan tugas melarang commit dataset besar.

## Struktur Penyimpanan

```text
data/
├── README.md
├── raw/
│   ├── .gitkeep
│   └── data.csv
└── processed/
    └── .gitkeep