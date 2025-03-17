# ZINC Data Downloader & Processor

Modul ini memungkinkan pengguna untuk mengunduh dan memproses file dari ZINC database dalam berbagai format seperti SDF, MOL2, PDBQT, dan SMI.

## Fitur Utama
- Mengunduh file dari ZINC database secara otomatis
- Mengekstrak file terkompresi `.gz`
- Mengonversi file `.smi` menjadi `.csv`
- Menggunakan `ProcessPoolExecutor` untuk pemrosesan paralel
- Mengelompokkan file berdasarkan formatnya

## Instalasi
Pastikan Anda memiliki Python 3.x dan pustaka yang diperlukan telah terinstal. Anda dapat menginstalnya dengan perintah berikut:

```sh
pip install requests pandas
```

## Cara Penggunaan

### 1. Mengunduh dan Mengekstrak File 3D dari ZINC

Simpan daftar URL file ZINC 3D dalam sebuah file teks (misalnya, `zinc_3d_urls.txt`).
Kemudian jalankan skrip berikut:

```python
from your_module import zinc_process_3d_files

zinc_process_3d_files("zinc_3d_urls.txt")
```

**Output:**
- Folder `data_zinc_sdf/` berisi file `.sdf`
- Folder `data_zinc_mol2/` berisi file `.mol2`
- Folder `data_zinc_pdbqt/` berisi file `.pdbqt`

### 2. Mengunduh dan Mengonversi File SMILES dari ZINC

Simpan daftar URL file `.smi` dalam sebuah file teks (misalnya, `zinc_smi_urls.txt`).
Kemudian jalankan:

```python
from your_module import zinc_process_smi_files

zinc_process_smi_files("zinc_smi_urls.txt")
```

**Output:**
- Semua file `.smi` dikonversi ke `.csv`
- File gabungan: `data_zinc_smiles.csv`

## Struktur Direktori
```
.
├── data_zinc_sdf/     # File SDF
├── data_zinc_mol2/    # File MOL2
├── data_zinc_pdbqt/   # File PDBQT
├── zinc_out/          # Folder sementara untuk SMI
└── data_zinc_smiles.csv  # Output gabungan dari SMI
```

## Lisensi
Proyek ini dirilis di bawah lisensi MIT.

