# IndoGlobalPrint — Website Multi-Halaman

Website e-commerce IndoGlobalPrint versi **multi-halaman** (bukan SPA), siap di-publish ke GitHub Pages.

## 📁 Struktur File

```
indoglobalprint/
├── index.html       ← Beranda (hero, produk trending, CTA)
├── toko.html        ← Toko (semua produk, filter, pencarian)
├── kategori.html    ← Kategori (browse per kategori)
├── tentang.html     ← Tentang Kami
├── login.html       ← Form Login
├── daftar.html      ← Form Pendaftaran
├── style.css        ← Semua styling (shared)
├── app.js           ← Semua logic JS (shared)
└── README.md
```

## ✨ Fitur Lengkap

### Halaman
- 🏠 **Beranda** (`index.html`) — Hero, produk trending, stats, CTA
- 🛒 **Toko** (`toko.html`) — 29 produk, filter kategori, pencarian real-time
- 📂 **Kategori** (`kategori.html`) — Browse per kategori + pratinjau produk
- ℹ️ **Tentang** (`tentang.html`) — Cerita perusahaan, nilai, statistik
- 🔐 **Login** (`login.html`) — Form login + validasi + toggle password + lupa sandi
- 📝 **Daftar** (`daftar.html`) — Registrasi + password strength meter + validasi lengkap

### Fitur Teknis
- 🛍️ **Keranjang** — Sidebar cart, qty management, total harga
- 🔍 **Modal Produk** — Detail lengkap per produk
- 🔔 **Toast Notifikasi** — Feedback real-time
- 📱 **Responsive** — Mobile, tablet, desktop
- 💾 **Auth Persisten** — Login state tersimpan di `localStorage`
- 🛒 **Cart Persisten** — Cart tersimpan di `sessionStorage`
- 🔒 **Guard Login** — Harus login untuk tambah ke keranjang

## 🚀 Deploy ke GitHub Pages

### 1. Init & Push

```bash
git init
git add .
git commit -m "feat: IndoGlobalPrint multi-page website"
git branch -M main
git remote add origin https://github.com/<USERNAME>/<REPO>.git
git push -u origin main
```

### 2. Aktifkan GitHub Pages

1. Buka repository → **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: **main** · Folder: **/ (root)**
4. Klik **Save**
5. Tunggu 1-2 menit → website live di:
   `https://<USERNAME>.github.io/<REPO>/`

### 3. Custom Domain (Opsional)

Tambahkan file `CNAME` berisi domain Anda, contoh:
```
www.indoglobalprint.com
```
Lalu set CNAME record di DNS provider ke `<USERNAME>.github.io`.

---

## 🛠️ Kustomisasi

### Tambah Produk Baru
Edit array `ALL_PRODUCTS` di `app.js`:
```js
{
  id: 'ID_BARU',
  name: 'Nama Produk',
  price: 1.50,
  category: 'Stiker',   // atau 'T-Shirt'
  image: 'URL_GAMBAR',
  size: 'Ukuran',
  shape: 'Bentuk',
  material: 'Material',
  usage: 'Kegunaan',
}
```

### Ubah Warna Tema
Edit variabel di `style.css`:
```css
:root {
  --primary:   #7c22d4;   /* Ungu */
  --secondary: #ff3d9a;   /* Pink */
  --accent:    #ffd600;   /* Kuning */
}
```

### Produk Featured di Beranda
Edit array `FEATURED_IDS` di `app.js`:
```js
const FEATURED_IDS = ['19', '29', '31', '34'];
```

---

## 🔐 Sistem Auth (Frontend-only)

| Penyimpanan | Data |
|-------------|------|
| `localStorage.igp_users` | Daftar semua pengguna terdaftar |
| `localStorage.igp_user` | Pengguna yang sedang login |
| `sessionStorage.igp_cart` | Isi keranjang belanja |

> ⚠️ Ini adalah implementasi frontend-only untuk demo/prototype. Untuk produksi, gunakan backend & database yang aman.

---

&copy; 2025 IndoGlobalPrint. Semua hak dilindungi.
