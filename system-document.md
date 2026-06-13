# SYSTEM DOCUMENTATION

## Aplikasi Web Wisata Kuliner

### Versi Dokumen

1.0

### Tanggal

13 Juni 2026

### Status

Draft

### Penyusun

Tim Pengembang Wisata Kuliner

---

# 1. PENDAHULUAN

## 1.1 Latar Belakang

Wisata kuliner merupakan salah satu daya tarik utama bagi wisatawan. Namun informasi mengenai lokasi restoran, menu makanan, harga, jam operasional, dan ulasan pelanggan masih tersebar di berbagai platform.

Aplikasi Web Wisata Kuliner dibuat untuk menyediakan informasi kuliner dalam satu platform yang mudah digunakan oleh masyarakat maupun wisatawan.

---

## 1.2 Tujuan Sistem

Sistem ini bertujuan untuk:

* Menampilkan informasi restoran secara lengkap.
* Menampilkan lokasi restoran pada peta digital.
* Menampilkan menu dan harga makanan.
* Membantu wisatawan menemukan kuliner terdekat.
* Menjadi media promosi bagi pelaku usaha kuliner.
* Menyediakan ulasan dan rating dari pelanggan.

---

## 1.3 Ruang Lingkup

Sistem mencakup:

* Manajemen restoran
* Manajemen menu makanan
* Informasi lokasi restoran
* Pencarian kuliner
* Sistem review dan rating
* Dashboard administrator
* Sistem autentikasi pengguna

---

# 2. DESKRIPSI SISTEM

## 2.1 Nama Sistem

Wisata Kuliner Indonesia

## 2.2 Jenis Sistem

Web Application

## 2.3 Platform

* Desktop
* Tablet
* Smartphone

## 2.4 Pengguna Sistem

### Pengunjung

Dapat melihat informasi restoran tanpa login.

### Member

Dapat memberikan review dan menyimpan restoran favorit.

### Admin

Mengelola seluruh data sistem.

---

# 3. ARSITEKTUR SISTEM

## Frontend Layer

Fungsi:

* Menampilkan antarmuka pengguna
* Menampilkan peta lokasi
* Menampilkan daftar restoran
* Menampilkan menu makanan

Teknologi:

* HTML5
* CSS3
* JavaScript
* Bootstrap
* Tailwind CSS

---

## Backend Layer

Fungsi:

* Memproses data pengguna
* Menjalankan API
* Mengelola autentikasi
* Mengelola database

Teknologi:

* Node.js
* Express.js

atau

* PHP Laravel

---

## Database Layer

Fungsi:

* Menyimpan data restoran
* Menyimpan data menu
* Menyimpan data review
* Menyimpan data pengguna

Teknologi:

* MySQL
* PostgreSQL

---

# 4. FITUR SISTEM

## 4.1 Beranda

Menampilkan:

* Banner promosi
* Restoran populer
* Restoran terbaru
* Kategori kuliner

---

## 4.2 Daftar Restoran

Informasi:

* Nama restoran
* Foto restoran
* Rating
* Alamat
* Jam operasional

---

## 4.3 Detail Restoran

Informasi:

* Nama restoran
* Deskripsi
* Lokasi peta
* Menu makanan
* Harga makanan
* Foto galeri
* Review pelanggan

---

## 4.4 Peta Kuliner

Fitur:

* Marker lokasi restoran
* Informasi singkat restoran
* Petunjuk arah

---

## 4.5 Pencarian

Filter:

* Nama restoran
* Jenis makanan
* Harga
* Rating
* Lokasi

---

## 4.6 Review

Pengguna dapat:

* Memberikan rating
* Menulis ulasan
* Mengunggah foto makanan

---

## 4.7 Favorit

Pengguna dapat:

* Menyimpan restoran favorit
* Mengakses daftar favorit

---

## 4.8 Dashboard Admin

Fitur:

* Kelola restoran
* Kelola menu
* Kelola pengguna
* Kelola review
* Statistik kunjungan

---

# 5. STRUKTUR DATABASE

## Tabel Users

| Field      | Tipe      |
| ---------- | --------- |
| id         | bigint    |
| name       | varchar   |
| email      | varchar   |
| password   | varchar   |
| role       | enum      |
| created_at | timestamp |

---

## Tabel Restaurants

| Field       | Tipe    |
| ----------- | ------- |
| id          | bigint  |
| name        | varchar |
| description | text    |
| address     | text    |
| latitude    | decimal |
| longitude   | decimal |
| phone       | varchar |
| image       | varchar |
| rating      | decimal |

---

## Tabel Menus

| Field         | Tipe    |
| ------------- | ------- |
| id            | bigint  |
| restaurant_id | bigint  |
| menu_name     | varchar |
| description   | text    |
| price         | decimal |
| image         | varchar |

---

## Tabel Reviews

| Field         | Tipe    |
| ------------- | ------- |
| id            | bigint  |
| user_id       | bigint  |
| restaurant_id | bigint  |
| rating        | integer |
| comment       | text    |

---

# 6. ALUR SISTEM

## Alur Pengunjung

1. Membuka website
2. Melihat daftar restoran
3. Mencari restoran
4. Membuka detail restoran
5. Melihat menu dan harga
6. Melihat lokasi restoran

---

## Alur Member

1. Login
2. Mencari restoran
3. Menambahkan favorit
4. Memberikan review
5. Memberikan rating

---

## Alur Admin

1. Login admin
2. Mengelola restoran
3. Mengelola menu
4. Mengelola review
5. Melihat laporan

---

# 7. API DOKUMENTASI

## Authentication

POST /api/register

POST /api/login

POST /api/logout

---

## Restaurants

GET /api/restaurants

GET /api/restaurants/{id}

POST /api/restaurants

PUT /api/restaurants/{id}

DELETE /api/restaurants/{id}

---

## Menus

GET /api/menus

GET /api/menus/{id}

POST /api/menus

PUT /api/menus/{id}

DELETE /api/menus/{id}

---

## Reviews

GET /api/reviews

POST /api/reviews

DELETE /api/reviews/{id}

---

# 8. KEAMANAN SISTEM

Sistem menerapkan:

* JWT Authentication
* Password Hashing (bcrypt)
* HTTPS
* Input Validation
* SQL Injection Protection
* XSS Protection
* Rate Limiting
* Role Based Access Control (RBAC)

---

# 9. DEPLOYMENT

## Frontend

* Vercel
* Netlify

## Backend

* VPS Ubuntu
* Railway
* Render

## Database

* PostgreSQL
* MySQL

## File Storage

* Cloudinary
* AWS S3

---

# 10. MAINTENANCE

Pemeliharaan sistem meliputi:

* Backup database harian
* Monitoring server
* Update keamanan
* Optimasi performa
* Monitoring error log

---

# 11. ROADMAP PENGEMBANGAN

## Versi 1.0

* Daftar restoran
* Lokasi restoran
* Menu dan harga
* Review

## Versi 2.0

* Login pengguna
* Favorit restoran
* Dashboard admin

## Versi 3.0

* AI rekomendasi kuliner
* Booking meja
* Integrasi pembayaran digital

## Versi 4.0

* Aplikasi Android
* Aplikasi iOS
* Sistem franchise kuliner nasional

---

# 12. KESIMPULAN

Aplikasi Web Wisata Kuliner dirancang untuk menjadi pusat informasi kuliner yang lengkap, modern, dan mudah digunakan. Sistem ini membantu wisatawan menemukan kuliner terbaik sekaligus mendukung promosi UMKM kuliner melalui teknologi digital.
