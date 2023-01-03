# Tugas 5 Pemrosesan Citra Digital

Mata Kuliah | Pemrosesan Citra Digital
--------|--------
Nim  : 1810131120017
Nama : Rapiyah hawa nur

## Tugas 5
# Membuat Pseudo Code dari pola Patterning, Ditthering, Bit Plane Slacing, dan Histogram Equalization
## Pseudo Code Pathering
Untuk Pathering, Berdasarkan analisis yang saya lakukan, didapatkan algoritmanya seperti berikut
### Citra Digital Grayscale
Disini saya menggunakan pseudo code untuk program PYTHON

```python
print("""Disini saya menggunakan citra yang berukuran 3 x 3, sehingga untuk banyaknya level/banyak pola 
adalah 10 pola yang didapatkan dari 3 x 3 + 1 = 10, adapun algoritmanya seperti berikut""")
print("""Dari 256 level warna, akan dibagi untuk menjadi 10 pola, sehingga 256/10 = 25,6 yang
dibulatkan menjadi 26 dan didapatkanlah pada masing-masing pola terdapat 26 panjang rentangan.""")
print("Pola ke-1 didapat dari rentang 0-25")
pola_1 = [[0,0,0], [0,0,0], [0,0,0]]
print("Pola 2 didapat dari rentang 26-51")
pola_2 = [[0,0,0], [0,0,0], [0,0,1]]
print("Pola ke-3 didapat dari rentang 52-77")
pola_3 = [[1,0,0], [0,0,0], [0,0,1]]
print("Pola ke-4 didapat dari rentang 78-103")
pola_4 = [[1,0,1], [0,0,0], [0,0,1]]
print("Pola ke-5 didapat dari rentang 104-129")
pola_5 = [[1,0,1], [0,0,0], [1,0,1]]
print("Pola ke-6 didapat dari rentang 130-155")
pola_6 = [[1,0,1], [0,0,0], [1,1,1]]
print("Pola ke-7 didapat dari rentang 156-181")
pola_7 = [[1,0,1], [1,0,0], [1,1,1]]
print("Pola ke-8 didapat dari rentang 182-207")
pola_8 = [[1,0,1], [1,0,1], [1,1,1]]
print("Pola ke-9 didapat dari rentang 208-233")
pola_9 = [[1,1,1], [1,0,1], [1,1,1]]
print("Pola ke-10 didapat dari rentang 234-259")
pola_10 = [[1,1,1], [1,1,1], [1,1,1]]
gambar = []
for(x = 1; x < gambar.length; x++):
    for(y = 1; y < gambar.length; y++):
        if(gambar[x,y] >=0 and gambar[x,y] <= 25):
            gambar[x,y] = pola_1
        elif(gambar[x,y] >=26 and gambar[x,y] <= 51):
            gambar[x,y] = pola_2
        elif(gambar[x,y] >=52 and gambar[x,y] <= 77):
            gambar[x,y] = pola_3
        elif(gambar[x,y] >=78 and gambar[x,y] <= 103):
            gambar[x,y] = pola_4
        elif(gambar[x,y] >=104 and gambar[x,y] <= 129):
            gambar[x,y] = pola_5
        elif(gambar[x,y] >=130 and gambar[x,y] <= 155):
            gambar[x,y] = pola_6
        elif(gambar[x,y] >=156 and gambar[x,y] <= 181):
            gambar[x,y] = pola_7
        elif(gambar[x,y] >=182 and gambar[x,y] <= 207):
            gambar[x,y] = pola_8
        elif(gambar[x,y] >=208 and gambar[x,y] <= 233):
            gambar[x,y] = pola_9
        elif(gambar[x,y] >=234 and gambar[x,y] <= 259):
            gambar[x,y] = pola_10
        else:
            print('level warna tidak ada')
            
print(gambar)
```
### **Pseudo Code Dithering**
Untuk Dithering, Berdasarkan analisis yang saya lakukan, didapatkan lah algooritmanya seperti berikut
```javascript
    Trashold = [100 150 ; 200 50]
    for(x = 1; x < gambar.length; i++){
        if(x%2 == 1){
            for(y = 1; y < gambar.length; y++){
                if(y%2 == 1){
                    if(gambar[x,y] >= Trashold[1,1]){
                        gambar[x,y] = 1;
                    }
                    else{
                        gambar[x,y] = 0;
                    }
                }
                else{
                    if(gambar[x,y] >= Trashold[1,2]){
                        gambar[x,y] = 1;
                    }
                    else{
                        gambar[x,y] = 0;
                    }
                }
            }
        }
        else{
            for(y = 1; y < gambar.length; y++){
                if(y%2 == 1){
                    if(gambar[x,y] >= Trashold[2,1]){
                        gambar[x,y] = 1;
                    }
                    else{
                        gambar[x,y] = 0;
                    }
                }
                else{
                    if(gambar[x,y] >= Trashold[2,2]){
                        gambar[x,y] = 1;
                    }
                    else{
                        gambar[x,y] = 0;
                    }
                }
            }
        }
    }
```

