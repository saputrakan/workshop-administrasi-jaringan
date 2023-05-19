# Laporan Install Web Server di Linux

### Dosen pengampu: Dr. Ferry Astika Saputra. S.T, M. Sc.
### Kelas : 2 D4 Teknik Informatika A

### 1. Sandy Pradana Putra (3121600017)

### 2. Obed Christian S (3121600022)

### 3. Muhammad Rizqy F (3121600024)

### 4. Daffa Ridwan R (3121600027)

Berikut langkah - langkah untuk menginstall web server: 

1. pastikan dns server menggunakan dns server yang sudah  disediakan dan juga pastikan gateway sesuai dengan router
[![Whats-App-Image-2023-05-12-at-19-17-15.jpg](https://i.postimg.cc/SNwJNVmc/Whats-App-Image-2023-05-12-at-19-17-15.jpg)](https://postimg.cc/MvmW97MG)

2. Cek apakah jaringan sudah benar
[![Whats-App-Image-2023-05-12-at-19-18-12.jpg](https://i.postimg.cc/2ySBh5tv/Whats-App-Image-2023-05-12-at-19-18-12.jpg)](https://postimg.cc/CB91VwSL)
 
3. Kemudian dilanjutkan dengan menginstall **Nginx**, **MariaDB**, **Php**.

[![Whats-App-Image-2023-05-12-at-20-29-36.jpg](https://i.postimg.cc/vm40cQFD/Whats-App-Image-2023-05-12-at-20-29-36.jpg)](https://postimg.cc/1gZGd1zZ)

4. Setelah itu menginstall package utility yang digunakan untuk menginstall composer nantinya.

[![Whats-App-Image-2023-05-12-at-19-22-49.jpg](https://i.postimg.cc/851Fg5N3/Whats-App-Image-2023-05-12-at-19-22-49.jpg)](https://postimg.cc/HJhWQTJ4)

5. Download **composer.phar**, lalu pindah ke folder usr/bin agar bisa diakses sebagai program linux

[![Whats-App-Image-2023-05-12-at-19-29-26.jpg](https://i.postimg.cc/90sF0FHc/Whats-App-Image-2023-05-12-at-19-29-26.jpg)](https://postimg.cc/GTJ1SRpf)

6. Cek hasilnya dengan melihat version dari **composer**

[![Whats-App-Image-2023-05-12-at-19-29-50.jpg](https://i.postimg.cc/XYSY0Jg8/Whats-App-Image-2023-05-12-at-19-29-50.jpg)](https://postimg.cc/nC2J4ngj)

### Mencoba menginstall contoh projek laravel(php) dan dijalankan menggunakan Server

**Pertama**, Menjalankan perintah **composer** untuk menginstall Laravel lewat bantuan Composer

[![Whats-App-Image-2023-05-12-at-20-37-33.jpg](https://i.postimg.cc/cHbhW25w/Whats-App-Image-2023-05-12-at-20-37-33.jpg)](https://postimg.cc/47pVbLGx)
 
**Kedua** lakukan install package menggunakan composer

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/d2oi33urt57piry4wexf.png)

**Ketiga** Menjalankan **php artisan serve**

[![Whats-App-Image-2023-05-12-at-20-41-46.jpg](https://i.postimg.cc/fbhT2bz0/Whats-App-Image-2023-05-12-at-20-41-46.jpg)](https://postimg.cc/MndSXqjW)

Hasil akhirnya akan menampilkan halaman website seperti ini

[![Whats-App-Image-2023-05-12-at-20-07-09.jpg](https://i.postimg.cc/Bnm1RDz1/Whats-App-Image-2023-05-12-at-20-07-09.jpg)](https://postimg.cc/PC8xwLTt)
