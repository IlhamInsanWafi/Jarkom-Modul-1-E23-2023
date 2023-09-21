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
karena pada soal 1 mengambil contoh aktivitas mengunggah suatu file, maka bisa lebih cepat lagi kita search dengan `STOR` (perintah unggah)
```
ftp.request.command == STOR
```
Setelah itu, pilih sesuai perintah


pada sisi bawah terdapat beberapa panel, klik panel `Transmission Control Protocol` terdapat keterangan untuk menjawab `1a,b`


untuk `1c,d` karena perintah soal menunjukkan response dari aktivitas sebelumnya, maka kita bisa search pada display filter `ftp.response.code == 150`
`150` bentuk kode respons setelah klien mengirim perintah `STOR`
tetapi lebih cepat jika kita langsung pilih packet setelah `STOR` tadi. Setelah itu langkahnya sama seperti `1a,b`


setelah itu copy 
```
nc 10.21.78.111 12345
```
pada terminal, jika masih salah jangan berkecil hati, tetapi jika benar akan muncul flag untuk submit pada platform praktikum.

---
### Soal 2
---
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

---
### Jawaban
---

Search pada display filter:
```
http.server
```
pilih salah satu packet dengan protocol `HTTP` kemudian klik kanan pilih `Follow` kemudian `TCP Stream`


muncul keterangan server untuk menjawab perintah soal.


setelah itu copy 
```
nc 10.21.78.111 13579
```
pada terminal, jika masih salah jangan frustasi, tetapi jika benar akan muncul flag untuk submit pada platform praktikum.




