
# 🚗 Line Follower dengan 3 Sensor IR – Arduino

Proyek ini merupakan robot line follower sederhana yang menggunakan **3 buah sensor IR (infrared)** untuk mendeteksi garis hitam dan mengikuti jalurnya secara otomatis. Motor DC digunakan untuk menggerakkan robot, dan sensor IR menentukan arah gerakan.

---

## 🔧 Komponen yang Digunakan

| Komponen                  | Jumlah |
|--------------------------|--------|
| Arduino UNO / Nano       | 1      |
| Sensor IR (infrared)     | 3      |
| Motor Driver L298N       | 1      |
| Motor DC (gear motor)    | 2      |
| Rangka Robot + Roda      | 1 set  |
| Power supply (baterai)   | 1      |
| Kabel jumper + breadboard| secukupnya |

---

## ⚡ Wiring Diagram

### 🟢 Sensor IR

| Sensor IR | Arduino Pin |
|-----------|-------------|
| Kiri      | 2           |
| Tengah    | 3           |
| Kanan     | 4           |

> Sensor IR akan memberi logika **LOW (0)** jika mendeteksi **warna hitam**, dan **HIGH (1)** jika mendeteksi **warna putih**.

---

### 🔴 Motor Driver L298N

| L298N Pin | Arduino Pin |
|----------|-------------|
| IN1      | 5           |
| IN2      | 6           |
| IN3      | 9           |
| IN4      | 10          |
| ENA      | 11 (PWM)    |
| ENB      | 12 (PWM)    |

---

## 📄 Penjelasan Kode Program

Kode berfungsi untuk:
- Membaca input dari 3 sensor IR
- Mengontrol arah dan kecepatan motor berdasarkan posisi garis

### 👇 Logika Utama:
| Sensor Kiri | Tengah | Kanan | Aksi Robot       |
|-------------|--------|-------|------------------|
| 1           | 0      | 1     | Maju (Lurus)     |
| 0           | 0      | 1     | Belok Kanan      |
| 1           | 0      | 0     | Belok Kiri       |
| 0           | 1      | 0     | Lurus            |
| 0           | 0      | 0     | Berhenti         |
| 1           | 1      | 1     | Lurus (default)  |

### 🚦 Fungsi Penting:
- `digitalRead()`: Membaca input dari sensor IR
- `analogWrite()`: Mengatur kecepatan motor
- `digitalWrite()`: Mengatur arah motor

---

## 🛠 Setup

1. Hubungkan semua komponen sesuai wiring.
2. Upload kode `.ino` ini ke Arduino melalui Arduino IDE.
3. Letakkan robot pada lintasan bergaris hitam di atas permukaan putih.
4. Robot akan mengikuti garis sesuai logika sensor.

---

## ✅ Tips

* Gunakan permukaan putih doff (tidak mengkilap) agar IR tidak memantul berlebihan.
* Atur posisi sensor agak menunduk dan sejajar.
* Gunakan PWM untuk mengatur kecepatan motor agar belokan lebih halus.

---

## 📸 Dokumentasi (Opsional)

Tambahkan foto robot, diagram wiring (Fritzing), atau video hasil demo.

---

## 📚 Lisensi

Proyek ini bebas digunakan untuk keperluan edukasi, tugas kuliah, dan pengembangan pribadi.
