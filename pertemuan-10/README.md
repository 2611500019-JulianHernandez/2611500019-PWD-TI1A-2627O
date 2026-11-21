# Catatan Pertemuan 10: Basis Data MySQL dan phpMyAdmin

NIM 2611500019, Julian Hernandez, TI

Pada pertemuan ini formulir kontak dari P9 dihubungkan dengan basis data MySQL. Pekerjaan dilakukan di phpMyAdmin (Laragon), lalu hasilnya diekspor dan dicatat di repositori.

## 1. Persiapan dan Analisis Data

Artefak P9 saya salin sebagai dasar P10, lalu saya pastikan tampilannya masih sama. Setelah itu saya cek formulir kontak di `index.php` lewat atribut `name`, dan ada 8 data yang dikirim: nama, email, semester, tanggal, jenis_pesan, minat, prodi, dan pesan.

Yang disimpan ke basis data hanya 8 data tersebut. NIM, nama mahasiswa, dan program studi di bagian profil tidak disimpan karena itu bukan isian formulir.

Checkbox minat memakai `name="minat[]"`, jadi PHP menerimanya sebagai larik (misalnya `["HTML", "CSS"]`). Karena tabelnya hanya satu, pilihan minat saya simpan sebagai satu teks yang dipisah koma, misalnya `HTML, CSS`.

## 2. Rancangan Tabel

- Basis data: `db_pwd_2611500019`
- Tabel: `tbl_kontak_2611500019`

| Atribut | Tipe data | Keterangan |
|---|---|---|
| id | INT | PRIMARY KEY, AUTO_INCREMENT |
| nama | VARCHAR(50) | sesuai maxlength formulir |
| email | VARCHAR(255) | |
| semester | TINYINT | |
| tanggal | DATE | |
| jenis_pesan | VARCHAR(20) | pertanyaan atau saran |
| minat | VARCHAR(50) | HTML, CSS, atau keduanya |
| prodi | VARCHAR(2) | SI atau TI |
| pesan | VARCHAR(300) | sesuai maxlength formulir |

Kolom `id` saya tambahkan sebagai identitas unik tiap baris, sehingga tabel punya 9 atribut.

## 3. Membuat Basis Data dan Tabel (DDL)

Lewat tab SQL saya menjalankan `CREATE DATABASE`, `USE`, dan `CREATE TABLE`:

```sql
CREATE DATABASE db_pwd_2611500019;
USE db_pwd_2611500019;
CREATE TABLE tbl_kontak_2611500019 (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nama VARCHAR(50),
    email VARCHAR(255),
    semester TINYINT,
    tanggal DATE,
    jenis_pesan VARCHAR(20),
    minat VARCHAR(50),
    prodi VARCHAR(2),
    pesan VARCHAR(300)
);
```

Kendala yang saya alami: saat kode itu terkirim lagi, muncul error #1007 (database exists) karena basis datanya sudah ada. Saya lalu menghapusnya dengan `DROP DATABASE db_pwd_2611500019;` dan membuatnya ulang dengan kode di atas sampai muncul pesan sukses.

## 4. Memeriksa Struktur

Struktur saya cek lewat tab Structure dan perintah `DESCRIBE tbl_kontak_2611500019;`. Hasilnya 9 atribut dengan tipe yang sesuai rancangan, dan kolom `id` berstatus PRI dengan auto_increment. Tidak ada yang perlu diperbaiki.

## 5. Memasukkan Data (DML)

Data pertama saya masukkan lewat fasilitas Insert dengan kolom `id` dikosongkan:

- Julian Hernandez, 2611500019@mahasiswa.atmaluhur.ac.id, semester 1, 2026-11-21, saran, HTML, CSS, TI, "Tolong tambahkan materi database". Hasilnya id = 1.

Data kedua saya masukkan dengan perintah SQL. Kolom `id` tidak ditulis karena sudah diisi otomatis:

```sql
INSERT INTO tbl_kontak_2611500019
    (nama, email, semester, tanggal, jenis_pesan, minat, prodi, pesan)
VALUES
    ('Julian Hernandez', '2611500019@mahasiswa.atmaluhur.ac.id', 1, '2026-11-21',
     'pertanyaan', 'HTML, CSS', 'TI', 'Saya ingin belajar pemrograman web.');
```

Hasilnya id = 2.

## 6. Memeriksa Data

Di tab Browse tampil 2 baris (id 1 dan 2) dengan nilai yang sama seperti yang saya isi, dan kolom minat tampil sebagai teks. Semua nilai sudah sesuai aturan formulir P9, jadi tidak ada data yang diperbaiki.

## 7. Ekspor Basis Data

Di tab Export saya memilih metode Quick dengan format SQL, lalu menyimpan hasilnya sebagai `db_pwd_2611500019.sql` dan memindahkannya ke folder `pertemuan-10`.

Isi berkas saya buka di VS Code. Di dalamnya ada `CREATE TABLE tbl_kontak_2611500019` dengan 9 atribut, 2 baris `INSERT INTO` yang cocok dengan tab Browse, `AUTO_INCREMENT` pada `id`, dan index hanya `PRIMARY KEY (id)`.

## 8. Perubahan pada index.php

Kode `index.php` saya sesuaikan dengan kode akhir di modul:

- `include` diganti `require_once("fungsi.php")`.
- Larik `$teknologiWeb` ditambahkan dan ditampilkan dengan `foreach`.
- Semua output diamankan dengan `bersihkan()`, dan nama di beranda memakai `tebal()`.
- Hasil formulir ditampilkan lewat larik asosiatif `$labelMap`.
- Topik minat tampil sebagai daftar, atau "Belum ada topik yang dipilih." jika kosong.
- Bagian "Rencana Kegiatan" dihapus karena tidak ada di kode akhir modul.
- Data profil memakai data saya sendiri.

## Cara Menjalankan

1. Jalankan Laragon (Start All), pastikan Apache dan MySQL aktif.
2. Buka phpMyAdmin dan login sebagai `root` tanpa password.
3. Jika `db_pwd_2611500019` belum ada, buat basis data itu, pilih, buka tab Import, pilih `pertemuan-10/db_pwd_2611500019.sql`, lalu Import.
4. Buka halaman `pertemuan-10` lewat localhost (sesuaikan dengan lokasi folder di Laragon).

## Hasil Pengujian

| No. | Yang diperiksa | Hasil |
|---|---|---|
| 1 | Struktur tabel | 9 atribut sesuai rancangan, index hanya PRIMARY pada id |
| 2 | Data awal | 2 baris (id 1 dan 2) tersimpan dan sesuai ketentuan |
| 3 | Berkas `db_pwd_2611500019.sql` | memuat CREATE TABLE dan INSERT INTO |
| 4 | Halaman pertemuan-10 di localhost | 
| 5 | Validasi JavaScript formulir | 
| 6 | Kirim formulir ke PHP | 