# Laporan Konfigurasi DNS Server pada Linux Workshop Administrasi Jaringan

### Dosen pengampu: Dr. Ferry Astika Saputra. S.T, M. Sc.
### Kelas : 2 D4 Teknik Informatika A

### 1. Sandy Pradana Putra (3121600017)

### 2. Obed Christian S (3121600022)

### 3. Muhammad Rizqy F (3121600024)

### 4. Daffa Ridwan R (3121600027)


#
## DNS ?
Domain Name Server atau DNS adalah sebuah sistem yang menghubungkan Uniform Resource Locator (URL) dengan Internet Protocol Address (IP Address). Dengan menggunakan DNS maka akan lebih lebih mudah untuk dipakai dan juga akan lebih aman.

DNS adalah sistem yang meringkas pekerjaan ini untuk Anda. Kini, Anda tinggal mengingat nama domain dan memasukkannya dalam address bar. DNS kemudian akan menerjemahkan domain tersebut ke dalam IP Address yang komputer pahami contoh mengakses Google. kita tidak menulis 172.217.0.142 ke dalam address bar, namun memasukkan alamat Google.com. 

## Fungsi DNS
1. Meminta informasi IP Address sebuah website berdasarkan nama domain
2. Meminta informasi URL sebuah website berdasarkan IP Address yang dimasukkan;
3. Mencari server yang tepat untuk mengirimkan email.


## Macam-Macam DNS
Berikut adalah 10 DNS record yang paling sering dijumpai:

1. A Record atau Address record ─ menyimpan informasi soal hostname, time to live (TTL), dan IPv4 Address.
2. AAA Record ─ menyimpan informasi hostname dan hubungannya dengan IPv6 address.
3.  MX Record ─ merekam server SMTP yang khusus digunakan untuk saling berkirim email di suatu domain.
4.  CNAME Record ─ digunakan untuk me-redirect domain atau subdomain ke sebuah IP Address. Lewat fungsi satu ini, Anda tak perlu memperbarui DNS record.
5.  NS Record ─ merujuk subdomain pada authoritative name server yang diinginkan. Record ini berguna jika subdomain Anda di web hosting berbeda dengan domain.
6. PTR Record ─ memberikan izin pada DNS resolver untuk menyediakan informasi soal IP Address dan menampilkan hostname (reverse DNS lookup).
7. CERT Record ─ menyimpan sertifikat enkripsi atau sertifikat keamanan.
8. SRV Record ─ menyimpan informasi terkait lokasi komunikasi, semacam Priority, Name, Weight, Port, Points, dan TTL
9. TXT Record ─ membawa dan menyalurkan data yang hanya bisa dibaca oleh mesin.
10. SOA Record ─ bagian yang muncul di awal dokumen DNS zone. Bagian yang sama juga merujuk pada Authoritative Name Server serta informasi lengkap sebuah domain.
#
## Langkah - Langkah untuk Instalasi dan Konfigurasi DNS

## Demo Konfigurasi DNS
[Demo Konfigurasi DNS](https://drive.google.com/file/d/1-qWYChJnH_8Af3fPv31fWJJVwdMGwgTS/view)


## Instalasi DNS
1. Melakukan pembaruhan untuk linux (kali ini saya memakai Ubuntu)
```
> sudo apt-get update
> sudo apt-get upgrade
```

2. Menginstall package **bind9** dan **bind9utils**
```
> sudo apt-get install bind9 bind9utils
```

## Konfigurasi DNS

1. Buka file named-conf, disini kami menggunakan software nano untuk mengeditnya

   ![image](https://user-images.githubusercontent.com/89308108/231804943-b1cd9457-ffc0-415e-bc8d-3c433c15b2d3.png)
    
    Mengganti konfigurasi pada named-conf
 
    ![image](https://user-images.githubusercontent.com/89308108/231805433-abf83714-bb13-4a59-bb75-a78890e68d5b.png)
        
    isi dari /etc/bind/named.conf.option
    ![image](https://user-images.githubusercontent.com/89308108/231806573-1f7efc9f-c56d-4526-8808-bb46ba3362f0.png)
    
    isi dari /etc/bind/named.conf.local
    ![image](https://user-images.githubusercontent.com/89308108/231808861-894e41d0-cbbe-4b8a-a21e-90c7ab4e17a4.png)
    
    isi dari /etc/bind/named.conf.default.zones
    ![image](https://user-images.githubusercontent.com/89308108/231809455-0724eace-b1b8-40d5-9e7e-454727d72af0.png)


2. Membuka file forward sesuai dengan tempat file tersebut disimpan

   ![image](https://user-images.githubusercontent.com/89308108/231810306-87b4fc2b-691a-430c-8023-748f32496f3d.png)

   Mengganti konfigurasi pada forward

   ![image](https://user-images.githubusercontent.com/89308108/231809876-165599ca-1b61-4bf8-82f9-06f226b02d74.png)

   
   Rubahkan root menjadi ns, localhost name dengan hostname "kampus-04.takehome.com", dan juga IPnya sesuaikan dengan IP anda. lalu ikuti konfigurasi dibawahnya


3. Membuka file reverse sesuai dengan tempat file tersebut disimpan

   ![image](https://user-images.githubusercontent.com/89308108/231811674-e2381b46-4285-4f1b-8b1d-065e1cfaaed8.png)

   Mengganti konfigurasi pada forward
   
   ![image](https://user-images.githubusercontent.com/89308108/231812096-320d9434-0aff-4425-a487-94e8af853cbb.png)

   Rubahkan root menjadi ns, localhost name dengan hostname "kampus-04.takehome.com", dan 1.0.0 menjadi bilangan IP okter terakhir anda. lalu ikuti konfigurasi dibawahnya

4. Konfigurasi resolve
![image](https://user-images.githubusercontent.com/89308108/231812617-12369a03-e5e0-4825-b5c3-1694cba41e96.png)

5. Restart Bind9 dan Cek status bind9
   ```
   > systemctl restart bind9.service
   > systemctl status bind9.service
   ```
   ![image](https://user-images.githubusercontent.com/89308108/231813226-c4d7e057-cc57-4826-9684-5f2563a49320.png)

#
## Pengujian DNS
1. Menginstall package **dnsutils**
    ```
    > sudo aptinstall dnsutils
    ```


2. Melakukan pengujian

   ![image](https://user-images.githubusercontent.com/89308108/231813743-b3018452-5e7c-48e4-b8ab-3c933d61cb36.png)
   ![image](https://user-images.githubusercontent.com/89308108/231814409-ff0c29c5-8967-467d-8c61-4d59c8a0bbb3.png)
