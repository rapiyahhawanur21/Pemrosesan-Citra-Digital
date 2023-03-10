#  Tugas 7 Pemrosesan Citra Digital

Mata Kuliah | Pemrosesan Citra Digital
--------|--------
Nim : 1810131120017
Nama:  Rapiyah hawa nur
## **Tugas 7**
## Menjelaskan spatial dan frequency domain dengan bahasa yang mudah
## Sebutkan metode spatial
## Menjelaskan Spatial Domain dan Frequency Domain dengan bahasa yang mudah
Teknik (Image Enhnacment) atau peningkatan kualitas citra dapat dibagi menjadi dua kategori berdasarkan ranah operasinya yaitu:
1. Domain Spasial : Suatu citra dapat direpresentasikan dalam bentuk matriks 2D dimana setiap elemen matriks merepresentasikan intensitas piksel. Keadaan matriks 2D yang menggambarkan distribusi intensitas suatu gambar disebut Domain Spasial. 
2. Domain Frekuensi : Dalam metode domain frekuensi didasarkan pada Transformasi Fourier dari suatu citra. Secara kasar, istilah frekuensi dalam sebuah gambar menceritakan tentang laju perubahan nilai piksel.Secara kasar, istilah frekuensi dalam sebuah gambar menceritakan tentang laju perubahan nilai piksel.

### Processing

Cara paling mudah untuk melakukan peningkatan mutu pada domain spatial adalah dengan melakukan pemrosesan yang hanya melibatkan satu piksel saja (tidak menggunakan jendela ketetanggaan). Pengolahan menggunakan histogram juga termasuk dalam bagian point processing. Operasi titik disebut juga operasi _pointwise_, yang terdiri dari pengaksesan pixel pada lokasi yg diberikan, memodifikasinya dengan operasi linier atau non linier, menempatkan nilai piksel baru pada lokasi yang bersesuaian di dalam citra yg baru.

Operasi ini dapat dibagi menjadi 3 macam :
1. Berdasarkan intensitas --> Contrast stretching, Image Negative, Histogram equalization, Image Substration, Image Averaging.

2. Berdasarkan geometri --> Posisi pixel diubah ke posisi yg baru, sedangkan intensitasnya tidak berubah. Contoh : rotasi, translasi, penskalaan (dilatasi), distorsigeometri.

3. Gabungan keduanya --> Operasi ini tidak hanya mengubah nilai intensitas pixel, tapi juga mengubah posisinya. Misal: _image morphing_ yaitu perubahan bentuk objek beserta intensitasnya.

###  Processing

Jika pada point processing kita hanya melakukan operasi terhadap masing-masing piksel, maka pada mask processing kita melakukan operasi terhadap suatu jendela ketetanggaan pada citra. Kemudian kita menerapkan (mengkonvolusikan) suatu mask terhadap jendela tersebut. Masksering juga disebut filter. Filtering pada citra adalah suatu proses dimana diambil sebagian sinyal dari frekuensi tertentu dan membuang sinyal pada frekuensi yang lain.

   Contoh: Jendela ketetanggan 3x3, nilai piksel pada posisi x dipengaruhi oleh nilai 8 tetangganya.

   | 1 | 2 | 3 |
   |:----:| :----:| :----: |
   | 8 | X | 4 |
   | 7 | 6 | 5 |

   Perbedaan dengan point processing: pada point processing, nilai suatu piksel tidak dipengaruhioleh nilai tetangga-tetangganya.

## Metode Domain Frequency (Image enhancement dalam ranah frekuensi)

Citra domain frekuensi merupakan citra hasil dari transformasi fourier dimana nilai pikselnya adalah nilai pada frekuensi tertentu. Citra domain spasial ditransformasikan ke domain frekuensi menggunakan transformasi Fourier. Citra dalam domain frekuensi dioperasikan dengan fungsi filter kemudian ditransformasikan kembali ke domain spasial menggunakan Inverse Fourier Transform akan diperoleh citra hasil. 

<img src="/gambar/gambar9.png" width="70%" height="70%">

Berbagai detail pada citra seperti tepian dan noise adalah hasil dari frekuensi tinggi, sedangkan frekuensi rendah berdampak pada tampilan citra yang smooth atau blur. Filter yang melewatkan frekuensi rendah dan menahan frekuensi tinggi disebut _Low Pass Filter_ dan sebaliknya untuk _High Pass Filter_. Dalam teknik domain frekuensi, peningkatan kualitas citra dilakukan dengan cara memanipulasi koefisien transformasi yang memungkinkan operasi pada konten frekuensi citra, maka konten yang berfrekuensi tinggi seperti tepi, batas maupun informasi lainnya dengan mudah bisa dideteksi dan ditingkatkan. 


