<div align="center">

<img src="https://img.shields.io/badge/Platform-XiaoMi%20MiMo-orange?style=for-the-badge&logo=xiaomi&logoColor=white"/>
<img src="https://img.shields.io/badge/Node.js-v18+-green?style=for-the-badge&logo=node.js&logoColor=white"/>
<img src="https://img.shields.io/badge/Playwright-Automation-blue?style=for-the-badge&logo=playwright&logoColor=white"/>
<img src="https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge"/>

```
  __  __ _ __  __       ___          _    _            
 |  \/  (_)  \/  |___  | _ \___ __ _(_)__| |_ ___ _ _ 
 | |\/| | | |\/| / _ \ |   / -_) _` | (_-<  _/ -_) '_|
 |_|  |_|_|_|  |_\___/ |_|_\___\__, |_/__/\__\___|_|  
                                |___/                   
```

# 🤖 MiMo Register Bot — XiaoMi MiMo Platform

### ⚡ Auto Register + API Key Extractor | Multi-Worker | Smart Resume

</div>

---

## 💥 HARGA SPESIAL — TERBATAS!

<div align="center">

> ### ~~Rp 250.000~~
> ## 🔥 **Rp 50.000** 🔥
> ### Harga khusus untuk **user tercepat!**
> ⚠️ *Slot terbatas — habis, harga kembali normal!*

**💬 Order sekarang via Telegram:**

[![Telegram](https://img.shields.io/badge/Telegram-Order%20Sekarang-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/indocafe1992)

### 👉 [https://t.me/indocafe1992](https://t.me/indocafe1992)

</div>

---

## 📸 Preview

<img width="749" height="367" alt="preview" src="https://github.com/user-attachments/assets/29e06e4b-9796-4eb0-beca-e7e9ebf2e83b" />



> *Dashboard real-time dengan multi-worker, progress tracker, dan smart resume system*

---

## ✨ Fitur Unggulan

| Fitur | Keterangan |
|---|---|
| 🤖 **Auto Register** | Register akun XiaoMi MiMo secara otomatis via Google OAuth |
| 🔑 **Auto API Key** | Buat & ekstrak API Key langsung setelah register berhasil |
| 👥 **Multi-Worker** | Jalankan beberapa akun secara paralel (hemat waktu!) |
| 📋 **Smart Resume** | Otomatis skip akun yang sudah berhasil — aman restart kapan saja |
| 🔗 **Auto Ref Bind** | Bind referral code otomatis setelah register |
| 📊 **Live Dashboard** | Progress real-time dengan spinner animasi di console |
| 💾 **Dual Output** | Simpan ke `results.txt` (email\|apiKey) & `apikeys.txt` (key saja) |
| 🛡️ **Anti-Bot Bypass** | Stealth mode dengan Chrome asli, bukan Chromium bawaan Playwright |

---

## 🚀 Quick Start

### 1. Install Dependencies

```bash
npm install
```

### 2. Install Playwright Browser

```bash
npx playwright install chromium
```

### 3. Siapkan File Input

Buat file `dataInput.txt`, isi satu email per baris:

```
user1@gmail.com
user2@gmail.com
user3@gmail.com
```

### 4. Jalankan Bot

```bash
node index
```

Bot akan menanyakan:
- 🔐 Google password (disembunyikan dengan `*`)
- 👁️ Mode browser (y = visible / n = headless)
- 👥 Jumlah worker paralel
- 🔗 Referral code (opsional)

---

## 📂 Struktur File

```
mimoRegister-Bot/
├── index.js          # 🤖 Script utama (tidak disertakan di repo ini)
├── dataInput.txt     # 📧 List email yang akan didaftarkan
├── results.txt       # ✅ Tracking: email|apiKey (auto-generated)
├── apikeys.txt       # 🔑 Kumpulan API Key hasil register
└── package.json      # 📦 Dependencies
```

---

## ⚙️ Cara Kerja

```
┌─────────────────────────────────────────────────────┐
│  1. Baca dataInput.txt  →  List semua email         │
│  2. Cek results.txt     →  Skip yang sudah selesai  │
│  3. Proses pending      →  Multi-worker paralel     │
│                                                     │
│     Per akun:                                       │
│     ├── Buka MiMo Platform                         │
│     ├── Klik "Sign in with Google"                  │
│     ├── Input email & password Google               │
│     ├── Handle redirect Xiaomi Account              │
│     ├── Register / Login akun Xiaomi                │
│     ├── Buat API Key via API                        │
│     ├── Bind referral code (jika ada)               │
│     └── Simpan ke results.txt & apikeys.txt         │
└─────────────────────────────────────────────────────┘
```

---

## 💡 Smart Resume System

Berbeda dari bot biasa yang **reset dari awal** setiap kali dijalankan, bot ini memiliki sistem **Smart Resume**:

- ✅ Akun yang **sudah berhasil** → otomatis **di-skip**
- 🔄 Akun yang **gagal** → otomatis **di-retry** di run berikutnya
- 📁 Data tersimpan permanen di `results.txt`
- 🚀 **Aman restart kapan saja** — tidak ada data yang hilang!

---

## 📊 Format Output

**`results.txt`** — Tracking lengkap (email + API Key):
```
user1@gmail.com|sk-ab1234567890abcdef
user2@gmail.com|sk-xy9876543210xyzabc
```

**`apikeys.txt`** — Kumpulan API Key saja (siap pakai):
```
sk-ab1234567890abcdef
sk-xy9876543210xyzabc
```

---

## 📦 Dependencies

| Package | Versi | Fungsi |
|---|---|---|
| `playwright` | ^1.61.1 | Browser automation |
| `picocolors` | ^1.1.1 | Warna console |
| `figlet` | ^1.11.0 | ASCII art banner |
| `readline-sync` | ^1.4.10 | Input terminal interaktif |

---

## ❓ FAQ

**Q: Apakah bot ini aman?**  
A: Bot menggunakan Chrome asli (bukan headless) dengan mode off-screen, sehingga lebih sulit terdeteksi sebagai bot.

**Q: Berapa batas maksimal worker?**  
A: Disarankan 1–3 worker. Lebih dari 3 bisa memperlambat atau trigger rate-limit Google.

**Q: Apa yang terjadi jika bot dihentikan di tengah proses?**  
A: Tidak ada masalah! Smart Resume System akan melanjutkan dari akun yang belum selesai.

**Q: Apakah bisa digunakan di Linux/Mac?**  
A: Ya, bot mendukung Windows, Linux, dan macOS.

---

## 💬 Order & Support

<div align="center">

Dapatkan script lengkap sebelum kehabisan slot harga spesial!

[![Telegram](https://img.shields.io/badge/💬%20Telegram-@indocafe1992-2CA5E0?style=for-the-badge&logo=telegram)](https://t.me/indocafe1992)

### 📲 Admin: [https://t.me/indocafe1992](https://t.me/indocafe1992)

> **💰 Harga: ~~Rp 250.000~~ → Rp 50.000**  
> *Harga khusus untuk user tercepat — sangat terbatas!*

</div>

---

<div align="center">

Made with ❤️ by **Z3R0 0N3 ID**  
⭐ Jangan lupa **Star** repo ini jika bermanfaat!

</div>
