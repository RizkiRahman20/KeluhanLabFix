# Keluhan Lab Test

Keluhan Lab Test adalah aplikasi web berbasis Laravel untuk sistem pelaporan keluhan laboratorium dan maintenance. Project ini menggunakan Laravel, Filament Admin Panel, Filament Shield, Vite, dan Tailwind CSS.

## Teknologi yang Digunakan

- PHP 8.2 keatas
- Laravel versi 12.12.2
- Filament Admin Panel versi 3.3.50
- Laravel DOMPDF versi 3.1.2
- Laravel Livewire untuk kanban board
- Filament Shield versi 3.9.10
- Composer versi 2.7.1
- Node.js
- NPM
- Vite
- Tailwind CSS
- SQLite / MySQL

## Cara install dependency yang ada
### Filament
```bash
composer require filament/filament:"^3.3"
```
```bash
php artisan filament:install --panels
```
#### pilih nama panel default yaitu admin lalu enter

### DOMPDF
```bash
composer require barryvdh/laravel-dompdf
```

## Requirement

Pastikan perangkat sudah terinstall:

- PHP minimal versi 8.2
- Composer
- Node.js
- NPM
- Git
- SQLite atau MySQL
- Laragon / XAMPP / Laravel Herd / environment PHP lainnya

Cek versi dengan command berikut:

```bash
php -v
composer -V
node -v
npm -v
git --version
```

## Cara Install Project

### 1. Clone Repository

```bash
git clone https://github.com/RizkiRahman20/KeluhanLabFix.git
```

Masuk ke folder project:

```bash
cd Keluhan-Lab-Test
```

### 2. Install Dependency Laravel

```bash
composer install
```

### 3. Install Dependency Frontend

```bash
npm install
```

### 4. Copy File Environment

Untuk Linux / macOS:

```bash
cp .env.example .env
```

Untuk Windows CMD:

```bash
copy .env.example .env
```

Untuk Windows PowerShell:

```bash
Copy-Item .env.example .env
```

### 5. Generate Application Key

```bash
php artisan key:generate
```

## Konfigurasi Database

Project ini dapat menggunakan SQLite atau MySQL.

## Opsi 1: Menggunakan SQLite

Pastikan konfigurasi database pada file `.env` seperti berikut:

```env
DB_CONNECTION=sqlite
```

Buat file database SQLite.

Untuk Linux / macOS:

```bash
touch database/database.sqlite
```

Untuk Windows CMD:

```bash
type nul > database\database.sqlite
```

Untuk Windows PowerShell:

```bash
New-Item database/database.sqlite -ItemType File
```

Jalankan migration:

```bash
php artisan migrate
```

## Opsi 2: Menggunakan MySQL

