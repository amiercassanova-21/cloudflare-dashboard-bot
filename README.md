<div align="center">

# ☁️ Cloudflare Dashboard Telegram Bot
### Automated Multi-Domain & Cloudflare Infrastructure Management via Telegram

[![GitHub Repository](https://img.shields.io/badge/Repository-amiercassanova--21%2Fcloudflare--dashboard--bot-38bdf8?style=for-the-badge&logo=github&logoColor=white)](https://github.com/amiercassanova-21/cloudflare-dashboard-bot)
[![Engine Version](https://img.shields.io/badge/Cloudflare_API-v4-f97316?style=for-the-badge&logo=cloudflare&logoColor=white)](https://dash.cloudflare.com/)
[![Telegram Contact](https://img.shields.io/badge/Telegram-@kang__rebahan-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/kang_rebahan)
[![WhatsApp Contact](https://img.shields.io/badge/WhatsApp-Chat_Owner-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](https://wa.link/3yhb8f)

<p align="center">
  <b>Bot Telegram Interaktif untuk Mengelola DNS Record, Proxy Toggle, Purge Cache, dan Keamanan Cloudflare Secara Real-Time Tanpa Buka Browser.</b>
</p>

---

</div>

## 📌 Tentang Proyek

**Cloudflare Dashboard Telegram Bot** adalah solusi manajemen infrastruktur Cloudflare berbasis Bot Telegram yang memungkinkan administrator web dan pengelola server mengontrol seluruh domain, *DNS Records*, *Security Level*, serta *Cache Status* langsung dari genggaman tangan.

Dengan bot ini, Anda tidak perlu lagi *login* ke dashboard web Cloudflare yang lambat saat berada di perangkat seluler. Cukup gunakan perintah instan atau menu tombol interaktif (*inline keyboard*) di Telegram untuk melakukan pembaruan DNS, mengaktifkan proteksi *Under Attack Mode*, hingga menghapus *cache* secara instan.

🌐 **GitHub Repository:** [https://github.com/amiercassanova-21/cloudflare-dashboard-bot](https://github.com/amiercassanova-21/cloudflare-dashboard-bot)

---

## ✨ Fitur Unggulan

- 🌐 **Manajemen DNS Lengkap (A, AAAA, CNAME, TXT, MX)**: Tambah, edit, hapus, dan tampilkan seluruh *DNS Record* domain dengan cepat.
- 🟠 **Toggle Proxy Status (Orange / Grey Cloud)**: Aktifkan atau matikan proteksi Proxy Cloudflare (`CDN / WAF`) pada *record* DNS hanya dengan 1 klik.
- 🚀 **Purge Cache Instan**: Hapus seluruh *cache* domain (*Purge Everything*) atau URL spesifik saat pembaruan situs web.
- 🛡️ **Proteksi Keamanan Fast-Switch**: 
  - Toggle **Under Attack Mode** saat server mengalami serangan DDoS.
  - Pengaturan *Security Level* (Essentially Off, Low, Medium, High, I'm Under Attack).
  - Toggle **Development Mode** secara instan.
- 🔐 **Whitelisting & Hak Akses Terproteksi**: Bot dilengkapi dengan pengamanan `Allowed Chat IDs` sehingga hanya ID Telegram terdaftar yang dapat mengeksekusi perintah.
- 📊 **Monitoring Telemetri Zone & Domain Status**: Cek status SSL/TLS, kuota domain, dan kesehatan *Zone* Cloudflare secara *real-time*.
- 📱 **Interface Inline Keyboard Ergonomis**: Navigasi menu menggunakan tombol interaktif Telegram yang responsif di HP maupun PC.

---

## 🛰️ Arsitektur Integrasi

```
+------------------+         Encrypted Bot API         +---------------------------+
|                  | --------------------------------> |                           |
| Telegram Client  |                                   |  Cloudflare Dashboard Bot |
|  (Admin Device)  | <-------------------------------- |      (Node.js / Python)    |
+------------------+                                   +---------------------------+
                                                                     |
                                                                     | Cloudflare REST API v4
                                                                     v
                                                       +---------------------------+
                                                       |   Cloudflare Global Net   |
                                                       |  (DNS, Cache, WAF, SSL)   |
                                                       +---------------------------+
```

---

## 🛠️ Persyaratan Sistem (Prerequisites)

Sebelum menjalankan bot, pastikan Anda telah menyiapkan:

1. **Node.js** v18+ atau **Python** 3.9+ (sesuai *stack* pengembang).
2. **Telegram Bot Token**: Dapatkan dari [@BotFather](https://t.me/BotFather) di Telegram.
3. **Cloudflare API Token**: Dapatkan dari Dashboard Cloudflare (`My Profile` -> `API Tokens`) dengan izin:
   - `Zone - DNS - Edit`
   - `Zone - Zone - Read`
   - `Zone - Cache Purge - Purge`
4. **Telegram User ID**: Dapatkan ID akun Telegram Anda dari [@userinfobot](https://t.me/userinfobot) untuk pengamanan hak akses admin.

---

## 🚀 Cara Instalasi & Penggunaan

### 1. Clone Repository
```bash
git clone https://github.com/amiercassanova-21/cloudflare-dashboard-bot.git
cd cloudflare-dashboard-bot
```

### 2. Install Dependensi
```bash
# Untuk Node.js
npm install

# Atau jika menggunakan Python
pip install -r requirements.txt
```

### 3. Konfigurasi Environment Variables (`.env`)
Buat file `.env` di direktori utama dan isi kredensial Anda:

```env
# Telegram Configuration
TELEGRAM_BOT_TOKEN=1234567890:ABCdefGHIjklMNOpqrsTUVwxyZ
ALLOWED_CHAT_IDS=123456789,987654321

# Cloudflare API Configuration
CF_API_TOKEN=your_cloudflare_api_token_here
CF_ACCOUNT_ID=your_cloudflare_account_id_here
```

### 4. Jalankan Bot
```bash
# Untuk Node.js
npm start

# Untuk Python
python bot.py
```

---

## 📋 Daftar Perintah Telegram Bot (`Commands`)

| Perintah | Fungsi / Keterangan |
| :--- | :--- |
| `/start` | Membuka menu utama & navigasi interaktif |
| `/domains` | Menampilkan daftar seluruh domain (*Zones*) yang terhubung |
| `/dns <domain>` | Menampilkan seluruh *DNS Records* dari domain target |
| `/adddns` | Panduan interaktif menambahkan A / AAAA / CNAME / TXT record |
| `/deldns` | Hapus record DNS tertentu berdasarkan ID / nama |
| `/toggleproxy` | Ubah status CDN Cloudflare (Proxied 🟠 / DNS Only ⚪) |
| `/purgecache` | Hapus seluruh *cache* atau *single URL cache* domain |
| `/underattack` | Aktifkan / matikan *I'm Under Attack Mode* |
| `/help` | Menampilkan panduan bantuan dan fitur bot |

---

## 👤 Pemilik & Pengembang

Dikembangkan dan dipelihara secara independen oleh **amiercassanova**.

- 🐙 **GitHub Repository:** [amiercassanova-21/cloudflare-dashboard-bot](https://github.com/amiercassanova-21/cloudflare-dashboard-bot)
- 💬 **Telegram:** [@kang_rebahan](https://t.me/kang_rebahan)
- 📱 **WhatsApp:** [Hubungi Pengembang](https://wa.link/3yhb8f)

---

<div align="center">
  <sub>Developed with ❤️ by <b>amiercassanova</b> • Powered by Cloudflare API v4 & Telegram Bot API</sub>
</div>