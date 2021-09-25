# Jaringan Komputer C-09 (2021)
Laporan Resmi Jaringan Komputer Modul 1 - Crimping and Wireshark

NRP              | Nama
-----------------|-----------
05111940000014   | Ega Prabu Pamungkas
05111940000178   | Muhammad Rizqullah Akbar
05111940000227   | Rayhan Daffa Alhafish

## Soal No. 1 <br>
Pada soal ini diminta kita untuk menyebutkan webserver yang digunakan pada <i>ichimaru.tech</i>. Untuk menjawab pertanyaan tersebut terdapat beberapa langkah yang harus dilakukan yaitu : <br>
- Langkah pertama kita dapat melakukan display filter dengan command `http contains ""ichimarumaru.tech"`<br>
  ![ss-an](https://github.com/rayhandaffa/Jarkom-Modul-1-C09-2021/blob/main/ss-an/ss-no1-contains.jpg)
- Selanjutnya, pilih salah satu paket. Kemudian, untuk melihat detail paket dengan cara klik kanan pada mouse dan pilih Follow -> TCP Stream 
  ![ss-an](https://github.com/rayhandaffa/Jarkom-Modul-1-C09-2021/blob/main/ss-an/ss-no1-hasil.jpg)
- Finally, webserver yang digunakan pada link tersebut dapat dilihat pada bagian di bawah ini : <br> 
  ![ss-an](https://github.com/rayhandaffa/Jarkom-Modul-1-C09-2021/blob/main/ss-an/ss-no1-detailhasil.jpg)

Berdasarkan langkah-langkah di atas, dapat diketahui bahwasanya webserver yang digunakan adalah **nginx**

## Soal No. 2 <br> 
Soal no.2 ini meminta kita untuk menemukan paket dari web yang menggunakan basic authentication. Untuk dapat menemukan paket-paket tersebut cukup dengan menggunakan display filter `http.authbasic`. Berikut adalah hasil dari paket-paket yang menggunakan basic authentication : <br> 
![ss-an](https://github.com/rayhandaffa/Jarkom-Modul-1-C09-2021/blob/main/ss-an/ss-no2.png)
![ss-an](https://github.com/rayhandaffa/Jarkom-Modul-1-C09-2021/blob/main/ss-an/ss-no2-detail.jpg)

## Soal No. 3
Soal no.3 ini meminta kan untuk menemukan username dan password agar dapat masuk pada link <i>basic.ichimarumaru.tech</i>
Terdapat beberapa langkah untuk menemukan username dan password agar dapat masuk pada link tersebut: <br>
 - Langkah pertama yang kita dapat menggunakan display filter `http.host == basic.ichimaru.tech` dan pilihlah salah satu paket 
   ![ss-an](https://github.com/rayhandaffa/Jarkom-Modul-1-C09-2021/blob/main/ss-an/ss-no3-display.png)
 - Kemudian, lihat pada bagian <i>**Hypertext Transfer Protocol**</i> lalu lihat pada bagian <i>**Authorization**</i> nantinya akan ada sebuah <i>**Credentials**</i> yang dimana merupakan tempat username dan password itu berada. Untuk usernamenya adalah : **kuncimenujulautan** dan passwordnya yang ditemukan adalah : **tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN**
 ![ss-an](https://github.com/rayhandaffa/Jarkom-Modul-1-C09-2021/blob/main/ss-an/ss-no3-displaydetail.jpg)
 - Selanjutnya, buka link <i>basic.ichimarumaru.tech</i> dan login menggunkan username dan password yang ditemukan dan terdapat sebuah pertanyaan untuk menyebutkan urutan konfigurasi pengkabelan T586A 
 ![ss-an](https://github.com/rayhandaffa/Jarkom-Modul-1-C09-2021/blob/main/ss-an/ss-no3-hasil.png)
 
## Soal No. 4 
Untuk dapat menemukan paket-paket **mysql** dapat menggunakan display filter `mysql contains “select”`

## Soal No. 5 

## Soal No. 6 
**Cari username dan password ketika melakukan login ke FTP Server!**

Untuk mencari *username* dan *password* kita dapat menggnakan *display filter* `ftp contains "USER"` untuk mencari username. Dan untuk mencari password kita dapat menggunakan *display filter* `ftp contains "PASS"`.

**USER**

![6_1](/ss-an/6_1.png)

**PASS**

![6_2](/ss-an/6_2.png)

## Soal No. 7
**Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")**

Langkah pertama yaitu dengan menggunakan *display filter* `ftp-data and frame contains "Real.pdf"` untuk mencari file .zip yang memiliki bernama "Real.pdf"

**Filtering**

![7_1](/ss-an/7_1.png)

Kemudian *follow TCP STREAM* Selanjutnya ubah format ASCII ke RAW. Lalu save file .zip, selanjutnya buka file.

**Hasil**

![7_2](/ss-an/7_2.png)

## Soal No. 8
**Cari paket yang menunjukan pengambilan file dari FTP tersebut!**

Untuk mencari paket tersebut, maka menggunakan *display filter* `ftp-data` lalu cari menggunakan ctrl + F find by string "RETR"

**Hasil Filter**

![8_1](/ss-an/8_1.png)

Namun pada file 8-10.pcap tidak ada paket yang menunjukan file dari FTP Server.

## Soal No. 9
**Dari paket-paket yang menuju FTP terdapat inidkasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!**

Cari menggunakan *display filter* `ftp-data` lalu cari nama file menggunakan ctrl + F fin by string "secret.zip". Lalu follow TCP Stream dan ubah format ASCII ke RAW. Lalu safe file .zip, selanjutnya buka file.

**Hasil Filter**

![9_1](/ss-an/9_1.png)

Saat file secret.zip dibuka ternyata masih terkunci sehingga diperlukan untuk mencari *password*nya.

**File secret.zip**

![9_2](/ss-an/9_2.png)

Dari soal No.10 kami menemukan passwordnya yaitu "d1b1langbukanapaapajugagapercaya". Sehingga file secret.zip dapat terbuka.

**Isi file secret.zip**

![9_3](/ss-an/9_3.png)

## Soal No. 10
**Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!**

Sama seperti cara nomor sebelumnya, tapi menggunakan format ASCII untuk mendapatkan file log nya. pada file history.txt merupakan barisan kode *bash* dimana kode tersebut melakukan pengambilan password dari file bukanapaapa.txt untuk membuka file secret.zip.

**Hasil Filter**

![10_2](/ss-an/10_2.png)

**Isi file history.txt**

![10_1](/ss-an/10_1.png)

Lalu cari file bukanapa.txt menggunakan cara yang sama.

**Hasil Filter**

![10_3](/ss-an/10_3.png)

**Isi file bukanapaapa.txt**

![10_4](/ss-an/10_4.png)

## Soal No. 11
Untuk menampilkan paket-paket yang berasal dari port 80 dapat menggunakan _display filter_ `tcp.srcport == 80`

**_Display Filter_**
![11](/ss-an/11.jpeg)

## Soal No. 12
Untuk menampilkan paket-paket yang memiliki port 21 (menuju maupun berasal) dapat menggunakan _displat filter_ `tcp.port == 21` atau _capture filter_ `port 21`

**_Display Filter_**
![12](/ss-an/12.jpeg)

## Soal No. 13
Untuk menampilkan paket-paket yang memiliki tujuan port 443 dapat menggunakan _display filter_ `tcp.dstport == 443` atau _capture filter_ `dst port 443`

**_Display Filter_**
![13](/ss-an/13.jpeg)

## Soal No. 14
Untuk menampilkan paket-paket yang menuju ke **kemenag.go.id** dapat menggunakan _capture filter_ `dst host kemenag.go.id`

**Paket-paket yang menuju _kemenag.go.id_**
![14](/ss-an/14.jpeg)

## Soal No. 15
Untuk menampilkan paket-paket yang berasal dari IP komputer kalian, sebelumnya untuk mengetahui ip komputer kalian dapat mengetik command `ipconfig` pada terminal, setelah itu akan muncul ip komputer kalian. Setelah itu baru dimasukkan ke dalam wireshark dimana untuk _capture filter_ dapat menggunakan `src host [IP Komputer]` atau _display filter_ `ip.src_host == [IP Komputer]`

**ipconfig pada terminal**
![15-1](/ss-an/15-1.jpeg)

**Capture Filter**
![15-2](/ss-an/15-2.jpeg)

**Display Filter**
![15-3](/ss-an/15-3.jpeg)

## Kendala
Praktikum modul satu ini kebetulan bertepakan dengan adanya masalah pada jaringan indiehome dan telkomsel sehingga menjadi kendala untuk mendownload file .pcap yang disediakan, ditambah juga dengan ukuran yang besar. Namun, tidak menjadi kendala yang besar karena salah satu anggota kelompok dapat menggunakan VPN agar file dapat terdownload. Selain itu, masalah jaringan juga menjadi kendala dalam berkomunikasi dan berdiskusi antar anggota kelompok. Pada soal nomor 11 - 15 tidak diberikan kejelasan apakah harus menampilkan _display filter_ atau _capture filter_ sehingga ditulis keduanya.
