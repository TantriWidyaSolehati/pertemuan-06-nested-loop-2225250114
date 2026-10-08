# Pertemuan 06 Nested Loop Python
- Nama: Tantri Widya Solehati
- NIM: 2225250114
- Kelas: 3F
## Tujuan
Menggunakan nested loop, pola, akumulasi, dan pencacahan.
## Cara Menjalankan
python3 tugas/tabel_perkalian_dan_statistik.py
## Algoritma Tugas 3
1. Loop luar (for i in range(1, n+1))
    - Peran: Mengatur baris tabel perkalian.
    - Setiap nilai i mewakili baris ke‑i dalam tabel.
    - Jadi loop luar memastikan tabel berjalan dari baris 1 sampai baris n.
2. Loop dalam (for j in range(1, n+1))
    - Peran: Mengatur kolom tabel perkalian.
    - Untuk setiap baris i, loop dalam menghitung hasil perkalian i * j untuk semua j dari 1 sampai n.
    - Jadi loop dalam menghasilkan isi tabel pada baris tersebut.
3. Akumulator (total_baris, total_semua)
    - Peran: Menyimpan hasil penjumlahan sementara.
    - total_baris: menjumlahkan semua hasil perkalian dalam satu baris (reset setiap kali pindah baris).
    - total_semua: menjumlahkan semua hasil perkalian di seluruh tabel (global, tidak direset).
    - Akumulator dipakai untuk menghitung total nilai, bukan jumlah banyaknya data.
4. Counter (count_genap)
    - Peran: Menghitung berapa banyak hasil perkalian yang genap.
    - Setiap kali ditemukan hasil % 2 == 0, counter bertambah 1.
    - Counter dipakai untuk menghitung frekuensi/kuantitas, bukan nilai total.
## Hasil Pengujian
| n |                hasil yang diharapkan               |                  keluaran aktual                   | status |
|   |----------------------------------------------------|----------------------------------------------------|        |
|   | jumlah pasangan | total semua | banyak hasil genap | jumlah pasangan | total semua | banyak hasil genap |        |
|---|-----------------|-------------|--------------------|-----------------|-------------|--------------------|--------|
| 1 | 1               | 1           | 0                  | 1               | 1           | 0                  | sesuai |
| 2 | 4               | 9           | 3                  | 4               | 9           | 3                  | sesuai |
| 3 | 9               | 36          | 5                  | 9               | 36          | 5                  | sesuai |
## Analisis Efisiensi
- Loop luar (for i) berjalan sebanyak n kali.
- Loop dalam (for j) juga berjalan sebanyak n kali untuk setiap iterasi loop luar.
Total eksekusi badan loop dalam
Karena loop dalam berjalan n kali untuk setiap iterasi loop luar, maka total eksekusi badan loop dalam adalah:
𝑛 × 𝑛 = 𝑛^2
## Refleksi
1. Kesalahan:
salah menempatkan inisialisasi variabel akumulator atau counter.
total_baris = 0
for i in range(1, n+1):
    for j in range(1, n+1):
        hasil = i * j
        total_baris += hasil
    print(f"Jumlah baris {i} = {total_baris}")

2.  Cara memperbaiki :
Inisialisasi total_baris harus dilakukan di dalam loop luar, sebelum loop dalam dimulai:
for i in range(1, n+1):
    total_baris = 0   # reset setiap baris
    for j in range(1, n+1):
        hasil = i * j
        total_baris += hasil
    print(f"Jumlah baris {i} = {total_baris}")
