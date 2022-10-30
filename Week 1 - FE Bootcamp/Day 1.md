# WRITING WEEK 4 - DAY 1
## INTRODUCTION REACT JS
### Apa itu React JS
- React JS dibuat pada tahun 2011 oleh tim engineer Facebook dan rilis pada tahun 2013
- React merupakan library javascript open source untuk membangun sebuah user interface pada website secara interaktif
- Library yang dimaksud adalah react menyediakan function bawaan yang dapat kita gunakan untuk membuat sebuah user interface

### Instalasi React JS
- Install [Node.js](https://nodejs.org/en/download/) versi LTS
- Buka terminal (git bash) ketikkan `npx create-react-app nama_aplikasi`
- Ketikkan `y` dan enter
- Tunggu proses loading sampai git bash menampilkan “Happy hacking!”
- Buka folder aplikasi di visual studio code
![image](https://user-images.githubusercontent.com/85722923/198873364-f7da6510-d2e7-4241-9b7c-fde2ceddf5b1.png)



### Kekurangan React JS
- Perlu melakukan beberapa konfigurasi pada setiap awal membuat project atau aplikasi
- Dokumentasi react js tidak bagus karena informasi yang diberikan tidak lengkap

### Kelebihan React JS
- Membuat aplikasi front-end menjadi lebih cepat
- Dapat menerapkan konsep modular javascript pada react js. Dimana react js membagi 1 tampilan website menjadi komponen-komponen kecil. Konsep modular ini disebut components
- Menggunakan react js jika data elements pada aplikasi berubah setiap satuan waktu
- Dapat digunakan pada aplikasi skala kecil maupun kompleks

## VIRTUAL DOM


## JSX (*JavaScript Syntax Extension*)
- JSX adalah ekstensi react untuk javasript
- JSX terlebih dahulu akan dicompile menjadi javascript sebelum ditampilkan pada browser
- JSX digunakan untuk menulis HTML pada file ekstensi javascript

### Peraturan JSX
- Setiap JXS hanya bisa memiliki 1 parent element, jika lebih maka program akan error
![image](https://user-images.githubusercontent.com/85722923/198872059-c27fe5a3-8635-4eb4-be71-ae22057a8ec5.png)
- Solusi:
  - Gunakan tag `<div> </div>` sebagai parent element
![image](https://user-images.githubusercontent.com/85722923/198872586-168ef6cd-2818-4d40-9aae-eb6e6294e72e.png)
  - Atau gunakan tag fragment `<> </>` sebagai parent element
![image](https://user-images.githubusercontent.com/85722923/198872613-bdfe55eb-b7a6-4e3f-9e7f-88e2a6c5c094.png)

