# GitHub Pages Deployment — SD Negeri Kibitay

**Target URL:** `https://sdnkibitayofficial.github.io/sdnkibitayOK/`

---

## Langkah-langkah Deploy (Manual)

Karena GitHub CLI belum terautentikasi, lakukan langkah berikut secara manual:

### 1️⃣ Siapkan Folder Deploy
Folder siap deploy ada di:
```
/mnt/workspace/portal-sdn-kibitay/PUBLISH_READY/
```

Isi folder:
- `index.html` — Halaman utama website (282 baris)
- `README.md` — Dokumentasi
- `.nojekyll` — Meng Disable Jekyll processing

### 2️⃣ Buat Repository di GitHub

1. Buka browser dan login ke GitHub
2. Kunjungi: https://github.com/new
3. Isi form:
   - **Owner/Username**: `sdnkibitayofficial` (atau username GitHub Anda)
   - **Repository name**: `sdnkibitayOK`
   - **Description**: SD Negeri Kibitay - Official Website
   - **Visibility**: Public
   - ❌ Jangan centang "Add a README file"
4. Klik **Create repository**

### 3️⃣ Upload File ke Repository

Dari terminal/Command Prompt, jalankan:

```bash
# Clone repository baru
git clone https://github.com/sdnkibitayofficial/sdnkibitayOK.git
cd sdnkibitayOK

# Copy file dari folder publish ready
copy /Y "\mnt\workspace\portal-sdn-kibitay\PUBLISH_READY\*" .
# atau
cp /mnt/workspace/portal-sdn-kibitay/PUBLISH_READY/* .

# Commit dan push
git add .
git commit -m "Initial website deployment - SD Negeri Kibitay"
git branch -M main
git push -u origin main
```

### 4️⃣ Aktifkan GitHub Pages

1. Di halaman repository GitHub, klik tab **Settings**
2. Scroll ke bawah, pilih **Pages**
3. Di bagian **Source**, pilih **Deploy from a branch**
4. Di **Branch**, pilih:
   - Branch: `main`
   - Folder: `/ (root)`
5. Klik **Save**
6. Tunggu 2-5 menit, website akan live!

### 5️⃣ Verifikasi Website Live

Website akan tersedia di:
```
https://sdnkibitayofficial.github.io/sdnkibitayOK/
```

---

## CATATAN PENTING ⚠️

| Aspek | Status |
|-------|--------|
| Static HTML | ✅ Support |
| Tailwind CSS CDN | ✅ Support |
| JavaScript | ✅ Support |
| Database (SQLite) | ❌ Tidak support di GitHub Pages |
| PHP/Laravel | ❌ Tidak support di GitHub Pages |
| Admin Panel | ❌ Tidak support (butuh backend) |
| Form Kontak | ✅ Bisa pakai formsubmit atau Google Forms |

---

## Solusi Alternatif

Jika butuh fitur database (admin panel, PPDB online):

1. **Gunakan Netlify + Firebase/Supabase**
   - Frontend: Netlify (free)
   - Backend: Supabase (free tier)

2. **Gunakan Vercel + MongoDB Atlas**
   - Frontend: Vercel (free)
   - Database: MongoDB Atlas (free tier)

3. **Hosting Lokal + Domain**
   - Sewa hosting Indonesia (~Rp 50rb/bulan)
   - Daftar domain sendiri (.sch.id)

---

## Deadline Soft Launch

📅 **15 Agustus 2026**

Silakan selesaikan deploy sebelum deadline!

---

*Panduan dibuat: 14 Agustus 2026*
