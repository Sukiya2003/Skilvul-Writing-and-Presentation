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
- Data cookie disimpan maksimal 4096 byte atau 4KB dan maksimal 180 cookie per domain (chrome)
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
  - `window.localStorage`: menyimpan data tanpa expiration date
  - `window.sessionStorage`: menyimpan data untuk satu sesi (data akan hilang jika tab browser ditutup)
- Sebelum menggunakan web storage, pastikan browser mendukung fitur localStorage maupun sessionStorage
```js
    if (typeof(Storage) !== "undefined") {
      // Code for localStorage/sessionStorage.
    } else {
      // Sorry! No Web Storage support..
    }
```
- Data yang disimpan pada web storage dapat dilihat pada:
  - Klik kanan pada web browser, pilih *inspect*
  - Lalu pilih tab *application* (Google Chrome) atau *storage* (Mozilla Firefox)
![image](https://user-images.githubusercontent.com/85722923/194801869-9fdcc210-11ba-45e8-967c-c7eb4bfe16f6.png)
![image](https://user-images.githubusercontent.com/85722923/194801614-ef7ec9b2-e0fd-4437-8a16-3aa5635545d5.png)

### The localStorage Object
- Menyimpan data tanpa expiration date pada browser
- Data tidak bakal terhapus ketika browser ditutup dan data akan tersedia di hari, minggu, atau tahun selanjutnya
- Penyimpanan localStorage sebesar 10MB
- **Mendeklarasikan suatu nilai**
```js
    localStorage.setItem('variabel', 'value');
```
- **Mengambil data**
```js
    localStorage.getItem('variabel');
```
- **Menghapus data**
```js
    localStorage.removeItem('variabel');
```
- **Menghapus semua localStorage**
```js
    localStorage.clear();
```

### The sessionStorage Object
- Menyimpan data untuk satu sesi pada browser (data akan hilang jika tab browser ditutup)
- Penyimpanan sessionStorage sebesar 5MB
- **Mendeklarasikan suatu nilai**
```js
   sessionStorage.setItem('variabel', 'value');
```
- **Mengambil data**
```js
    sessionStorage.getItem('variabel');
```
- **Menghapus data**
```js
    sessionStorage.removeItem('variabel');
```
- **Menghapus semua sessionStorage**
```js
    sessionStorage.clear();
```
