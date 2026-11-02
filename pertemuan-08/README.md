# Profil Mahasiswa

Tugas Pertemuan 08 mata kuliah **Pemrograman Web Dasar** (tahun akademik 2026/2027).

| | |
|---|---|
| Nama | Julian Hernandez |
| NIM | 2611500019 |
| Program Studi | Teknik Informatika (TI) |
| Kelas | TI1A |
| GitHub | [2611500019-JulianHernandez](https://github.com/2611500019-JulianHernandez) |

## Deskripsi

Halaman profil mahasiswa satu halaman (single page) yang dibangun dengan HTML, CSS, JavaScript, dan PHP. Pada pertemuan ini ditambahkan menu dan section baru **Rencana Kegiatan Mahasiswa** yang berisi formulir untuk mencatat rencana kegiatan.

## Fitur

- **Navigasi** dengan menu Beranda, Tentang, Rencana Kegiatan, dan Kontak. Menu bisa dibuka-tutup pada layar kecil.
- **Beranda** berisi sapaan dan foto profil.
- **Tentang** menampilkan profil singkat, target belajar (perulangan `for`), dan daftar semester (perulangan `while`). Datanya diolah dengan variabel, konstanta, operator, `if-elseif-else`, dan `switch-case`.
- **Rencana Kegiatan Mahasiswa** (baru) berupa formulir dengan lima isian:
  - Nama Kegiatan
  - Kategori Kegiatan (Akademik, Organisasi, Lomba, Pengabdian)
  - Tanggal Pelaksanaan
  - Lokasi Kegiatan
  - Deskripsi Kegiatan

  Data dikirim lewat metode POST, disimpan ke `$_SESSION["rencana"]`, lalu ditampilkan kembali di bawah formulir. Tombol **Kirim** mengirim data dan **Batal** mengosongkan isian.
- **Kontak** berupa formulir dengan validasi JavaScript dan hasil kiriman yang disimpan di session.

## Perubahan pada Pertemuan Ini

1. Menambahkan item menu **Rencana Kegiatan** yang mengarah ke `#rencana-kegiatan`.
2. Menambahkan `section#rencana-kegiatan` sebelum `section#contact`.
3. Membuat formulir rencana kegiatan dengan `label`, `id`, `name`, `required`, serta tombol Kirim dan Batal, dengan tampilan mengikuti pola `section#contact`.
4. Menambahkan pemrosesan PHP di bagian atas `index.php`: data formulir disimpan ke session, lalu halaman dialihkan kembali ke `#rencana-kegiatan` (pola Post/Redirect/Get) agar data tidak terkirim ulang saat halaman dimuat ulang.
5. Menampilkan data yang tersimpan dengan `htmlspecialchars()` untuk mencegah XSS.

## Riwayat Commit

Kode commit untuk tugas ini:

- `eaab5f8`
- `a9184d7`
- `742d215`

## Struktur Folder

```
pertemuan-08/
├── index.php      # halaman utama dan pemrosesan formulir
├── style.css      # gaya tampilan
├── script.js      # navigasi dan validasi formulir kontak
└── img/
    └── foto-profil.jpg
```

## Cara Menjalankan

1. Pasang [Laragon](https://laragon.org/) (atau XAMPP) dan jalankan Apache.
2. Letakkan folder proyek di `C:\laragon\www\`.
3. Buka `http://localhost/<path-ke-folder>/pertemuan-08/index.php` di browser.

PHP 7.4 atau lebih baru dibutuhkan (kode memakai operator `??` dan sintaks `<?= ?>`).

## Teknologi

- HTML5
- CSS3
- JavaScript
- PHP (session, pemrosesan formulir)
- Git dan GitHub
