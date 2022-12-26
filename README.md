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
       2. Kemudian ketikkan script program berikut di Arduino IDE.
       3. Upload program tersebut ke ESP32. 
       4. Setelah program berhasil diupload, buka serial monitor. 
       5. Catat Mac Address ESP32. (ss mac add)

     B.ESP-NOW One-Way Point-to-Point Communication 
       1. Siapkan board ESP32 sejumlah 2 unit yang akan diprogram sebagai Sender dan Receiver. 
       2. Kemudian ketikkan script program berikut untuk mengkonfigurasi ESP32 sebagai sender. 
       3. Isi array broadcastAddress [] dengan MAC Address ESP32 Receiver yang didapatkan pada poin A. 
       4. Upload program pada ESP32 Sender.
       5. Setelah ESP32 sender dikonfigurasi, kemudian konfigurasikan ESP32 yang lain sebagai Receiver. Ketikkan script program berikut untuk mengkonfigurasi ESP32 sebagai receiver. 
       6. Upload program, kemudian dokumentasikan hasilnya. 
       7. Buatlah analisis atau flow chart program untuk menjelaskan fungsi per-bagian pada program.
       8. Buatlah data dummy dengan ukuran yang terbaca oleh receiver ± 250 byte. 
       9. Aturlah jarak awal komunikasi antara sender dan receiver yaitu 1 meter. Kemudian ubah jarak komunikasi dengan penambahan 1 meter. Data yang dikirim pada tiap iterasi pengujian adalah 10 data. 
       10. Aturlah tinggi antena atau peletakan ESP32 pada ground level (menempel tanah), 30 cm di atas tanah, dan 1 meter di atas tanah. 
       11. Masukkan hasil pengukuran pada kolom berikut dan buatlah analisisnya dengan pendekatan teori freshnel zone.

     C.One-Way, One-to-Many Communication 
       a) Mengirim Pesan yang Sama Ke Beberapa Board ESP32 
          1. Siapkan 4 unit board ESP32. 
          2. Unggah program untuk mendapatkan Mac Address, kemudian catat masing-masing Mac Address pada setiap board ESP32 yang akan diatur sebagai Receiver.
          3. Siapkan 1 unit ESP-32 yang akan dikonfigurasi sebagai Master/Sender.
          4. Ketik program berikut ini dan tambahkan semua Mac Address ESP32 Receiver pada bagian broadcastAddress[].
          5. Upload program tersebut pada board ESP32 Sender. 
          6. Siapkan board Receiver, kemudian ketik script berikut ini pada Arduino IDE.
          7. Upload program tersebut pada Receiver. 
          8. Dokumentasikan output dari program tersebut secara lengkap pada masing-masing board. 
          9. Matikan salah satu board Receiver, dokumentasikasikan hasilnya, dan buatlah analisisnya. 
          10. Buatlah koneksi menggunakan semua board ESP32 yang ada dikelas, dengan menambahkan Receiver ke dalam jaringan secara bertahap, 
          11. Dokumentasikan hasilnya secara lengkap. Catat dan analisis jumlah board maksimal yang dapat membentuk jaringan.
       b) Mengirim Pesan yang Berbeda Ke Beberapa Board ESP32 
          1. Siapkan 4 board ESP32, 1 board sebagai Sender dan 3 board sebagai Receiver. 
          2. Buatlah program pada Sender agar dapat mengirim pesan yang berbeda pada 3 Receiver. 
          3. Tips : Buat 3 buat struktur data. Buat 3 random data dummy generator pada masing-masing variabel x dan y. Gunakan fungsi esp_now_send() pada masing-masing broadcastAddress dengan script yang terpisah

     D.One-Way, Many-to-One Communication Di dalam mode ini, Receiver harus dapat mengidentifikasi setiap MAC Address unik dari Sender. Namun, untuk dapat membaca MAC Address yang berbeda cukup rumit dan butuh sedikit trik. Sehingga, untuk membuatnya lebih mudah, masing-masing Sender akan diberikan ID unik, agar Receiver dapat lebih mudah mengidentifikasi Sender. 
       1. Siapkan 4 board ESP32. 3 board diatur sebagai Sender dan 1 board diatur sebagai Receiver. 
       2. Unggah program untuk menemukan MAC Address pada board Receiver, kemudian catat MAC Address-nya. 
       3. Ketikkan program berikut pada Arduino IDE untuk mengkonfigurasi board Sender
       4. Upload program tersebut pada board Sender. 
       5. Siapkan board Receiver, ketikkan script berikut di Arduino IDE, kemudian upload program tersebut.
       6. Buka serial monitor dan dokumentasikan output program

     E.Two-Way Communication 
       1. Siapkan 2 unit ESP32 dan 2 unit sensor DHT11. 
       2. Buatlah rangkaian seperti pada Gambar di bawah ini
![1](https://user-images.githubusercontent.com/121161133/209563183-075e3128-7810-49e0-bb2b-d6b88929e25c.png)

       3. Install library sensor DHT 11 melalui Sketch > Include Library > Manage Libraries. Ketikkan DHT pada kolom pencarian, pilih library yang akan diinstall seperti pada Gambar berikut ini. Kemudian install juga Adafruit Unified Sensor menggunakan cara yang sama.
       4. Upload program berikut ini untuk melakukan pengecekan sensor DHT11.
       5. Dokumentasikan output program yang ditampilkan pada serial monitor Arduino IDE.
       6. Unggah program menemukan MAC Address pada masing-masing board, kemudian catat MAC Address-nya. 
       7. Ketikkan script berikut, kemudian masukkan MAC Address receiver pada masing masing board. 
       8. Upload program pada masing-masing board.
       9. Buka serial monitor pada Arduino IDE, kemudian dokumentasikan outputnya. 
       10. Buatlah jaringan sensor nirkabel ESPNow topologi MESH berlandaskan Two-Way Communication. Diagram blok jaringan dapat dilihat pada Gambar 5
