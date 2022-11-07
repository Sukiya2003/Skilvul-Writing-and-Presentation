# WRITING WEEK 2 FE - DAY 3
## STATE MANAGEMENT REACT REDUX
Sebuah aplikasi react memiliki beberapa component, jika ingin mengirim data dari component A ke component D, maka harus menambahkan props di component C dan D. Hal ini tidak menjadi masalah jika aplikasi react memiliki sedikit component, tetapi jika component pada aplikasi react bertingkat maka kita harus menambahkan props di setiap component yang dilewati. Hal ini disebut dengan *props drilling*. 
![image](https://user-images.githubusercontent.com/85722923/200297470-abc244b9-f3f2-4ef4-9ebc-60a5c56caa1b.png)
- Props drilling merupakan kegiatan mengoper props yang sama dari parent ke child-child
- Alur data dari props drilling tentu akan panjang dan ribet
- Salah satu cara mengatasi props drilling adalah dengan menggunakan **Redux**
- Redux merupakan salah satu state management
- State management adalah library yang digunakan untuk mengelola state pada suatu aplikasi JavaScript
- Contoh state management: redux, mobX, flux, recoil
- Redux diperkenalkan pertama kali pada tahun 2015
- Redux adalah satu tempat penyimpanan untuk mengelola data dan meamnipulasi state
- Ketika banyak data yang berubah dari waktu ke waktu maka gunakan redux
- Redux didukung oleh package middleware yang bertebaran di npm
- Package middleware ini memudahkan dalam melakukan development seperti redux-thunk, redux-saga, redux-persist, dan lainnya

### Langkah 1: Setup React Redux
- Buat aplikasi react js atau buka folder aplikasi react js jika sudah ada
- Buka terminal aplikasi react dan install redux dengan perintah `npm install redux react-redux`
- Buat folder redux di dalam folder src

### Langkah 2: Setup Redux Store
- Buat file `store.js` pada folder redux


![image](https://user-images.githubusercontent.com/85722923/200301421-161cf241-4157-486e-b74e-2f0a9ae6774c.png)

### Langkah 3: Setup Types
- Contoh kali ini membahas redux yang menyimpan state **counter**
- Buat folder `types` di dalam folder redux dan sebuah file `counter.js`
- Export constanta dengan nama kegiatan tertentu


![image](https://user-images.githubusercontent.com/85722923/200303361-7f390c42-7f5a-4cbc-af8b-4cf6d1879c26.png)

### Langkah 4: Setup Actions
- Buat folder `actions` di dalam folder redux dan sebuah file `counter.js`
- Semua action akan diletakkan pada folder ini


![image](https://user-images.githubusercontent.com/85722923/200303745-192777dd-70ca-4f1f-a533-7d40747e438a.png)
- Penjelasan:
  - Pada line 1 import semua kegiatan yang kita miliki pada tipe kegiatan yang akan terjadi pada reducer counter
  - Pada line 3-5 merupakan sebuah arrow function dengan nama `increment` yang hanya mengirim sebuah object (dispatch) ke reducer kita dengan isian object seperti tertera pada line 4
  - Pada line 7-9 sama dengan baris function sebelumnya hanya beda kegiatan, yaitu `decrement`

### Langkah 5: Setup Reducer
- Buat folder `reducers` di dalam folder redux dan sebuah file pertama `index.js`
- Dalam folder ini semua states akan tinggal
- File index.js digunakan untuk indexing setiap reducer dan menggabungkan semua state yang dimiliki


![image](https://user-images.githubusercontent.com/85722923/200304485-3e08a48d-e81a-4695-8f13-34689ecfe50c.png)
- Penjelasan:
  - Line 1 import `combineReducers` sebuah function dari package redux untuk menggabungkan object-object state yang dimiliki
  - Line 3 import counter dari file Counter.js
  - Line 5 export secara default object yang sudah digabung menggunakan `combineReducers`
- Jika memiliki banyak reducers, maka
```js
  import counter from "./counter";
  import people from "./people";
  import todo from "./todo";

  export default combineReducers({ counter, people, todo });
```
- Buat file reducer dengan nama counter.js pada folder reducers


![image](https://user-images.githubusercontent.com/85722923/200305687-02ae95f3-bead-4d88-9c5a-da71ac684701.png)
- Penjelasan:
  - Pada line 1 sama seperti pada file actions/counter.js dimana kita import semua kegiatan yang akan terjadi pada reducer counter
  - Pada line 3 buat sebuah variable dengan nama `initialState` yang mana isinya adalah sebuah object untuk menampung keadaan state dari reducer counter pada saat aplikasi pertama kali di load
  - Pada line 7 buat function reducer, dimana function ini menerima argument state yang akan diisi dengan `initialState` ketika pertama diload dan argument kedua yaitu `action`, argument action ini akan berisi sesuai dengan object yang dikirim dari file [/src/redux/actions/counter.js], yaitu `{ type: INCREMENT }`
  - Pada line 8-15 buat logic pemisah setiap kegiatan dengan code `switch` dan dicek berdasarkan `action.type`
  - Pada line 9-10 deklarasikan setiap kegiatan, kita bisa taruh logic penyimpanan state kita pada baris tersebut seperti melakukan mapping data, memfilter data, data penjumlahan dan lainnya
  - Pada line berikutnya kita bisa sisipkan kegiatan yang lain
  - Pada line 18 `export default reducer` agar bisa digunakan pada file [/src/redux/reducers/index.js]

### Langkah 6: Provider
![image](https://user-images.githubusercontent.com/85722923/200307859-bd7c5af1-39de-4e74-83c9-51c7cb8bdedf.png)
- Penjelasan:
  - Pada line 7-8 import Provider dari react-redux dan store data pada folder [redux/store/index.js]
  - Pada line 12-14 bungkus aplikasi dengan Provider dan sertakan props store yang diisi store

### Langkah 7: App.js
![image](https://user-images.githubusercontent.com/85722923/200308644-9aeb9975-5f28-4b3c-ae20-f2291aeb4687.png)
- Penjelasan:
  - Pada line 3 import `useSelector` dan `useDispatch` dari react-redux
  - Import setiap kegiatan yang dibutuhkan pada line 5 yaitu increment dan decrement dari file [/src/redux/actions/counter.js]
  - Pada line 8 buat variable baru dengan nama `counter`, lalu isi dengan cara panggil function `useSelector` dan sisipkan arrow function
  - Function callback tersebut menerima 1 argument yaitu `state` lalu pada bagian returnnya panggil `state.counter` atau `state[namaReducer]` jika memiliki reducer lainnya
  - Pada line 9 siapkan function `dispatch` untuk melakukan action nantinya
  - Pada line 15-17 terdapat dua button untuk menambah atau mengurangi state saat ini dan 1 text untuk menunjukkan keadaan state saat ini
  - Pada setiap function beri event `onClick` dimana ketika diclick button akan menjalankan sebuah function dispatch dan sisipkan action yang sudah dibuat sebelumnya pada file [/src/redux/actions/counter.js]
