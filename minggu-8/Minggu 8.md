# Laporan Konfigurasi Web Server dan FTP Server

### Dosen pengampu: Dr. Ferry Astika Saputra. S.T, M. Sc.
### Kelas : 2 D4 Teknik Informatika A

### 1. Sandy Pradana Putra (3121600017)

### 2. Obed Christian S (3121600022)

### 3. Muhammad Rizqy F (3121600024)

### 4. Daffa Ridwan R (3121600027)

### 1.1 Instalasi package web server, php, dan database

Masukkan perintah dibawah untuk menginstall webserver (apache2), php dan database(mariadb-server)

```console
sudo apt install apache2
```

[![apache2](https://i.postimg.cc/SQdWL41J/Screenshot-4653.png)](https://postimg.cc/XXZG3Rbb)

pilih yes dan enter dan tunggu sampai selesai.

Untuk mengecek apakah webserver sudah terinstall, masukkan perintah `sudo systemctl status apache2`

[![apache_service](https://i.postimg.cc/zXVhySgk/Screenshot-4655.png)](https://postimg.cc/fJQyFd53)

Lalu install mysql dengan perintah `sudo apt install mysql-server`

[![mysql-server](https://i.postimg.cc/mDBX46hj/Screenshot-4656.png)](https://postimg.cc/KKprrfP3)

Untuk mengecek apakah mysql sedang berjalan, masukkan perintah `sudo service mysql status`

[![Screenshot-4658.png](https://i.postimg.cc/50gP2qCV/Screenshot-4658.png)](https://postimg.cc/2bqdHWGc)

### 1.2 mariadb-server

Pada langkah sebelumnya mariadb sudah berhasil terinstall, namun belum ada konfigurasi. Masukkan perintah dibawah untuk mengkonfigurasi

```console
sudo mysql_secure_installation
```

Setelah di enter, maka akan dihadapkan beberapa pilihan konfigurasi seperti password dan lain-lain. Kemudian tunggu sampai proses selesai

[![mariadb_config](https://i.postimg.cc/g2d5KJHr/Screenshot-4660.png)](https://postimg.cc/2Vc2kCJf)

### 1.3 Login User sebagai Root

Pertama masuk ke root user dengan perintah

```console
sudo mysql -u root password
```

[![login_user](https://i.postimg.cc/rF9cTSD8/Screenshot-4661.png)](https://postimg.cc/RNq2QJ18)

### 1.4 .htaccess

Jika diperlukan konfigurasi .htaccess, buka file `apache2.conf` dengan perintah di bawah

```console
sudo nano /etc/apache2/apache2.conf
```

Cari baris kode `AccessFileName .htaccess`. Jika di depannya ada tanda pagar (#) silakan dihapus.

Kemudian temukan baris kode dengan script di bawah ini.

```console
<Directory /var/www/>
     Options Indexes FollowSymLinks
     AllowOverride None
     Require all granted
</Directory>
```

Kemudian ganti kata “None” menjadi “All”

`AllowOverride All`

Selanjutnya aktifkan ModRewrite dengan mengetikkan perintah.

```console
sudo a2enmod rewrite
```

Terakhir restart apache server

```console
sudo service apache2 restart
```

## 2. FTP Server

### 2.1 Install Package Proftpd

lakukan instalasi package Proftpd dengan menggunakan perintah berikut :

```console
sudo apt-get install proftpd
```

[![Screenshot-4663.png](https://i.postimg.cc/jSKY2vWW/Screenshot-4663.png)](https://postimg.cc/bs6BFx98)

### 2.2 Melakukan backup

Sebelum mengedit file anda perlu melakukan backup paa file `proftpd.conf` dengan mengetikan perintah berikut.

```console
sudo cp /etc/proftpd/proftpd.conf /etc/proftpd/proftpd.conf.backup
```

### 2.3 Melakukan edit pada file proftpd.conf

Untuk mengedit file proftpd.conf dengan mengetikan perintah berikut.

```console
sudo nano /etc/proftpd/proftpd.conf
```

setelah itu akan terbuka file `proftpd.conf`. anda hanya perlu menganti beberapa baris untuk settingan default.

Ubah UseIPv6 yang awalnya on menjadi off, dan kemudian Ubah Domain sesuai dengan nama Domain Anda. Disini Nama Domain saya adalah `kampus-06.takehome.com`.

[![Screenshot-4667.png](https://i.postimg.cc/7ZXd648c/Screenshot-4667.png)](https://postimg.cc/K1kJqdYr)

Setelah itu uncommand `DefaultRoot` di bagian bawah file.

[![Screenshot-4666.png](https://i.postimg.cc/pdpGLnBh/Screenshot-4666.png)](https://postimg.cc/FfXgPz8N)

Setelah itu anda dapat menekan `"Ctrl+X"` untuk keluar dan tekan `"Y"` untuk konfirmasi dan kemudian tekan `"Enter"`.

### 2.4 Membuat user

Masukkan perintah `sudo adduser [namauser]` untuk membuat user, kemudian tekan `y`

Anda dapat mengubah `namauser` dengan nama yang ingin anda berikan pada user. kemudian isi data yang muncul di layar. untuk yang wajib di isi adalah.

```console
New password :
Retype new password :
```

Kemudian tekan `Y` untuk konfirmasi.

[![Screenshot-4668.png](https://i.postimg.cc/bwsVzB8H/Screenshot-4668.png)](https://postimg.cc/MnJm5tnv)

### 2.5 Ujicoba Access FTP

Anda bisa menggunakan file exploler pada windows atau dengan file exploler lainnya.

jika anda menggunakan file exploler pada windows, anda dapat mengetikan alamat ip servic seperti berikut

[![FTP](https://i.postimg.cc/bY9BLn3b/Whats-App-Image-2023-04-29-at-10-22-44.jpg)](https://postimg.cc/233GS1p8)

Kemudian tekan `Enter` dan anda akan di arahkan untuk melakukan login dengan memasukkan username dan password.

[![Output](https://i.postimg.cc/bl4Ba4ek/Whats-App-Image-2023-04-29-at-10-45-23.jpg)](https://postimg.cc/2d4g4fhr)

Setelah itu masukan Username and Password anda lalu tekan Log On. dan selamat anda sudah dapat melakukan Upload file pada server.
