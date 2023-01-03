# Laporan Tugas Pemrosesan Citra Digital

Mata Kuliah | Pemrosesan Citra Digital
--------|--------
Nim  : 1810131120017
Nama : Rapiyah hawa nur
## TUGAS 6
<h2 align=center><u>Implementasi Bit Plane Slicing Pada Octave</u></h2>
### Apa itu Bit Plane Slicing?
metode yang digunakan untuk melihat kontribusi atau pengaruh dari tiap bit penyusun citra.

Format biner untuk nilai piksel 167 adalah 10100111 Demikian pula, untuk 144 adalah 10010000. Gambar 8-bit ini terdiri dari delapan bidang 1-bit. Plane 1 berisi bit urutan terendah dari semua piksel dalam gambar.

Mari kita lihat bagaimana kita bisa melakukannya dengan menggunakan MATLAB
```oktave
A = [ 167 133 111
      144 140 135
      159 154 148 ]
B = bitget(A,1); %Bit urutan terendah dari semua piksel
'bitget' adalah fungsi MATLAB yang digunakan untuk mengambil bit 
dari posisi yang ditentukan dari semua piksel.
B = [ 1 1 1
      0 0 1
      1 0 0 ]
B = bitget(A,8); %Bit urutan tertinggi dari semua piksel
B = [ 1 1 0
      1 1 1 
      1 1 1 ]
      
```
### Implementasi Bit Plane Slicing di Octave

Hal pertama yang perlu dipersiapkan adalah gambar, ketentuan gambar dibebaskan asal jangan yang macam-macam ya.

Lalu ketikkan kode program seperti di bawah ini :
- ini adalah gambar asli yang akan saya gunakan

<img src="/gambar/rgb.jpg" width="50%" height="50%" align="center">

Lalu ketikkan kode program seperti di bawah ini pada oktav :

