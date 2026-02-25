# Sistem Peminjaman Buku (Contoh UI)

## Ringkasan

Halaman HTML sederhana untuk mendemonstrasikan fitur inventaris dan peminjaman buku.  
Ditulis sebagai contoh praktikum kepatuhan **SKKNI No. 282 Tahun 2016** — Skema **Pemrogram Junior (Junior Coder)**.  
Tidak memerlukan server — cukup buka file HTML di peramban.

---

## Fitur

- Tambah koleksi buku baru (judul + penulis).
- Daftar buku dengan status: **Tersedia** / **Dipinjam**.
- Tombol **Pinjam** dan **Kembali** untuk mengubah status buku.
- Panel **Spesifikasi Program** (collapsible) — memenuhi J.620100.009.01.
- **Log aktivitas** sederhana dengan tampilan konsol di halaman.
- **Debug view** untuk memantau struktur data JSON secara real-time.
- Tombol **"Uji Sistem"** menjalankan pengujian unit otomatis (3 skenario).

---

## Struktur File

```
README.md       — dokumentasi ini
index.html      — UI, style CSS, dan skrip JavaScript tersemat
```

---

## Model Data

`inventarisBuku` — Array of Objects:

| Field      | Tipe    | Keterangan                  |
|------------|---------|-----------------------------|
| `id`       | number  | Identifikasi unik buku      |
| `judul`    | string  | Judul buku                  |
| `penulis`  | string  | Nama penulis                |
| `dipinjam` | boolean | Status peminjaman buku      |

---

## Fungsi Utama

| Fungsi                      | Deskripsi                                                        |
|-----------------------------|------------------------------------------------------------------|
| `tambahBukuBaru()`          | Validasi input → tambahkan buku → refresh UI → catat log        |
| `tampilkanBuku()`           | Render daftar buku ke DOM berdasarkan `inventarisBuku`           |
| `pinjamBuku(id)`            | Set `dipinjam = true`, catat log, refresh UI                     |
| `kembalikanBuku(id)`        | Set `dipinjam = false`, catat log, refresh UI                    |
| `tambahLog(pesan, tipe)`    | Tambahkan entri ke panel log dengan timestamp                    |
| `updateDebugView()`         | Tampilkan JSON state ke panel debug (J.620100.025.02)            |
| `jalankanUjiUnit()`         | Jalankan 3 pengujian unit otomatis dan tulis hasil ke log        |

---

## Cara Menjalankan

1. Simpan file HTML ke disk (`index.html`).
2. Buka file di browser (double-click atau drag ke browser).
3. Gunakan form **"Tambah Koleksi Buku"** untuk menambah data.
4. Klik **"Uji Sistem"** untuk menjalankan pengujian unit.
5. Klik **"Toggle Debug"** untuk memantau struktur data JSON secara langsung.

---

## Penyesuaian Cepat

- **Mengganti data awal:** edit variabel `inventarisBuku` di dalam `<script>`.
- **Persistensi data:** integrasikan LocalStorage atau API backend.
- **Menambahkan kolom baru:** tambah elemen input dan perluas objek buku.

---

## Catatan Pengembangan

- Kode ditulis untuk **kejelasan pembelajaran**, bukan produksi.
- Untuk produksi: pisahkan CSS/JS ke file terpisah, tambahkan build step, dan sanitasi input untuk mencegah XSS.

---

## Unit Kompetensi SKKNI

**Skema:** Pemrogram Junior (Junior Coder) — **SKKNI No. 282 Tahun 2016**  
**Judul Proyek:** Pengembangan Aplikasi Peminjaman Buku  
**Bobot:** 10

| Kode Unit           | Judul Unit Kompetensi                                                              | Bukti Implementasi                                                                              |
|---------------------|------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| J.620100.004.02     | Menggunakan Struktur Data                                                          | Array `inventarisBuku` dengan operasi `push`, `find`, dan mutasi properti objek                 |
| J.620100.009.01     | Menggunakan Spesifikasi Program                                                    | Panel spesifikasi (collapsible) memuat nama sistem, bahasa, platform, I/O, batasan, dan skema   |
| J.620100.010.01     | Menerapkan Perintah Eksekusi Bahasa Pemrograman Berbasis Teks, Grafik, dan Multimedia | Form tambah buku, daftar inventaris, tombol aksi (Pinjam/Kembali), dan log aktivitas berbasis DOM |
| J.620100.016.01     | Menulis Kode Dengan Prinsip Sesuai Guidelines dan Best Practices                   | Validasi input di `tambahBukuBaru()` mencegah data kosong; komentar dokumentasi JSDoc            |
| J.620100.017.02     | Mengimplementasikan Pemrograman Terstruktur                                        | Fungsi `refreshUI()` dan `tampilkanBuku()` merender DOM secara terstruktur berdasarkan data      |
| J.620100.023.02     | Membuat Dokumen Kode Program                                                       | Panel log `tambahLog()` mencatat semua aktivitas; komentar blok JSDoc pada setiap fungsi utama  |
| J.620100.025.02     | Melakukan Debugging                                                                | Debug view `updateDebugView()` menampilkan JSON state; Toggle Debug untuk analisis real-time     |
| J.620100.033.02     | Melaksanakan Pengujian Unit Program                                                | Fungsi `jalankanUjiUnit()` menjalankan 3 skenario uji dan mencatat hasil BERHASIL/GAGAL ke log  |

---

## Lisensi

Bebas digunakan untuk pembelajaran dan pengembangan. Cantumkan kredit bila digunakan kembali.