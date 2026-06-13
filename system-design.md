# 🍜 Sistem Desain Aplikasi Web Wisata Kuliner

## 1. Gambaran Umum

Aplikasi Web Wisata Kuliner adalah platform yang membantu pengguna menemukan tempat makan berdasarkan lokasi, kategori makanan, harga, rating, dan menu yang tersedia.

Tujuan utama:
- Memudahkan wisatawan mencari kuliner.
- Menampilkan informasi lokasi restoran.
- Menyediakan daftar menu dan harga.
- Memberikan navigasi menuju lokasi restoran.
- Menjadi media promosi bagi pelaku UMKM kuliner.

---

# 2. Arsitektur Sistem

## Frontend
Teknologi:
- HTML5
- CSS3
- JavaScript
- Bootstrap / Tailwind CSS
- Leaflet Maps atau Google Maps API

Fitur:
- Responsive Design
- Search & Filter
- Detail Restoran
- Peta Lokasi
- Review Pengguna

---

## Backend

Teknologi:
- Node.js + Express.js
atau
- PHP Laravel

Fitur:
- REST API
- Authentication
- CRUD Restoran
- CRUD Menu
- CRUD Review
- Dashboard Admin

---

## Database

Teknologi:
- MySQL
atau
- PostgreSQL

---

# 3. User Roles

## Pengunjung

Hak akses:
- Melihat daftar restoran
- Melihat lokasi
- Melihat menu
- Melihat harga
- Mencari restoran

## Member

Hak akses:
- Semua fitur pengunjung
- Memberi review
- Menyimpan favorit

## Admin

Hak akses:
- Mengelola restoran
- Mengelola menu
- Mengelola pengguna
- Mengelola review

---

# 4. Fitur Utama

## Dashboard

Menampilkan:
- Jumlah restoran
- Jumlah menu
- Jumlah pengguna
- Restoran populer

---

## Daftar Kuliner

Informasi:
- Nama resto
- Foto
- Rating
- Alamat
- Jam buka

---

## Detail Restoran

Informasi:
- Nama restoran
- Deskripsi
- Galeri foto
- Lokasi Maps
- Menu
- Harga
- Rating

---

## Pencarian

Filter:
- Nama restoran
- Kategori makanan
- Harga
- Lokasi
- Rating

---

## Peta Kuliner

Menampilkan:
- Marker lokasi restoran
- Detail singkat restoran
- Tombol petunjuk arah

---

## Review

Pengguna dapat:
- Memberi bintang
- Menulis ulasan
- Upload foto makanan

---

# 5. Struktur Database

## Table Users

| Field | Type |
|---------|---------|
| id | bigint |
| name | varchar |
| email | varchar |
| password | varchar |
| role | enum |
| created_at | timestamp |

---

## Table Restaurants

| Field | Type |
|---------|---------|
| id | bigint |
| name | varchar |
| description | text |
| address | text |
| latitude | decimal |
| longitude | decimal |
| phone | varchar |
| open_hours | varchar |
| image | varchar |
| rating | decimal |

---

## Table Categories

| Field | Type |
|---------|---------|
| id | bigint |
| name | varchar |

---

## Table Menus

| Field | Type |
|---------|---------|
| id | bigint |
| restaurant_id | bigint |
| category_id | bigint |
| menu_name | varchar |
| price | decimal |
| image | varchar |
| description | text |

---

## Table Reviews

| Field | Type |
|---------|---------|
| id | bigint |
| user_id | bigint |
| restaurant_id | bigint |
| rating | integer |
| comment | text |
| created_at | timestamp |

---

## Table Favorites

| Field | Type |
|---------|---------|
| id | bigint |
| user_id | bigint |
| restaurant_id | bigint |

---

# 6. Relasi Database

Users
│
├── Reviews
│
└── Favorites

Restaurants
│
├── Menus
│
├── Reviews
│
└── Favorites

Categories
│
└── Menus

---

# 7. API Endpoint

## Authentication

POST /api/register

POST /api/login

POST /api/logout

---

## Restaurant

GET /api/restaurants

GET /api/restaurants/{id}

POST /api/restaurants

PUT /api/restaurants/{id}

DELETE /api/restaurants/{id}

---

## Menu

GET /api/menus

GET /api/menus/{id}

POST /api/menus

PUT /api/menus/{id}

DELETE /api/menus/{id}

---

## Review

GET /api/reviews

POST /api/reviews

DELETE /api/reviews/{id}

---

# 8. UI/UX Design

## Warna Utama

Primary:
#0F4C81

Secondary:
#FF6B35

Background:
#F8F9FA

Success:
#28A745

Warning:
#FFC107

---

## Font

Heading:
Poppins Bold

Body:
Inter Regular

---

# 9. Halaman Aplikasi

## Landing Page

Berisi:
- Hero Banner
- Search Kuliner
- Restoran Populer
- Kategori Kuliner

---

## Halaman Restoran

Berisi:
- Daftar restoran
- Filter
- Pagination

---

## Halaman Detail

Berisi:
- Foto restoran
- Lokasi maps
- Daftar menu
- Harga
- Review

---

## Dashboard Admin

Berisi:
- Statistik
- CRUD restoran
- CRUD menu
- CRUD review

---

# 10. Keamanan

- JWT Authentication
- Password Hashing (bcrypt)
- CSRF Protection
- Rate Limiting
- Input Validation
- XSS Protection
- SQL Injection Protection

---

# 11. Deployment

Frontend:
- Vercel
- Netlify

Backend:
- VPS Ubuntu
- Railway
- Render

Database:
- PostgreSQL
- MySQL

Storage:
- Cloudinary
- AWS S3

---

# 12. Roadmap

Versi 1.0
✅ Daftar restoran
✅ Lokasi maps
✅ Menu & harga
✅ Review

Versi 2.0
✅ Favorit
✅ Login pengguna
✅ Dashboard admin

Versi 3.0
✅ AI rekomendasi kuliner
✅ Booking meja
✅ Integrasi GoFood
✅ Integrasi GrabFood

Versi 4.0
✅ Mobile App Android
✅ Mobile App iOS
✅ Sistem franchise kuliner
