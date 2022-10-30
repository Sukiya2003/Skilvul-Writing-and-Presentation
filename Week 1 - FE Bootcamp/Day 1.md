# WRITING WEEK 1 FE - DAY 1
## INTRODUCTION REACT JS
### Apa itu React JS
- React JS dibuat pada tahun 2011 oleh tim engineer Facebook dan rilis pada tahun 2013
- React bukan sebuah framework
- React merupakan library javascript open source untuk membangun sebuah user interface pada website secara interaktif
- Library yang dimaksud adalah react menyediakan function bawaan yang dapat kita gunakan untuk membuat sebuah user interface
- File ekstensi dari javascript pada react adalah jsx
- React menggunakan teknologi SPA (Single Page Application)
- SPA (Single Page Application)
  - Dengan SPA react hanya memiliki satu halaman .html
  - SPA tidak seperti traditional web application yang harus membuat banyak halaman jika ingin membuat halaman about dan lainnya
  - SPA tidak memuat ulang halaman jika user melakukan request. Contoh website SPA [Skilvul](https://skilvul.com/home). Pada bagian beasiswa, challenge, webinar halaman tidak refresh ketika direquest
  - SPA digunakan untuk membuat web application yang datanya setiap hari di update

### Instalasi React JS
- Install [Node.js](https://nodejs.org/en/download/) versi LTS
- Buka terminal (git bash) ketikkan `npx create-react-app nama_aplikasi`
- Ketikkan `y` dan enter
- Tunggu proses loading sampai git bash menampilkan “Happy hacking!”
- Buka folder aplikasi di visual studio code
![image](https://user-images.githubusercontent.com/85722923/198873364-f7da6510-d2e7-4241-9b7c-fde2ceddf5b1.png)

### Struktur Folder React JS
- Terdapat tiga folder dalam folder aplikasi react (node_module, public, src)
- Folder node_modules merupakan packages-packages yang digunakan untuk project react. Tetapi folder ini diabaikan saja
- Folder public berisi struktur web utama, seperti satu file .html, logo, dan lainnya
- Didalam file .html terdapat `div id=”root”` yang nantinya disisipkan halaman home, about, contact, dan lainnya. Pada file inilah metode SPA
- Folder public juga diabaikan
- Folder src akan dikotak-katik. Folder ini memiliki file utama yaitu index.js
- Didalam index.js akan mengimport react dan membuat sebuah virtual DOM, dimana nantinya akan mengambil element id=”root” `getElementById(‘root’)` pada file .html di folder public
- Setelah itu root akan merender atau menampilkan function dengan return value html
- Untuk menjalankan folder react buka terminal (bash) dan ketikkan `npm start`

### Kekurangan React JS
- Perlu melakukan beberapa konfigurasi pada setiap awal membuat project atau aplikasi
- Dokumentasi react js tidak bagus karena informasi yang diberikan tidak lengkap

### Kelebihan React JS
- Membuat aplikasi front-end menjadi lebih cepat
- Dapat menerapkan konsep modular javascript pada react js. Dimana react js membagi 1 tampilan website menjadi komponen-komponen kecil. Konsep modular ini disebut components
- Menggunakan react js jika data elements pada aplikasi berubah setiap satuan waktu
- Dapat digunakan pada aplikasi skala kecil maupun kompleks

## FITUR VIRTUAL DOM
- Virtual DOM merupakan real DOM yang disalin kedalam bentuk JSON
- Virtual DOM digunakan react sebagai perantara ke dom. Jadi, ketika element dirender ulang maka yang mengalami perubahan hanya yang dirubah saja sehingga peforma website menjadi lebih cepat
- Cara kerja virtual DOM:
  - Virtual DOM menyalin semua node yang ada pada DOM kedalam bentuk JSON
  - React mengubah state aplikasi
  - Virtual DOM baru dibuat oleh react berdasarkan Virtual DOM lama, namun dengan mengikuti perubahan state (Virtual DOM lama tetap ada)
  - Virtual DOM lama dan Virtual DOM baru dibandingkan untuk mengetahui letak node yang berubah
  - Setelah mengetahui node mana yang berubah, maka Virtual DOM baru menyalin node yang berubah ke DOM

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
- Gunakan `className` untuk menggantikan attribute class pada HTML
- Gunakan curly braces `{}` untuk mengakses syntax javascript pada element HTML. Jika tidak menggunakan `{}` maka dianggap sebagai konten HTML
![image](https://user-images.githubusercontent.com/85722923/198875040-8c7ce0cb-b23a-4864-bed3-4a48e8a81b92.png)
- Gunakan curly braces `{}` untuk menggunakan method javascript dalam elemen HTML

### Variable pada JSX
- Gunakan curly braces `{}` untuk mengakses variabel
![image](https://user-images.githubusercontent.com/85722923/198875141-3356c3d9-4a9f-48a2-a0e9-ab6b43708ff0.png)

### Attribute pada JSX
- Gunakan curly braces `{}` untuk data attribute
![image](https://user-images.githubusercontent.com/85722923/198875155-18027a01-b944-426f-b02f-518f5d16a0bd.png)

### Event pada JSX
- Gunakan curly braces `{}` untuk deklarasi event
![image](https://user-images.githubusercontent.com/85722923/198875185-787caa59-75ac-41bd-bf79-1494f034ca68.png)

