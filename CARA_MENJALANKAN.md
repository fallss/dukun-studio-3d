# Panduan Menjalankan Website (Dukun — Gen Z)

Panduan langkah demi langkah untuk menjalankan website secara lokal di komputer Anda.

---

## 1. Prasyarat Sistem

Pastikan sistem Anda sudah terinstal:
- **Node.js**: Versi `v18+` atau `v20+` (disarankan LTS).
- **npm**: Versi `9+` atau `10+`.

Untuk memeriksa versi yang terpasang di terminal:
```bash
node -v
npm -v
```

---

## 2. Buka Terminal di Direktori Proyek

Pastikan Anda berada di direktori proyek ini:
```bash
cd /home/ifhalfaizi/Downloads/Dukun-website
```

---

## 3. Instalasi Dependensi (Jika Belum)

*Catatan: Dependensi (`node_modules`) sudah di-install sebelumnya. Namun jika Anda memindahkan folder atau menghapus `node_modules`, jalankan perintah berikut:*

```bash
npm install
```

---

## 4. Menjalankan Dev Server

Jalankan perintah ini di terminal Anda:

```bash
npm run dev
```

Setelah perintah dijalankan, terminal akan menampilkan output seperti:
```text
  VITE v7.3.6  ready in ~350 ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: http://192.168.1.6:5173/
```

---

## 5. Membuka Website di Browser

Buka browser pilihan Anda (Google Chrome, Mozilla Firefox, Brave, Edge, dll.), lalu akses alamat:

👉 **[http://localhost:5173](http://localhost:5173)**

---

## 6. Cara Menghentikan Server

Untuk mematikan/menghentikan server development:
- Klik pada jendela terminal tempat `npm run dev` berjalan.
- Tekan kombinasi tombol **`Ctrl + C`** pada keyboard.

---

## 7. Perintah Lain yang Tersedia

| Perintah | Deskripsi |
| :--- | :--- |
| `npm run dev` | Menjalankan local development server dengan hot reload. |
| `npm run build` | Membuat build static produksi ke folder `dist/`. |
| `npm run preview` | Menjalankan preview server lokal dari hasil build `dist/`. |
| `npm test` | Menjalankan smoke test suite (`scripts/smoke.mjs`). |

---

## 8. Tips & Pemecahan Masalah (Troubleshooting)

- **Port 5173 Terpakai (Port Already in Use):**
  Jika port `5173` sedang dipakai aplikasi lain, Vite otomatis menggunakan port berikutnya (misalnya `5174`). Cek URL yang tertera di log terminal.
- **Tampilan 3D / WebGL lambat:**
  Pastikan fitur **Hardware Acceleration** aktif di pengaturan browser Anda agar Three.js dan React Three Fiber berjalan optimal.
