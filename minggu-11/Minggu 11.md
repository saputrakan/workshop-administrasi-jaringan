# Laporan Konfigurasi DNS pada Slave

### Dosen pengampu: Dr. Ferry Astika Saputra. S.T, M. Sc.
### Kelas : 2 D4 Teknik Informatika A

### 1. Sandy Pradana Putra (3121600017)

### 2. Obed Christian S (3121600022)

### 3. Muhammad Rizqy F (3121600024)

### 4. Daffa Ridwan R (3121600027)

Lanjutan dari konfigurasi DNS pada minggu sebelumnya

1. Yang pertama dilakukan adalah menambah `allow-transfer` pada zone di file **named.conf.local**

[![Whats-App-Image-2023-05-12-at-19-02-30.jpg](https://i.postimg.cc/qMSRRgBS/Whats-App-Image-2023-05-12-at-19-02-30.jpg)](https://postimg.cc/BX5s7SKB)

2. Kemudian tambahkan juga forwarder dari IP DNS di **/var/cache/bind9/**


[![Whats-App-Image-2023-05-12-at-19-06-39.jpg](https://i.postimg.cc/8P2pG3tV/Whats-App-Image-2023-05-12-at-19-06-39.jpg)](https://postimg.cc/vcvFL0JP)

3. Langkah berikutnya restart service bind9


[![Whats-App-Image-2023-05-12-at-19-08-48.jpg](https://i.postimg.cc/Zn9mtFNR/Whats-App-Image-2023-05-12-at-19-08-48.jpg)](https://postimg.cc/64NgCZYJ)

4. Konfigurasi pada apache agar bisa diakses 

[![Whats-App-Image-2023-05-12-at-14-48-28.jpg](https://i.postimg.cc/VkzY5MQ7/Whats-App-Image-2023-05-12-at-14-48-28.jpg)](https://postimg.cc/HVPGhrL5)


Berikut hasil akhirnya 

[![Whats-App-Image-2023-05-12-at-19-50-36.jpg](https://i.postimg.cc/wT1tJhmF/Whats-App-Image-2023-05-12-at-19-50-36.jpg)](https://postimg.cc/D8Ky345b)
