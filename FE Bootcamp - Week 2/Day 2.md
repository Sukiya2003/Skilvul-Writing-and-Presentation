# WRITING WEEK 2 FE - DAY 2
## REACT ROUTER
- React router merupakan library external yang digunakan untuk routing pada react
- Routing merupakan istilah pada web development untuk menghandle request dari user berdasarkan URL yang dikunjungi
- Library react router digunakan untuk mengarahkan page satu ke page yang lain berdasarkan path URL yang ditentukan
- React router memiliki 2 jenis router yang dapat digunakan, yaitu:
  - <HashRouter>: digunakan jika ingin membuat sebuah web yang static atau tidak ada server untuk me-render data yang dinamis
  - <BrowserRouter>: digunakan jika ingin membuat web yang menggunakan data dinamis dengan server backend

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
  - Didalam route terdapat dua properti, yaitu `path` dan `element`
    - `path`: sebagai acuan untuk pindah ke alamat halaman mana 
    - `element`: yang akan memanggil page yang kita punya
![image](https://user-images.githubusercontent.com/85722923/200257124-a158f1ed-28c7-421d-a6ab-69384e554644.png)

### Tiga Cara Penggunaan Router
- Routing Dasar
- Dynamic Routing
  - Digunakan untuk route pada data yang bersifat dinamis (sering berubah-ubah)
  - Menggunakan parameter `:id`
  - Contoh
```js
  import {Link,Route, Routes} from 'react-router-dom';
  import Artist from './Artist';
  import './App.css';
  
  function App() {
  return (
  <>
  <ul>
  <li><Link to="/artist/Ariana">Ariana</Link></li>
  <li><Link to="/artist/Taylor">Taylor</Link></li>
  <ul>
  
  <Routes>
  <Route path="/artist/:name" element={<Artist />}/>
  </Routes>
  </>
   );
  }
```
- Nested Routing
  - Digunakan bila terdapat banyak rute yang menggunakan parent route yang sama
  - Langkah yang dapat dilakukan adalah membuat parent route digunakan untuk semua child route. Kemudian di dalam parent route letakkan semua komponen child route
  - Contoh
```js
  import User from './user/User';
  import Setting from './user/setting/Setting';
  import Profile from './user/profile/Profile';
  import Favorite from './favorite/Favorite';

  function App() {
    return (
      <>
    <ul className='user'>

    <li><Link to="/">Home</Link></li>
    <li><Link to="/user">User</Link></li>
    <li><Link to="/favorite">FavoriteKu</Link></li>
    <li> <Link to="/galeri">Galeri</Link></li>
    </ul>

    <Routes>
          <Route path='/' element={<Home/>}/>
          <Route path='/User' element={<User/>}/>
          <Route path='/Gallery' element={<Gallery/>}/>
          <Route path='/Favorite' element={<Favorite/>}/>

          {/* Nested router */}
          <Route path='/Favorite/Music' element={<Music/>}/>
          <Route path='/User/Profile' element={<Profile/>}/>
          <Route path='/User/Settings' element={<Settings/>}/>
    </Routes>
     </>
    );
  }
```
      
**Catatan:**
- Get data akan dilakukan di file App.jsx tetapi untuk proses logic dan pemanggilan component akan dilakukan di halamannya masing-masing
- `BrowserRouter` digunakan untuk membuat routing pada aplikasi react
- `Routes` digunakan untuk membungkus tag <Route />
- `Route` digunakan untuk merender komponen berdasarkan jalur yang ditentukan
- `Link to` digunakan untuk berpindah antar halaman, property `to` untuk merujuk pada path di Route yang akan dituju
- Link ibarat tag <a> atau anchor dan `to` ibarat href di HTML
- Jika ingin mengetahui link mana yang aktif maka ganti <link to> menjadi `<NavLink to>`
```js
  <NavLink to=”/” exact activeStyle={
    {color:’red’}
  }>Home</NavLink>
```


