# Writing and Presentation Test
## Day 1: Unix Command Line
Shell merupakan perantara yang digunakan antara user dan sistem operasi untuk berinteraksi atau memerintah sistem melalui perintah tertulis. Command Line Interface (CLI) merupakan jenis shell yang berbasis teks. Jadi, shell merupakan software terminal yang memproses semua perintah yang user ketik di CLI lalu shell menginstruksikan sistem operasi untuk menjalankan perintah tersebut.

### Mengakses CLI dan Menggunakan Terminal
- Mengakses CLI dapat dilakukan dengan berbagai tipe shell
- Terdapat 2 tipe shell yang populer, yaitu Windows shell (Windows) dan Bash (Linux dan MacOS)
- Menggunakan terminal:
  - Membuka jendela terminal
  - Mengetik perintah pada terminal

### File System Structure
- Proses yang mengatur dimana dan bagaimana sebuah data disimpan dan diakses dalam disk penyimpanan (storage device)
- Struktur sistem file dan direktori disusun seperti pohon (tree)

### Terminal Commands
1. Melihat current working directory

    Dengan **pwd** (print working directory)
```
    pwd
```

2. Melihat isi file dari sebuah direktori

    Dengan **ls** (lists)
```
    ls
```

3. Pindah direktori

    Dengan **cd** (change directory)
```
    cd /tujuanDirektori
```

4. Melihat isi file

    Terdapat 3 command:
    - **head** (melihat 10 baris pertama dari file text)
    - **tail** (melihat 10 baris terakhir dari file text)
    - **cat** (melihat seluruh isi dari file text)
```
    head namaFile
    tail namaFile
    cat namaFile
```

> Jika ingin melihat bagian isi file sesuai baris yang diinginkan
```
    head -baris <namaFile
```

5. Membuat file dan direktori

    Terdapat 2 command:
    - **touch** (membuat sebuah file)
    - **mkdir** (membuat sebuah direktori)
```
    touch namaFile
    mkdir 'namaFolder'
```

6. Menyalin file dan direktori

    Terdapat 2 command:
    - **cp** (menyalin file)
    - **cp -R** (menyalin direktori)
```
    cp namaFileCopy namaFilePaste
    cp -R namaFolderCopy namaFolderPaste
```

7. Memindahkan/rename file dan direktori

    Terdapat 2 command:
    - **mv** (memindahkan/rename file)
    - **mv -R** (memindahkan/rename direktori)
```
    mv namaOldFile namaNewFile
    mv -R namaOldFolder namaNewFolder
```

8. Menghapus file dan direktori

    Terdapat 2 command:
    - **rm** (menghapus file)
    - **rm -R** atau **rm -d** (menghapus direktori)
```
    rm namaFile
    rm -R namaFolder
```

---
## Day 1: Git dan GitHub
### 'WHY' Git & GitHub Tools Wajib
Seorang programmer tidak akan pernah bekerja sendirian. File yang disimpan dengan git akan melacak setiap perubahan yang terjadi. Jika file disimpan dengan git dan diupload ke github maka programmer dapat berkerja sama dengan mudah tanpa harus ribet copy paste file aplikasi.

### Git
Git adalah aplikasi yang dapat melacak setiap perubahan yang terjadi pada suatu file atau folder. Git merupakan software berbasis version control system yang bertujuan untuk menyimpan database pada semua orang yang terlibat dalam penyusunan code.

### GitHub
GitHub adalah layanan cloud yang berguna untuk menyimpan dan mengelola sebuah repository atau project. GitHub merupakan platform yang mirip dengan google drive tetapi postingannya berkaitan dengan pemrograman.

### Alur Kerja Git & GitHub
1. Download dan install git

2. Check apakah instalasi berhasil
```
    git --version
```

3. Melakukan setup awal
```
    git config --global user.name "usernameKamu"
    git config --global user.email emailKamu@gmail.com
```

4. Check apakah setup awal berhasil
```
    git config --list
```

5. Membuat repository
```
    git init
```

6. Tambahkan file ke repository
```
    git add namaFile
```

7. Melakukan commit dan memberi keterangan pada setiap perubahan
```
    git commit -m "Pesan"
```

8. Melakukan push project ke github

## Membuat Repository Git
```
    git init namaDirektori
```
Command line tersebut akan membuat sebuah direktori baru. Namun, jika sudah memiliki direktori maka command line yang digunakan adalah
```
    git init .
```

## Melakukan Commit pada Git
1. Gunakan command 'git status' untuk melihat status dari file
```
    git status
```

