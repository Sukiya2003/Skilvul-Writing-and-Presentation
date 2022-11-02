# WRITING WEEK 1 FE - DAY 2
## Membuat Folder React
Terdapat 2 cara untuk membuat folder react:
- Biasa
  - Buka terminal (bash) ketikkan `npx create-react-app nama_aplikasi`
  - Tunggu proses loading sampai git bash menampilkan “Happy hacking!”
  - Ketikkan `cd nama_aplikasi`
  - Perintah untuk menjalankan project `npm start`
- Dengan [vite](https://vitejs.dev/guide/)
  - Buka terminal (bash) ketikkan `npm create vite@latest nama_aplikasi --template react`
  - Ketikkan `y` dan enter
  - Pilih framework `react`
  - Pilih variant `javascript`
  - Ikuti perintah yang sudah tertera di terminal:
    - `cd nama_aplikasi`
    - `npm install`
    - `npm run dev` perintah untuk menjalankan project
    - Buka link local di terminal dengan `ctrl + click link`
![image](https://user-images.githubusercontent.com/85722923/198905192-54c3d30b-64f0-4223-b171-fc29f1a62216.png)


Perbedaan kedua cara membuat folder react ini hanya pada kecepatan loading install dan struktur folder, dimana pada vite beberapa file akan dihapus tetapi tidak mempengaruhi project. Jika menggunakan vite maka file utama di folder src memiliki ekstensi .jsx (main.jsx) yang sebelumnya .js

## REACT JS COMPONENT
- Component merupakan salah satu core dari react js
- Component membagi user interface dalam satuan-satuan kecil yang apabila disatukan dengan component lain akan membentuk sebuah halaman utuh, seperti component navbar/header, searchBar, employeeList, dan lainnya
![component-based](https://user-images.githubusercontent.com/85722923/198900524-9c921f4e-494c-4f41-b586-ff3708b2dfd2.png)
- Component dibuat jika component tersebut memiliki sifat reusable code (digunakan atau dibutuhkan pada section atau page lain)
- Terdapat dua cara membuat component
  - Gunakan class
  ```js
      import React, {Component} from 'react'

      export default class Header extends Component {
        render() {
          return (
            <h1>Judul Halaman</h1>
          )
        }
      }
  ```
      
  - Gunakan function (rekomendasi dari dokumentasi resmi react js)
  ```js
      const NamaComponent = () => {
        return (
          <div>
            <h1>Ini contoh component</h1>
          </div>
        )
      }

      export default NamaComponent
  ```
- Cara membuat react js component
  - Buat folder `components` di dalam folder src
  - Sesuaikan nama file atau folder dengan component yang akan dibuat. Misal mau membuat member buat nama filenya `MemberInfo.jsx`
  - Nama folder, file, dan function component harus menggunakan huruf kapital diawal dan di kata selanjutnya
  - Panggil component pada halaman yang membutuhkan dengan import component pada file App.js

### CBA (Component Based Architecture)
- React menggunakan konsep CBA karena konsep ini react populer
- Sebelum belajar react kita masih menggunakan template based architecture dimana logicnya ditumpuk atau di copy paste pada seluruh halaman
- Kelebihan CBA ini memiliki logic masing-masing jadi jika terdapat error pada component maka hanya perlu memperbaiki component yang error saja tanpa harus membuka seluruh halaman

## PROPS DAN STATE
- Props dan state digunakan react untuk menghandle data di dalam component
- Props dan state bisa menjadi stateful atau stateless
- Stateless: tidak memiliki state, hanya memiliki props
- Stateful: memiliki state dan bisa mengirim state tersebut ke component
- Functional component hanya bisa menggunakan props itu sebabnya function component disebut stateless component
- Class component dapat menggunakan props dan state

### Props
- Props digunakan untuk komunikasi antara parent dan child
- Props merupakan parameter dari function component
- Props merupakan singkatan dari properties dimana argument diteruskan dari suatu component react ke component react lain melalui attribute HTML
- Yang bisa dikirim props adalah data, variables, state function, dan class
- Props bersifat read-only yang berarti data dari props tidak bisa diubah
- Tetapi kadang data perlu untuk diupdate. Solusinya adalah menggunakan state

### State
- State merupakan data local (nilai dari state ditentukan sendiri oleh suatu component)
- State digunakan untuk menghandle data component yang terus berubah
- Data state bersifat private yang hanya dapat diakses  di dalam component dimana state itu dibuat
- Stateless component adalah component yang tidak memiliki state internal sendiri, melainkan data yang didapatkan oleh komponen tersebut berasal dari luar (props)
- Stateful component adalah component yang memiliki state sendiri sehingga stateful component harus menggunakan react [hook](https://github.com/Sukiya2003/Writing-and-Presentation-Test/blob/b5362d7e040ece6c5b66d5f4221573d9e65be1e9/Week%201%20-%20FE%20Bootcamp/Day%204.md), seperti `setState` atau `useState`
- Cara menggunakan state:
  - Membuat state terlebih dahulu dengan `useState()`
  ```js
      import React, { useState } from 'react';

      export default function App() {
        const [state, setState] = useState('brachio');

        return (
          <div>
            <h1>Hello Devsaurus</h1>
            <p>My Name is {state}</p>
          </div>
        );
      }
  ```
  - Mengakses nilai state dengan curly brackets `{}`
  ```js
      import React, { useState } from 'react'; // import useState

      export default function App() {
        const [state, setState] = useState('brachio');

        return (
          <div>
            <h1>Hello Devsaurus</h1>
            <p>My Name is {state}</p>
          </div>
        );
      }
  ```
  - Mengupdate data state dengan `setState()`
  ```js
      import React, { useState } from 'react';

      export default function App() {
        const [state, setState] = useState('brachio');

        const handleChange = () => {
          setState('t-rex');
        };

        return (
          <div>
            <h1>Hello Devsaurus</h1>
            <p>My Name is {state}</p>
            <button onClick={handleChange}>Change Name</button>
          </div>
        );
      }
  ```

## REACT JS STYLING
Terdapat beberapa cara melakukan styling pada component react js
- External CSS
  - Cara ini sama seperti membuat external CSS biasa
  - Buat file .css lalu import filenya ke component yang dibuat
  - Styling yang ada pada file css akan di implementasikan pada component sesuai `className` yang dipanggil
  ```css
      .DottedBox {
        margin: 40px;
        border: 5px dotted pink;
      }

      .DottedBox_content {
        font-size: 15px;
        text-align: center;
      }
  ```
  ```js
      import React from 'react'
      import './DottedBox.css'

      const DottedBox = () => (
        <div className="DottedBox">
          <p className="DottedBox_content">Get started with CSS styling</p>
        </div>
      )

      export default DottedBox
  ```

- Inline CSS
  - Tuliskan styling didalam file component kita
![image](https://user-images.githubusercontent.com/85722923/198902016-4aa27318-229f-43d9-964d-e9da4fc3c53a.png)

- Bootstrap
Kita dapat menggunakan framework bootstrap ke react tetapi gunakan salah satu cara agar tidak tabrakan
  - Menggunakan bootstrap CDN
    - Buka webiste [bootstrap](https://getbootstrap.com/)
    - Lalu copy paste link CDN ke folder `public/index.html` pada bagian tag head
    - CSS : `<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">`
    - JavaScript: `<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM" crossorigin="anonymous"></script>`

    - Setelah paste, buka folder `src/App.jsx` dan edit code bootstrap di file tersebut
    - Simpan dan jalankan project

  - Menginstall bootstrap melalui npm
    - Buka terminal (bash) dan arahkan ke dalam folder project react
    - Ketikkan `npm install bootstrap`
    - Lalu import file bootstrap ke dalam folder src/main.jsx atau src/index.js
    - CSS: `import "bootstrap/dist/css/bootstrap.min.css"`
    - JavaScript: `import "bootstrap/dist/js/bootstrap.bundle.min"`
    - Simpan dan jalankan project
