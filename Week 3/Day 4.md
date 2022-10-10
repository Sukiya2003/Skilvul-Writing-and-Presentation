# WRITING WEEK 3 - DAY 4
## JS INTERMEDIATE - ASYNCHRONOUS
### Asynchronous of JavaScript
- Javascript dijalankan pada satu proses atau single-thread
- **Single-thread** atau satu jalur dimana urutan eksekusi kode dilakukan secara berurutan atau synchronous
- **Synchronous** dimana setiap perintah di eksekusi satu persatu sesuai urutan kode yang dituliskan
  - Output dari synchronous akan sesuai urutan, karena setiap perintah harus menunggu perintah sebelumnya selesai. Proses antrian ini disebut *blocking*
- **Multi-thread** atau banyak jalur yang memungkinkan program dapat dipecah dan mengerjakan lebih dari satu tugas dalam satu waktu
- **Asynchronous** dimana proses eksekusi dilakukan secara tidak berurutan (bisa menjalankan perintah lain selagi menunggu suatu perintah diproses)
  - Output dari asynchronous tidak selalu sesuai urutan kode, tetapi berdasarkan waktu proses
  - Proses asynchronous disebut *non-blocking*
- Asynchronous pada javascript memiliki 3 kunci utama, yaitu:
  - Callback
  - Promise
  - Async Await

### Asynchronous - Callback
- Callback merupakan function, namun cara eksekusinya berbeda dengan function biasa
- Function biasa dieksekusi secara langsung (dari atas ke bawah), *callback* dieksekusi pada poin tertentu (parameter)
- Callback dapat digunakan dalam synchronous maupun asynchronous
- Contoh asynchronous
![image](https://user-images.githubusercontent.com/85722923/194787369-9f350c67-2ee3-4baa-ab5d-9dbc47c517eb.png)
- Penjelasan:
  - `setTimeout()`: metode panggilan fungsi setelah beberapa millisecond (delay)
  - `p2` akan kedelay selama 100 millisecond atau 0.1 second
- Contoh penggunaan callback pada asynchronous
![image](https://user-images.githubusercontent.com/85722923/194787841-97762f47-d098-4336-b921-15361dd7fc59.png)
- Penjelasan:
  - Penggunaan callback untuk memperbaiki urutan p1, p2, p3 asynchronous
  - Buat fungsi `p3` menjadi callback untuk `p2`


### Asynchronous - Promise
- Promise merupakan fitur terbaru dari ES6
- Promise merupakan object yang merepresentasikan 3 state:
  - Pending (dalam proses)
  - Fulfilled (berhasil)
  - Rejected (gagal)
- Promise biasanya digunakan sebagai alternatif *callback*, ketika terdapat callback di dalam callback di dalam callback lagi
- Promise hanya dapat berjalan di asynchronous
- Promise dapat membuat kode lebih readable
- Promise memiliki error handling. Jadi, ketika ada kesalahan maka dapat ditindak lanjuti
- Promise mengembalikan object dan hanya dapat digunakan pada satu event
- Untuk membuat promise cukup dengan memanggil constructornya. Contoh penggunaan 3 state:

1. Pending merupakan state awal sebelum menjadi fullfilled atau rejected. Penggunaan state pending ada pada state fulfilled dan rejected

2. Fulfilled


![image](https://user-images.githubusercontent.com/85722923/194790834-ccbf9b76-78a3-4627-96b2-52b9118ff8e0.png)
- Keterangan:
  - `.then()` untuk mengakses promise fulfilled
  - Setelah 2000 ms maka akan tampil `berhasil` di tab console

3. Rejected


![image](https://user-images.githubusercontent.com/85722923/194790893-fe17a394-068f-44de-8cd9-cc11d3fb2ed8.png)
- Keterangan:
  - `.catch()` untuk mengakses promise rejected
  - Setelah 300 ms maka akan tampil `batal` di tab console

### Asynchronous - Async/Await
- Fitur yang hadir sejak ES2017 (ES8)
- Terdapat 2 kata kunci, yaitu `async` dan `await`
```js
    async function f() {

      let janji = new Promise((resolve, reject) => {
        setTimeout(() => resolve("done!"), 300)
      });

      let result = await janji; //wait until the promise resolves
      console.log(result); //Output: done!
    }

    f();
```
- Penjelasan:
  - `async` untuk mengubah function menjadi asynchronous
  - `await` untuk menunda eksekusi hingga proses asynchronous selesai. Dimana `console.log(result)` tidak akan di eksekusi sebelum proses `janji` selesai

### Asynchronous - Fetch
- Fetch merupakan cara baru dalam melakukan network request
- Fetch merupakan API yang memanfaatkan sebuah *Promise* dan diperkenalkan sejak ES6
- Untuk mengaksesnya, gunakan `fetch()` kemudian tuliskan URL yang akan dituju
```js
    fetch('<URL-to-the-resource-that-is-being-requested>')
           .then(response => {
               return response.json()
           })
           .catch(error => {
               console.log(error)
           })
           .then(function(data) {
               //variabel {data} siap digunakan! 
           })
```
- Penjelasan:
  - Fetch mengembalikan sebuah promise
  - Jika request pada fetch berhasil dilakukan, maka `.then()` akan terpanggil dan mengembalikan nilai objek sesuai response yang didapat
  - Jika request pada fetch gagal dilakukan, maka `.catch()` akan terpanggil dan menampilkan error pada console
  - Parameter data pada fungsi `.then()` merupakan nilai yang dikembalikan dari `response.json()` dan menjadi `undefined` jika fungsi fetch gagal dilakukan
