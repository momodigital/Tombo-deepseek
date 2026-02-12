# 🎤 DeepSeek TTS - Voice Assistant Bahasa Indonesia

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.8+-blue?logo=python" alt="Python">
  <img src="https://img.shields.io/badge/Flask-2.3.3-green?logo=flask" alt="Flask">
  <img src="https://img.shields.io/badge/DeepSeek-AI-orange" alt="DeepSeek">
  <img src="https://img.shields.io/badge/TTS-gTTS-brightgreen" alt="gTTS">
  <img src="https://img.shields.io/badge/Platform-Android%20%7C%20Linux%20%7C%20Windows-lightgrey" alt="Platform">
</p>

<p align="center">
  <b>✨ Asisten AI dengan suara Bahasa Indonesia, jalan di HP Android via Termux! ✨</b><br>
  <i>Khusus dioptimalkan untuk Samsung A02 (2GB RAM) sebagai server pribadi</i>
</p>

---

## 📋 **DAFTAR ISI**
- [Fitur Lengkap](#-fitur-lengkap)
- [Kebutuhan Sistem](#-kebutuhan-sistem)
- [Cara Install di HP Server (Samsung A02)](#-cara-install-di-hp-server-samsung-a02)
- [Cara Menjalankan Aplikasi](#-cara-menjalankan-aplikasi)
- [Cara Menggunakan Aplikasi (Panduan User)](#-cara-menggunakan-aplikasi-panduan-user)
- [Cara Remote Akses dari HP Lain](#-cara-remote-akses-dari-hp-lain)
- [Cara Membuat APK untuk Dibagikan](#-cara-membuat-apk-untuk-dibagikan)
- [Troubleshooting](#-troubleshooting)
- [Optimasi untuk Samsung A02](#-optimasi-untuk-samsung-a02)
- [Tanya Jawab](#-tanya-jawab)

---

## ✨ **FITUR LENGKAP**

### 🎯 **Fitur Utama**
| Fitur | Deskripsi | Cara Pakai |
|-------|-----------|------------|
| **🤖 Chat AI** | Tanya apa saja, AI jawab | Ketik teks atau bicara |
| **🎤 Voice Input** | Bicara langsung ke mic | Tekan tombol 🎤 |
| **🔊 Voice Output** | AI jawab dengan suara | Otomatis + bisa tekan 🔊 |
| **🇮🇩 Bahasa Indonesia** | 100% Bahasa Indonesia | Setting otomatis |
| **📱 Server di HP** | HP bekas jadi cloud | Pakai Termux |
| **🌐 Remote Akses** | Akses dari HP mana pun | Pakai Serveo/Ngrok |
| **📲 APK Installer** | Jadi app seperti biasa | Web2APK |

### 🎨 **Fitur Tampilan**
- ✅ UI seperti aplikasi chatting
- ✅ Bubble chat user (biru) dan AI (putih)
- ✅ Animasi mic saat merekam
- ✅ Animasi speaker saat bersuara
- ✅ Typing indicator (AI sedang mengetik)
- ✅ Responsif untuk semua layar HP

---

## 💻 **KEBUTUHAN SISTEM**

### **Untuk HP Server (Samsung A02)**
```

📱 Model: Samsung A02 (atau HP Android lain)
🧠 RAM: Minimal 2 GB (A02 = 2GB ✅)
💾 Storage: Minimal 500 MB free
🔋 Baterai: 5000 mAh (tahan 12-15 jam)
📶 Koneksi: WiFi / Paket data

```

### **Untuk HP User (Client)**
```

📱 Android 5.0 ke atas
💾 Storage: 20 MB (APK 5-8 MB + cache)
🌐 Koneksi internet
🎤 Mic (untuk voice input)
🔊 Speaker (untuk voice output)

```

---

## 🚀 **CARA INSTALL DI HP SERVER (SAMSUNG A02)**

### **📌 STEP 1: Install Termux**

```bash
1. Buka Chrome/ browser di HP A02
2. Kunjungi: https://f-droid.org
3. Download F-Droid.apk
4. Install F-Droid
5. Buka F-Droid, cari "Termux"
6. Install Termux (JANGAN dari Play Store!)
```

📸 Cara Install F-Droid:

```
F-Droid → Search "Termux" → Klik Install → Buka Termux
```

---

📌 STEP 2: Setup Awal Termux

```bash
# 1. Buka Termux, ketik perintah berikut SATU PERSATU:

# Update package
pkg update && pkg upgrade -y

# Beri akses storage
termux-setup-storage

# Install git dan python
pkg install git python python-pip -y

# Cek instalasi
python --version
git --version
```

✅ Hasil:

```
Python 3.11.x
git version 2.x.x
```

---

📌 STEP 3: Download Proyek dari GitHub

```bash
# 1. Clone repository Anda
git clone https://github.com/USERNAME_ANDA/deepseek-tts.git

# 2. Masuk ke folder proyek
cd deepseek-tts

# 3. Lihat isi folder
ls -la
```

✅ Hasil:

```
app.py
requirements.txt
README.md
templates/
```

---

📌 STEP 4: Install Dependencies

```bash
# Install semua library yang dibutuhkan
pip install -r requirements.txt

# Atau install manual:
pip install flask openai gtts flask-cors
```

⏳ Proses: 1-2 menit

✅ Hasil:

```
Successfully installed flask-2.3.3 openai-1.3.0 gtts-2.5.1 ...
```

---

📌 STEP 5: Masukkan API Key DeepSeek

```bash
# 1. Edit file app.py
nano app.py

# 2. Cari baris ini (sekitar baris 10):
DEEPSEEK_API_KEY = "ISI_API_KEY_ANDA_DISINI"

# 3. Ganti dengan API key asli Anda:
DEEPSEEK_API_KEY = "sk-xxxxxxxxxxxxxxxxxxxxxxxx"

# 4. Simpan: 
#    Tekan Ctrl + X
#    Tekan Y
#    Tekan Enter
```

📌 Cara Dapat API Key:

```
1. Buka https://platform.deepseek.com/api_keys
2. Login / Daftar
3. Klik "Create new API key"
4. Beri nama "deepseek-tts"
5. Copy API key-nya
6. Simpan di Notes HP!
```

---

📌 STEP 6: Jalankan Server!

```bash
# Jalankan aplikasi Flask
python app.py
```

✅ Hasil:

```
 * Serving Flask app 'app'
 * Debug mode: off
 * Running on http://0.0.0.0:5000
 * Running on http://192.168.1.xxx:5000
```

---

🎮 CARA MENJALANKAN APLIKASI

Setiap kali mau pakai:

```bash
# 1. Buka Termux
# 2. Masuk ke folder proyek
cd /storage/emulated/0/deepseek-tts

# 3. Jalankan server
python app.py

# 4. Buka Chrome
#    Ketik: http://localhost:5000
```

Cara Stop Server:

```
Tekan Ctrl + C di Termux
```

Auto-start (Biar otomatis jalan):

```bash
# Buat file start.sh
nano start.sh

# Isi dengan:
#!/bin/bash
cd /storage/emulated/0/deepseek-tts
python app.py &

# Simpan, lalu buat executable
chmod +x start.sh

# Tambahkan ke bashrc
echo "bash /storage/emulated/0/deepseek-tts/start.sh" >> ~/.bashrc
```

---

👤 CARTA MENGGUNAKAN APLIKASI (PANDUAN USER)

🎬 DEMO PENGGUNAAN LENGKAP

---

🔹 CARA 1: Chat dengan TEKS

Langkah-langkah:

```
1. Buka aplikasi (browser atau APK)
2. Tap kotak input "Ketik pesan..."
3. Ketik pertanyaan, contoh: "siapa presiden Indonesia?"
4. Tap tombol ➤ (kirim)
5. Tunggu AI menjawab (ada animasi titik-titik)
6. Jawaban muncul dengan suara OTOMATIS!
```

📝 Contoh Percakapan:

```
👤 Anda: "siapa presiden indonesia?"
🤖 AI: "Presiden Indonesia saat ini adalah Bapak Prabowo Subianto." 🔊
     [tekan speaker untuk ulang suara]

👤 Anda: "buatkan puisi tentang ibu"
🤖 AI: "Ibu, kau adalah cahaya di hidupku..." 🔊
```

---

🔹 CARA 2: Chat dengan SUARA (Voice Input)

Langkah-langkah:

```
1. Buka aplikasi
2. Tap tombol 🎤 (mic) - warna merah, berkedip
3. IZINKAN akses mic (pertama kali)
4. DEKATKAN mic ke mulut
5. BICARA dengan jelas, contoh: "halo apa kabar"
6. DIAM sejenak, suara akan diproses
7. TEKS otomatis muncul di kotak input
8. LANGSUNG dikirim ke AI
9. AI jawab dengan SUARA!
```

🎯 Tips Suara:

```
✅ Bicara jelas, tidak terlalu cepat
✅ Jarak mic 10-20 cm dari mulut
✅ Hindari tempat bising
✅ Bicara natural seperti ngobrol biasa
✅ Tunggu 1 detik setelah selesai bicara
```

📝 Contoh Voice Input:

```
🎤 Anda bicara: "hari ini cuaca bagaimana"
📝 Jadi teks: "hari ini cuaca bagaimana"
🤖 AI jawab: "Maaf, saya tidak bisa mengakses data cuaca real-time..." 🔊

🎤 Anda bicara: "ceritakan dongeng kancil"
📝 Jadi teks: "ceritakan dongeng kancil"
🤖 AI jawab: "Dahulu kala, hiduplah seekor kancil yang cerdik..." 🔊
```

---

🔹 CARA 3: Mengulang Suara Jawaban

Langkah-langkah:

```
1. Lihat pesan dari AI (bubble putih)
2. Cari tombol 🔊 di samping kanan teks
3. Tap tombol 🔊
4. Suara akan keluar lagi
5. Tombol beranimasi saat bersuara
```

---

🔹 CARA 4: Membersihkan Chat

Langkah-langkah:

```
1. Scroll ke bawah
2. Tap tombol "🗑️ Hapus Percakapan" (jika ada)
3. Atau refresh browser (F5)
4. Chat akan kembali ke pesan sambutan
```

---

📋 CONTOH PERCAKAPAN LENGKAP

```
🎤 [Anda tekan mic] 
Anda: "hai, perkenalkan diri kamu"

🤖 AI: 
"Halo! Senang berkenalan dengan Anda. 
Saya adalah asisten AI dari DeepSeek, 
teman ngobrol virtual Anda. 
Saya bisa membantu menjawab pertanyaan, 
bercerita, atau sekadar menemani Anda. 
Ada yang bisa saya bantu hari ini?" 🔊

------------------------------------

📝 [Anda ketik]
Anda: "apa itu kecerdasan buatan?"

🤖 AI:
"Kecerdasan Buatan atau Artificial Intelligence (AI) 
adalah teknologi yang membuat komputer bisa 
berpikir dan belajar seperti manusia. 
Contohnya: asisten virtual, rekomendasi video, 
mobil otonom, dan saya sendiri! 
AI bekerja dengan memproses data besar 
dan mengenali pola-pola di dalamnya." 🔊

------------------------------------

🎤 [Anda tekan mic]
Anda: "buatkan pantun lucu"

🤖 AI:
"Tentu, ini pantun untuk Anda:

Jalan-jalan ke kota Blitar
Jangan lupa beli suvenir
Kalau kamu suka baper
Mending main ke sini, di sini seru abis! 😄" 🔊
```

---

🌍 CARTA REMOTE AKSES DARI HP LAIN

🎯 TUJUAN:

HP A02 jadi server, HP lain (teman, keluarga) bisa akses tanpa install Termux!

---

📌 METODE 1: SERVEO (PALING MUDAH)

Di HP A02 (Termux):

```bash
# 1. Install openssh
pkg install openssh -y

# 2. Jalankan server Flask (di tab/sesi 1)
cd /storage/emulated/0/deepseek-tts
python app.py

# 3. Buka Termux BARU (geser dari kiri)
#    Jalankan tunnel:
ssh -R 80:localhost:5000 serveo.net
```

✅ Hasil:

```
Forwarding HTTP traffic from https://abc123.serveo.net
```

📌 COPY URL INI! Contoh: https://kancil123.serveo.net

Di HP User:

```
1. Buka Chrome
2. Ketik URL: https://kancil123.serveo.net
3. LANGSUNG bisa chat & voice!
```

---

📌 METODE 2: NGROK (STABIL)

Di HP A02 (Termux):

```bash
# 1. Download ngrok
cd /storage/emulated/0/deepseek-tts
wget https://bin.equinox.io/c/4VmDzA7iaHb/ngrok-stable-linux-arm64.zip
unzip ngrok-stable-linux-arm64.zip
chmod +x ngrok

# 2. Daftar dapat token (sekali saja)
#    Buka: https://dashboard.ngrok.com/signup
#    Copy authtoken

# 3. Setup token
./ngrok authtoken YOUR_TOKEN_HERE

# 4. Jalankan tunnel
./ngrok http 5000
```

✅ Hasil:

```
Forwarding https://abc123.ngrok.io -> http://localhost:5000
```

Di HP User:

```
Buka https://abc123.ngrok.io
```

---

📌 METODE 3: CLOUDFLARE TUNNEL (BANDWIDTH UNLIMITED)

```bash
# Download cloudflared
wget https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-arm64
chmod +x cloudflared

# Jalankan
./cloudflared tunnel --url http://localhost:5000
```

✅ Hasil:

```
https://something.trycloudflare.com
```

---

📲 CARTA MEMBUAT APK UNTUK DIBAGIKAN

🎯 TUJUAN:

Biar user cukup install APK, tidak perlu buka Chrome dan ketik URL.

---

📌 STEP 1: Dapatkan URL Publik

Gunakan salah satu tunnel di atas, dapatkan URL seperti:

```
https://kancil123.serveo.net
https://abc123.ngrok.io
https://something.trycloudflare.com
```

---

📌 STEP 2: Buka Web2APK

```
1. Buka Chrome di HP mana saja
2. Kunjungi: https://web2apk.com
```

---

📌 STEP 3: Isi Form APK

```
🔴 FORM APK:

App Name        : DeepSeek AI Voice
                (nama aplikasi di HP)

URL             : https://kancil123.serveo.net
                (GANTI dengan URL tunnel Anda!)

Icon            : (Opsional) Upload gambar
                Ukuran 512x512 px

Package Name    : com.deepseek.voice
                (identitas unik)

Version         : 1.0

Description     : Asisten AI dengan suara Bahasa Indonesia
                Bisa chat dan bicara langsung!
```

---

📌 STEP 4: Generate APK

```
1. Klik "Create APK"
2. Tunggu 1-2 menit
3. Klik "Download APK"
4. File APK tersimpan di HP
```

---

📌 STEP 5: Install dan Bagikan

```
1. Klik file APK
2. Klik "Install" (izin unknown source)
3. Buka aplikasi
4. LANGSUNG terhubung ke server A02 Anda!
```

📤 Cara Bagikan:

```
- WhatsApp: Kirim file APK
- Bluetooth: Share file
- Google Drive: Upload, share link
```

---

🔧 TROUBLESHOOTING

❌ Masalah: Module not found

```
Error: No module named 'flask'
```

✅ Solusi:

```bash
pip install -r requirements.txt
# atau
pip install flask openai gtts flask-cors
```

---

❌ Masalah: Port already in use

```
Error: Address already in use
```

✅ Solusi:

```bash
pkill python
python app.py
```

---

❌ Masalah: DeepSeek API Error

```
Error: 401 - Invalid API key
```

✅ Solusi:

```
1. Cek API key di app.py
2. Pastikan tidak ada spasi
3. Copy paste ulang dari dashboard
4. Cek saldo: https://platform.deepseek.com/usage
```

---

❌ Masalah: TTS Error / Suara tidak keluar

```
Error: gTTS error
```

✅ Solusi:

```
1. Cek koneksi internet
2. Ganti DNS ke 8.8.8.8
3. Setting HP:
   - Setting → Koneksi → DNS
   - Private DNS: 8.8.8.8
4. Restart server
```

---

❌ Masalah: Voice Input tidak berfungsi

```
Mic tidak merespon / error not-allowed
```

✅ Solusi:

```
1. Chrome: Klik ikon kunci di address bar
2. Izinkan "Microphone"
3. Refresh halaman
4. Coba lagi
```

---

❌ Masalah: Remote akses lambat

```
Serveo/ngrok lemot
```

✅ Solusi:

```
1. Cek sinyal HP server
2. Gunakan WiFi (lebih stabil)
3. Ganti ke Cloudflare tunnel
4. Restart tunnel
```

---

⚡ OPTIMASI UNTUK SAMSUNG A02 (2GB RAM)

1. Kurangi Memory Flask

Edit app.py:

```python
app.run(host='0.0.0.0', port=5000, 
        debug=False,           # Matikan debug
        threaded=False)       # Single thread
```

---

2. Matikan Animasi Android

```
Settings → Developer Options → 
- Window animation scale: 0.5x
- Transition animation scale: 0.5x
- Animator duration scale: 0.5x
- Background process limit: 2 processes
```

---

3. Setting Baterai

```
Settings → Device care → Battery → 
- Power saving mode: ON
- Adaptive battery: ON
- Put unused apps to sleep: ON
```

---

4. Auto-clean Cache

```bash
# Buat file cleaner
nano /storage/emulated/0/deepseek-tts/clean.sh
```

```bash
#!/bin/bash
rm -rf /storage/emulated/0/deepseek-tts/__pycache__
rm -rf /storage/emulated/0/deepseek-tts/templates/__pycache__
find /storage/emulated/0 -name "*.mp3" -type f -mmin +60 -delete
echo "✅ Bersih!"
```

```bash
chmod +x clean.sh
./clean.sh  # Jalankan seminggu sekali
```

---

5. Matikan Aplikasi Latar

```
- Matikan Bluetooth
- Matikan GPS
- Matikan Auto-sync
- Hapus aplikasi tidak penting
```

---

❓ TANYA JAWAB

Q: Berapa lama baterai tahan?

A: Samsung A02 5000 mAh bisa tahan 12-15 jam nonstop. Cas tiap malam, server 24/7.

---

Q: Bisa pakai HP lain selain A02?

A: BISA! Semua HP Android bisa:

· RAM minimal 2GB
· Android 8.0 ke atas
· Storage 500MB free

---

Q: Kalau HP server mati?

A:

· User tidak bisa akses
· Hidupkan HP, jalankan Termux lagi
· Tunnel otomatis dapat URL baru
· Update URL di APK (buat ulang)

---

Q: Berapa biaya per bulan?

A:

· Listrik: ~5 watt × 24 jam × 30 hari = 3.6 kWh = Rp 5.000
· Paket data: ~5-10 GB = Rp 50.000
· Total: ~Rp 55.000/bulan

Jauh lebih hemat dari cloud hosting ($5-50/bulan = Rp 80.000 - 800.000)!

---

Q: Bisa untuk ramai-ramai?

A:

· 1-5 user bersamaan: ✅ LANCAR
· 5 user: ⚠️ AGEN LAMBAT
· Solusi: Tambah HP server lain

---

Q: Data aman?

A:

· Percakapan tidak disimpan
· Tidak ada database
· API key tersimpan lokal di HP
· Tunnel terenkripsi (HTTPS)

---

Q: Voice input selalu minta izin?

A: Hanya sekali. Izin disimpan browser. 
Untuk APK WebView, izin cukup sekali.

---

Q: Bisa ganti suara perempuan?

A: Bisa! Edit di app.py:

```python
# Suara default (perempuan Indonesia)
tts = gTTS(text=text, lang='id', tld='co.id', slow=False)

# Suara lebih cepat
tts = gTTS(text=text, lang='id', slow=False)

# Suara lebih lambat (lebih jelas)
tts = gTTS(text=text, lang='id', slow=True)
```

---

Q: Bisa ditambah fitur history chat?

A: Bisa, tapi butuh database. Untuk sekarang belum.

---

🎉 PENUTUP

Selamat! Sekarang Anda punya:

✅ Server AI pribadi dari HP bekas
✅ Voice Assistant Bahasa Indonesia
✅ Bisa diakses dari mana saja
✅ APK siap bagikan ke teman
✅ GRATIS SELAMANYA! 🎊

---

<p align="center">
  <b>Dibuat dengan ❤️ untuk pengguna Android Indonesia</b><br>
  <i>#DeepSeek #TTS #VoiceAssistant #Termux #SamsungA02</i><br>
  <br>
  <b>📱 Repository: https://github.com/momodigital/tombo-deepseek</b><br>
  <b>🐦 Kontak: [opsional]</b><br>
  <br>
  <i>Happy coding! 🚀</i>
</p>
