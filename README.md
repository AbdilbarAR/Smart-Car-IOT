# 🤖 WiFi Based Robot with Android Application Control

[cite_start]Proyek ini bertujuan untuk mengembangkan robot serbaguna yang dapat dikendalikan dari jarak jauh melalui jaringan WiFi[cite: 13, 14]. [cite_start]Robot ini mengintegrasikan komponen hardware dengan software kontrol yang dibuat menggunakan **MIT App Inventor**[cite: 14].



---

## 🎯 Gambaran Umum Proyek

[cite_start]Robot dikendalikan melalui aplikasi Android kustom yang berkomunikasi dengan modul **Arduino NodeMcu (ESP8266)** [cite: 15] [cite_start]yang dikonfigurasi sebagai **Access Point (AP)** dan **Web Server**[cite: 47, 234].

### Spesifikasi Jaringan
* [cite_start]**Mode:** Access Point (AP) [cite: 47, 234]
* [cite_start]**SSID:** `Robot Wifi` [cite: 97, 235]
* [cite_start]**Password:** `87654321` [cite: 98, 235]
* [cite_start]**IP Address Server:** `192.168.4.1` [cite: 5, 236]

---

## ⚙️ Daftar Komponen Hardware

[cite_start]Berikut adalah daftar komponen utama yang digunakan dalam perakitan robot[cite: 15]:

| Komponen | Deskripsi | Kuantitas |
| :--- | :--- | :--- |
| **Arduino NodeMcu** | [cite_start]Modul WiFi dan Mikrokontroler [cite: 19] | 1 |
| **L298 Motor Driver** | [cite_start]Driver motor DC dengan Dual H-Bridge [cite: 25, 40] | 1 |
| **DC Gear Motor** | [cite_start]Motor penggerak roda [cite: 18] | 4 |
| **Roda** | [cite_start]4Pcs Smart Robot Car Tyers Wheels [cite: 26] | 4 |
| **Baterai** | [cite_start]18650 Battery Cell $3.7V$ [cite: 31] | 2 |
| **LED** | [cite_start]White LED dan Red LED untuk lampu [cite: 23, 24, 38] | @2 |
| **Rangka** | [cite_start]VPC Cardboard (5mm) [cite: 16] | 1 |
| **Lain-lain** | [cite_start]Resistor, Transistor (BD139/C945), Jumper Wires, Switch [cite: 20, 21, 22, 27, 28, 29] | - |

---

## ⚡ Detail Sirkuit dan Koneksi

[cite_start]Dua sel baterai $3.7V$ dihubungkan seri untuk menghasilkan total $7.4V$ sebagai sumber daya utama[cite: 33, 45].

### Kontrol Motor (L298N)
[cite_start]L298 Motor Driver mengontrol empat motor DC[cite: 40].

| Motor | Pin NodeMcu | GPIO Pin |
| :--- | :--- | :--- |
| **Motor Kanan** (OUT1, OUT2) | [cite_start]D2, D3, D4 [cite: 41, 44] | [cite_start]GPIO4 (ENA), GPIO0 (IN1), GPIO2 (IN2) [cite: 99] |
| **Motor Kiri** (OUT3, OUT4) | [cite_start]D6, D7, D8 [cite: 42, 43] | [cite_start]GPIO12 (IN3), GPIO13 (IN4), GPIO15 (ENB) [cite: 99] |

### Kontrol Lampu
[cite_start]Empat LED (2 putih untuk depan, 2 merah untuk belakang) dikontrol melalui satu transistor NPN[cite: 37, 38].
* [cite_start]**Pin Kontrol:** Pin D0 (GPIO16) NodeMcu [cite: 36, 100]

---

## 📱 Kontrol Aplikasi Android (MIT App Inventor)

[cite_start]Aplikasi Android menyediakan *User Interface* dengan kontrol berikut[cite: 66, 67]:

* [cite_start]**Tombol Panah:** Untuk navigasi pergerakan robot (Maju, Mundur, Belok, Diagonal)[cite: 67].
* [cite_start]**Tombol Mikrofon:** Untuk perintah suara[cite: 67].
* [cite_start]**Tombol Bullet:** Untuk mengaktifkan/menonaktifkan lampu LED[cite: 68].
* [cite_start]**Slider:** Untuk mengatur kecepatan robot (nilai $0$ hingga $9$)[cite: 69].

### Daftar Perintah HTTP (`command = server.arg("State")`)

[cite_start]Perintah dikirim sebagai parameter **State** melalui HTTP *request*[cite: 127, 241].

| Perintah | Deskripsi | Fungsi |
| :--- | :--- | :--- |
| **F** | Maju | [cite_start]`goForword()` [cite: 128, 130, 238] |
| **B** | Mundur | [cite_start]`goBack()` [cite: 128, 131, 238] |
| **L** | Belok Kiri | [cite_start]`goLeft()` [cite: 129, 131, 238] |
| **R** | Belok Kanan | [cite_start]`goRight()` [cite: 132, 133, 238] |
| **S** | Berhenti | [cite_start]`stopRobot()` [cite: 153, 240] |
| **W** | Lampu ON (HIGH) | [cite_start]`digitalWrite(Light, HIGH)` [cite: 135, 136, 239] |
| **w** | Lampu OFF (LOW) | [cite_start]`digitalWrite(Light, LOW)` [cite: 135, 137, 239] |
| **I** | Maju Kanan | [cite_start]`goForwordRight()` [cite: 133, 238] |
| **G** | Maju Kiri | [cite_start]`goForwordLeft()` [cite: 134, 238] |
| **J** | Mundur Kanan | [cite_start]`goBackRight()` [cite: 134, 238] |
| **H** | Mundur Kiri | [cite_start]`goBackLeft()` [cite: 134, 238] |
| **0 - 9** | Atur Kecepatan | [cite_start]`speedCar` (100 - 255) [cite: 140-152, 240] |

---

## 🛠️ Desain dan Konstruksi

[cite_start]Desain rangka robot dapat dicetak pada lembar A4 dan dipotong pada lembaran Akrilik atau Foam Board setebal 5mm[cite: 61].



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
