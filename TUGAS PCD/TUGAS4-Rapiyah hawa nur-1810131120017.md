# Laporan Tugas Pemrosesan Citra Digital

Mata Kuliah | Pemrosesan Citra Digital
--------|--------
Nim : 1810131120017
Nama: Rapiyah hawa nur 
# Cara menentukan pola Patterning
Sebagai contoh pada sebuah citra berukuran 3×3, nilai biner pada pusat citra dibandingkan dengan nilai sekelilingnya. Dengan cara membanding nilai piksel pada pusat citra dengan nilai piksel disekelilingnya, jika hasilnya lebih atau sama maka diberi nilai 1 dan jika hasilnya kurang maka diberi nilai 0. 
Secara umum algoritma ini mempunyai 2 langkah  :
1. Langkah thresholding.

Disini, semua nilai pixel disamping dari nilai yang diambil pada setiap pola akan dikomparasi dengan nilai yang ada dipusat diantara nilai – nilai pola mereka, ini untuk dikonversi nilai mereka menjadi nilai biner yaitu (0 dan 1).  Untuk nilai 0 yang mempunyai nilai lebih kecil dengan nilai pusat sedangkan nilai 1 untuk angka lebih besar dari nilai pusatnya. 

2. Langkah encoding

Kemudian dalam langkah encoding, sejumlah nilai biner yang diperoleh dari langkah thresholding akan dirubah atau dikonversi kedalam bilangan desimal untuk karakteristik dari struktur pola.  Nilai-nilai LBP selanjutnya direpresentasikan melalui histogram. Histogram menun Hasil akhir dari ekstraksi fitur menggunakan local binary pattern adalah hasil dari histogram tersebut, dimana satu citra memiliki ciri sebanyak 256 nilai yang merupakan frekuensi kemunculan dari nilai 0 s.d. 255. Pada contoh di atas, kita menggunakan matriks ketetanggaan sebanyak 8 (menggunakan window ukuran 3×3). Hasil yang lebih baik bisa didapat dengan menggunakan matriks ketetanggaan sebanyak 16, yakni dengan menggunakan window berukuran 5×5.

Untuk proses pengambilan ciri citra dapat menggunaan beberapa window selain yang berukuran 3 x3 adalah window 5 x 5. Ini dimaksudkan untuk mendapatkan ekstraksi ciri citra dengan beberapa window sehingga menjadi lebih optimal hasilnya.





# Cara menentukan matriks pada Ditherning

Image enhancement memiliki arti proses memanipulasi atau mengubah citra sehingga citra yang dihasilkan lebih cocok daripada citra input untuk tugas tertentu.

 Grayscalling adalah teknik yang digunakan untuk mengubah citra berwana (RGB) menjadi bentuk grayscale atau tingkat keabuan.Dengan pengubahan ini, matriks penyusun citra yang sebelumnya 3 matriks akan berubah menjadi 1 matriks saja.
 
Citra grayscale disebut juga citra satu kanal, karena warnanya hanya ditentukan oleh satu fungsi intensitas saja, artinya mempunyai skala abu dari 0 sampai 255, yang dalam hal ini nilai intensitas 0 menyatakan hitam, nilai intensitas 255 menyatakan putih.

Dalam komputasi, suatu citra digital grayscale atau greyscale adalah suatu citra dimana nilai dari setiap pixel merupakan sampel tunggal. Citra yang ditampilkan dari citra jenis ini terdiri atas warna abu-abu, bervariasi pada warna hitam pada bagian yang intensitas terlemah dan warna putih pada intensitas terkuat. 

 Pada citra grayscale warna bervariasi antara hitam dan putih, tetapi variasi warna diantaranya sangat banyak. Citra grayscale seringkali merupakan perhitungan dari intensitas cahaya pada setiap pixel pada spektrum elektromagnetik single band. Citra grayscale disimpan dalam format 8 bit untuk setiap sampel pixel, yang memungkinkan sebanyak 256 intensitas. Format ini sangat membantu dalam pemrograman karena manipulasi bit yang tidak terlalu banyak. Pada aplikasi lain seperti pada aplikasi medical imaging dan remote sensing biasa juga digunakan format 10,12 mau pun 16 bit. Citra grayscale disimpan dalam format 8 bit untuk setiap sampel pixel, yang memungkinkan sebanyak 256 intensitas.

Ada tiga transformasi tingkat abu-abu.
1. Transformasi linier
Transformasi linier meliputi identitas sederhana dan transformasi negatif. Transisi identitas ditunjukkan oleh garis lurus. Pada transisi ini, setiap nilai dari citra masukan langsung dipetakan satu sama lain dengan nilai citra keluaran. Itu menghasilkan gambar input dan gambar output yang sama. Dan karenanya disebut transformasi identitas.
2. Transformasi negatif
Merupakan kebalikan dari transformasi identitas. Dalam transformasi negatif, setiap nilai dari citra masukan dikurangkan dari L-1 dan dipetakan ke citra keluaran.
Dalam hal ini transisi berikut telah dilakukan.

            s = (L – 1) – r

    karena citra masukan Einstein adalah citra 8 bpp, maka jumlah tingkatan pada citra ini adalah 256. Dengan memasukkan 256 ke dalam persamaan, kita mendapatkan

            s = 255 – r

    Jadi setiap nilai dikurangi dengan 255 dan gambar hasil telah ditampilkan di atas. Jadi yang terjadi adalah, piksel yang lebih terang menjadi gelap dan gambar yang lebih gelap menjadi terang. Dan itu menghasilkan citra negatif.

3.  Transformasi logaritma
    - Transformasi log
Transformasi log dapat didefinisikan dengan rumus ini
s = c log(r + 1).
Dimana s dan r adalah nilai piksel dari output dan gambar input dan c adalah konstanta. Nilai 1 ditambahkan pada setiap nilai piksel citra masukan karena jika terdapat intensitas piksel 0 pada citra, maka log (0) sama dengan tak terhingga. Jadi 1 ditambahkan, untuk membuat nilai minimum setidaknya 1.
Selama transformasi log, piksel gelap dalam gambar diperluas dibandingkan dengan nilai piksel yang lebih tinggi. Nilai piksel yang lebih tinggi agak dikompresi dalam transformasi log. Ini menghasilkan peningkatan gambar berikut.
Nilai c dalam transformasi log menyesuaikan jenis peningkatan yang Anda cari
    - Kekuasaan – Transformasi hukum
Ada dua transformasi selanjutnya yaitu transformasi power law, yang meliputi transformasi pangkat ke-n dan transformasi akar ke-n. Transformasi ini dapat diberikan oleh ekspresi:
s=cr^γ
Simbol ini disebut gamma, karena itu transformasi ini juga dikenal sebagai transformasi gamma. Variasi nilai memvariasikan peningkatan gambar. Perangkat tampilan / monitor yang berbeda memiliki koreksi gamma sendiri, itulah sebabnya mereka menampilkan gambar mereka pada intensitas yang berbeda. Jenis transformasi ini digunakan untuk menyempurnakan gambar untuk berbagai jenis perangkat tampilan. Gamma perangkat tampilan yang berbeda berbeda. Misalnya Gamma CRT berada di antara 1,8 sampai 2,5, artinya gambar yang ditampilkan pada CRT gelap.