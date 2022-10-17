# WRITING WEEK 4 - DAY 3
## RESPONSIVE WEB DESIGN (RWD)
- RWD bertujuan untuk membuat desain web kita dapat diakses dalam device apapun (laptop/PC, smartphone, tablet)
- Tools yang digunakan untuk menerapkan responsive web design:
  - Mengatur viewport
  - Properti max-width
  - Relative CSS unit
  - Media query
  - Flexbox dan grid

### Viewport 
- Viewport merupakan bagian dari responsive website
- Viewport merupakan area website yang dapat diakses user (ukuran layar itu viewport)
- Viewport berada pada meta didalam head file .html
- 1vw = 1% lebar viewport
- Jika lebar viewport sebesar 100cm, maka 1vw adalah 1cm

### max-width
- Untuk menentukan lebar maksimal dari suatu element
- `max-width: 100%`: element akan memiliki lebar maksimum sebesar 100% dari parent element, namun jika ukuran maksimal aslinya tidak selebar parent elementnya, maka akan menampilkan ukuran maksimal aslinya

### Relative CSS Unit
- Salah satu satuan unit relative CSS unit, yaitu %, rem, vh, vw
- Ukuran relative `rem` dan `em` sama sama mengikuti ukuran huruf yang membedakan rem mengikuti ukuran huruf root elemen/HTML sedangkan em mengikuti parent elemen terdekat
- `rem` mengikuti font-size HTML. Ukuran huruf default HTML untuk device laptop itu 16px. Contoh: `font-size: 2rem;` (maka 2 kali 16px)

### Media Query
- Mengatur lebar suatu element atau memberikan style lain yang berbeda-beda sesuai dengan  ukuran dari browser

### Flexbox (*Flexible Box*)
- Memudahkan dalam mengatur layout, posisi, dan ukuran dari tiap element di dalamnya
- Mengatur arah dimensi hanya horizontal saja atau vertical saja
- Ada dua istilah penting saat belajar flexbox:
  - `container` adalah element yang membungkus dan mengatur tampilan dari element di dalamnya
  - `item` adalah element dalam container yang diatur tampilannya

### Grid
- Mengatur arah dimensi secara horizontal dan vertikal

## BOOTSTRAP 5
- Bootstrap adalah framework HTML, CSS, dan JavaScript
- Berfungsi untuk mendesain website menjadi responsive dengan cepat dan mudah
- Framework bootstrap tersusun dari kumpulan file CSS dan JavaScript yang berbentuk class dan tinggal pakai
- Bootstrap sering digunakan website pemerintah
- Framework bootstrap dan tailwind jangan dicollab
- Satu website hanya menggunakan satu framework saja menghindari bentrok class dan menghemat memory
- Cara menggunakan bootstrap:
  - Buka [Bootstrap 5](https://getbootstrap.com/)
  - Klik docs di navbar
  - Klik download di bagian side bar, scroll ke bagian CDN via jsDelivr
  - Copas code CDN ke file .html bagian header
- Grid system bootstrap dibangun dengan menggunakan flexbox
- Styling bootstrap bisa digabung sama css vanilla
