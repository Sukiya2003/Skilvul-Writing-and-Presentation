# WRITING WEEK 1 FE - DAY 5
## FORMS PADA REACT JS
- Form atau formulir dimana user bisa menginput data yang disimpan pada server atau ditampilkan pada tampilan website
- React JS menggunakan form agar user bisa berinteraksi dengan halaman web, seperti mengisi biodata, login, register, mencari data, dan lainnya
- Terdapat 2 konsep dalam form react js, yaitu controlled component dan uncontrolled component

### Controlled Component
- Data atau value setiap element dalam form disimpan dalam component state
- Sebuah element HTML yang valuenya dikontrol oleh react disebut controlled component
- Contoh
```js
    import React, { useState } from 'react';

    export default function App() {
      const [state, setState] = useState('');

      const handleSubmit = () => {
        alert(`Hi ${state}`);
      };

      const handleChange = (e) => {
        setState(e.target.value);
      };

      return (
        <div>
          <h1>Masukan Nama</h1>
          <form onSubmit={handleSubmit}>
            <label>
              Nama:
              <input type="text" value={state} onChange={handleChange} />
            </label>
            <input type="submit" value="Submit" />
          </form>
        </div>
      );
    }
```
![image](https://user-images.githubusercontent.com/85722923/198907518-b7d5c972-dbb5-4178-bf74-a6ec272ba2c5.png)
- Penjelasan:
  - Value dari element `<input>` disimpan dalam state dan diupdate menggunakan `setState()`
  - Handler `handleSubmit()` dieksekusi ketika form disubmit oleh user
  - `e.target.value` merupakan event object yang mewakili value dari sebuah element DOM

### Uncontrolled Component
- Data atau value tidak dikontrol oleh react
- Contoh uncontrolled component adalah `<input type="file" />`
- Untuk mengakses file maka harus menggunakan file API dan Refs
- Refs digunakan untuk mengakses react element di dalam method render
- Membuat Refs gunakan `React.createRef()` yang dipasang ke sebuah elemen lewat attribute ref
```js
    import React from "react";

    export default function App() {
      const fileInput = React.createRef();

      const handleSubmit = (e) => {
        e.preventDefault();
        alert(`Nama file: ${e.fileInput.current.files[0].name}`);
      };

      return (
        <div>
          <h1>Upload File</h1>
          <form onSubmit={handleSubmit}>
            <label>
              Pilih File 
              <input type="file" ref={fileInput} style={{marginLeft: "5px"}} />
            </label>
          </form>
        </div>
      );
    }
```
![image](https://user-images.githubusercontent.com/85722923/198907532-d8129dd7-5818-4ec0-963b-d87908f1d326.png)

- Catatan materi forms:
  - Attribute onChange digunakan untuk mengambil perubahan data dari inputan
  - Attribute onSubmit merupakan event yang menghandle submit dari form (mensubmit data sehingga data bisa diproses)
  - Jadi, onChange untuk mengambil data sedangkan onSubmit untuk memberi data dari inputan
  - preventDefault digunakan agar halaman browser tidak memuat ulang atau refresh