2. Gunakan command 'git add' ketika perubahan sudah dilakukan tetapi belum ditandai
```
    git add .
```

3. Gunakan command 'git commit' untuk menyimpan perubahan pada version control
```
    git commit -m "Pesan"
```

## Publish Aplikasi ke GitHub
1. Siapkan proyek aplikasi yang ingin dipublish
2. Membuat akun github jika belum pernah mendaftar
3. Membuat repository baru
4. Publish proyek menggunakan git
5. Pastikan git kita berada di dalam direktori proyek yang akan dipublish
6. Lakukan 'git branch' untuk membuat branch dengan nama main
```
    git branch -m main
```
7. Lakukan 'git remote' untuk meremote repository github
```
    git remote add origin copasLinkGithub
```
8. Lakukan 'git push' untuk upload aplikasi ke github
```
    git push -u origin main
```

## Cloning GitHub ke Local
Clone github merupakan duplikat sebuah repository di github ke local komputer kita. Cara clonning github ke local:
1. Copy link repository github
2. Buka aplikasi terminal dan arahkan directory mana yang akan menyimpan clone
3. Ketikkan command line
```
    git clone pasteLink
```
4. Check proyek yang kita clone pada local directory

---
## Day 2: HTML (*Hypertext Markup Language*)
- Bukan termasuk bahasa pemrograman
- Kerangka website yang menampilkan berbagai konten, seperti:
  - Teks
  - Gambar
  - Video
  - Audio
  - Link
- Bersifat statis yang hanya menampilkan tanpa bisa mengolah data

### Tools Pendukung
Terdapat 2 tools utama yang dibutuhkan dalam membuat HTML, yaitu:
1. Web browser

    Chrome merupakan browser yang recommended
2. Code editor

    Visual Studio Code (VSC) merupakan code editor yang recommended

### HTML Structure
```html
    <!DOCTYPE html>
    <html lang="en">
      <head>
          <meta charset="UTF-8">
          <meta name="viewport" content="width=device-width, initial-scale=1.0">
          <title>Document</title>
      </head>
      <body>
        <h1>Hello, ini Sukii</h1>
        <a href="https://www.wikipedia.org">Website Wikipedia</a>
      </body>
    </html>
```

- HTML Element, pada umumnya terdiri dari:
  - Opening tag: `<a>`
  - Attribute: `href`
  - Value: `"https://www.wikipedia.org"`
  - Content: `Website Wikipedia`
  - Closing tag: `</a>`
- HTML Comment untuk memberi keterangan dari line code `<!--  -->`

### Running HTML secara Manual dan Live Server
Bisa saja kita running HTML secara manual tetapi setiap ada perubahan atau kita selesai mengedit code maka kita harus memuat ulang halaman HTML pada browser.
- Run manual:
  - Cari lokasi file HTML
  - Jalankan dengan membukanya melalui browser
- Run live server VSC:
  - Klik icon extensions
  - Cari live server lalu install
  - Pada bagian explorer klik kanan file HTML lalu pilih 'open with Live Server'
  - File HTML sudah auto reload

### Populer Tag HTML
- `<a>` untuk link
- `<b>` untuk huruf tebal
- `<i>` untuk huruf miring
- `<br>` untuk baris baru
- `<p>` untuk paragraf
- `<h1> <h2> <h3> <h4> <h5> <h6>` untuk judul
- `<img>` untuk gambar
- `<ol>` untuk ordered list dalam bentuk angka
- `<ul>` untuk unordered list dalam bentuk simbol bullet
- `<table>` untuk tag utama membuat table
- `<th>` untuk membuah header tabel
- `<tr>` untuk membuat baris tabel
- `<td>` untuk wadah dari data tabel

### Semantic HTML
Semantic HTML adalah penggunaan elemen HTML sesuai dengan kebutuhan konten agar dokumen HTML mudah dibaca dan dimengerti. Contoh: 

Daripada menulis `<div class="header">` lebih baik menulis `<header>`

