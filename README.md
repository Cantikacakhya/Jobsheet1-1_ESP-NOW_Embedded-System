# Jobsheet1-1_ESP-NOW_Embedded-System
 JARINGAN SENSOR NIRKABEL MENGGUNAKAN ESP-NOW

I. PENJELASAN SINGKAT

ESP-NOW adalah protokol yang dikembangkan oleh Espressif, yang memungkinkan banyak perangkat untuk berkomunikasi satu sama lain tanpa menggunakan Wi-Fi. Protokol ini mirip dengan konektivitas nirkabel 2.4GHz berdaya rendah. Pendifinisian alamat (MAC Address) pada masing-masing ESP32 diperlukan pada awal konfigurasi. Setelah konfigurasi alamat selesai dilakukan, jaringan peer-to-peer akan terbentuk dan perangkat tidak perlu melakukan handshaking kembali ketika akan berkomunikasi. Sehingga, setelah perangkat ESP32 saling terpasang satu sama lain, koneksi akan tetap ada. Jika tiba-tiba salah satu ESP32 kehilangan daya atau diatur ulang, ketika restart, secara otomatis akan terhubung ke pasangan ESP32 yang telah terdefinisi alamatnya untuk melanjutkan komunikasi.  ESP-NOW mempunyai 2 tipe jaringan, yaitu One-Way Communication dan Two-Way Communication. One-Way Communication terbagi menjadi Point-to-Point, One-to-Many Communication dan Many-to-One Communication. Sementara Two-Way Communication terbagi menjadi Point-to-Point dan Mesh Communication. Praktikum ini bertujuan supaya dapat memahami konsep  dan dapat melakukan konfigurasi berbagai topologi jaringan sensor nirkabel berbasis ESPNOW da menentukan topologi ESP-NOW sesuai dengan studi kasus.

II. ALAT DAN BAHAN

    1) ESP32 
    2) Breadboard 
    3) Kabel jumper 
    4) Resistor 10K Ohm

III. LANGKAH PERCOBAAN 

     A.Memperoleh MAC Address ESP32 Receiver 
       1. Buka Arduino IDE 
       2. Kemudian ketikkan script program MAC.ino ke dalam Arduino IDE.
       3. Upload program tersebut ke ESP32. 
       4. Setelah program berhasil diupload, buka serial monitor. 
       5. Berikut ini adalah dokumentasi MAC Address ESP32 yang ditampilkan pada serial monitor
