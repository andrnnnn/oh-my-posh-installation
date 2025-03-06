# Panduan Instalasi dan Konfigurasi Oh My Posh di Git Bash & VS Code

## 📌 1. Instalasi Oh My Posh

Oh My Posh adalah prompt yang dapat dikustomisasi untuk terminal, seperti Git Bash dan VS Code Terminal.

### 🔹 Langkah 1: Unduh dan Instal Oh My Posh

1. Buka **PowerShell** sebagai Administrator.
2. Jalankan perintah berikut untuk mengunduh dan menginstal Oh My Posh:
   ```powershell
   winget install JanDeDobbeleer.OhMyPosh -s winget
   ```
3. Setelah instalasi selesai, verifikasi versi dengan perintah:
   ```powershell
   oh-my-posh --version
   ```
   Jika instalasi berhasil, akan muncul versi Oh My Posh yang terinstal.

---

## 📌 2. Menemukan Lokasi Oh My Posh

Setelah instalasi, cari lokasi file eksekusi Oh My Posh dengan perintah berikut di **Command Prompt (CMD):**

```cmd
where oh-my-posh
```

Biasanya, lokasi default adalah:

```
C:\Users\[Username]\AppData\Local\Programs\oh-my-posh\bin\oh-my-posh.exe
```

---

## 📌 3. Menambahkan Oh My Posh ke Git Bash

### 🔹 Langkah 1: Export Path Oh My Posh

Agar Git Bash dapat mengenali **Oh My Posh**, kita perlu menambahkan lokasinya ke dalam **PATH**.

1. Buka Git Bash dan jalankan perintah berikut untuk menambahkan **Oh My Posh** ke **PATH** secara sementara:
   ```bash
   export PATH="$PATH:/c/Users/[Username]/AppData/Local/Programs/oh-my-posh/bin"
   ```
   Gantilah `[Username]` dengan nama pengguna di komputer Anda.
2. Untuk menjadikannya permanen, tambahkan perintah ini ke **`.bashrc`**:
   ```bash
   echo 'export PATH="$PATH:/c/Users/[Username]/AppData/Local/Programs/oh-my-posh/bin"' >> ~/.bashrc
   ```

### 🔹 Langkah 2: Edit File `.bashrc`

Untuk menggunakan Oh My Posh setiap kali membuka Git Bash, kita perlu menambahkan konfigurasinya ke file **`.bashrc`**.

1. Buka Git Bash, lalu jalankan perintah berikut untuk mengedit `.bashrc` dengan **Nano**:
   ```bash
   nano ~/.bashrc
   ```
2. Tambahkan baris berikut di bagian paling bawah:
   ```bash
   export PATH=$PATH:/c/Users/Lenovo/AppData/Local/Programs/oh-my-posh/bin
   eval "$(oh-my-posh init bash --config 'C:/Users/Lenovo/AppData/Local/Programs/oh-my-posh/themes/atomic.omp.json')"
   ```
3. Simpan perubahan:
   - Tekan **`Ctrl + X`**, lalu **`Y`**, lalu **`Enter`**.

### 🔹 Langkah 3: Terapkan Perubahan

Untuk menerapkan perubahan tanpa harus restart terminal, jalankan:

```bash
source ~/.bashrc
```

Sekarang tampilan Git Bash Anda seharusnya sudah berubah sesuai tema yang dipilih.

---

## 📌 4. Menginstal dan Menggunakan Nerd Fonts

Oh My Posh menggunakan **Nerd Fonts** untuk menampilkan ikon dengan benar.

### 🔹 Langkah 1: Unduh dan Instal Nerd Fonts

1. Kunjungi [Nerd Fonts](https://www.nerdfonts.com/)
2. Pilih font seperti **FiraCode Nerd Font** atau **Cascadia Code Nerd Font**.
3. Unduh dan instal font di komputer Anda.

### 🔹 Langkah 2: Mengatur Font di Git Bash

1. Buka **Git Bash**.
2. Klik kanan pada jendela Git Bash → **Options**.
3. Pilih **Text** → **Font**, lalu pilih **Nerd Font** yang telah diinstal.
4. Klik **Apply**, lalu **Save**.

---

## 📌 5. Mengatur Oh My Posh di VS Code

1. Buka **VS Code**.
2. Tekan **`Ctrl + ,`** untuk membuka **Settings**.
3. Cari **`terminal.integrated.fontFamily`**.
4. Klik **Edit in settings.json**, lalu tambahkan baris berikut:
   ```json
   "terminal.integrated.fontFamily": "nama-font",
   ```
   (Ganti dengan nama font Nerd Font yang telah diinstal jika berbeda)
5. Simpan dan restart **VS Code**.

---

## 📌 6. Mengubah Tema Oh My Posh

Untuk mengubah tema, edit **`.bashrc`** dan ganti bagian ini:

```bash
export PATH=$PATH:/c/Users/Lenovo/AppData/Local/Programs/oh-my-posh/bin
eval "$(oh-my-posh init bash --config 'C:/Users/Lenovo/AppData/Local/Programs/oh-my-posh/themes/nama-tema.omp.json')"
```

Lalu, jalankan:

```bash
source ~/.bashrc
```

Sekarang, tampilan terminal akan berubah sesuai tema yang dipilih.

---

## 🎉 Selesai!

Sekarang **Oh My Posh** sudah terpasang di **Git Bash** dan **VS Code** dengan tema dan font yang sesuai. 🚀

