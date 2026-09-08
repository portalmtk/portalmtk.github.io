# Portal Siswa SMP Negeri Muara Siram (GitHub Pages)

Aplikasi Web Pembelajaran Terpadu berbasis **GitHub Pages** yang terhubung langsung ke database dan storage **Supabase**:
1. **📤 Kirim Tugas Mandiri**: Multi-foto tugas, nama otomatis terkunci setelah mengumpulkan, dan tanda terima waktu kirim (WITA).
2. **📊 Rekapitulasi & Nilai**: Mode Guru dengan PIN (`GURUCERDAS` atau `1234`) untuk melihat foto tugas, memberikan nilai, serta Export CSV.
3. **📅 Jadwal Pelajaran**: Jadwal interaktif per kelas (VII, VIII, IX) dan per hari (Senin - Jumat).
4. **📚 Materi Pelajaran per Pertemuan**: Siswa dapat memfilter materi berdasarkan Pertemuan (Pertemuan 1 s/d 8) dan mengunduh modul/file. Guru dapat mengunggah modul materi baru langsung ke Supabase Storage.

---

## 🚀 Cara Menghubungkan ke GitHub Pages (Selesai dalam 2 Menit)

### Opsi 1: Lewat Web GitHub (Paling Praktis Tanpa Command Line)
1. Buka [github.com/new](https://github.com/new) dan buat repository baru (contoh nama repo: `portal-smp`). Pilih opsi **Public**.
2. Klik tombol **"uploading an existing file"**.
3. Drag & drop seluruh isi folder ini (`index.html`, `supabase_schema.sql`, dan `README.md`) ke web GitHub, lalu klik **Commit changes**.
4. Masuk ke menu **Settings** repository > pilih tab **Pages** (di sidebar kiri).
5. Pada bagian **Build and deployment > Branch**:
   - Pilih Branch: `main` (atau `master`)
   - Folder: `/ (root)`
   - Klik **Save**.
6. Tunggu sekitar 1 menit, link website Anda akan langsung aktif di:
   `https://<username-anda>.github.io/portal-smp/`

---

### Opsi 2: Menggunakan Git Bash / Terminal
Buka terminal di folder `PORTAL_GITHUB_PAGES`:
```bash
git init
git add .
git commit -m "Deploy Portal Siswa SMP Muara Siram"
git branch -M main
git remote add origin https://github.com/<username-anda>/<nama-repo>.git
git push -u origin main
```
Lalu aktifkan GitHub Pages di menu **Settings > Pages > Branch: main > Save**.

---

## 🗄️ Menjalankan Skrip Database Supabase (Opsional tapi Direkomendasikan)
Buka [Supabase Dashboard](https://supabase.com/dashboard) project Anda:
1. Pilih menu **SQL Editor** di sidebar kiri.
2. Buka file `supabase_schema.sql` di folder ini, lalu salin (*copy*) seluruh isinya.
3. Tempel (*paste*) ke SQL Editor Supabase, kemudian klik **Run**.
4. Tabel `materi_pelajaran` dan `jadwal_pelajaran` otomatis terbentuk lengkap dengan data jadwal default!
*(Catatan: Web portal sudah dilengkapi sistem cerdas fallback/cache lokal, sehingga tetap berjalan lancar saat diakses pertama kali).*

---

## 🔐 Kredensial & Akses Guru
- **PIN Akses Guru**: `GURUCERDAS` (atau `1234`)
- **Fungsi Mode Guru**:
  - Memeriksa foto lembar tugas siswa ukuran penuh.
  - Memberi nilai & catatan guru yang langsung tersimpan di Supabase.
  - Mengunduh rekap nilai format file CSV Excel.
  - Mengunggah file modul materi pelajaran baru berdasarkan nomor pertemuan.
