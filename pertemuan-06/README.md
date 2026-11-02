P6 - PHP Dasar dan Pemrograman Sisi Peladen

Deskripsi

Pertemuan 6 (P6) merupakan lanjutan dari pertemuan sebelumnya, yaitu P5. Pada pertemuan ini, halaman web yang sebelumnya menggunakan HTML diubah menjadi PHP agar dapat menjalankan pemrograman sisi peladen (server-side programming).

Materi yang dipelajari meliputi variabel, konstanta, tipe data, operator, percabangan, perulangan, fungsi bawaan PHP, serta penggunaan formulir dengan metode GET.

Fitur dan Pengembangan

- Pengembangan dari P5: Melanjutkan struktur website sebelumnya dengan menggunakan file "index.php", "style.css", "script.js", dan folder "img".
- Tag PHP Dasar: Menggunakan tag PHP, komentar, serta perintah "echo" dan "print" untuk menampilkan informasi.
- Variabel dan Konstanta: Membuat variabel untuk menyimpan NIM, nama mahasiswa, program studi, tahun akademik, semester, IPK, status aktif, dan catatan tambahan.
- Tipe Data: Menggunakan tipe data string, integer, float, boolean, dan null.
- Operator PHP: Menerapkan operator aritmetika, perbandingan, logika, penggabungan string, serta operator ternary.
- Percabangan: Menggunakan "if", "elseif", "else", dan "switch" untuk menentukan keterangan semester dan program studi.
- Perulangan: Menggunakan "for" untuk menampilkan target belajar dan "while" untuk menampilkan nomor semester.
- Fungsi Bawaan PHP: Menggunakan "number_format()" untuk memformat IPK, memeriksa nilai null, serta "date("Y")" untuk menampilkan tahun secara dinamis.
- Formulir GET: Membuat formulir dengan "action="index.php"" dan "method="get"" untuk pengiriman data.
- Tampilan Website: Mempertahankan tampilan halaman Home, About, dan Contact.

Cara Menjalankan

1. Jalankan Laragon dan aktifkan Apache.

2. Pastikan folder proyek berada di direktori web server yang sesuai.

3. Buka browser.

4. Masukkan alamat berikut:
   
   "http://localhost:8080/PWD/2627o/ti1a/2611500019-PWD-TI1A-2627O/pertemuan-06/index.php"

5. Tekan Enter untuk menjalankan halaman PHP.

Catatan: File PHP harus dijalankan melalui server lokal seperti Laragon atau Apache, bukan dengan membuka file "index.php" secara langsung menggunakan "file://".

Pengujian

Berdasarkan kode PHP yang dibuat, hasil pengujian yang diharapkan adalah sebagai berikut:

- NIM ditampilkan sesuai variabel "$nim".
- Nama mahasiswa ditampilkan sebagai Julian Hernandez.
- Program studi ditampilkan sebagai Teknik Informatika (TI).
- Tahun akademik ditampilkan sebagai 2026/2027.
- Semester saat ini adalah 1.
- Batas semester adalah 8 dan sisa semester adalah 7.
- Status semester ditampilkan sebagai "Sesuai rentang".
- Keterangan semester ditampilkan sebagai "Semester awal".
- Fokus program studi ditampilkan sebagai "Komputasi dan pengembangan perangkat lunak".
- IPK ditampilkan dengan format dua angka desimal, yaitu 3,75.
- Status aktif ditampilkan sesuai nilai boolean "true".
- Catatan tambahan ditampilkan sebagai "Belum ada" karena nilainya "null".
- Perulangan "for" menampilkan target belajar semester 1 sampai 5.
- Perulangan "while" menampilkan nomor semester 1 sampai 3.
- Tahun pada footer mengikuti tahun saat halaman dijalankan.
- Formulir menggunakan metode GET dengan tujuan pengiriman ke "index.php".

Catatan

- Pastikan Apache berjalan sebelum membuka halaman PHP.
- Periksa kembali struktur HTML agar setiap tag pembuka dan penutup sesuai.
- Pastikan formulir dapat mengirim data sesuai fungsi yang diharapkan.
- Jika formulir tidak mengirim data, periksa kembali kode pada "script.js", terutama jika terdapat "event.preventDefault()".

Riwayat Pengembangan

- Menyesuaikan action formulir ke index.php ("cf08acb")

Repository

GitHub: https://github.com/2611500019-JulianHernandez/2611500019-PWD-TI1A-2627O