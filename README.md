# Jarkom-Modul-1-E23-2023
Laporan Resmi Praktikum Jaringan Komputer
***
## Anggota Kelompok
1. Ilham Insan Wafi (5025211255)
2. Elmira Farah Azalia (5025211197)

---
### Soal 1
---
nc 10.21.78.111 12345

User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.

a. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? 

b. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 

c. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

d. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

---
### Jawaban
---
Search pada display filter:
```
ftp 
```
karena pada soal 1 mengambil contoh aktivitas mengunggah suatu file, maka bisa juga search dengan `STOR` (perintah unggah)
```
ftp.request.command == STOR
```
![soal1.1](img/soal1.1.png)
setelah itu pilih sesuai perintah,
![soal1.2](img/soal1.2.png)
pada sisi bawah terdapat beberapa panel, klik panel `Transmission Control Protocol..` untuk menemukan jawaban `1a,b`
![soal1.3](img/soal1.3.png)

Kemudian untuk `1c,d` karena perintah soal menunjukkan response dari aktivitas sebelumnya, maka kita bisa search pada display filter: 
```
ftp.response.code == 150
```
`150`= bentuk kode respons setelah klien mengirim perintah `STOR`
agar lebih cepat, langsung pilih packet setelah `STOR` tadi. Setelah itu langkahnya sama seperti `1a,b`
![soal1.4](img/soal1.4.png)

Untuk menjawab soal, copy`nc 10.21.78.111 12345`pada terminal, jika masih salah jangan berkecil hati, tetapi jika benar akan muncul flag untuk submit pada platform praktikum.
![soal1.5](img/soal1.5.png)

---
### Soal 2
---
nc 10.21.78.111 13579

Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

---
### Jawaban
---

Search pada display filter:
```
http.server
```
![soal2.1](img/soal2.1.png)
pilih salah satu packet dengan protocol `HTTP` kemudian klik kanan pilih `Follow` kemudian `TCP Stream`
![soal2.2](img/soal2.2.png)
muncul keterangan server untuk menjawab perintah soal.
![soal2.3](img/soal2.3.png)

Setelah itu copy`nc 10.21.78.111 13579`pada terminal, jika masih salah jangan frustasi, tetapi jika benar akan muncul flag untuk submit pada platform praktikum.
![soal2.4](img/soal2.4.png)

---
### Soal 3
---
nc 10.21.78.111 13590

Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:

a. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?

b. Protokol layer transport apa yang digunakan?

---
### Jawaban
---










---
### Soal 4
---
nc 10.21.78.111 13591

Berapa nilai checksum yang didapat dari header pada paket nomor 130?

---
### Jawaban
---
Search pada display filter:
```
frame.number == 130
```
perintah tersebut akan mengarahkan langsung pada paket 130
![soal4.1](img/soal4.1.png)
lalu, pada sisi kiri bawah klik panel `User Data Protocol..` dapat-lah jawaban nilai cheksum.
![soal4.2](img/soal4.2.png)
copy`nc 10.21.78.111 13591` pada terminal untuk mendapatkan kenyataan yang sebenarnya, jangan senang dahulu wahai manusia byasa. Jika berhasil dan mendapatkan flag, submit pada platform praktikum.
![soal4.3](img/soal4.3.png)

---
### Soal 5
---
Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.

a. Berapa banyak packet yang berhasil di capture dari file pcap tersebut?

b. Port berapakah pada server yang digunakan untuk service SMTP?

c. Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?

---
### Jawaban
---






---
### Soal 6
---
nc 10.21.78.111 6666

Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

---
### Jawaban
---





---
### Soal 7
---
nc 10.21.78.111 6565

Berapa jumlah packet yang menuju IP 184.87.193.88?

---
### Jawaban
---
Search pada display filter:
```
ip.dst == 184.87.193.88
```
![soal7.1](img/soal7.1.png)
perintah akan menunjukkan semua paket dengan destinasi (tujuan) ip 184.87.193.88
![soal7.2](img/soal7.2.png)
pada sisi kanan bawah juga tercantum berapa total paket yang menuju ip tersebut.

Seperti biasa, copy`nc 10.21.78.111 6565` pada terminal, please jangan sombonk dulu, buktikanlah..buktikanlah.. jika sudah benar, bersyukur, submit ke platform praktikum.
![soal7.3](img/soal7.3.png)


---
### Soal 8
---
nc 10.21.78.111 7171

Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)

---
### Jawaban
---






---
### Soal 9
---
nc 10.21.78.111 7272

Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!

---
### Jawaban
---






---
### Soal 10
---
nc 10.21.78.111 7373

Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet

---
### Jawaban
---


