#  Hasil Eksplorasi Octave menggunakan Package image
#  Eksplorasi Octave menggunakan Package image

<p align="center"><img src="/gambar/gambar33.jpg" width="600px"></p>
<p align="center"><img src="/gambar/gambar34.jpg" width="600px"></p>
<p align="center"><img src="/gambar/gambar35.jpg" width="600px"></p>
<p align="center"><img src="/gambar/gambar36.jpg" width="600px"></p>

Jelaskan ada berapa layer pada gambar berwarna! 
1. screenshot hasil ekplorasi layer pada aplikasi octave.Gunakan fungsi (1) imread, (2) imshow (3) dan imhist.
2.  jelaskan fungsi2 tersebut disertakan screenshot.
jawab:

Seperti hasil yang sudah kita lakukan diatas, bahwa sebuah gambar berwarna terdiri atas 3 layer, yaitu merah, hijau, dan biru, dan menurut eksplorasi saya, gambar yang saya gunakan lebih dominan berwarna hijau, karena pada layer hijau gambar terlihat lebih cerah dari gambar pada layer biru ataupun merah.

<p align="center"><img src="/gambar/gambar36.jpg" width="600px"></p>
 
Adapun untuk membahas tentang imhist, imread, dan imshow, berikut adalah kode yang saya ketikkan waktu mengeksplorasi pada oktave dengan foto berwarna dan berdimensi 32 bit.
Dari gambar di atas dapat di simpulkan bahwa suatu gambar terbagi menjadi 3 layer yaitu layer Red, Green, dan Blue
Suatu gambar terbagi menjadi 3 layer yaitu layer Red, Green, dan Blue

### **imhist**
Penggunaan imhist ditujukan untuk menampilkan histogram dari sebuah gambar
### **imread**
Adapun fungsi imread, itu seperti membaca sebuah foto, jika pada html bisa seperti src di tag `<img>` 
### **imshow**
Dan terakhir ada imshow untuk menampilkan fotonya atau gambar.
### **Eksplorasi yang lain**
Adapun beberapa hal yang saya dapat diluar imread, imhist, dan imshow, kita sebelumnya harus menentukan warna apa yg akan kita tampilkan, misal pada varial `Red = cat(R,G*0,B*0);` disini artinya menyimpan gambar yang terfokus pada layer merah saja dan juga untuk yang Blue, dan Green juga sama, hanya saja kita rubah yang R dikalikan 0 dan G tidak untuk di simpan di variabel Green.
Dan untuk menampilkan gambar sebelum imshow, kita juga memerlukan subplot untuk mengatur tata letak gambarnya.