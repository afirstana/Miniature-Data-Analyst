# The Ledger: Studi Kasus Analisis Fraud

Repositori ini mendokumentasikan investigasi saya terhadap dataset fraud kartu kredit Eropa. Tujuannya bukan sekadar menulis kode, melainkan mendemonstrasikan cara saya memproses data mentah, merumuskan hipotesis, dan menghasilkan nilai bisnis.

## Struktur Investigasi

- **notebooks/01_EDA_dan_Modeling.ipynb**
  Ruang kerja utama yang berisi kode Python, transformasi data, dan pemodelan statistik.

- **Step_1_Time_Analysis/**
  Fase pertama investigasi. Alih-alih langsung menggunakan algoritma kompleks, saya mulai dengan mempertanyakan sifat temporal (waktu) dari kejahatan ini. 
  - `Analyst_Methodology_Step1_EN.md` / `_ID.md`: Pola pikir saya tentang pentingnya waktu dan penanganan data yang tidak seimbang.
  - `Interactive_Report_Step1.html`: Bukti visual interaktif.
  - `Advanced_Dashboard_Step1.xlsx`: Ringkasan eksekutif untuk pemangku kepentingan bisnis.

## Mengapa ini penting
Deteksi fraud di dunia nyata selalu dihantui oleh ketidakseimbangan data yang ekstrem. Portofolio ini membuktikan kemampuan saya dalam melakukan *feature engineering* dan menerjemahkan anomali menjadi kebijakan keamanan yang dapat ditindaklanjuti (seperti *Night-Watch Protocol*).

- **Step_2_Amount_Analysis/**
  Fase kedua mengungkap 'Anomali Zona Menengah'. Penipu sengaja membatasi nilai curian di level menengah ($100-$2000) untuk menghindari alarm otomatis bank. Berisi Boxplot interaktif dan SVG metodologi.
