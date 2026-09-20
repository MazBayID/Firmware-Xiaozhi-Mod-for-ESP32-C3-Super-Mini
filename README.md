# Xiaozhi AI Mod for ESP32-C3 Super Mini 🚀

Modifikasi dan konfigurasi khusus untuk menjalankan **Xiaozhi AI** pada mikrokontroler **ESP32-C3 Super Mini**, lengkap dengan dukungan audio I2S (INMP441 & MAX98357A) serta layar OLED 0.96".

Proyek ini berbasis dari repository resmi [78/xiaozhi-esp32](https://github.com/78/xiaozhi-esp32).

---

## 🛠️ Komponen yang Digunakan

| Komponen | Jumlah | Keterangan |
| :--- | :---: | :--- |
| **ESP32-C3 Super Mini** | 1 unit | Mikrokontroler utama |
| **INMP441** | 1 unit | Modul Mikrofon I2S |
| **MAX98357A** | 1 unit | Modul Amplifier Audio I2S |
| **OLED 0.96" I2C  SSD1306** | 1 unit | Layar Display (SCL/SDA) |
| **Push Button** | 1 unit | Tombol interaksi (Pullup internal) |
| **Speaker 8Ω 0.8W** | 1 unit | Output suara |

---

## 📌 Skema Pinout Mapping

Berikut adalah pemetaan pin (Pinout Mapping) yang disesuaikan khusus untuk konfigurasi modifikasi ini:

| Fungsi | ESP32-C3 Pin | Modul / Keterangan |
| :--- | :--- | :--- |
| **5V (Daya)** | `5V` | MAX98357A VCC |
| **G (Ground)** | `G` | MAX98357A GND + OLED GND + INMP441 GND + Tombol |
| **3V (Daya)** | `3V` | INMP441 VCC |
| **I2S BCLK** | `GPIO 1` | INMP441 SCK + MAX98357A BCLK |
| **I2S WS/LRC** | `GPIO 2` | INMP441 WS + MAX98357A LRC |
| **I2S Audio OUT** | `GPIO 3` | MAX98357A DIN |
| **Tombol** | `GPIO 4` | Tombol → GND (`INPUT_PULLUP`) |
| **I2S Audio IN** | `GPIO 8` | INMP441 SD |
| **OLED SCL** | `GPIO 20` | OLED SCL |
| **OLED SDA** | `GPIO 21` | OLED SDA |

---

## 🎨 Legenda Warna Kabel (Panduan Merakit)

*   🔴 **5V** (Merah) - Daya 5 Volt
*   ⚫ **GND** (Hitam) - Ground / Negatif
*   🟠 **3V** (Oranye) - Daya 3.3 Volt
*   🔵 **GPIO 1** (Biru Tua) - I2S BCLK
*   🟢 **GPIO 2** (Hijau) - I2S WS/LRC
*   🟣 **GPIO 3** (Ungu) - I2S Audio OUT
*   🔵 **GPIO 4** (Cyan/Biru Muda) - Tombol
*   🩷 **GPIO 8** (Pink/Magenta) - I2S Audio IN
*   🟢 **GPIO 20** (Hijau Tua) - OLED SCL
*   🔵 **GPIO 21** (Biru) - OLED SDA

---

## ⚠️ Catatan Penting Pemasangan

1.  **Ground Bersama:** Pastikan semua kabel `GND` (ground) tersambung bersama dengan baik.
2.  **Catu Daya Stabil:** Gunakan power supply 5V yang stabil untuk menyuplai MAX98357A dan ESP32-C3.
3.  **Tegangan INMP441:** INMP441 menggunakan tegangan **3.3V**.
4.  **Konfigurasi Tombol:** Tombol menggunakan mode `INPUT_PULLUP` internal (tidak memerlukan resistor eksternal tambahan).
5.  **Kapasitas Speaker:** Speaker 8Ω 0.8W sudah sangat cukup untuk penggunaan kecil dan menghasilkan suara output yang jernih dari MAX98357A.

---

## 🚀 Memulai (Getting Started)

Sesuaikan konfigurasi pin di dalam kode sumber firmware Anda dengan tabel **Pinout Mapping** di atas sebelum melakukan *flashing* ke ESP32-C3.
Anda bisa mengikuti **flash_args.txt** atau Anda juga bisa langsung flahsing file **merged-binary.bin** pada offset 0x0.

---

## 📄 Lisensi
Proyek modifikasi ini mengikuti lisensi dari repository asli [78/xiaozhi-esp32](https://github.com/78/xiaozhi-esp32).

---

## 🌏 Xiaozhi Website

https://xiaozhi.me/
