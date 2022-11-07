# WRITING WEEK 2 FE - DAY 2
## REACT ROUTER
- React router merupakan library external yang digunakan untuk routing pada react
- Routing merupakan istilah pada web development untuk menghandle request dari user berdasarkan URL yang dikunjungi
- Library react router digunakan untuk mengarahkan page satu ke page yang lain berdasarkan path URL yang ditentukan
- React router memiliki 2 jenis router yang dapat digunakan, yaitu:
  - HashRouter: digunakan jika ingin membuat sebuah web yang static atau tidak ada server untuk me-render data yang dinamis
  - BrowserRouter: digunakan jika ingin membuat web yang menggunakan data dinamis dengan server backend

### Varian React Router
- React router memiliki beberapa varian berdasarkan platform dan kebutuhan, yaitu:
  - `react-router-dom`: digunakan untuk routing react web
  - `react-router-native`: digunakan untuk routing pada react native
  - `react-router-redux`: digunakan untuk integrasi redux

### Setiing Awal React Router
- Buat project react js atau buka folder project react js jika sudah ada
- Setiap membuat react router instalasi versi npm dengan `npm install react-router-dom@6`
- Untuk memastikan react router sudah terinstall, lihat di file `package.json` bagian dependencies terdapat versi `react-router-dom` yang sudah terinstall

### Membuat Halaman React Router
- Buat folder `pages` di dalam folder src yang akan menampung halaman-halaman router
- Buat file baru dan sesuaikan nama file dengan halaman yang akan dibuat. Misal HomePage.jsx dan AboutPage.jsx
- Lalu, routing alamat halaman yang sudah dibuat dan jangan lupa diimport setiap halaman yang diroute pada file App.jsx

### Menggunakan React Router
- Import BrowserRouter di file main.jsx `import { BrowserRouter } from ‘react-router-dom’;`
- Buat tag `<BrowserRouter>` di file main.jsx dimana BrowserRouter akan membungkus `<App />`. Semua yang dibungkus oleh BrowserRouter boleh menggunakan fitur react router
```js
    <BrowserRouter>
      <App />
    </BrowserRouter>
```
- File App.jsx:
  - Letakkan `import { Routes, Route, Link } from "react-router-dom";` untuk menampung alamat halaman yang akan dibuat
  - Didalam tag `<Routes>` terdapat tag `<Route />
  - Didalam route terdapat `path` sebagai acuan untuk pindah ke alamat halaman mana dan `element` yang akan memanggil page yang kita punya
![image](https://user-images.githubusercontent.com/85722923/200257124-a158f1ed-28c7-421d-a6ab-69384e554644.png)

**Catatan:**
- Get data akan dilakukan di file App.jsx tetapi untuk proses logic dan pemanggilan component akan dilakukan di halamannya masing-masing
- `BrowserRouter` digunakan untuk membuat routing pada aplikasi react
- `Routes`
- `Route`
- `Link to` digunakan pada react router untuk mengganti tag <a> atau anchor dan `to` ibarat href di HTML
- `