![MAC_Address](https://user-images.githubusercontent.com/121161133/210077525-cdccbe19-9129-40ab-a93a-cf8cba25aa00.png)

     B.ESP-NOW One-Way Point-to-Point Communication 
       1. Siapkan board ESP32 sejumlah 2 unit yang akan diprogram sebagai Sender dan Receiver. 
       2. Kemudian ketikkan script program berikut untuk mengkonfigurasi ESP32 sebagai sender. 
       3. Isi array broadcastAddress [] dengan MAC Address ESP32 Receiver yang didapatkan pada poin A. 
       4. Upload program pada ESP32 Sender.
       5. Setelah ESP32 sender dikonfigurasi, kemudian konfigurasikan ESP32 yang lain sebagai Receiver. Ketikkan script program PTPReceiver.ino untuk mengkonfigurasi ESP32 sebagai receiver. 
       6. Upload program, hasilnya akan seperti gambar berikut ini
MAC Address Tx (Nabila & Hesti) : 24:0A:C4:C6:06:54

![B_Tx](https://user-images.githubusercontent.com/121161133/210081338-aa3df660-fb39-4b76-a43c-b48b9ff54f61.jpg)
![B-Tx](https://user-images.githubusercontent.com/121161133/210080791-ef2a5582-da42-4249-86d2-62dacf991d6c.jpg)

MAC Address Rx (Razan & Cantika) : 30:AE:A4:7A:8F:B8

![B_Rx](https://user-images.githubusercontent.com/121161133/210081376-e1f96af3-2516-4aae-9adc-ed25c1f5c9e5.png)
![B-Rx](https://user-images.githubusercontent.com/121161133/210081067-7c36cc65-4113-4262-9411-c69476a54a85.png)

       7. Buatlah analisis atau flow chart program untuk menjelaskan fungsi per-bagian pada program.
       8. Buatlah data dummy dengan ukuran yang terbaca oleh receiver ± 250 byte. 
       9. Aturlah jarak awal komunikasi antara sender dan receiver yaitu 1 meter. Kemudian ubah jarak komunikasi dengan penambahan 1 meter. Data yang dikirim pada tiap iterasi pengujian adalah 10 data. 
       10. Aturlah tinggi antena atau peletakan ESP32 pada ground level (menempel tanah), 30 cm di atas tanah, dan 1 meter di atas tanah. 
TX - RX Ground, Jarak 1,2 Meter
![B Ground_Tinggi1 2M](https://user-images.githubusercontent.com/121161133/210082068-e1089197-5142-40aa-898d-3806db87590c.png)

TX - RX Ground, Jarak 2,4 Meter
![Ground_Tinggi2 4M](https://user-images.githubusercontent.com/121161133/210082370-ae6e8d64-2f3b-4057-b741-7daf0f562d15.png)

TX - RX Ground, Jarak 3 Meter
![Ground_Tinggi 3 Meter](https://user-images.githubusercontent.com/121161133/210082413-b6798c49-718b-4939-be49-30b19b04c2b9.png)

TX - RX Ground, Jarak 4,2 Meter
![Ground_Tinggi 4 2 Meter](https://user-images.githubusercontent.com/121161133/210085445-21118fb0-b103-4e8a-8641-9a578effa710.png)

TX - RX Ground, Jarak 5,4 Meter
![Ground 5,4m](https://user-images.githubusercontent.com/121161133/210086781-c8222a1e-b2ba-4a34-9de9-5b6f43d8dd3b.png)

TX - RX Tinggi 30cm, Jarak 1,2 Meter
![30cm1,2m](https://user-images.githubusercontent.com/121161133/210085698-385f5f9a-e815-431f-839f-d09b1167c231.png)

TX - RX Tinggi 30cm, Jarak 2,4 Meter
![30cm_2,4m](https://user-images.githubusercontent.com/121161133/210085799-c6c1ef7b-29e0-48a2-a928-cb2c7a6d4028.png)

TX - RX Tinggi 30cm, Jarak 3 Meter
![30cm_3m](https://user-images.githubusercontent.com/121161133/210084302-e88914cf-5093-49b8-8849-576794584fb4.png)

TX - RX Tinggi 30cm, Jarak 4,2 Meter
![30cm_4 2m](https://user-images.githubusercontent.com/121161133/210085916-eedbdfc8-25ac-4ac1-8869-d0041d12a32e.png)

TX - RX Tinggi 30cm, Jarak 5,4 Meter
![30cm_5,4m](https://user-images.githubusercontent.com/121161133/210086487-cd9081e4-112a-4ccd-bdbe-0d47ababdc20.png)

TX - RX Tinggi 1 Meter, Jarak 1,2 Meter
![3m_1m](https://user-images.githubusercontent.com/121161133/210084327-8fa7eb3e-9765-4683-9a37-918d96ceefb9.png)

TX - RX Tinggi 1 Meter, Jarak 2,4 Meter
![1m-2,4m](https://user-images.githubusercontent.com/121161133/210086249-755cb10d-bd9e-44c0-9ac2-999a4bc66eeb.png)

TX - RX Tinggi 1 Meter, Jarak 3 Meter
![1m_3m](https://user-images.githubusercontent.com/121161133/210086170-272347bc-5e5a-45f4-9cdc-5f58fdb49641.png)

TX - RX Tinggi 1 Meter, Jarak 4,2 Meter
![1m-4,2m](https://user-images.githubusercontent.com/121161133/210086318-ea24f290-093e-4c70-85cd-d53240c9f307.png)

TX - RX Tinggi 1 Meter, Jarak 5,4 Meter
![1m-5,4m](https://user-images.githubusercontent.com/121161133/210086402-a9e1dc79-80bc-4a19-9ce0-55e0eff309ba.png)

       11. Masukkan hasil pengukuran pada kolom berikut dan buatlah analisisnya dengan pendekatan teori freshnel zone.
![Tabel 1](https://user-images.githubusercontent.com/121161133/210081883-5ea2f3d3-ab32-4636-b441-f35eb332e0d8.png)

     C.One-Way, One-to-Many Communication 
       a) Mengirim Pesan yang Sama Ke Beberapa Board ESP32 
          1. Siapkan 4 unit board ESP32. 
          2. Unggah program untuk mendapatkan Mac Address, kemudian catat masing-masing Mac Address pada setiap board ESP32 yang akan diatur sebagai Receiver.
          3. Siapkan 1 unit ESP-32 yang akan dikonfigurasi sebagai Master/Sender.
          4. Ketik program OneToManyReceiver.ino dan tambahkan semua Mac Address ESP32 Receiver pada bagian broadcastAddress[].
          5. Upload program tersebut pada board ESP32 Sender. 
          6. Siapkan board Receiver, kemudian ketik script berikut ini pada Arduino IDE.
          7. Upload program tersebut pada Receiver. 
          8. Dokumentasikan output dari program tersebut secara lengkap pada masing-masing board. 
MAC Sender (Syauqi & Vania) : 3C:71:BF:F1:4B:08

MAC Reciver 1 (Noviantie & Dionysius) : 24:6F:28:02:C3:1C

MAC Receiver 2 (Hesti & Nabila) : 24:0A:C4:C6:06:54

MAC Receiver 3 (Cantika & Razan) : 30:AE:A4:7A:8F:B8
![C_1](https://user-images.githubusercontent.com/121161133/210084728-29bef717-ba18-451f-aff7-3b6b3539066e.png)

          9. Matikan salah satu board Receiver, dokumentasikasikan hasilnya, dan buatlah analisisnya.
![C2](https://user-images.githubusercontent.com/121161133/210083608-2b7e5fe1-d099-47ea-a0d2-e0e62df9f0bc.png)

          10. Buatlah koneksi menggunakan semua board ESP32 yang ada dikelas, dengan menambahkan Receiver ke dalam jaringan secara bertahap, 
          11. Dokumentasikan hasilnya secara lengkap. Catat dan analisis jumlah board maksimal yang dapat membentuk jaringan.

       b) Mengirim Pesan yang Berbeda Ke Beberapa Board ESP32 
          1. Siapkan 4 board ESP32, 1 board sebagai Sender dan 3 board sebagai Receiver. 
          2. Buatlah program pada Sender agar dapat mengirim pesan yang berbeda pada 3 Receiver. 
          3. Tips : Buat 3 buat struktur data. Buat 3 random data dummy generator pada masing-masing variabel x dan y. Gunakan fungsi esp_now_send() pada masing-masing broadcastAddress dengan script yang terpisah

     D.One-Way, Many-to-One Communication Di dalam mode ini, Receiver harus dapat mengidentifikasi setiap MAC Address unik dari Sender. Namun, untuk dapat membaca MAC Address yang berbeda cukup rumit dan butuh sedikit trik. Sehingga, untuk membuatnya lebih mudah, masing-masing Sender akan diberikan ID unik, agar Receiver dapat lebih mudah mengidentifikasi Sender. 
       1. Siapkan 4 board ESP32. 3 board diatur sebagai Sender dan 1 board diatur sebagai Receiver. 
       2. Unggah program untuk menemukan MAC Address pada board Receiver, kemudian catat MAC Address-nya. 
       3. Ketikkan program ManyToOneSender.ino pada Arduino IDE untuk mengkonfigurasi board Sender
       4. Upload program tersebut pada board Sender. 
       5. Siapkan board Receiver, ketikkan script berikut di Arduino IDE, kemudian upload program tersebut.
       6. Buka serial monitor dan dokumentasikan output program
MAC Sender 1 (Syauqi & Vania) : 24:0A:C4:C5:E2:DC

MAC Sender 2 (Hesti & Nabila) : 

MAC Sender 3 (Cantika & Razan) : 24:0A:C4:C6:0E:7C

MAC Receiver  (Dionysius & Noviantie) : 3C:71:BF:F1:42:70

Dari Pihak Sender akan muncul seperti gambar di bawah ini
![D1](https://user-images.githubusercontent.com/121161133/210083025-e3455b4b-71a9-43d1-afb2-8764d3bfb73b.png)

Dari pihak receiver akan muncul seperti gambar di bawah ini
![D2](https://user-images.githubusercontent.com/121161133/210083043-f6cdbfde-0505-47be-99d0-9eb9a3a73b32.jpg)

     E.Two-Way Communication 
       1. Siapkan 2 unit ESP32 dan 2 unit sensor DHT11. 
       2. Buatlah rangkaian seperti pada Gambar di bawah ini
![1](https://user-images.githubusercontent.com/121161133/209563183-075e3128-7810-49e0-bb2b-d6b88929e25c.png)

       3. Install library sensor DHT 11 melalui Sketch > Include Library > Manage Libraries. Ketikkan DHT pada kolom pencarian, pilih library yang akan diinstall seperti pada Gambar berikut ini. Kemudian install juga Adafruit Unified Sensor menggunakan cara yang sama.
       4. Upload program ToWayCom1.ino untuk melakukan pengecekan sensor DHT11.
       5. Dokumentasikan output program yang ditampilkan pada serial monitor Arduino IDE.
       6. Unggah program menemukan MAC Address pada masing-masing board, kemudian catat MAC Address-nya. 
       7. Ketikkan script berikut, kemudian masukkan MAC Address receiver pada masing masing board. 
       8. Upload program pada masing-masing board.
       9. Buka serial monitor pada Arduino IDE, kemudian dokumentasikan outputnya. 
       10. Buatlah jaringan sensor nirkabel ESPNow topologi MESH berlandaskan Two-Way Communication. Diagram blok jaringan dapat dilihat pada Gambar 5
Hasil pengecekan Sensor menggunakan DHT22

![E_2](https://user-images.githubusercontent.com/121161133/210087583-64f69ded-8b83-4fb3-9ebd-9e3a0466b5e3.png)

Tampilan pada serial monitor

![E1](https://user-images.githubusercontent.com/121161133/210082780-534d7fd7-c1c3-4fc3-ad7c-cb62c9b72a53.png)