### Algoritma Patterning
Langkah-langkah
1. Siapkan matriks yang berisi angka, baik itu matriks 2 x 2, 3 x 3 atau yang lainnya. Tujuannya adalah untuk menentukan pola yang akan digunakan dari angka yang dikandungnya.
2. Tentukan matriks yang diperbesarnya, misal 3 x 3, berarti akan ada 10 jenis pola. Hal itu didapat dari 3 x 3 = 9 ditambah 1. Kemudian, untuk menentukan interval tiap-tiap pola, adalah dengan 10/255 = 26.
~ jadi, tiap satu pola memuat angka yang panjangnya 26 (Dimulai dari angka 0 sampai dengan 255)
~ untuk 4 x 4 yaitu -> 4 x 4 = 16 + 1 = 17. Tinggal menentukan interval untuk 17 pola, begitu juga 5 x 5 dan seterusnya.
3. Membuat pola yang pengambilan polanya ditentukan oleh matriks yang telah disiapkan di awal.
Kesimpulannya, matriks sebagai patokan, memasang pola dengan panjang interval sesuai dengan matriks yang diperbesarnya, lalu membuat pola dengan menyesuaikan angka dalam matriks dengan pola yang berisi interval.
### Algoritma Dithering
Langkah-langkah
1.Siapkan matriks satu yang berisi angka
2. Siapkan matriks dua yang akan menjadi bahan perbandingan dengan matriks sebelumnya
3. Apabila perbandingan tiap ordo yang selaras, matriks dua lebih kecil dari matriks satu, maka kotaknya akan berwarna hitam. Sebaliknya, apabila matriks dua lebih besar daripada matriks satu, maka kotaknya akan berwarna putih.
Kesimpulannya, harus ada matriks satu dan matriks dua yang akan dibandingkan. Matriks dua yang menjadi penentu warna hitam atau putih.
###  Penyetaraan Histogram Algoritma
Kata Kunci
Pembuatan Histogram berhubungan dengan hasil perhitungan dari Grayscale Enhancement. Jadi, sebelum mencapai pembuatan histogram, kita harus menghitungnya terlebih dahulu.
Langkah-langkah
1. Menentukan gambar dan membagi total pixel. Misal, ada gambar 3 bit, maka gray levelnya adalah 8. Dan sebanyak 8 buah macam pula pixel-pixel yang dibuat atau keluar. Biasanya dua macam ini berasal dari pembuatan soal atau permasalahan awal, jadi kita hanya perlu melanjutkan ke langkah selanjutnya.
2. Yang kedua adalah menjumlah semua piksel dari awal hingga akhir.
3. Hasil akhir dari penjumlahan keseluruhan tersebut adalah penentu yang menjadi pembagi piksel masing-masing.
4. Kemudian mengalikan pixel yang dibagi berdasarkan jumlah keseluruhan pixel dengan banyaknya gray level satu demi satu, misal gray level ada 7, maka : (pixel / sumpixel)*gray level
5. Hasil dari perhitungan tersebut dibulatkan
6. Menghitung kembali hasil dari rumus di atas dengan memperhatikan tingkat keabuan dan jumlah piksel yang disediakan pada langkah pertama tadi. Jadi, ada tiga hal yang akan kita perhatikan, yaitu hasil akhir, tingkat keabuan dan no pixel --yang kemudian akan menghasilkan no pixel yang baru untuk pembuatan histogram.
Jika langkah-langkah di atas sudah selesai, kita tinggal memperhatikan pembuatan histogram. Hal yang harus diperhatikan adalah gray level dan no pixel, dan khusus no pixel ini diambil dari hasil perhitungan sebelumnya. Arah panah x mendatar adalah angka untuk gray level, sedangkan aray panah y tegak lurus merupakan angka no of pixel. Jadi, tinggi rendahnya titik histogram dapat ditentukan setelah kita menyelesaikan tugas di atas.
Kesimpulannya, pembuatan histogram harus menyelesaikan perhitungan peningkatan grayscale terlebih dahulu, lalu hasil akhir perhitungan tersebut yang menentukan tinggi atau banyaknya piksel pada tiap-tiap level.
##  Algoritma Bit Place Slicing
Algoritma ini berhubungan dengan biner, yang tujuannya adalah memotong bit / area warna grayscale pada sebuah gambar. Hal pertama yang harus kita ketahui adalah pemotongan daerah secara umum terlebih dahulu, yaitu :
~ 0 untuk angka yang tidak digunakan
~ 1 untuk angka yang digunakan
Dalam biner, ada 8 buah angka desimal, di antaranya :
128 | 64 | 32 | 16 | 8 | 4 | 2 | 1
Langkah-langkah
1. Pelajari cara merubah angka desimal menjadi angka biner
2.Siapkan matriks yang berisi angka
3. Lihat angkanya lalu ubah ke dalam bentuk biner
Contoh
| 64 59 |
| 77 123 |
<br>
Mengiris Tempat Bit
| 01000000 00111011 |
| 01001101 01111011 |
Kesimpulannya, algoritma ini merupakan metode kontribusi atau pengaruh tiap bit penyusun citra, tujuannya adalah merubah angka desimal menjadi angka biner.