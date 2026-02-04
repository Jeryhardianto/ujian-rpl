# Sistem Peminjaman Buku (Contoh UI)

Ringkasan
- Halaman HTML sederhana untuk mendemonstrasikan fitur inventaris dan peminjaman buku.
- Ditulis sebagai contoh praktikum kepatuhan SKKNI (Unit J.620100.xxxx).
- Tidak memerlukan server — buka file HTML di peramban.

Fitur
- Tambah koleksi buku baru (judul + penulis).
- Daftar buku dengan status: Tersedia / Dipinjam.
- Tombol Pinjam dan Kembali untuk mengubah status buku.
- Log aktivitas sederhana dengan tampilan konsol di halaman.
- Tombol "Uji Sistem" menjalankan dua pengujian unit dasar (penambahan dan pengembalian).

Struktur file
- README.md — dokumentasi ini.
- untitled:Untitled-2 (HTML) — berisi UI, style, dan skrip JavaScript tersemat.

Model data
- inventarisBuku: Array objek buku.
  - id: number (unik)
  - judul: string
  - penulis: string
  - dipinjam: boolean

Fungsi utama (di dalam HTML)
- tambahBukuBaru(): validasi input → tambahkan buku → refresh UI → catat log.
- tampilkanBuku(): render daftar buku ke DOM.
- pinjamBuku(id): set dipinjam = true, catat log, refresh.
- kembalikanBuku(id): set dipinjam = false, catat log, refresh.
- tambahLog(pesan, tipe): tambahkan entri ke panel log.
- jalankanUjiUnit(): menjalankan dua tes sederhana dan menulis hasil ke log.

Cara menjalankan
1. Simpan file HTML ke disk (mis. `index.html`).
2. Buka file tersebut di browser (double-click atau drag ke browser).
3. Gunakan form "Tambah Koleksi Buku" untuk menambah data.
4. Klik "Uji Sistem" untuk menjalankan pengujian unit contoh.

Penyesuaian cepat
- Mengganti data awal: edit variabel `inventarisBuku`.
- Menyimpan data persistensi: integrasikan LocalStorage atau API backend.
- Menambahkan validasi/kolom baru: tambah elemen input dan perluas objek buku.

Catatan pengembangan
- Kode ditulis untuk kejelasan pembelajaran, bukan produksi.
- Untuk produksi: pisahkan CSS/JS, tambahkan build step, dan sanitasi input.

## Unit Kompetensi (SKKNI)

Daftar unit kompetensi yang dicakup oleh contoh aplikasi dan bukti implementasi singkat:

- J.620100.004.02 - Struktur Data  
  Implementasi: array `inventarisBuku` dan operasi tambah/cari/ubah status pada skrip.

- J.620100.010.01 - GUI  
  Implementasi: form tambah buku, daftar buku, tombol aksi (Pinjam/Kembali) dan styling.

- J.620100.016.01 - Validasi  
  Implementasi: validasi input pada fungsi `tambahBukuBaru()` untuk mencegah input kosong.

- J.620100.017.02 - Render UI  
  Implementasi: fungsi `tampilkanBuku()` yang merender DOM berdasarkan data `inventarisBuku`.

- J.620100.023.02 - Logging  
  Implementasi: panel log dan fungsi `tambahLog()` untuk mencatat aktivitas sistem.

- J.620100.033.02 - Pengujian Unit  
  Implementasi: fungsi `jalankanUjiUnit()` melakukan dua uji sederhana (penambahan & pengembalian) dan menulis hasil ke panel log.

Lisensi
- Bebas digunakan untuk belajar dan pengembangan. Cantumkan kredit bila digunakan kembali.