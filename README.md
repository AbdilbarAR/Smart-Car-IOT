# 🤖 WiFi Based Robot with Android Application Control

Proyek ini bertujuan untuk mengembangkan robot serbaguna yang dapat dikendalikan dari jarak jauh melalui jaringan WiFi. Robot ini mengintegrasikan komponen hardware dengan software kontrol yang dibuat menggunakan **MIT App Inventor**.

---

## 🎯 Gambaran Umum Proyek

Robot dikendalikan melalui aplikasi Android kustom yang berkomunikasi dengan modul **Arduino NodeMcu (ESP8266)** yang dikonfigurasi sebagai **Access Point (AP)** dan **Web Server**.

### Spesifikasi Jaringan
* **Mode:** Access Point (AP)
* **SSID:** `Robot Wifi`
* **Password:** `87654321`
* **IP Address Server:** `192.168.4.1`

---

## ⚙️ Daftar Komponen Hardware

Berikut adalah daftar komponen utama yang digunakan dalam perakitan robot:

| Komponen | Deskripsi | Kuantitas |
| :--- | :--- | :--- |
| **Arduino NodeMcu** | Modul WiFi dan Mikrokontroler | 1 |
| **L298 Motor Driver** | Driver motor DC dengan Dual H-Bridge | 1 |
| **DC Gear Motor** | Motor penggerak roda | 4 |
| **Roda** | 4Pcs Smart Robot Car Tyers Wheels | 4 |
| **Baterai** | 18650 Battery Cell $3.7V$ | 2 |
| **LED** | White LED dan Red LED untuk lampu | 2 |
| **Rangka** | VPC Cardboard (5mm) | 1 |
| **Lain-lain** | Resistor, Transistor (BD139/C945), Jumper Wires, Switch | - |

---

## ⚡ Detail Sirkuit dan Koneksi

Dua sel baterai $3.7V$ dihubungkan seri untuk menghasilkan total $7.4V$ sebagai sumber daya utama.

### Kontrol Motor (L298N)
L298 Motor Driver mengontrol empat motor DC.

| Motor | Pin NodeMcu | GPIO Pin |
| :--- | :--- | :--- |
| **Motor Kanan** (OUT1, OUT2) | D2, D3, D4 | GPIO4 (ENA), GPIO0 (IN1), GPIO2 (IN2) |
| **Motor Kiri** (OUT3, OUT4) | D6, D7, D8 | GPIO12 (IN3), GPIO13 (IN4), GPIO15 (ENB) |

### Kontrol Lampu
Empat LED (2 putih untuk depan, 2 merah untuk belakang) dikontrol melalui satu transistor NPN.
* **Pin Kontrol:** Pin D0 (GPIO16) NodeMcu

---

## 📱 Kontrol Aplikasi Android (MIT App Inventor)

Aplikasi Android menyediakan *User Interface* dengan kontrol berikut:

* **Tombol Panah:** Untuk navigasi pergerakan robot (Maju, Mundur, Belok, Diagonal).
* **Tombol Mikrofon:** Untuk perintah suara.
* **Tombol Bullet:** Untuk mengaktifkan/menonaktifkan lampu LED.
* **Slider:** Untuk mengatur kecepatan robot (nilai $0$ hingga $9$).

### Daftar Perintah HTTP (`command = server.arg("State")`)

Perintah dikirim sebagai parameter **State** melalui HTTP *request*.

| Perintah | Deskripsi | Fungsi |
| :--- | :--- | :--- |
| **F** | Maju | `goForword()` |
| **B** | Mundur | `goBack()` |
| **L** | Belok Kiri | `goLeft()` |
| **R** | Belok Kanan | `goRight()` |
| **S** | Berhenti | `stopRobot()` |
| **W** | Lampu ON (HIGH) | `digitalWrite(Light, HIGH)` |
| **w** | Lampu OFF (LOW) | `digitalWrite(Light, LOW)` |
| **I** | Maju Kanan | `goForwordRight()` |
| **G** | Maju Kiri | `goForwordLeft()` |
| **J** | Mundur Kanan | `goBackRight()` |
| **H** | Mundur Kiri | `goBackLeft()` |
| **0 - 9** | Atur Kecepatan | `speedCar` (100 - 255) |

---

## 🛠️ Desain dan Konstruksi

Desain rangka robot dapat dicetak pada lembar A4 dan dipotong pada lembaran Akrilik atau Foam Board setebal 5mm.

---

## 🧑‍🤝‍🧑 Foto Kelompok

Berikut adalah tim yang berdedikasi di balik proyek Robot WiFi ini.

![Foto Kelompok Proyek Smart Car](Foto%20Kelompok.jpg)

---

## 🔗 File Proyek

Silakan unduh file-file berikut untuk membangun proyek ini:
* [Kode Arduino IDE (ino file)](URL_ANDA)
* [Desain Rangka Robot (pdf/dxf)](URL_ANDA)
* [Diagram Sirkuit](URL_ANDA)
* [File Aplikasi Android App Inventor (.aia)](URL_ANDA)
