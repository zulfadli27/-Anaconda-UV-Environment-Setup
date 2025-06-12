Berikut adalah panduan lengkap **setup Anaconda** dan **virtual environment menggunakan `uv`** (Ultra Rapid Virtualenv) — tool modern pengganti `pip`/`venv`, untuk semua platform (Windows/MacOS/Linux).

---

## ✅ 1. Install Anaconda

### 🔹 Windows / MacOS / Linux:

1. Unduh Anaconda dari [https://www.anaconda.com/products/distribution](https://www.anaconda.com/products/distribution)
2. Ikuti proses instalasi sesuai OS.
3. Setelah selesai, buka terminal:

   * **Windows**: buka **Anaconda Prompt**
   * **MacOS/Linux**: buka **Terminal**

Untuk cek bahwa Python dari Anaconda sudah aktif:

```bash
python --version
# Output: Python 3.xx.x (Anaconda)
```

---

## ✅ 2. Install `uv` (Modern Dependency + Virtual Environment Manager)

### 🔸 Gunakan `curl`:

```bash
curl -Ls https://astral.sh/uv/install.sh | bash
```

### 🔸 Atau via `cargo` (jika sudah punya Rust):

```bash
cargo install uv
```

> Pastikan folder `~/.cargo/bin` (atau lokasi instalasi `uv`) sudah masuk PATH.

### 🔹 Cek apakah `uv` sudah terpasang:

```bash
uv --version
```

---

## ✅ 3. Setup Proyek dan Environment Virtual dengan `uv`

### 🔸 Buat folder proyek:

```bash
mkdir proyek-anaconda-uv
cd proyek-anaconda-uv
```

### 🔸 Inisialisasi virtual environment:

```bash
uv venv
```

Ini akan:

* Membuat `.venv/` folder
* Menyiapkan Python environment yang cepat dan ringan

---

## ✅ 4. Aktifkan Virtual Environment

### 🔹 Windows:

```bash
.\.venv\Scripts\activate
```

### 🔹 Linux/MacOS:

```bash
source .venv/bin/activate
```

> Prompt akan berubah menandakan environment aktif.

---

## ✅ 5. Install Paket (Lebih Cepat dari pip)

Contoh:

```bash
uv pip install numpy pandas matplotlib
```

### 🔹 Simpan dependensi:

```bash
uv pip freeze > requirements.txt
```

---

## ✅ 6. Menonaktifkan Virtual Environment

```bash
deactivate
```

---

## 🔁 Bonus: Gunakan `pyproject.toml` (opsional)

Jika kamu ingin memakai standar `pyproject.toml` (seperti Poetry):

```bash
uv pip install flask
uv sync  # install semua dari pyproject.toml secara otomatis
```

---

## 🔚 Ringkasan

| Tool     | Fungsi                                     |
| -------- | ------------------------------------------ |
| Anaconda | Distribusi Python lengkap                  |
| `uv`     | Pengganti pip + venv super cepat           |
| `.venv/` | Folder virtual environment                 |
| `uv pip` | Install dependency dengan kecepatan tinggi |

---

Kalau kamu ingin template proyek `Anaconda + uv` atau integrasi dengan Jupyter Notebook, Data Science, atau Web Dev (Flask/FastAPI), tinggal bilang ya!