Ubah konfigurasi database pada file `.env`:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=keluhan_lab_test
DB_USERNAME=root
DB_PASSWORD=
```

Buat database MySQL terlebih dahulu:

```sql
CREATE DATABASE keluhan_lab_test;
```

Jalankan migration:

```bash
php artisan migrate
```

## Menjalankan Project

Jalankan Laravel server:

```bash
php artisan serve
```

Jalankan Vite:

```bash
npm run dev
```

Buka aplikasi di browser:

```text
http://127.0.0.1:8000
```

## Menjalankan Project dengan Satu Command

Jika project sudah memiliki script `dev` di `composer.json`, jalankan:

```bash
composer run dev
```

Command tersebut biasanya menjalankan beberapa service seperti:

- Laravel server
- Queue listener
- Laravel Pail
- Vite development server

## Build Asset untuk Production

```bash
npm run build
```

## Setup Filament

Halaman admin Filament biasanya dapat diakses melalui:

```text
http://127.0.0.1:8000/admin
```

Jika route admin berbeda, cek konfigurasi panel di folder berikut:

```text
app/Providers/Filament
```

## Membuat User Filament

Jalankan command berikut:

```bash
php artisan make:filament-user
```

Contoh data user:

```text
Name: Admin
Email: admin@example.com
Password: password
```

Setelah itu login ke halaman Filament.

## Setup Filament Shield

Publish konfigurasi Shield sesuai nama panel.

Jika nama panel adalah `admin`, gunakan command berikut:

```bash
php artisan shield:publish admin
```

Generate permission:

```bash
php artisan shield:generate --all
```

Membuat super admin:

```bash
php artisan shield:super-admin
```

Jika nama panel bukan `admin`, sesuaikan command dengan nama panel yang digunakan di project.

## Storage Link

Jika project menggunakan upload file atau gambar, jalankan:

```bash
php artisan storage:link
```

## Menjalankan Queue

```bash
php artisan queue:work
```

Atau:

```bash
php artisan queue:listen
```

## Melihat Log Laravel

```bash
php artisan pail
```

Atau cek file log manual di:

```text
storage/logs/laravel.log
```

## Menjalankan Testing

```bash
php artisan test
```

Atau:

```bash
composer run test
```

## Struktur Folder Penting

```text
app/              Berisi logic utama aplikasi Laravel
bootstrap/        File bootstrap Laravel
config/           Konfigurasi aplikasi
database/         Migration, seeder, dan factory
public/           File publik aplikasi
resources/        View Blade, CSS, dan JS
routes/           File routing aplikasi
storage/          File cache, log, dan upload
tests/            File testing aplikasi
```

## Command Artisan yang Sering Digunakan

Menjalankan server:

```bash
php artisan serve
```

Menjalankan migration:

```bash
php artisan migrate
```

Rollback migration:

```bash
php artisan migrate:rollback
```

Refresh migration:

```bash
php artisan migrate:fresh
```

Refresh migration dengan seeder:

```bash
php artisan migrate:fresh --seed
```

Membersihkan semua cache:

```bash
php artisan optimize:clear
```

Membersihkan config cache:

```bash
php artisan config:clear
```

Membersihkan route cache:

```bash
php artisan route:clear
```

Membersihkan view cache:

```bash
php artisan view:clear
```

Generate ulang autoload Composer:

```bash
composer dump-autoload
```

## Troubleshooting

### Error `.env` Tidak Ditemukan

Linux / macOS:

```bash
cp .env.example .env
php artisan key:generate
```

Windows CMD:

```bash
copy .env.example .env
php artisan key:generate
```

Windows PowerShell:

```bash
Copy-Item .env.example .env
php artisan key:generate
```

### Error `APP_KEY` Kosong

```bash
php artisan key:generate
```

### Error Database SQLite Tidak Ditemukan

Linux / macOS:

```bash
touch database/database.sqlite
php artisan migrate
```

Windows CMD:

```bash
type nul > database\database.sqlite
php artisan migrate
```

Windows PowerShell:

```bash
New-Item database/database.sqlite -ItemType File
php artisan migrate
```

### Error Dependency Composer

```bash
composer install
composer dump-autoload
php artisan optimize:clear
```

### Error Dependency NPM

Linux / macOS:

```bash
rm -rf node_modules package-lock.json
npm install
```

Windows CMD:

```bash
rmdir /s /q node_modules
del package-lock.json
npm install
```

Windows PowerShell:

```bash
Remove-Item -Recurse -Force node_modules
Remove-Item package-lock.json
npm install
```

### Error Vite Tidak Jalan

```bash
npm install
npm run dev
```

### Error Permission atau Role Shield Tidak Muncul

```bash
php artisan shield:generate --all
php artisan optimize:clear
```

### Error Class Tidak Ditemukan

```bash
composer dump-autoload
php artisan optimize:clear
```

## Setup Cepat

### Linux / macOS

```bash
git clone https://github.com/RizkiRahman20/KeluhanLabFix.git
cd Keluhan-Lab-Test
composer install
npm install
cp .env.example .env
php artisan key:generate
touch database/database.sqlite
php artisan migrate
php artisan storage:link
npm run dev
php artisan serve
```

### Windows CMD

```bash
git clone https://github.com/RizkiRahman20/KeluhanLabFix.git
cd Keluhan-Lab-Test
composer install
npm install
copy .env.example .env
php artisan key:generate
type nul > database\database.sqlite
php artisan migrate
php artisan storage:link
npm run dev
php artisan serve
```

### Windows PowerShell

```bash
git clone https://github.com/RizkiRahman20/KeluhanLabFix.git
cd Keluhan-Lab-Test
composer install
npm install
Copy-Item .env.example .env
php artisan key:generate
New-Item database/database.sqlite -ItemType File
php artisan migrate
php artisan storage:link
npm run dev
php artisan serve
```

## Akun Admin

Jika belum ada akun admin, buat dengan command:

```bash
php artisan make:filament-user
```

Contoh akun lokal:

```text
Email: admin@example.com
Password: password
```