#🎤 DeepSeek TTS - Voice Assistant Bahasa Indonesia

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.8+-blue?logo=python">
  <img src="https://img.shields.io/badge/Flask-2.3.3-green?logo=flask">
  <img src="https://img.shields.io/badge/DeepSeek-AI-orange">
  <img src="https://img.shields.io/badge/TTS-gTTS-brightgreen">
</p>

<p align="center">
  <b>Asisten AI dengan suara Bahasa Indonesia, jalan di HP Android via Termux! 🇮🇩</b>
</p>

---

📋 DAFTAR ISI

· Fitur
· Kebutuhan
· Instalasi di HP Server
· Menjalankan Server
· Remote Akses
· Membuat APK
· Troubleshooting

---

✨ FITUR

Fitur Teknologi
🤖 Chat AI DeepSeek API
🎤 Voice Input Web Speech API (id-ID)
🔊 Voice Output Google gTTS (Bahasa Indonesia)
📱 Server di HP Termux + Flask
🌐 Remote Akses Serveo/Ngrok
📲 APK Installer Web2APK

---

💻 KEBUTUHAN

HP Server (Samsung A02):

· RAM 2GB, Storage 500MB free
· Termux dari F-Droid (bukan Play Store)

HP User:

· Android 5.0+, Chrome/Edge
· APK size 5-8MB

---

🚀 INSTALASI DI HP SERVER

1. Install Termux

```bash
# Download F-Droid: https://f-droid.org
# Install Termux dari F-Droid
```

2. Setup Termux

```bash
pkg update && pkg upgrade -y
termux-setup-storage
pkg install git python -y
```

3. Clone & Install

```bash
git clone https://github.com/USERNAME_ANDA/deepseek-tts.git
cd deepseek-tts
pip install flask openai gtts flask-cors
```

4. Masukkan API Key

```bash
nano app.py
# Ganti: DEEPSEEK_API_KEY = "sk-xxx" (isi API key Anda)
# Ctrl+X, Y, Enter
```

🔑 Dapat API Key: https://platform.deepseek.com/api_keys

---

▶️ MENJALANKAN SERVER

```bash
python app.py
```

📱 Buka Chrome: http://localhost:5000

✅ Selesai! Aplikasi siap digunakan.

---

🌍 REMOTE AKSES (DARI HP LAIN)

Opsi 1: Serveo (Paling Mudah)

```bash
ssh -R 80:localhost:5000 serveo.net
```

📌 Dapat URL: https://random.serveo.net

Opsi 2: Ngrok (Stabil)

```bash
wget https://bin.equinox.io/c/4VmDzA7iaHb/ngrok-stable-linux-arm64.zip
unzip ngrok-stable-linux-arm64.zip
./ngrok http 5000
```

📌 Dapat URL: https://abc123.ngrok.io

---

📲 MEMBUAT APK (5 MENIT)

1. Dapatkan URL publik dari Serveo/Ngrok
2. Buka: https://web2apk.com
3. Isi form:
   · App Name: DeepSeek AI Voice
   · URL: https://url-dari-tunnel-anda
   · Package: com.deepseek.voice
4. Klik "Create APK" → Download → Install

✅ APK size 5-8MB, siap dibagikan!

---

🎮 CARTA PAKAI

📝 Chat Teks

```
Ketik pesan → Enter → AI jawab + suara otomatis
```

🎤 Voice Input

```
Tekan tombol 🎤 → Bicara → Otomatis terkirim → AI jawab + suara
```

🔊 Ulang Suara

```
Tekan tombol 🔊 di bubble chat AI
```

---

🔧 TROUBLESHOOTING

Masalah Solusi
Module not found pip install -r requirements.txt
Port already in use pkill python lalu python app.py
API Key error Cek API key di app.py
Suara tidak keluar Cek internet, ganti DNS 8.8.8.8
Mic error Izinkan akses mic di browser

---

⚡ OPTIMASI A02 (2GB RAM)

```python
# Di app.py - ubah baris terakhir:
app.run(host='0.0.0.0', port=5000, debug=False, threaded=False)
```

---

📁 STRUKTUR FILE

```
deepseek-tts/
├── app.py
├── requirements.txt
├── README.md
└── templates/
    └── index.html
```

---

📌 LINK PENTING

· DeepSeek API: https://platform.deepseek.com
· Termux F-Droid: https://f-droid.org/packages/com.termux
· Web2APK: https://web2apk.com
· Serveo: https://serveo.net

---

<p align="center">
  <b>Dibuat dengan ❤️ untuk Android Indonesia</b><br>
  <i>#DeepSeek #TTS #Termux #SamsungA02</i><br>
  <br>
  <b>📱 GitHub: https://github.com/USERNAME_ANDA/deepseek-tts</b>
</p>
```
