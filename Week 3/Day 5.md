# WRITING WEEK 3 - DAY 5
## JS INTERMEDIATE - WEB STORAGE

<!-- memanipulasi data menggunakan Web Storage -->
### What is HTML Web Storage?
- Web storage atau disebut DOM storage (*Document Object Model Storage*)
- Web storage merupakan salah satu web API yang dapat menyimpan data secara lokal di dalam browser pengguna (client-side)
- Data yang disimpan pada web storage akan bertahan lama karena data disimpan pada storage browser
- Sebelum HTML5, kita menggunakan *cookies* namun penyimpanan yang tersedia sangat kecil

### JavaScript Cookies
- Cookies merupakan tempat penyimpanan di browser dan server
- Data cookie disimpan maksimal 4096 byte atau 4Kb dan maksimal 180 cookie per domain (chrome)
- Cookie tidak bisa menyimpan data dalam jumlah besar
- Cookie diciptakan untuk memecahkan masalah "Bagaimana mengingat informasi tentang pengguna?"
- Kegunaan cookie:
  -  Menyimpan login informasi user
  -  Menyimpan konfigurasi website, misalnya bahasa
  -  Memberikan rekomendasi berdasarkan aktivitas, misalnya iklan, playlist, dan lainnya
- Javascript dapat membuat, membaca, dan menghapus cookie dengan properti `document.cookie`
- **Membuat cookie dengan javascript**
```js
    document.cookie = "username=John Doe; expires=Thu, 10 Oct 2022 12:00:00 UTC; path=/";
```
- Penjelasan:
  - Tanggal kadaluwarsa ditulis dalam waktu UTC
  - `path=/` memberi tahu browser secara default bahwa cookie milik halaman saat ini
- **Membaca cookie dengan javascript**
```js
    var x = document.cookie;
```
- Penjelasan:
  - `document.cookie` akan mengembalikan semua cookie dalam satu string. Seperti: `cookie1 = value; cookie2 = value;`
- **Mengubah cookie dengan javascript**
```js
    document.cookie = "username=John Smith; expires=Fri, 10 Oct 2022 12:00:00 UTC; path=/";
```
- Penjelasan:
  - Cara mengubah cookie sama seperti cara membuat cookie
  - Cookie lama akan ditimpa dengan cookie baru

### HTML Web Storage Objects
- HTML web storage menyediakan dua object atau tipe dalam menyimpan data pada browser pengguna:
  -  

### The localStorage Object


### The sessionStorage Object




