# WRITING WEEK 3 - DAY 3
## JS INTERMEDIATE - MODULES
- JS modules diperkenalkan pada ES2015 (ES6)
- JS modules adalah cara untuk memisahkan kode ke file yang berbeda
- Keuntungan js modules:
  -  Mudah untuk mengelola kode
  -  Code tidak menumpuk dalam satu file
- Cara menggunakan js modules:
  - Sambungkan file HTML dan file .js
  - Tambahkan attribute `type="module` di element script .js
  - Siapkan script kedua dan seterusnya untuk melakukan export
  - Lakukan import pada file atau script utama
- Terdapat dua istilah dalam js modules, yaitu export dan import

### Export
Export digunakan untuk mengexport function, objek atau nilai primitif pada sebuah module sehingga bisa digunakan pada program lain dengan menggunakan statement import. Contoh:
```js
    //beri nama file jepang.js
    export let motor = ['Kawasaki', 'Honda', 'Yamaha']
```
- Export biasa:
  -  Mengirim file dari dalam ke luar
  -  `export` ditangkap oleh `import`
  -  Menggunakan kurung kurawal
- Export default:
  - Hanya bisa mengexport satu
  - Ditangkap tanpa menggunakan kurung kurawal
  - Menerima jika ada perbedaan atau typo nama

### Import
Import bisa dikatakan adalah pasangan dari statement export. Jadi, import digunakan tentunya untuk mengimport function, objek, variabel yang sudah di export pada module lain.
- Mengirim file dari luar ke dalam
- Contoh (sambungan dari contoh export):
```js
    //buat file baru dengan nama indonesia.js
    import {motor} from "./jepang.js";
    console.log(motor)
    
    //output: 'Kawasaki', 'Honda', 'Yamaha'
```

## JS INTERMEDIATE - RECURSIVE
- Recursive adalah function yang memanggil dirinya sendiri sampai kondisi tertentu
- Recursive digunakan untuk case matematika, fisika, kimia, dan hal yang berkaitan dengan kalkulator
- Recursive akan berhenti memanggil dirinya sendiri jika kondisi terpenuhi
- Ciri-ciri recursive:
  - Memiliki kondisi yang menyatakan kapan fungsi tersebut berhenti
  - Selalu memaanggil dirinya sendiri sambil mengurangi atau memecahkan data masukan setiap panggilannya
- Struktur recursive
```js
    function recursive() {
        //...
        recursive();
        //...
    }
```
- Contoh menghitung mundur angka:
![image](https://user-images.githubusercontent.com/85722923/194839521-996155c0-231b-445b-80f7-8023e875ff38.png)
