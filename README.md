# ZINC Data Downloader and Processor

## Deskripsi
Modul ini digunakan untuk mengunduh, mengekstrak, dan memproses file data dari ZINC database, termasuk format **SMILES** dan **3D molecular structures** seperti **SDF, MOL2, dan PDBQT**. Modul ini mendukung pemrosesan paralel menggunakan `ProcessPoolExecutor` untuk meningkatkan efisiensi.

## Fitur
- **Mengunduh file SMILES dan mengonversinya ke CSV**
- **Mengunduh dan mengekstrak file 3D molecular structures dalam format SDF, MOL2, dan PDBQT**
- **Pemrosesan data dalam mode paralel** untuk meningkatkan kecepatan
- **Pengelolaan file secara otomatis** termasuk penghapusan file yang tidak diperlukan setelah pemrosesan

## Instalasi
Modul ini memerlukan Python 3 dan beberapa dependensi. Pastikan Anda menginstalnya terlebih dahulu dengan perintah berikut:

```bash
pip install requests pandas
```

## Penggunaan

### 1. Mengunduh dan Memproses File SMILES
Sediakan file teks (`.uri`) yang berisi daftar URL SMILES dari ZINC database. Lalu, jalankan:

```python
from module_name import zinc_process_smi_files

zinc_uri_smiles = 'zinc_smiles.uri'  # Ganti dengan path file URI yang sesuai
zinc_process_smi_files(zinc_uri_smiles)
```

Hasilnya akan disimpan dalam file `data_zinc_smiles.csv`.

### 2. Mengunduh dan Memproses File 3D Molecular Structures
Siapkan file `.uri` berisi daftar URL file ZINC 3D (SDF, MOL2, PDBQT). Kemudian jalankan:

```python
from module_name import zinc_process_3d_files

zinc_uri_3d = 'zinc_3d.uri'  # Ganti dengan path file URI yang sesuai
zinc_process_3d_files(zinc_uri_3d)
```

File yang diunduh akan diproses dan diekstrak ke folder `data_zinc_sdf`, `data_zinc_mol2`, dan `data_zinc_pdbqt` sesuai formatnya.

## Struktur Folder
Setelah menjalankan program, struktur folder akan seperti ini:

```
.
├── data_zinc_sdf/   # File SDF hasil ekstraksi
├── data_zinc_mol2/  # File MOL2 hasil ekstraksi
├── data_zinc_pdbqt/ # File PDBQT hasil ekstraksi
├── zinc_smiles.uri  # File daftar URL SMILES
├── zinc_3d.uri      # File daftar URL 3D
├── data_zinc_smiles.csv  # Hasil pengolahan data SMILES
```

## Catatan
- Pastikan URL yang digunakan valid dan dapat diakses.
- Gunakan koneksi internet yang stabil untuk menghindari error saat mengunduh data.

## Lisensi
Modul ini dirilis di bawah lisensi **MIT**.

