# Ardill Fashion — Website E-Commerce

Website katalog & pemesanan produk fashion berbasis single-file HTML (HTML + CSS + JavaScript murni, tanpa framework, tanpa build tools). Cukup buka `index.html` di browser atau upload ke hosting statis mana pun.

## ✨ Fitur

- **Katalog produk** dengan grid responsif, dikelompokkan per kategori (Atasan, Bawahan, Dress).
- **Pencarian produk** langsung (live search) dengan saran/autocomplete di topbar.
- **Keranjang belanja (cart panel)** — tambah, ubah jumlah, hapus produk, dan lihat total belanja secara real-time.
- **Hero carousel** di halaman utama (bisa geser otomatis via tombol panah/dots).
- **Formulir pemesanan** — nama, alamat, username Instagram, no. HP, serta pemilihan produk dari keranjang.
- **Metode pembayaran**: Cash (COD), QRIS, dan E-Wallet DANA — masing-masing menampilkan instruksi & rincian sendiri di modal.
- **Konfirmasi pesanan via WhatsApp** — otomatis membentuk pesan (nama, alamat, produk, total, metode bayar) yang siap dikirim ke nomor WhatsApp toko.
- **Sidebar navigasi** dengan tautan cepat ke setiap section (Beranda, Katalog, Kategori, Kontak, Form Pesan), termasuk versi mobile (hamburger menu).
- **Sepenuhnya responsif** — menyesuaikan tampilan untuk desktop, tablet, dan mobile.
- **Gambar produk tertanam permanen** sebagai data `base64` langsung di dalam file HTML (bukan link eksternal, bukan localStorage), sehingga gambar tetap tampil meski file dihosting di GitHub Pages, Netlify, Vercel, atau dibuka secara offline.

## 🗂️ Struktur Proyek

Proyek ini hanya terdiri dari **satu file**:

```
index.html   → berisi seluruh markup (HTML), styling (CSS), dan logika (JavaScript)
```

Tidak ada dependency eksternal selain Google Fonts (`Playfair Display` & `Jost`) yang dimuat via CDN.

## 🛍️ Data Produk

Daftar produk didefinisikan langsung di dalam script (variabel `products`), masing-masing berisi `id`, `name`, `category`, dan `price`. Contoh kategori yang tersedia saat ini:

| Kategori | Contoh Produk |
|---|---|
| Atasan | Baju Kemeja, Kaos Polos, Cardigan, Crop Top, Hoodie |
| Bawahan | Celana Jeans, Celana Pendek, Kulot, Celana Cargo |
| Dress | Dress |

## 🔧 Cara Kustomisasi

### 1. Mengganti gambar produk
Cari komentar `GANTI GAMBAR` di dalam file, lalu ganti isi `src="data:image/jpeg;base64,...."` pada tag `<img>` terkait dengan gambar baru (boleh data base64 baru atau URL gambar biasa).

### 2. Menambah/mengubah produk
Edit array `products` di bagian `<script>` — tambahkan objek baru dengan format:
```js
{id:'id-unik', name:'Nama Produk', category:'Atasan', price:100000}
```
Lalu tambahkan juga kartu produk (`product-card`) yang sesuai di bagian HTML katalog.

### 3. Mengganti kontak (WhatsApp, Instagram, Email, No. Rekening)
Gunakan **Ctrl+F** untuk mencari dan mengganti seluruh kemunculan:
- Nomor WhatsApp/DANA: `082216889411`
- Email: `adilaputrirahmadita@gmail.com`
- Username Instagram: `adlptrirhmdta`

### 4. Mengganti warna & gaya tampilan
Warna tema utama diatur lewat CSS custom properties di bagian `:root`, misalnya:
```css
--accent:#B3855F;
--accent-deep:#6B4F3B;
--bg-cream:#FAF5EC;
```
Ubah nilai-nilai ini untuk mengganti skema warna keseluruhan situs.

## 💳 Metode Pembayaran yang Didukung

1. **Cash (COD)** — pembayaran tunai saat barang diambil/diterima di alamat toko.
2. **QRIS** — scan kode QR dari aplikasi e-wallet/m-banking apa saja.
3. **DANA** — transfer ke nomor e-wallet DANA toko.

Setelah memilih metode pembayaran dan mengisi form, pengguna akan diarahkan untuk mengonfirmasi pesanan melalui WhatsApp dengan pesan yang sudah otomatis terisi.

## 🚀 Cara Menjalankan

Karena ini adalah file HTML statis tanpa dependency build, cukup:

1. **Buka langsung secara offline** — double click `index.html`, atau
2. **Deploy ke hosting statis** seperti GitHub Pages, Netlify, atau Vercel — cukup upload file `index.html` tanpa konfigurasi tambahan.

## 📱 Teknologi yang Digunakan

- HTML5
- CSS3 (custom properties, flexbox, grid, animasi)
- JavaScript (vanilla, tanpa framework/library)
- Google Fonts (`Playfair Display`, `Jost`)

## 📄 Lisensi

Proyek ini merupakan template internal untuk toko **Ardill Fashion** dan dapat dimodifikasi sesuai kebutuhan pemilik toko.
