# Alat Ukur Cahaya dengan Kalman Filter

## Deskripsi
Proyek ini mengimplementasikan alat ukur cahaya berbasis sensor **BH1750** yang dilengkapi dengan **Kalman Filter** untuk menghasilkan estimasi cahaya yang lebih stabil. Data mentah yang diterima dari sensor BH1750 akan diproses menggunakan Kalman Filter untuk mengurangi noise dan fluktuasi, sehingga menghasilkan nilai cahaya yang lebih halus dan akurat.

Proyek ini menggunakan papan mikrokontroler seperti Arduino dan menampilkan data pada LCD 16x2 berbasis I2C, serta mencatat data ke serial monitor dengan interval waktu yang telah ditentukan.

## Fitur
- Mengukur tingkat cahaya menggunakan sensor **BH1750**.
- Menerapkan **Kalman Filter** untuk mengurangi noise dan mendapatkan estimasi yang lebih akurat.
- Menampilkan data mentah dan data terfilter pada **LCD 16x2**.
- Mencatat data ke serial monitor dengan informasi berupa waktu, cahaya mentah (lux), dan cahaya terfilter (lux).
- Pengukuran dilakukan dengan interval **2 menit (120 detik)** untuk **30 data point**.

## Komponen yang Digunakan
- **BH1750 Light Sensor**: Untuk mengukur tingkat cahaya di sekitar alat.
- **Arduino UNO**: Sebagai mikrokontroler untuk menjalankan program.
- **LCD 16x2 dengan I2C**: Untuk menampilkan data pengukuran.
- **Wire.h**: Untuk komunikasi I2C antara Arduino dan sensor serta LCD.
- **BH1750.h**: Library untuk komunikasi dengan sensor BH1750.
- **LiquidCrystal_I2C.h**: Library untuk mengontrol LCD berbasis I2C.

## Skema Koneksi
- **BH1750**:
  - VCC ke **5V** pada Arduino.
  - GND ke **GND** pada Arduino.
  - SDA ke pin **SDA** Arduino.
  - SCL ke pin **SCL** Arduino.
  
- **LCD 16x2 I2C**:
  - VCC ke **5V** pada Arduino.
  - GND ke **GND** pada Arduino.
  - SDA ke pin **SDA** Arduino.
  - SCL ke pin **SCL** Arduino.

## Instalasi
1. Pastikan Anda telah menginstal **Arduino IDE**.
2. Unduh dan install library berikut melalui **Library Manager**:
   - **Wire**: Untuk komunikasi I2C.
   - **BH1750**: Untuk sensor cahaya BH1750.
   - **LiquidCrystal_I2C**: Untuk LCD berbasis I2C.
3. Hubungkan komponen berikut ke **Arduino**:
   - **Sensor BH1750**: Hubungkan ke pin **I2C** pada Arduino.
   - **LCD 16x2**: Hubungkan ke pin **I2C** pada Arduino.
4. Upload program ke Arduino melalui **Arduino IDE**.

## Penggunaan
1. Setelah program diupload ke Arduino, alat akan memulai pengukuran tingkat cahaya.
2. LCD akan menampilkan dua nilai:
   - **Mentah**: Nilai tingkat cahaya yang dibaca langsung dari sensor (**lux**).
   - **Filter**: Nilai tingkat cahaya setelah diproses dengan **Kalman Filter** untuk mengurangi noise (**lux**).
3. Data akan dicatat di **serial monitor** setiap **2 menit**, dengan format:
   - **No (Nomor pengukuran)**
   - **Waktu (dalam menit)**
   - **Cahaya Mentah (lux)**
   - **Cahaya Terfilter (lux)**



