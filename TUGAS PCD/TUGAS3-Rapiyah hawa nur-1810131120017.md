# Tugas 3 Pemrosesan Citra Digital

Mata Kuliah | Pemrosesan Citra Digital
--------|--------
Nim : 1810131120017
Nama: Rapiyah hawa nur
# Menjelaskan tentang Method dan Grayscalle
<h2 align="center"><b> Grayscale </b></h2></p>
<p align="justify">Grayscale adalah berbagai nuansa warna monokromatik dari hitam menjadi putih. Oleh karena itu, gambar grayscale hanya memiliki warna abu-abu dan tidak berwarna. Sebuah gambar digital dapat disimpan sebagai grayscale (hitam dan putih), bahkan gambar berwarna berisi informasi grayscale.</p>

Di bawah ini, kita dapat melihat berbagai warna yang dapat digambarkan oleh model skala abu-abu :
<p align="center"><img src="/gambar/gambar28.jpg" width="600px"></p>
<h2 align="center"><b> Convert RGB to Grayscale </b></h2></p>
<p align="center"><img src="/gambar/gambar29.JPG" width="500px">
> ## Ligthness Method
Dimasukkan dalam rumus
```matlab
grayscale = (min(R,G,B) - max (R,G,B)) / 2
```
<p align="justify">Metode yang sangat sederhana adalah dengan mengambil nilai rata-rata yaitu menjumlahkan nilai tertinggi dan terendah. Kita dapat dengan mudah melihat bahwa metode ini menghadirkan kelemahan yang sangat serius karena satu komponen RGB tidak digunakan. Ini jelas merupakan masalah karena jumlah cahaya yang dilihat mata kita bergantung pada ketiga warna dasar. 
> ## Average Method
Dimasukkan dalam rumus
```matlab
grayscale = (R + G + B) / 3
```
  
<p align="justify">Cara lain adalah dengan mengambil nilai rata-rata dari ketiga komponen (merah, hijau, dan biru). Berdasarkan penelitian tentang penglihatan manusia, kita tahu bahwa mata kita bereaksi terhadap setiap warna dengan cara yang berbeda. Secara khusus, mata kita lebih sensitif terhadap hijau, lalu merah, dan akhirnya biru. Oleh karena itu, bobot dalam persamaan di atas harus berubah.
> ## Luminosity Method
Dimasukkan dalam rumus
```matlab
grayscale = (0.3 * R) + (0.59 * G) + (0.11 * B) 
```
<p align="justify">Metode terbaik adalah metode luminositas yang berhasil memecahkan masalah metode sebelumnya. Berdasarkan pengamatan di atas, kita harus mengambil rata-rata tertimbang dari komponen. Kontribusi warna biru pada nilai akhir harus berkurang, dan kontribusi warna hijau harus meningkat. Metode lightness cenderung mengurangi kontras.

# _HALFTONING_
<p align="justify">Halftoning atau halftoning analog adalah proses yang mensimulasikan nuansa abu-abu dengan memvariasikan ukuran titik-titik hitam kecil yang diatur dalam pola yang teratur. Teknik ini digunakan dalam printer, serta industri penerbitan. 

 Halftoning digital mirip dengan halftoning di mana gambar didekomposisi menjadi kotak sel halftone. Elemen (atau titik yang digunakan halftoning dalam mensimulasikan nuansa abu-abu) dari sebuah gambar disimulasikan dengan mengisi sel halftone yang sesuai. 
<p align="center"><img src="/Gambar/Gambar-Tugas-3/3.png" width="400px">
  

<p align="justify">Digital halftoning adalah suatu proses untuk mengkonversi citra yang kontinu ke dalam suatu array berupa titik-titik. Jika dilihat oleh sistem visual manusia, pola tersebut akan menciptakan suatu ilusi sehingga citra tersebut tampak bukan seperti citra hitam putih, namun seperti citra abu-abu yang kontinu. Metode yang paling sederhana untuk mengkonversi citra abu-abu menjadi citra biner adalah dengan menggunakan ambang batas, yaitu dengan dua tingkat (satu bit) kuantisasi. Misalkan f(i,j) adalah sebuah citra abu-abu, dan b(i,j) adalah citra yang dihasilkan dari metode ambang batas yang sederhana. Untuk ambang batas T, citra biner dihitung dengan sebagai berikut:

  > _b(i, j) = 255 if f(i, j) > T and 0 else_
<p align="justify">Halftoning bertujuan untuk memberikan kesan warna citra biner tampak seperti citra abu-abu meskipun hanya menggunakan piksel warna hitam dan putih saja. 


# _PATTERNING_
<p align="justify">Pola adalah yang paling sederhana dari tiga teknik untuk menghasilkan gambar halftoning digital. Ini menghasilkan gambar yang memiliki resolusi spasial lebih tinggi daripada gambar sumber. Jumlah sel halftone citra keluaran sama dengan jumlah piksel citra sumber. Namun, setiap sel halftone dibagi lagi menjadi kotak 4x4. Setiap nilai piksel input diwakili oleh jumlah kotak terisi yang berbeda dalam sel halftone. Karena kisi 4x4 hanya dapat mewakili 17 tingkat intensitas yang berbeda, gambar sumber harus dikuantisasi. Gambar dibawah menunjukkan matriks pola rekursif Rylander.
<p align="center"><img src="/gambar/gambar30.JPG" width="400px">
<p align="center"><i>Matriks pola rekursif Rylander</i>
<p align="center"><img src="/gambar/gambar31.JPG" width="500px">
<p align="center"><i>Operasi Pola</i>
<p align="justify">Pattern menghasilkan gambar halftoning digital dari gambar input menggunakan teknik pola. Pola program membaca gambar input, mengkuantisasi nilai piksel, dan memetakan setiap piksel ke pola yang sesuai. Gambar yang dihasilkan 16 kali lebih besar dari aslinya. Gambar yang dihasilkan ditulis ke file output sebagai file TIFF. Sebuah kata peringatan: "pola" membutuhkan banyak perhitungan, gambar berukuran kurang dari 100x100 direkomendasikan.



# _DITHERING_

<p align="justify">Teknik lain yang digunakan untuk menghasilkan gambar halftoning digital adalah dithering. Tidak seperti pola, dithering membuat gambar keluaran dengan jumlah titik yang sama dengan jumlah piksel pada gambar sumber. Dithering dapat dianggap sebagai thresholding gambar sumber dengan matriks gentar. Matriks diletakkan berulang kali di atas gambar sumber. Dimanapun nilai piksel gambar lebih besar dari nilai dalam matriks, titik pada gambar output diisi. Masalah dithering yang terkenal adalah menghasilkan artefak pola yang diperkenalkan oleh matriks ambang batas tetap. Gambar 4.5 menunjukkan contoh operasi dithering.

<p align="center"><img src="/gambar/gambar32.jpg" width="800px">
\