### Deployment HTML
Deploy adalah sebuah proses penyebaran aplikasi yang sudah kita kerjakan kepada user agar bisa digunakan. Aplikasi website akan di deploy ke server dan aplikasi mobile akan di deploy ke Google Play Store atau App Store. Gunakan tools 'Netlify' saat mendeploy HTML, berikut caranya:
- Buka website [Netlify](https://www.netlify.com/)
- Register menggunakan email atau github
- Masuk ke tab sites lalu drag dan drop seluruh folder HTML

---
## Day 3: CSS (*Cascading Style Sheets*)
- Bukan termasuk bahasa pemrograman, hanya bahasa styling
- CSS ibarat **'baju'** atau **'dekorator'** dari halaman website
- CSS digunakan untuk menambahkan design pada halaman website

### Styling CSS dalam HTML
Terdapat 3 cara menyisipkan CSS ke dalam HTML, yaitu:
1. **Inline CSS**, menggunakan attribute `style` langsung dalam HTML element pada bagian body
```html
    <body>
      <h1 style="color:green">Hello, ini Sukii</h1>
    </body>
```

2. **Internal CSS**, menggunakan tag `<style>` pada bagian head
```html
    <head>
        <title>Internal CSS</title>
        <style>
            h1 {
                background-color: black;
                color: gold;
            }
        </style>
    </head>
    <body>
        <h1>Hello, ini Sukii</h1>
    </body>
```

3. **External CSS**, file CSS terpisah dan dihubungkan dengan file HTML menggunakan tag `<link>` pada bagian head
```html
    <head>
        <title>External CSS</title>
        <link rel="stylesheet" href="style.css">
    </head>
```

### Syntax Dasar CSS
```css
    <!-- selector {
        property: value;
    } -->
```
- Selector: untuk memilih HTML element mana yang akan diberi style
- Property: untuk memilih bagian mana yang akan diberi style (teks, background)
- Value: untuk menampung nilai yang akan diberikan pada HTML element

CSS Selector:
- CSS selector HTML element
```css
    h1 {
      color: gold;
    }
```

- CSS selector by id


    Selector by id bersifat unik dan spesifik serta hanya dapat dipanggil sekali
```css
    #navigation li a{
        text-decoration: none;
    }
```

- CSS selector by class


    Selector by class dapat dipanggil berkali-kali
```css
    .title {
        color: brown;
    }
```

### Responsive Web Design dengan CSS
1. Mengatur viewport pada file HTML
```html
    <head>
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    </head>
```

2. Menggunakan presentase untuk menentukan niali lebar suatu element
`width: 80%;`

3. Menggunakan properti `max-width: 100%` agar element memiliki lebar maksimum sebesar 100% dari parent element. Namun, jika ukuran maksimal aslinya tidak selebar parent elementnya maka akan menampilkan ukuran maksimal aslinya

4. Menggunakan satuan 'vw' atau viewport width. Contoh: `font-size: 15vw` (ukuran huruf akan sebesar 15% dari lebar viewport)

5. Menggunakan media query, agar tampilan website kita dapat beradaptasi dengan berbagai macam device
```css
    @media (max-width: 400px) { 
        img { 
            width: 100%;
        }
    }
```

6. Menggunakan sistem flexbox

### Flexbox (Flexible Box)
- Memudahkan dalam mengatur layout, posisi, dan ukuran dari tiap element
- Terdapat 2 istilah:
  - Container: element yang membungkus dan mengatur tampilan dari element di dalamnya
  - Item: element dalam container yang diatur tampilannya
- Justify-content untuk mengatur tata letak dan ruang antar item secara horizontal. Properti justify-content memiliki beberapa nilai:
  - `flex-start` semua item akan ditempatkan di kiri atau depan
  - `flex-end` semua item akan ditempatkan di kanan atau belakang
  - `center` semua item di tengah
  - `space-between` memberi ruang pada setiap 2 item yang bersebelahan
  - `space-around` memberi ruang pada sekitar tiap item

---
## Day 4: Algoritma
- Algoritma: logika, urutan untuk menyelesaikan suatu permasalahan tertentu yang disusun secara sistematis dan logis
- Data structure: cara bagaimana kita mengelola sebuah data secara terstruktur pada sistem komputer sehingga lebih mudah diakses.

### Manfaat Algoritma dan  Data Structure
Manfaat algoritma:
- Dapat menyelesaikan masalah dengan sistematis dan logis
- Dapat mempertimbangkan langkah-langkah yang akan diambil dalam menyelesaikan masalah
- Dapat berpikir kritis dalam mencari solusi

Manfaat data structure:
- Dapat mengelompokan atau membagi data yang akan diolah agar mudah dipahami
- Dapat menyimpan data yang akan diproses agar data tidak hilang
- Dapat menjadi perintah dalam program

### Algoritma Sederhana
Penyajian algoritma dapat ditulis dengan 3 cara, yaitu deskriptif, flowchart, dan pseudo code
- Deskriptif (Contoh: ingin membuat teh)
  - Masukan air ke dalam panci lalu letakkan diatas kompor
  - Hidupkan kompor dengan api kecil
  - Setelah air mendidih, matikan kompor
  - Siapkan gelas lalu masukkan kantung teh dan gula
  - Tuang air yang sudah dimasak kedalam gelas
  - Teh siap diminum

- Flowchart: penyajian algoritma dengan tampilan visual berupa diagram alir
- Pseudo Code: penyajian algoritma dengan bahasa inggris sebelum diimplementasikan ke bahasa pemrograman
```
    program ganjil_genap

    deklarasi
    var number: integer

    algoritma
    INPUT number
    IF (number modulus 2 = 0) THEN
        OUTPUT "genap"
    ELSE
        OUTPUT "ganjil"
```

### Penerapan Algoritma dalam Bahasa Pemrograman
Ketika kita memiliki permasalahan maka kita membuat algoritma untuk menyelesaikan masalah tersebut dan mendapatkan solusi serta diimplementasikan ke dalam bahasa pemrograman. Contoh penerapan algoritma ke dalam JavaScript
```js
    var a, b, c;
    a = prompt("First Number?");
    b = prompt("Second Number?");
    c = Number(a) + Number(b);

    console.log(c);
    alert("Result = " + c);
```

---
## Day 4: Introduction JavaScript
- Bahasa pemrograman yang membuat website menjadi interaktif dan dinamis
- JavaScript ibarat **'otot'** yang menggerakkan tubuh agar bisa leluasa bergerak

### Running JavaScript
- File javascript dihubungkan dengan file HTML. Gunakan tag


    `<script src=“script.js”></script>`
- Running javascript melalui browser pada setiap device user

### Tipe Data JavaScript
- **String**: tipe data dalam bentuk huruf, angka, spasi, simbol. String diawali dan diakhiri dengan `'...'` atau `"..."`
- **Number**: tipe data dalam bentuk semua angka (bulat dan desimal)
- **Boolean**: tipe data untuk menentukan nilai benar atau tidak
- **Null**: tipe data untuk variabel atau data yang tidak memiliki nilai
- **Undefined**: tipe data yang merepresentasikan atau nilai pemanggilan varibel/data yang tidak memiliki nilai
- **Object**: tipe data yang memberikan penjelasan bagaimana data diolah dan menyimpan data dengan tipe data apapun

### Operator JavaScript
- **Aritmatika**: operator yang melibatkan operasi matematika
  - Penjumlahan `+`
  - Pengurangan `-`
  - Perkalian `*`
  - Perpangkatan `**`
  - Pembagian `/`
  - Sisa bagi `%`

- **Assignment**: memberikan tugas kepada variabel
  - Pengisian nilai `=`
  - Pengisian dan penambahan `+=`
  - Pengisian dan pengurangan `-=`
  - Pengisian dan perkalian `*`
  - Pengisian dan perpangkatan `**`
  - Pengisian dan pembagian `/`
  - Pengisian dan sisa bagi `%`

- **Perbandingan**: membandingkan dua nilai dan menghasilkan sebuah nilai boolean
  - Lebih besar `>`
  - Lebih kecil `<`
  - Sama dengan `==` atau `===`
  - Tidak sama dengan `!=` atau `!==`
  - Lebih besar sama dengan `>=`
  - Lebih kecil sama dengan `<=`

- **Logika**: melakukan operasi terhadap 2 nilai boolean
  - Logika AND `&&`
  - Logika OR `||`
  - Negasi `!`

- **Increment or decrement**: menambah atau mengurangi sebesar 1 nilai

---
Day 5: Conditiondal dan Looping JavaScript
### Conditional JavaScript
Conditional statement merupakan percabangan ketika kondisi lebih dari 1 dan berkaitan. Conditional statement mencari kondisi benar dan menjalankan perintah berdasarkan kondisi tersebut
- **If statement**: seleksi dari inputan yang diperintah dengan 1 cabang
```js
    if(true) {
        console.log('lanjut ke tahap selanjutnya');
    } 
```

- **If ... else statement**: seleksi dari inputan yang diperintah dengan 1 cabang dan kondisi bernilai false
```js
    let haus = true;
    if(haus) {
        consule.log('minum');
    } else {
        consule.log ('makan');
    }
```

### Looping JavaScript
Looping statement merupakan perintah yang mengulang sebuah kondisi sampai kondisi itu terpenuhi. Terdapat beberapa looping, yaitu:
- **Manual looping**
- **For loop**: pengulangan yang ditentukan nilai awal dan akhir. Ketika sudah sampai di nilai akhir maka penggulangan selesai
```js
    for (let i = 1; i <= 10; i++) {
      console.log(i);
    }
```
- **While loop**
- **Do while**
- **Nested loop**
