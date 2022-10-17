# WRITING WEEK 4 - DAY 1
## HUBUNGAN SERVER (BACKEND) DAN WEBSITE (FRONTEND)
- Data dinamis yang ada di website didapat dari server lalu ditampilkan
- Bagian frontend membuat tampilan, styling, dan menampilkan data
- Bagian backend bagian yang dibelakang layar (database dan server)
- Proses sebuah aplikasi atau website dinamis:
![image](https://user-images.githubusercontent.com/85722923/196163650-dfea2a99-2522-49e7-aa82-4b17860d3aa1.png)
  - Ketika user membuka aplikasi atau website maka akan meminta data ke server
  - Server akan mengambil data ke database
  - Lalu, database memberi data ke server
  - Server menerima data dari database dan dikirim ke bagian frontend
  - Selama proses transfer data ada API yang berfungsi sebagai perantara antara bagian frontend dan backend
- *Noted*:
  - Semua data tersimpan dalam database
  - Database hanya menyimpan data terstruktur, seperti string dan number
  - Untuk data yang tidak terstruktur, seperti video dan audio itu memiliki penyimpanan sendiri (mirip hard disk)
  - Alamat penyimpanan video dan audio akan disimpan di database
  - Biasanya data yang dikirim dan diterima oleh API itu dalam bentuk JSON
  - JSON (*JavaScript Object Notation*)
  - JSON sama seperti object tetapi bagian property ditulis dengan kutip 2. Contoh: `"status": true;`
- Cara menangkap API itu dengan menggunakan promise dan async/await

## JS ASYNCHRONOUS - ASYNC AWAIT
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

### Promise JavaScript
- Promise merupakan fitur terbaru dari ES6
- Promise merupakan object yang merepresentasikan 3 state di masa yang akan datang:
  - Pending (dalam proses)
  - Fulfilled (berhasil)
  - Rejected (gagal)
- Promise dapat membuat kode lebih readable
- Promise mengembalikan object dan hanya dapat digunakan pada satu event
- Untuk membuat promise cukup dengan memanggil constructornya
- Untuk membuat promise cukup dengan memanggil constructornya. Contoh penggunaan 3 state:

1. **Pending** merupakan state awal sebelum menjadi fullfilled atau rejected. Penggunaan state pending ada pada state fulfilled dan rejected

2. **Fulfilled**


![image](https://user-images.githubusercontent.com/85722923/194790834-ccbf9b76-78a3-4627-96b2-52b9118ff8e0.png)
- Keterangan:
  - `.then()` untuk mengakses promise fulfilled
  - Setelah 2000 ms maka akan tampil `berhasil` di tab console

3. **Rejected**


![image](https://user-images.githubusercontent.com/85722923/194790893-fe17a394-068f-44de-8cd9-cc11d3fb2ed8.png)
- Keterangan:
  - `.catch()` untuk mengakses promise rejected
  - Setelah 300 ms maka akan tampil `batal` di tab console

## JS ASYNCHRONOUS - FETCH
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
