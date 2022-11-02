# WRITING WEEK 1 FE - DAY 4
## REACT LIFECYCLE METHOD
![image](https://user-images.githubusercontent.com/85722923/198909810-540be6bc-6079-4489-909e-00bcf8f66eaa.png)
- Component react js memiliki alur hidup (lifecycle) selama berjalan di browser
- Struktur lifecycle:
  - Constructor: inisialisasi struktur data pada suatu component
  - Function: fungsi yang dibutuhkan pada komponen
  - Render: proses return atau mengembalikan component asli
- Tiga fase lifecycle component class:
  - Mounting
  - Updating
  - Unmounting

### Fase Mounting
- Fase ketika components di buat atau pertama kali di render ke DOM
- Mounting memiliki 3 method yang akan dieksekusi:
  - `componentWillMount`: method yang akan di eksekusi pertama kali, kemudian akan mengeksekusi method render
  - `render`: method render akan menyimpan file jsx yang nantinya akan di render ke DOM
  - `componentDidMount`: setelah method render dieksekusi maka method ini akan dieksekusi. Pada method componentDidMount akses dan manipulasi DOM dilakukan serta request data dari API

### Fase Updating
- Fase ketika sebuah component akan di render ulang
- Fase ini biasanya terjadi karena ada perubahan pada state atau props yang mengakibatkan perubahan DOM
- Updating memiliki 5 method yang akan dieksekusi:
  - `componentWillReceiveProps`: method ini akan dieksekusi jika state yang ada di component akan diupdate atau diubah dengan nilai props yang baru
  - `shouldComponentUpdate`: method ini untuk menentukan apakah sebuah component akan dirender ulang atau tidak. Method ini akan mengembalikan nilai boolean (true or false), jika true maka component akan dirender ulang begitu pula sebaliknya
  - `componentWillUpdate`: method ini akan dieksekusi jika method shouldComponentUpdate mengembalikan nilai true
  - `render`: setelah method componentWillUpdate berhasil dieksekusi maka method render akan dijalankan
  - `componentDidUpdate`: method ini sama dengan method componentDidMount yaitu untuk manipulasi DOM dan request data API

### Fase Unmounting
- Fase ketika component dihapus dari DOM yang sebelumnya didefinisikan
- Unmounting hanya memiliki 1 method yang akan dieksekusi, yaitu
  - `componentWillUnmount`: method ini dijalankan sebelum sebuah component di hapus dari DOM

## HOOKS REACT JS
- Hooks merupakan fitur baru react js yang dikenalkan pada tahun 2018
- Hooks digunakan untuk memudahkan penggunaan functional components agar bisa menggunakan state dan lifecycle lainnya
- Sebelumnya state dan lifecycle hanya bisa digunakan pada class component tetapi dengan hooks dapat digunakan pada functional component
- Beberapa contoh react hooks:
  - useState: digunakan untuk membuat state di function komponen
  - useEffect: digunakan untuk menambahkan side effect ke function komponen. Penggunaan fungsi ini mirip seperti method lifecycle componentDidMount, componentDidUpdate, dan componentWillMount di class component
  - useRef: digunakan untuk mengakses DOM node dalam sebuah komponen. Jika ingin mengakses element input, maka bisa menambahkan ref ke element inputnya
  - useMemo: digunakan untuk mengoptimalkan performance atau hasil sebuah function
  - useCallback: digunakan untuk mencegah render child komponen yang tidak di perlukan
- Hooks yang sering digunakan adalah `useState` dan `useEffect` 
- Cara tau kalau react kita menggunakan hooks dari keyword `use` seperti `useState`, `useEffect`

### Peraturan Hooks
Hooks merupakan fungsi javascript tetapi hooks memberlakukan beberapa peraturan:
- Jangan memanggil hooks dari dalam loops, conditions atau nested functions
- Jangan memanggil hooks dari fungsi-fungsi javascript biasa
- Panggil hooks dari komponen-komponen fungsi react
- Panggil hooks dari [custom hooks](https://id.reactjs.org/docs/hooks-custom.html)
```js
    // Kita melanggar aturan pertama dengan menggunakan hook didalam sebuah condition
    if (name !== '') {
      useEffect(function persistForm() {
        localStorage.setItem('formData', name);
      });
    }
```
```js
    useEffect(function persistForm() {
      // Kita tidak lagi melanggar aturan pertama
      if (name !== '') {
        localStorage.setItem('formData', name);
      }
    });
```

### Perbedaan Class Component dan Functional Component
- Functional component memiliki struktur code yang lebih ringkas
- Functional component hanya bisa menggunakan props
- Functional component disebut sebagai `stateless component`
- Class component dapat menggunakan state dan props