## Perbedaan Antara Peningkatan di Domain Spasial dan Domain Frekuensi
Perbedaan terbesar adalah ketika kita berurusan dengan gambar dalam domain spasial, pada dasarnya kita berurusan dengan gambar apa adanya. Nilai pikselnya mungkin berubah, misalnya, tetapi hanya menyangkut pengaturan dan pemandangan. Namun, dalam domain frekuensi, kecepatan perubahan nilai piksel merupakan salah satu titik fokus. Di Sini
Domain Spasial: Input -> Pemrosesan Gambar -> Output 
Domain Frekuensi: Frekuensi + Distribusi -> Pemrosesan Gambar -> Transformasi Terbalik -> Output
Tanpa terlalu teknis di area ini, kami akan mengalihkan fokus kami ke sisi peningkatan gambar ini. Jadi, mari kita lihat bagaimana peningkatan citra terjadi pada domain spasial dan frekuensi. 
Peningkatan Gambar di Domain Spasial
Domain spasial digunakan untuk menentukan koordinat spasial sebenarnya dari piksel dalam sebuah gambar, jadi ketika kita menggunakan istilah ini dalam bisnis peningkatan gambar, kita berbicara tentang hal-hal seperti pemerataan, penghalusan, dan penajaman. Berikut adalah beberapa contoh:
Persamaan Histogram
Ini adalah teknik peningkatan gambar umum yang terlihat untuk meningkatkan tampilan keseluruhan gambar. Bayangkan Anda memiliki gambar yang agak terlalu gelap, cukup umum dalam peningkatan gambar. Nah, fakta bahwa itu terlalu gelap memberi tahu kita bahwa keselarasan spasialnya berada di sisi bawah skala abu-abu. Jadi, merentangkan tingkat abu-abu itu akan menciptakan gambar yang lebih jelas karena menciptakan distribusi yang lebih seragam.
Hal yang sama berlaku untuk gambar yang terlalu terang. Keseimbangannya mungkin dimiringkan ke warna cerah tertentu, jadi menyamakan area gambar yang lebih gelap agar sesuai akan membuatnya lebih jelas.  
<p align="center"><img src="/Gambar/gambar11.png" width="500px">
Penghalusan Gambar
Tujuan utama penghalusan Penyempurnaan adalah untuk membantu meringankan gejala bahwa kamera dapat menyebabkan noise kamera, serta nilai piksel palsu dan hilang. Ada beberapa jenis pemulusan yang berbeda, jadi kami akan fokus pada proses yang dikenal sebagai rata-rata lingkungan. 
Kamera terkadang dapat menyebabkan tepi gambar menjadi kabur, akibatnya frekuensi pita yang lebih tinggi pada gambar menjadi berkurang karena pencahayaan atau kondisi lingkungan lainnya. Jadi, para ahli akan menggunakan taktik profesional yang dikenal sebagai pemfilteran median untuk mengatur tingkat keabuan area tersebut ke nilai piksel yang sama di lingkungan yang sama (mendekati) piksel tersebut.
<p align="center"><img src="/gambar/gambar12.png" width="500px">
Peningkatan Gambar di Domain Frekuensi
Gambar yang diedit dengan cara ini akan ditransfer ke domain frekuensi, di mana dimungkinkan untuk bekerja pada spektrum itu sendiri. Peningkatan gambar terjadi dalam transformasi Fourier gambar dan, dari perspektif pengeditan, berkaitan dengan pengaburan, penajaman, kontras, dan distribusi abu-abu. Namun, hasilnya adalah nilai piksel juga akan meningkat saat transformasi terjadi. 
Jenis gambar yang paling umum yang memerlukan jenis pengeditan ini adalah gambar satelit dan medis. Mari kita lihat beberapa contoh.
<p align="center"><img src="/gambar/gambar13.png" width="500px">
Penyempurnaan Gambar Low-Pass Filtering (Blurring)
Tepi dan transisi dalam nilai skala abu-abu gambar berkontribusi secara signifikan pada konten gambar yang ditemukan di frekuensi yang lebih tinggi. Dalam istilah awam, low-pass filtering akan membuat gambar menjadi lebih buram. Ada beberapa alasan mengapa Anda mungkin perlu memiliki gambar yang lebih buram. Pertama-tama, bahkan kamera kualitas tertinggi di dunia meninggalkan sejumlah noise. Jadi, pengaburan akan membantu menghilangkannya.
Piksel yang berbeda akan terpengaruh oleh noise ini dengan cara yang berbeda karena mereka semua menghasilkannya secara berbeda. Jadi, menggunakan filter low-pass dapat menghilangkan banyak noise sementara hanya berdampak minimal pada gambar. Misalnya, gambar yang diambil dari teleskop akan membuat gambarnya tersebar di banyak piksel, jadi mengaburkan gambar sebagian besar akan berdampak pada noise. 
<p align="center"><img src="/gambar/gambar14.png" width="500px">
Penyempurnaan Gambar Penyaringan High-Pass (Menajam)
Filter lolos tinggi digunakan untuk mempertajam gambar dan merupakan bentuk umum lain dari peningkatan citra domain frekuensi. Metode ini berfokus pada detail yang lebih halus pada gambar dan melakukan kebalikan dari filter low-pass. Sayangnya, itu juga berarti bahwa itu meningkatkan kebisingan juga, harga yang diekstraksi untuk menajamkan konten. 
Itu memberi tahu kita bahwa metode peningkatan gambar ini hanya boleh digunakan jika gambar mengandung noise minimal, jika tidak, mempertajamnya akan membuatnya jauh lebih buruk. Itu akan terlihat kasar dan tidak alami, jadi berhati-hatilah agar Anda tidak berlebihan.
<p align="center"><img src="/gambar/gambar15.png" width="500px">
Meningkatkan Gambar Normal menjadi Yang Menakjubkan
Yang benar adalah bahwa peningkatan gambar dapat mengubah foto biasa menjadi foto yang luar biasa, tetapi jika dilakukan dengan tidak benar, itu bisa merusak gambar. Itulah mengapa penting untuk membawa para profesional untuk membantu menyelesaikan ini dengan benar. Di Smart Photo Editors, kami telah mendedikasikan diri untuk membangun tim yang dilengkapi dengan pengetahuan dan pengalaman dengan peningkatan gambar di setiap industri, sehingga kami dapat menangani peningkatan gambar di domain spasial dan frekuensi. 

Jadi, jika Anda memiliki foto yang perlu dipertajam tetapi Anda tidak ingin mengambil risiko itu menjadi kasar, atau jika Anda perlu beberapa tepinya dihaluskan, maka mari kita ubah foto rata-rata Anda menjadi mahakarya yang menakjubkan.