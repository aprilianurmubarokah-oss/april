# Aprilia Portofolio

Portofolio editorial statis untuk **Aprilia Nur Mubaroka** — desainer UI/UX dan web junior asal Surabaya. Dibangun sebagai satu halaman HTML dengan Tailwind CSS via CDN, Google Fonts, dan aset lokal.

![Pratinjau portofolio](screen.png)

## Isi

- Hero dengan identitas dan foto profil
- Ringkasan lokasi, ketersediaan, dan daftar keahlian
- Enam kartu karya pilihan: short video, UI/UX, desain busana, animasi 3D, logo, dan magang
- Pendekatan kerja 5 fase
- Dua studi kasus magang beserta tautan sertifikat
- Empat layanan
- Footer kontak dan tautan media sosial

Sistem warna, tipografi, grid, dan komponen terdokumentasi di [`DESIGN.md`](DESIGN.md).

## Struktur

```text
.
├── index.html              # Halaman utama / entry point GitHub Pages
├── code.html               # Salinan sumber asli sebelum penambahan entry point
├── 404.html                # Halaman 404 sesuai gaya portofolio
├── favicon.svg             # Favicon "AP"
├── DESIGN.md               # Design system (warna, tipe, spacing, komponen)
├── README.md               # Dokumentasi repo dan cara deploy
├── LICENSE.md              # Hak cipta
├── .gitignore              # Pengecualian file OS/editor/dependency
├── .nojekyll               # Menonaktifkan pemrosesan Jekyll di GitHub Pages
├── .github/workflows/      # Workflow deploy GitHub Pages
├── screen.png              # Pratinjau untuk README
├── april Photostudio/      # Aset sertifikat
├── Diamond Propertindo/    # Aset dokumentasi magang
└── *.png, *.jpg, *.jpeg    # Aset karya (foto, short video, skill, UI/UX, 3D, busana, logo, magang)
```

Semua `src` gambar di `index.html` dan `code.html` sudah diselaraskan dengan nama file aktual di direktori tersebut.

## Menjalankan secara lokal

Karena ini situs statis, tidak perlu instalasi dependency. Buka `index.html` langsung di browser, atau jalankan server lokal agar perilaku identik dengan GitHub Pages:

```powershell
python -m http.server 8000
```

Lalu buka <http://localhost:8000>.

Alternatif lain:

```powershell
npx serve .
```

> Tailwind, Google Fonts, dan Material Symbols dimuat dari CDN, jadi koneksi internet diperlukan saat menampilkan halaman.

## Upload ke GitHub

1. Buat repository baru di GitHub (misalnya `aprilia-portofolio`). Sebaiknya biarkan kosong—tanpa README atau `.gitignore` bawaan—karena berkas tersebut sudah ada di sini.
2. Di repository, buka **Settings → Pages → Build and deployment**.
3. Pilih **Source: GitHub Actions**.
4. Tambahkan remote dan push:

   ```powershell
   git remote add origin https://github.com/<USERNAME>/<REPO>.git
   git branch -M main
   git push -u origin main
   ```

5. Workflow [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml) akan otomatis mem-publish ke GitHub Pages. URL situs tersedia di tab **Actions** atau **Settings → Pages**.

Jika lebih ingin tanpa Actions, pilih **Deploy from a branch → main → /(root)** pada pengaturan Pages. Berkas `.nojekyll` sudah disertakan agar GitHub tidak memproses berkas dengan Jekyll.

## Kustomisasi

- Ubah nama, deskripsi, email, dan tautan sosial langsung di `index.html`.
- Teks tombol **MINTA CV** saat ini mengarah ke bagian kontak. Jika sudah ada berkas CV, letakkan misalnya `CV/Aprilia-CV.pdf` lalu ganti `href="#contact"` pada tautan tersebut menjadi `href="CV/Aprilia-CV.pdf"` dan `target="_blank"`.
- Ganti metadata `og:title`, `og:description`, dan `twitter:*` dengan URL publik setelah repo di-deploy bila ingin pratinjau tautan yang presisi.
- Perbarui `screen.png` setiap kali tampilan utama berubah agar pratinjau README tetap relevan.

## Hak cipta

© 2026 Aprilia Nur Mubaroka. Seluruh hak dilindungi. Lihat [`LICENSE.md`](LICENSE.md).
