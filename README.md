# 📊 Pemantau Akaun Premium

Sebuah aplikasi web tanpa pelayan (serverless) yang direka khusus untuk memantau, merekod, dan mengesahkan transaksi pembayaran hutang dua hala secara telus. Aplikasi ini menggunakan antaramuka web berwajah premium dan menjadikan Google Sheets sebagai pangkalan data percuma sepenuhnya.

## ✨ Ciri-ciri Utama

* **Pengiraan Baki Dinamik:** Mengira baki hutang secara masa nyata (real-time). Hanya transaksi yang berstatus **"Sah"** akan diambil kira dalam jumlah baki.
* **Sistem Pengesahan:** Transaksi baharu akan dilabelkan sebagai **"Menunggu"** dan menghantar notifikasi e-mel automatik untuk tujuan pengesahan pihak kedua.
* **Antaramuka Premium:** Dibina menggunakan HTML, JavaScript, dan **Tailwind CSS** dengan rekaan mod gelap (Dark Mode) berkonsepkan *Glassmorphism*.
* **100% Percuma & Serverless:** Dihoskan secara percuma di GitHub Pages, manakala bahagian belakang (backend) dikuasakan oleh Google Apps Script dan Google Sheets.

---

## 🛠️ Panduan Pemasangan (Setup)

Sistem ini terbahagi kepada dua bahagian utama: **Pangkalan Data (Google)** dan **Antaramuka Web (GitHub)**.

### Bahagian 1: Menyiapkan Google Sheets & Apps Script
1. Buka [Google Sheets](https://sheets.google.com) baharu dan namakan helaian (sheet) pertama sebagai `Transaksi`.
2. Buat tajuk lajur (header) pada baris pertama: `A1: ID`, `B1: Tarikh`, `C1: Jumlah`, `D1: Jenis`, `E1: Status`.
3. Klik menu **Extensions > Apps Script**.
4. Salin kod *Google Apps Script* yang berkaitan dan tampal ke dalam editor. Pastikan anda menukar `emailPenerima` di dalam skrip kepada e-mel pihak kedua.
5. Klik **Deploy > New deployment**.
   * Pilih jenis: **Web app**
   * Execute as: **Me**
   * Who has access: **Anyone**
6. Salin **Web App URL** yang dijana. URL ini akan digunakan dalam fail web anda.

### Bahagian 2: Menyiapkan GitHub Pages (HTML)
1. Cipta repositori baharu di GitHub.
2. Muat naik fail `index.html`.
3. Buka fail `index.html` dan cari pembolehubah `SCRIPT_URL`. Gantikan URL tersebut dengan **Web App URL** yang anda salin dari Google Apps Script tadi.
   ```javascript
   const SCRIPT_URL = "MASUKKAN_URL_WEB_APP_ANDA_DI_SINI";
