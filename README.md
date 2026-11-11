# KerjaanGambarSEI

Repository **private** untuk menyimpan dan mengelola file CAD beserta seluruh lampiran/referensinya.

## Struktur folder

| Folder | Isi |
|---|---|
| `00_Projects` | Semua File Projects &  |
| `02_Template` | Semua Template 2D & 3D |

### Subfolder Projects

Untuk menjaga kerapian, setiap project di dalam `00_Projects` disarankan menggunakan standar subfolder berikut:

| Subfolder | Isi |
|---|---|
| `01_Xref` | Gambar referensi dasar, peta kontur, atau *base plan* yang di-Xref ke file utama. |
| `02_DED` | *Detailed Engineering Design* (file AutoCAD `.dwg` utama). |
| `03_Datasheet` | Dokumen spesifikasi teknis, brosur alat, dan manual operasional (PDF/PPTX). |
| `04_3D_Models` | Pemodelan 3D dan file *render* (SketchUp `.skp`, `.skb`, dan `.jpg`). |
| `05_PDF` | PDF Hasil dari DeD. |
| `06_ETC` | Dokumentasi drone dll |

## Aturan penamaan file

Gunakan pola:

`[NUMBER]_[SEI Code]_[DRAWING-TYPE]_REV[XX].[ext]`

Contoh:

- `01_Q-0000-26_SLO_REV00.dwg`

Hindari nama seperti `final.dwg`, `final_baru.dwg`, atau `fix_terakhir.dwg`.
Naikkan nomor revisi ketika ada perubahan yang perlu dilacak.

## Cara menyimpan XREF

1. Simpan file gambar utama di folder yang sesuai.
2. Simpan semua file referensi eksternal di dalam `03_XREF/`.
3. Atur path XREF menjadi **relative path** bila memungkinkan.
4. Jangan mengganti nama atau memindahkan file XREF tanpa memperbarui referensinya.
5. Sebelum commit, buka gambar utama dan pastikan semua XREF, image reference, dan font tampil benar.

## Alur kerja yang disarankan

1. Buat folder proyek atau area kerja di folder yang sesuai.
2. Simpan file sumber CAD dan seluruh lampirannya.
3. Periksa XREF, font, plot style, dan hasil PDF.
4. Commit dengan pesan yang menjelaskan perubahan.
5. Push ke GitHub setelah pekerjaan tersimpan dan tervalidasi.

Contoh pesan commit:

- `Add: SEI roof PV layout REV00`
- `Update: cable route drawing REV01`
- `Fix: relative XREF paths`
- `Archive: superseded drawing REV00`

## Catatan file besar

Repository ini menggunakan Git LFS untuk tipe file CAD dan aset biner tertentu. Setelah Git LFS terpasang, jalankan:

```bash
git lfs install
```

Periksa status pelacakan dengan:

```bash
git lfs track
git lfs ls-files
```

Jangan memasukkan file sementara, backup otomatis, atau lock file CAD ke repository. Aturan pengecualiannya tersedia di `.gitignore`.

## Catatan keamanan dan lisensi

- Repository dibuat **Private**. Tetap hindari menyimpan password, token, private key, atau kredensial.
- Pastikan Anda memiliki hak untuk menyimpan dan membagikan datasheet, font, block, serta dokumen pihak ketiga.
- Private repository bukan pengganti backup terpisah. Simpan salinan cadangan untuk file proyek penting.
