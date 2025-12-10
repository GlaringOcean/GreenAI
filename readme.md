# Panduan Instalasi & Menjalankan Model YOLOv8 (Green AI Project)



**Project:** Comparative Study of Green AI Models (YOLOv8 — Pruning, Distillation, Quantization)  

**Tujuan:** Menyiapkan environment, menginstal seluruh dependensi, melakukan verifikasi GPU, dan menjalankan kode di VS Code.



Ikuti langkah-langkah di bawah ini **secara berurutan**.



---



## 1. Persiapan Awal (Wajib)



Pastikan dua software berikut sudah terinstal di laptop Anda:



1. **Python (Versi 3.10 atau 3.12)**

   - Download: https://www.python.org/downloads/

   - Saat instalasi, **WAJIB** centang opsi: **“Add Python to PATH”**.



2. **Visual Studio Code (VS Code)**

   - Download: https://code.visualstudio.com/



---



## 2. Membuat Virtual Environment (Ruang Kerja Terisolasi)



Kita akan membuat environment khusus agar pustaka proyek ini tidak mengganggu proyek lain.



1. Buka **folder proyek** ini menggunakan VS Code.

2. Buka **Terminal**:

   - Menu **Terminal** → **New Terminal**.

3. Jalankan perintah berikut untuk membuat environment:



   ```bash

   python -m venv yolov8_lpr_env

Setelah berhasil, akan muncul folder baru bernama `yolov8_lpr_env` di panel kiri VS Code.



---



## 4. Mengaktifkan Virtual Environment



Aktifkan environment yang sudah dibuat agar semua instalasi berjalan terisolasi.



### Windows

```bash

.\yolov8_lpr_env\Scripts\activate

```



### macOS / Linux

```bash

source yolov8_lpr_env/bin/activate

```



## 5. Instalasi PyTorch



PyTorch adalah komponen inti untuk menjalankan model YOLOv8 dan seluruh eksperimen Green AI (pruning, distillation, quantization).  

Anda **HARUS** memilih salah satu opsi instalasi sesuai dengan spesifikasi perangkat Anda.



> **PENTING:** Perintah instalasi PyTorch dapat berubah mengikuti update versi.  

> Selalu cek perintah terbaru di situs resmi:  

> https://pytorch.org/get-started/locally/



---



### OPSI A — Jika Laptop/PC Anda Punya GPU NVIDIA (DISARANKAN)



Gunakan opsi ini jika perangkat Anda menggunakan GPU NVIDIA (misalnya: GTX 1650, RTX 3050, RTX 4060, dsb).  

Training YOLOv8 akan jauh lebih cepat dan lebih efisien energi.



#### Langkah-langkah:

1. Buka halaman resmi PyTorch:  

   https://pytorch.org/get-started/locally/



2. Konfigurasikan pilihan berikut:

   - **Package:** `pip`

   - **Language:** `Python`

   - **Compute Platform:** CUDA sesuai rekomendasi (misal: CUDA 11.8)



3. Salin *perintah instalasi* yang muncul dari website, lalu jalankan di terminal environment Anda.  

   Contoh format (*jangan copy tanpa memastikan di website PyTorch*):



```bash

pip install --pre torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118

```



### OPSI B — Jika Tidak Punya GPU NVIDIA (CPU Only)



Gunakan opsi ini jika perangkat Anda tidak memiliki GPU NVIDIA, seperti:

- Intel HD Graphics

- AMD Radeon tanpa CUDA

- MacBook (Intel / Apple Silicon)



Jalankan perintah berikut di terminal environment:



```bash

pip install torch torchvision torchaudio

```

Jika instalasi berhasil, lanjutkan ke langkah berikutnya.



## 6. Instalasi Library Tambahan (requirements.txt)



Setelah PyTorch berhasil diinstal, langkah berikutnya adalah memasang seluruh library tambahan yang digunakan dalam proyek ini, seperti:



- **YOLOv8 (ultralytics)**

- **OpenCV**

- **NumPy**

- **Matplotlib**

- **Pandas**

- Dan library pendukung lainnya



Seluruh daftar library sudah disiapkan dalam file:

```bash

requirements.txt

```



### Cara Menjalankan Instalasi (Wajib)



Pastikan Anda sudah berada di dalam folder proyek yang berisi file `requirements.txt`, dan **environment sudah aktif**.



### 1️⃣ Aktifkan environment terlebih dahulu



#### Windows

```bash

.\yolov8_lpr_env\Scripts\activate

```

###### macOS / Linux

```bash

source yolov8_lpr_env/bin/activate

```



# =========================================================

# 6. INSTALASI LIBRARY TAMBAHAN (requirements.txt)

# Semua penjelasan ada di dalam komentar terminal (#)

# =========================================================



# ---------------------------------------------------------

# 1️⃣ AKTIFKAN VIRTUAL ENVIRONMENT

# Pastikan environment aktif SEBELUM menjalankan instalasi.

# Jika environment tidak aktif, instalasi akan gagal.

# ---------------------------------------------------------



# Windows:

.\yolov8_lpr_env\Scripts\activate



# macOS / Linux:

source yolov8_lpr_env/bin/activate





# ---------------------------------------------------------

# 2️⃣ INSTALL REQUIREMENTS

# Perintah berikut membaca file requirements.txt dan

# menginstal semua library seperti ultralytics, numpy, opencv, dll.

# ---------------------------------------------------------



pip install -r requirements.txt





# ---------------------------------------------------------

# ⚠️ 3️⃣ JIKA TERJADI ERROR SAAT INSTALL REQUIREMENTS

# Biasanya error muncul karena:

# - versi pip terlalu lama

# - build wheel gagal

# - dependency tidak kompatibel

#

# Solusi: upgrade pip, setuptools, dan wheel

# ---------------------------------------------------------



python -m pip install --upgrade pip setuptools wheel





# ---------------------------------------------------------

# 4️⃣ PASTIKAN ENVIRONMENT MASIH AKTIF

# Setelah upgrade pip, environment kadang otomatis tertutup.

# Pastikan ada prefix: (yolov8_lpr_env)

# Jika tidak muncul, aktifkan ulang menggunakan:

# ---------------------------------------------------------



# Windows:

.\yolov8_lpr_env\Scripts\activate



# macOS / Linux:

source yolov8_lpr_env/bin/activate





# ---------------------------------------------------------

# 5️⃣ JALANKAN ULANG INSTALL REQUIREMENTS

# Setelah memastikan pip sudah di-upgrade dan environment aktif,

# jalankan kembali instalasi. Biasanya error hilang setelah langkah ini.

# ---------------------------------------------------------



pip install -r requirements.txt





# ---------------------------------------------------------

# 6️⃣ VERIFIKASI INSTALASI

# Perintah berikut menampilkan semua library yang terinstal.

# Pastikan ultralytics, numpy, opencv-python, dan lainnya muncul.

# ---------------------------------------------------------



pip list
