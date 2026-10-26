# ePasien

Aplikasi ePasien berbasis PHP untuk integrasi dengan database SIMRS. Repositori ini berisi kode sumber; konfigurasi operasional dan data pasien harus tetap berada di server privat.

## Keamanan sebelum menjalankan

1. Jangan pernah commit `conf/local-secrets.php`, file `.env`, dump database, atau dokumen/foto pasien.
2. Salin `conf/local-secrets.example.php` menjadi `conf/local-secrets.php` di server lokal.
3. Isi `EPASIEN_AES_KEY` dengan kunci privat yang saat ini digunakan oleh instalasi ePasien Anda. Jangan mengganti kunci tanpa rencana migrasi, karena dipakai untuk membaca/mencocokkan data password lama.
4. Sesuaikan koneksi database melalui variabel lingkungan `EPASIEN_DB_HOST`, `EPASIEN_DB_USER`, `EPASIEN_DB_PASSWORD`, dan `EPASIEN_DB_NAME`, atau sesuaikan nilai lokal pada konfigurasi server Anda. Jangan memakai akun database `root` tanpa kata sandi pada server produksi.
5. Jangan mengunggah hasil ekspor database `sik` atau data pasien ke repositori publik.

## Menjalankan di Mac dengan XAMPP

1. Letakkan folder aplikasi di direktori web XAMPP.
2. Siapkan database SIMRS yang sesuai di server lokal.
3. Buat `conf/local-secrets.php` dari file contoh dan atur konfigurasi privat pada server lokal.
4. Jalankan Apache dan MySQL dari XAMPP, lalu buka aplikasi melalui `http://localhost/ePasien/`.

> Catatan: aplikasi membutuhkan skema database SIMRS yang cocok dan konfigurasi privat yang benar. Repositori ini tidak menyertakan database.

## Git

Setelah repositori GitHub `RokhmanCore/ePasien` dibuat, jalankan `git init`, tambahkan remote, lalu push sesuai instruksi di terminal. Pastikan `git status --ignored` menunjukkan file rahasia dan data runtime tidak ikut dipentaskan.
