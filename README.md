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