```octave
pkg load image
Img = imread('rgb.jpg');
R = Img(:,:,1);
G = Img(:,:,2);
B = Img(:,:,3);

gray_img = (0.3*R) + (0.59*G) + (0.11*B);
subplot(3, 3, 1) ; imshow(gray_img) ; title("citra asli");

%menampilkan setiap bit slicing dengan fungsi bitget
figure(1);
for i = 1:8
  bit_img= bitget(gray_img, i);
  subplot(3, 3, i+1) ; imshow(bit_img); title(["bit plane ", num2st(i)]);
end
```
Hasil outputnya adalah :
<img src="/gambar/gambar16.PNG" width="100%" height="100%" align="center">
Adapun dengan menggunakan kode seperti berikut:
- Untuk layer pertama
```octave
pkg load image
img = imread('rgb.jpg');
% mengubah citra rgb ke grayscale
gray_img = rgb2gray(img);
% menampilkan setiap bit slicing dengan fungsi bitget
figure(1);
bit_img = bitget(gray_img, 1);
imshow(bit_img);
```
Maka hasil program ketika dijalankan adalah sebagai berikut :
<img src="/gambar/gambar18.PNG" width="50%" height="50%" align="center">
- Untuk layer kedua
```octave
pkg load image
img = imread('rbg.jpg');
% mengubah citra rgb ke grayscale
gray_img = rgb2gray(img);
% menampilkan setiap bit slicing dengan fungsi bitget
figure(1);
bit_img = bitget(gray_img, 2);
imshow(bit_img);
```
Maka hasil program ketika dijalankan adalah sebagai berikut :
<img src="/gambar/gambar21.PNG" width="50%" height="50%" align="center">
- Untuk layer ketiga
```octave
pkg load image
img = imread(rgb.jpg');
% mengubah citra rgb ke grayscale
gray_img = rgb2gray(img);
% menampilkan setiap bit slicing dengan fungsi bitget
figure(1);
bit_img = bitget(gray_img, 3);
imshow(bit_img);
```
Maka hasil program ketika dijalankan adalah sebagai berikut :
<img src="/gambar/gambar22.PNG" width="50%" height="50%" align="center">
- Untuk layer keempat
```octave
pkg load image
img = imread('rgb.jpg');
% mengubah citra rgb ke grayscale
gray_img = rgb2gray(img);
% menampilkan setiap bit slicing dengan fungsi bitget
figure(1);
bit_img = bitget(gray_img, 4);
imshow(bit_img);
```
Maka hasil program ketika dijalankan adalah sebagai berikut :
<img src="/gambar/gambar23.PNG" width="50%" height="50%" align="center">
- Untuk layer kelima
```octave
pkg load image
img = imread('rgb.jpg');
% mengubah citra rgb ke grayscale
gray_img = rgb2gray(img);
% menampilkan setiap bit slicing dengan fungsi bitget
figure(1);
bit_img = bitget(gray_img, 5);
imshow(bit_img);
```
Maka hasil program ketika dijalankan adalah sebagai berikut :
<img src="/gambar/gambar24.PNG" width="50%" height="50%" align="center">
- Untuk layer keenam
```octave
pkg load image
img = imread('rgb.jpg');
% mengubah citra rgb ke grayscale
gray_img = rgb2gray(img);
% menampilkan setiap bit slicing dengan fungsi bitget
figure(1);
bit_img = bitget(gray_img, 6);
imshow(bit_img);
```
Maka hasil program ketika dijalankan adalah sebagai berikut :
<img src="/gambar/gambar25.PNG" width="50%" height="50%" align="center">
- Untuk layer ketujuh
```octave
pkg load image
img = imread('rgb.jpg');
% mengubah citra rgb ke grayscale
gray_img = rgb2gray(img);
% menampilkan setiap bit slicing dengan fungsi bitget
figure(1);
bit_img = bitget(gray_img, 7);
imshow(bit_img);
```
Maka hasil program ketika dijalankan adalah sebagai berikut :
<img src="/gambar/gambar26.PNG" width="50%" height="50%" align="center">
- Untuk layer kedelapan
```octave
pkg load image
img = imread('rgb.jpg');
% mengubah citra rgb ke grayscale
gray_img = rgb2gray(img);
% menampilkan setiap bit slicing dengan fungsi bitget
figure(1);
bit_img = bitget(gray_img, 8);
imshow(bit_img);
```
### Apa itu Steganography?
Steganografi atau Steganography adalah sebuah ilmu, teknik atau seni menyembunyikan sebuah pesan rahasia dengan suatu cara sehingga pesan tersebut hanya akan diketahui oleh si pengirim dan si penerima pesan rahasia tersebut. Steganografi berasal dari Bahasa Yunani yaitu Stegano yang berarti “tersembunyi atau menyembunyikan” dan graphy yang berarti “Tulisan, jadi Steganografi adalah tulisan atau pesan yang disembunyikan. Steganografi kebalikannya kriptografi yang menyamarkan arti dari sebuah pesan rahasia saja, tetapi tidak menyembunyikan bahwa ada sebuah pesan. Kelebihan Steganografi dibandingkan dengan Kriptografi adalah pesan-pesannya akan dibuat tidak menarik perhatian dan tidak menimbulkan kecurigaan, berbeda dengan Kriptografi yang pesannya tidak disembunyikan, walaupun pesannya sulit untuk di pecahkan akan tetapi itu akan menimbulkan kecurigaan pesan tersebut.
Pesan rahasia yang akan disembunyikan akan disisipkan pada suatu media penampung seperti citra, suara, video dan sebagainya yang terlihat tidak mencurigakan untuk menyimpan pesan rahasia. Pesan rahasia akan memerlukan sebuah kunci rahasia yang dinamakan stego-key agar hanyak pihak yang berhak saja yang dapat membuka atau mengekstak pesan rasahia tersebut.
### Membuat Steganography di Citra dengan Octave
Kode program :
```octave
picture = imread('rgb.jpg');
gray = rgb2gray(picture);
[row,col] = size(picture);

pesan = "Rapiyah  hawa nur 1810131120017";
ascii = uint8(pesan);
biner = dec2bin(ascii,8);
biner2 = str2num(biner);

pesan2 = transpose(biner2);
pesan3 = pesan2(:);
hasil = transpose(pesan2);
panjang = length(hasil);
counter = 1;
steganography = gray;

for x = 1:row
for y = 1:col
	if (counter <= panjang)
		LSB = bitget(gray(x,y),1);
		biner3 = hasil(counter);
		temp = xor(LSB, biner3);
		steganography(x,y) = gray(x,y) + temp;
		counter = counter + 1;
	else
		break;
	endif
endfor
endfor

subplot(1,2,1); imshow(gray); title("Gambar Asli");
subplot(1,2,2); imshow(steganography, "rgb.jpg"); title("Steganography");

```
- ini adalah gambar asli yang akan saya gunakan
  
<img src="/gambar/rgb.jpg" width="50%" height="50%" align="center">

Hasil program :
- ini adalah gambar hasil steganografi
<img src="/gambar/gambar27.PNG" width="80%" height="80%" align="center">
