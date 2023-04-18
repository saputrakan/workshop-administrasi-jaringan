Kelompok 4:
- Sandy Putra Pradana
- Obed Christian Sanjaya
- Muhammad Rizqy Ferdiansyah
- Daffa Ridwhan Ramadhan
# Setting lokal NTP VMWare Debian

Pertama yang dilakukan adalah menginstall "ntp" nya seperti pada gambar dibawah ini

![Image description](https://i.postimg.cc/tg4Wksbj/npm-Install.jpg)

Setelah menginstall lalu masuk ke konfigurasi, dan edit file konfigurasi 

![Image description](https://i.postimg.cc/4dM6msrT/gedit.jpg)

Lalu baris paling bawah tambahkan kode yang menunjukan netword ID dari komputer dan netmask nya juga, dan Restart service dari ntp, lalu melakukan pengecekan status untuk memastikan ntp berjalan dengan baik.

![Image description](https://i.postimg.cc/qv08tmZg/restart.jpg)

lakukan command dibawah untuk mengecek apakah server ntp sudah ditambahkan, dan hasilnya seperti pada gambar dibawah ini.

[![ntpq.jpg](https://i.postimg.cc/g0gqbvsj/ntpq.jpg)](https://postimg.cc/qtCC869H)
