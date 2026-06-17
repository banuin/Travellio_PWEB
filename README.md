# Travellio 🏖️

**Travellio** adalah sebuah sistem informasi berbasis web untuk reservasi paket wisata. Dibangun menggunakan *framework* Laravel, aplikasi ini memfasilitasi pelanggan untuk mencari, memesan, dan mengunggah bukti pembayaran paket wisata, sekaligus memberikan kemudahan bagi pengelola (Admin) untuk mengonfirmasi pesanan dan mengelola katalog destinasi.

---

## 👥 PENULIS


---
# Petunjuk Pemasangan (Instalasi)

Sistem Travellio dirancang untuk dijalankan di lingkungan *local* (disarankan menggunakan **Laragon** atau **XAMPP**). Berikut adalah langkah-langkah untuk menjalankan proyek ini di komputer:

### 1. Persiapan Awal
Pastikan komputer sudah terpasang:
* PHP (minimal versi 8.1)
* Composer
* Node.js & npm
* Git

### 2. Clone Repositori
Buka terminal dan unduh kode sumber dari GitHub:
```bash
git clone [URL_REPO_GITHUB_INI]
cd Travellio_PWEB
```

### 3. Install Dependensi
Unduh seluruh pustaka (*library*) PHP dan komponen *frontend* yang dibutuhkan:
```bash
composer install
npm install
npm run build
```

### 4. Konfigurasi Database
1. Salin file `.env.example` dan ubah namanya menjadi `.env`.
2. Buka aplikasi Laragon (atau XAMPP) dan pastikan Apache & MySQL menyala.
3. Buat *database* kosong baru di phpMyAdmin/HeidiSQL dengan nama: `dbtravellio`.
4. Buka file `.env` di kode editor, lalu sesuaikan bagian koneksi *database* persis seperti ini:
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=dbtravellio
DB_USERNAME=root
DB_PASSWORD=
```

### 5. Generate Key & Eksekusi Database
Jalankan perintah ini secara berurutan di terminal untuk mengamankan aplikasi dan membentuk struktur tabel beserta data awalnya:
```bash
php artisan key:generate
php artisan migrate:fresh --seed
```

### 6. Tautkan Folder Penyimpanan Foto
Agar foto destinasi dan bukti transfer pembayaran dapat diakses dan ditampilkan di *website*, wajib jalankan perintah ini:
```bash
php artisan storage:link
```

### 7. Jalankan Aplikasi
Nyalakan *server* lokal Laravel:
```bash
php artisan serve
```

Aplikasi kini sudah berjalan. Buka *browser* dan akses **http://localhost:8000**.
