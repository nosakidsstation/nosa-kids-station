# 📘 PANDUAN UPDATE WEBSITE — NOSA KIDS STATION
# Baca ini sebelum mengubah apapun di website Anda!

---

## 📁 STRUKTUR FILE WEBSITE

```
nosa-kids-station/
│
├── index.html          ← Halaman Beranda (Home)
├── tentang.html        ← Halaman Tentang Kami
├── produk.html         ← Halaman Produk (dengan filter kategori)
├── galeri.html         ← Halaman Galeri (Ilustrasi / Video / Momen)
├── kontak.html         ← Halaman Kontak + FAQ + Form WA
│
├── favicon.svg         ← Logo kecil di tab browser (ganti dengan logo Anda)
│
└── assets/
    ├── css/
    │   └── style.css   ← Semua gaya/warna website
    ├── js/
    │   └── main.js     ← Script global (animasi, navbar, counter)
    └── images/         ← Taruh foto produk & ilustrasi di sini
```

---

## 🔧 HAL PERTAMA YANG HARUS DIGANTI

### 1. Nomor WhatsApp Business
Cari teks `6281234567890` di SEMUA file .html dan ganti dengan nomor WA Anda.
Gunakan fitur "Find & Replace" di text editor (Ctrl+H).
Format: 62 + nomor tanpa 0 di depan. Contoh: 0812-3456-7890 → 6281234567890

### 2. Link Toko Online
Cari dan ganti URL toko di semua file:
- `https://www.tokopedia.com/nosakids`  → URL toko Tokopedia Anda
- `https://shopee.co.id/nosakids`       → URL toko Shopee Anda
- `https://www.tiktok.com/shop/nosakids`→ URL TikTok Shop Anda

### 3. Link YouTube Channel
Ganti `https://www.youtube.com/@NosaKidsStation` dengan URL channel Anda.

### 4. Favicon (Logo Tab Browser)
Ganti file `favicon.svg` dengan logo Anda sendiri.
Format yang didukung: .svg, .png, .ico
Jika pakai .png, ubah di semua <head>:
  <link rel="icon" href="favicon.png" type="image/png" />

### 5. Email
Ganti `nosakidsstation@gmail.com` dengan email Anda.

---

## 🛍️ CARA TAMBAH / UPDATE PRODUK (produk.html)

### Tambah Produk Baru:
1. Buka `produk.html` dengan text editor (Notepad++, VS Code, dll.)
2. Cari komentar: `<!-- BUKU 1 -->` atau `<!-- FLASH CARD 1 -->`, dll.
3. Copy salah satu blok `<div class="product-card">` lengkap
4. Tempel setelah blok terakhir (sebelum `</div><!-- /products-grid -->`)
5. Ubah:
   - `data-cat="buku"` → sesuai kategori: buku / flashcard / merch
   - Nama, deskripsi, usia produk
   - Link Tokopedia, Shopee, TikTok, WA

### Tambah Foto Produk:
1. Simpan foto produk ke folder `assets/images/` (misal: `buku-hutan.jpg`)
2. Di dalam `.product-img`, hapus: `<span class="product-img-placeholder">📖</span>`
3. Ganti dengan: `<img src="assets/images/buku-hutan.jpg" alt="Nama Produk" class="product-photo">`
4. Tambahkan style di `.product-img`: hapus `display:flex; align-items:center; justify-content:center;`

---

## 🖼️ CARA TAMBAH FOTO DI GALERI (galeri.html)

### Tab Ilustrasi:
1. Buka `galeri.html`, cari bagian `<!-- TAB 1: ILUSTRASI -->`
2. Copy satu blok `<div class="masonry-item">` lengkap
3. Ganti emoji dengan foto:
   ```html
   <!-- SEBELUM (emoji placeholder): -->
   <div class="gallery-img">🦁</div>

   <!-- SESUDAH (foto asli): -->
   <div class="gallery-img" style="padding:0;font-size:0">
     <img src="assets/images/ilustrasi-nosa.jpg" alt="Nosa Lion" style="width:100%;display:block">
   </div>
   ```
4. Update teks di `onclick="openLightbox('Judul', 'emoji', 'Deskripsi')"`

### Tab Video (embed YouTube):
1. Cari `data-vcat="hewan"` (atau kategori lain)
2. Di `.video-thumb`, tambahkan ID video YouTube yang benar
3. Update onclick: `onclick="openVideoLink('ID_VIDEO_YOUTUBE_ANDA')"`
   Contoh ID video: `https://youtube.com/watch?v=dQw4w9WgXcQ` → ID-nya adalah `dQw4w9WgXcQ`

### Tab Momen (foto customer):
1. Cari `<div class="moment-card">`
2. Ganti emoji dengan foto customer:
   ```html
   <img src="assets/images/customer-sari.jpg" alt="Keluarga Sari"
        style="width:100%;height:100%;object-fit:cover;position:absolute;inset:0;border-radius:inherit">
   ```

---

## 🎬 CARA EMBED VIDEO YOUTUBE DI HOMEPAGE (index.html)

1. Buka `index.html`, cari fungsi `playVideo`
2. Ganti `VIDEO_ID_YOUTUBE` dengan ID video YouTube Anda:
   ```javascript
   wrap.innerHTML = `<iframe src="https://www.youtube.com/embed/ID_VIDEO_ANDA?autoplay=1" ...></iframe>`;
   ```

---

## 🎨 CARA UBAH WARNA WEBSITE (assets/css/style.css)

Cari bagian `:root {` di baris paling atas style.css.
Ubah nilai warna sesuai keinginan:

```css
:root {
  --primary: #FF8C42;       ← Warna oranye utama
  --secondary: #4ECDC4;     ← Warna teal/hijau aksen
  --accent: #FFD166;        ← Warna kuning highlight
  --bg: #FFFBF5;            ← Warna latar belakang halaman
}
```

---

## 📊 CARA UPDATE ANGKA STATISTIK (index.html)

Cari bagian `data-target=` di index.html dan ubah angkanya:
```html
<span data-target="250">0</span>  ← Jumlah subscriber
<span data-target="30">0</span>   ← Jumlah video
```

---

## 🚀 CARA UPLOAD KE HOSTING

1. **Upload semua file** ke folder `public_html` (atau `www`) di hosting Anda
2. **Pertahankan struktur folder** — jangan ubah nama folder `assets/`
3. Website langsung bisa diakses di domain Anda

### Rekomendasi Hosting Indonesia:
- Niagahoster (niagahoster.co.id)
- Hostinger Indonesia (hostinger.co.id)
- IDCloudHost (idcloudhost.com)
- Domainesia (domainesia.com)

---

## ❓ FAQ TEKNIS

**Q: Website tidak tampil dengan benar setelah diupload?**
A: Pastikan semua file terupload, termasuk folder `assets/css/` dan `assets/js/`

**Q: Font tidak muncul?**
A: Butuh koneksi internet untuk memuat Google Fonts. Pastikan hosting aktif.

**Q: Tombol WA tidak berfungsi?**
A: Pastikan nomor WA sudah diganti dengan benar. Format: 62 + nomor tanpa 0 di depan.

**Q: Gambar produk tidak muncul?**
A: Pastikan nama file foto sama persis dengan yang ditulis di kode (case-sensitive).

---

## 📞 BUTUH BANTUAN?

Simpan file ini sebagai referensi setiap kali Anda ingin update website.
Selamat berbisnis, semoga Nosa Kids Station terus berkembang! 🌟

---
Dibuat untuk: Nosa Kids Station
Website: nosakidsstation.com
