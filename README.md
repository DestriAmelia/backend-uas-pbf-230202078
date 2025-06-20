# 🏥 Backend API – Aplikasi Rumah Sakit (CodeIgniter 4)

Ini adalah proyek **backend RESTful API** untuk Aplikasi Rumah Sakit yang dibangun menggunakan **CodeIgniter 4**, dengan autentikasi **JWT** dan dukungan **CORS**. Backend ini menangani manajemen data **pasien** dan **obat**, serta autentikasi user untuk frontend Laravel.

---

## 📁 Struktur Folder Penting

- `app/Controllers/` – Menyimpan seluruh controller API seperti `PasiensController`, `ObatsController`, `Login`, `Register`.
- `app/Models/` – Menyimpan model database seperti `PasienModel`, `ObatModel`, `UserModel`.
- `app/Filters/Auth.php` – Filter untuk mengecek token JWT (Autentikasi).
- `app/Config/Routes.php` – Definisi endpoint REST API.

---

## ⚙️ Konfigurasi

1. **Database:**
   ```
   sql
   CREATE DATABASE db_rumahsakit_[NIM_ANDA];

   CREATE TABLE pasien (
     id INT AUTO_INCREMENT PRIMARY KEY,
     nama VARCHAR(100),
     alamat TEXT,
     tanggal_lahir DATE,
     jenis_kelamin ENUM('L', 'P')
   );

   CREATE TABLE obat (
     id INT AUTO_INCREMENT PRIMARY KEY,
     nama_obat VARCHAR(100),
     kategori VARCHAR(50),
     stok INT,
     harga DECIMAL(10,2)
   );
   ```
   ### .env:
   ```
  database.default.hostname = localhost
  database.default.database = db_rumahsakit_nim
  database.default.username = root
  database.default.password = 
   ``
  ### JWT Secret:
  Disimpan di app/Config/JWT.php atau .env.
  ### Autentikasi
- POST /login – Login dan dapatkan token JWT
- POST /register – Registrasi user baru
- GET /auth/check – Verifikasi token JWT
  ### Endpoint API
  ## Pasien
  GET /pasiens – Daftar pasien

GET /pasiens/{id} – Detail pasien

POST /pasiens – Tambah pasien

PUT /pasiens/{id} – Edit pasien

DELETE /pasiens/{id} – Hapus pasien

## Obat
GET /obats – Daftar obat

GET /obats/{id} – Detail obat

POST /obats – Tambah obat

PUT /obats/{id} – Edit obat

DELETE /obats/{id} – Hapus obat
  ###  Menjalankan Project 
  php spark serve
  ### Akses
  http://localhost:8080
  

