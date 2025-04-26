
# 📄 Sertifikat Generator

> **Otomatisasi pembuatan sertifikat** berbasis data Excel dan background gambar menggunakan Python.

---

## ✨ Fitur Utama

- Membuat **sertifikat belakang** yang berisi tabel acara dan kepanitiaan.
- Membuat **sertifikat tengah** berdasarkan **jabatan** dengan background khusus.
- Mendukung **mapping jabatan** ke background otomatis.
- Menggabungkan sertifikat **depan + tengah + belakang** menjadi satu file PDF final.
- Otomatis melewatkan file yang tidak tersedia tanpa error.

---

## 📦 Struktur Folder

```
.
├── data_sertifikat.xlsx         # Data peserta sertifikat
├── depan_output/                # Output sertifikat depan
├── tengah_output/               # Output sertifikat tengah
├── belakang_output/             # Output sertifikat belakang (dengan tabel)
├── final_output/                # Output sertifikat final (gabungan semua halaman)
├── background/                  # Folder berisi background image untuk masing-masing jabatan
├── fonts/                       # Folder font (seperti Poppins)
├── sertifikat_generator.py      # Main program Python
└── README.md                    # Dokumentasi project ini
```

---

## 📥 Installasi

1. Pastikan Python 3.8+ sudah terinstall di komputer kamu.
2. Install library yang dibutuhkan:

```bash
pip install pandas fpdf openpyxl Pillow PyPDF2
```

---

## 🛠️ Cara Pakai

1. **Siapkan data Excel**  
   Format kolom minimal:
   - `Nama`
   - `Jabatan`
   - `Acara`
   - `Kepanitiaan`

2. **Siapkan background gambar**  
   Untuk masing-masing jabatan seperti:
   - `tengah_ketua_umum.png`
   - `tengah_wakil_ketua_1.png`
   - `tengah_anggota.png` (jika perlu)
   
3. **Jalankan script**  
   Script ini akan:
   - Membuat file belakang (`sertifikat belakang`) berisi tabel.
   - Membuat file tengah berdasarkan jabatan.
   - Menggabungkan file depan + tengah + belakang menjadi 1 PDF final.

```bash
python sertifikat_generator.py
```

4. **Hasil akhir ada di folder `final_output/`.**

---

## 🧠 Catatan Penting

- **Mapping Jabatan**: Pastikan jabatan di Excel sesuai dengan daftar yang sudah didefinisikan. Jika jabatan tidak dikenal, sertifikat tidak akan dibuat.
- **File Background**: Pastikan semua background image tersedia di path yang benar.
- **Auto Skip**: Kalau file tengah atau belakang tidak ditemukan, sertifikat tetap dibuat menggunakan file yang tersedia.
- **PDF Layout**: Ukuran background diambil otomatis dari ukuran file gambar, lalu dikonversi ke ukuran mm untuk PDF.

---

## 📋 Contoh Mapping Jabatan

```python
jabatan_background_mapping = {
    "Ketua Umum": "tengah_ketua_umum.png",
    "Wakil Ketua I": "tengah_wakil_ketua_1.png",
    "Wakil Ketua II": "tengah_wakil_ketua_2.png",
    "Sekretaris Umum": "tengah_sekretaris_umum.png",
    "Wakil Sekretaris Umum": "tengah_wakil_sekretaris_umum.png",
    "Bendahara Umum": "tengah_bendahara_umum.png",
    "Wakil Bendahara Umum": "tengah_wakil_bendahara_umum.png",
    "Ketua Departemen": "tengah_ketua_departemen.png",
    "Wakil Ketua Departemen": "tengah_wakil_ketua_departemen.png",
    "Sekretaris Departemen": "tengah_sekretaris_departemen.png",
    "Anggota": "tengah_anggota.png"  # Optional tambahan
}
```

---

## ❓ FAQ

**Q: Bagaimana jika nama file mengandung karakter aneh seperti `/` atau `\`?**  
**A:** Script otomatis mengganti karakter berbahaya dengan tanda `-` agar aman di semua OS.

**Q: Bagaimana kalau hanya ada background depan saja?**  
**A:** File sertifikat tetap dibuat hanya dengan halaman depan.

**Q: Apakah mendukung custom font?**  
**A:** Ya, cukup tambahkan font `.ttf` di folder `fonts/` dan load di script.

---

## 🤝 Kontribusi

Kalau mau tambah fitur baru atau memperbaiki, feel free untuk fork dan pull request ya! 🚀  
Atau hubungi saya lewat issues.

---

## 📜 License

Project ini open-source dan bebas digunakan untuk keperluan organisasi, event, atau pribadi.

---

# 🚀 Selamat Mencoba dan Semoga Membantu!
