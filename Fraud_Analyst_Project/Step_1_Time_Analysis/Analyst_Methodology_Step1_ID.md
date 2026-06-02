# Metodologi Analis: Step 1 (Analisis Waktu)

Sebagai seorang Data Analyst, kode pemrograman hanyalah alat. Nilai sesungguhnya terletak pada **cara kita berpikir** dan mengambil keputusan saat menghadapi data mentah. Dokumen ini mendokumentasikan jalan pikiran (*thought process*) langkah demi langkah di balik penulisan kode pada Step 1.

---


## 0. Alur Pemikiran Analis (Flowchart)
Berikut adalah cetak biru metodologi analitik yang saya gunakan.

![Flowchart](Methodology_Flowchart.svg)

## 1. Mengapa Memulai dari Waktu (Time)?
> *"Penjahat beroperasi di luar batas kewajaran."*

Saat menerima dataset berukuran 284.807 baris, insting pertama seorang pemula biasanya langsung mencari korelasi fitur-fitur kompleks. Namun, secara logis, kelemahan terbesar sistem perbankan adalah **ketidakhadiran campur tangan manusia (korban)**. 

Jika penipu mencuri di siang bolong, korban akan langsung menerima notifikasi SMS dan memblokir kartu. Karena itu, hipotesis pertama saya adalah: *Penipuan pasti memiliki pola waktu yang berbeda dari transaksi normal.*

---

## 2. Keputusan Transformasi Data (Feature Engineering)
Dataset memberikan kolom `Time` dalam format "detik yang berlalu". Data ini tidak bisa dibaca oleh bisnis. Direktur Bank tidak peduli dengan "detik ke-86.400", mereka peduli dengan "Jam berapa?". 

Oleh karena itu, saya merancang kode untuk mengekstrak **Jam**.

```python
# Transformasi Detik ke Format 24 Jam
import pandas as pd
df = pd.read_csv('creditcard.csv')

# Logika: 3600 detik = 1 jam. Modulo (%) 24 digunakan agar jam ke-25 kembali menjadi jam 1.
df['Hour'] = (df['Time'] / 3600).astype(int) % 24
```

---

## 3. Tantangan Visualisasi: Ketidakseimbangan Data (Imbalanced Data)
> *"Bagaimana cara membandingkan semut dan gajah di dalam satu kandang yang sama?"*

Tantangan terbesar dalam mendeteksi *Fraud* adalah *Imbalanced Data*. Transaksi normal ada **284.315**, sedangkan Fraud hanya **492** (0.17%). Jika menggunakan grafik biasa, garis Fraud tidak akan terlihat.

Oleh karena itu, saya mengambil keputusan teknis untuk **memisahkan Sumbu Y (Dual-Axis)**. Dengan begitu, fluktuasi pergerakan penipu sekecil apapun akan terlihat secara proporsional.

### Bukti Visual: Lonjakan Tengah Malam
![Time Analysis Chart](Time_Analysis_Chart.png)

---

## 4. Hasil Akhir & Rekomendasi Bisnis
Berdasarkan grafik, aktivitas transaksi normal menurun sangat tajam mulai pukul 00:00 hingga 06:00 pagi. Namun, aktivitas penipuan **tidak mengalami penurunan drastis** pada dini hari. 

**Rekomendasi (The Night-Watch Protocol):**
Tingkatkan sensitivitas sistem pada jam 01:00 - 06:00 pagi. Setiap transaksi bernominal besar di jam tersebut wajib memicu **Step-Up Authentication** (meminta verifikasi OTP) sebelum dana dicairkan.
