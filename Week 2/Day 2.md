# Writing Week 2 - Day 2
## Data Type Built in Prototype & Method
- Objek merupakan sebuah variabel yang pasti menyimpan nilai (properti) dan fungsi (method)
- **Properti**: Ciri khas dari objek atau yang membedakan antara 1 objek dengan objek lain (variabel)
- **Method**: Tingkah laku dari objek (fungsi)

### Prototype
- Prototype adalah properti objek yang menjadi induk dan menghubungkan objek ke objek lain
- Semua objek dalam javaScript memiliki prototype
- Objek mewarisi method dan properti dari prototypenya
- Gunakan properti prototype untuk menambahkan properti dan metode baru ke prototype javaScript

### Data Type
- Tipe data adalah jenis data yang disimpan dalam variabel
- Tipe data merepresentasikan sebuah nilai yang berbeda dan mempermudah pemrosesan data
- Tipe data fundamental pada javascript:
  - String
  - Number
  - Boolean
  - Null
  - Undefined
  - Object

### String
- Objek string merupakan objek yang berisi properti dan method untuk memanipulasi tipe data string
- Method objek string dalam javascript:
  - string.length: Menghitung banyak karakter dari sebuah string
  - string.concat(): Menggabungkan dua atau lebih string
  - string.toLowerCase(): Mentransformasi semua huruf dalam teks menjadi huruf kecil
  - string.toUpperCase(): Mentransformasi semua huruf dalam teks menjadi huruf besar
- Contoh: string.length
![image](https://user-images.githubusercontent.com/85722923/193513100-3161abd0-5b3b-4aca-8399-189d12a9b96c.png)

### Number
- Objek number merupakan objek yang dapat melakukan operasi matematis
- Javascript bisa mengenali bilangan oktal dan hexadecimal
- Bilangan oktal akan dikenali jika dimulai dengan angka `0`. Contoh: 06072003
- Bilangan hexadecimal akan dikenali jika dimulai dengan `0x`. Contoh: 0xAE
- Method objek number dalam javascript:
  - .toExponential(): Menampilkan angka menjadi tampilan scientific notation
  - .toFixed(): Menampilkan angka dengan jumlah desimal yang tetap
  - .toPrecision(): Menampilkan angka dengan jumlah digit angka yang tetap tergantung nilai yang dijadikan sebagai argumen


    .toPrecision() menampilkan jumlah digit sebelum dan sesudah desimal
    ![image](https://user-images.githubusercontent.com/85722923/193515628-cfbc422a-66b2-43eb-9857-697fe607c61c.png)
  - .toString(): Mengonversi tipe data number menjadi string

### Math
- Objek math terdiri dari berbagai kosntanta dan juga method (fungsi)
- Objek math digunakan untuk fungsi pemangkatan, akar kuadrat, logaritma, dan trigonometri

#### Konstanta
- Konstanta disebut dengan read-only property dari objek Math
- Konstanta objek math dalam javascript:
  - Math.E: Berisi nilai dari logaritma natural e
  - Math.LOG10E: Berisi nilai dari logaritma natural e basis 10
  - Math.PI: Berisi nilai dari pi (π) dengan nilai 3.14

#### Method
- Method objek math mungkin akan jarang digunakan
- Digunakan jika ingin membuat aplikasi ilmiah atau kalkulator
- Method objek math dalam javascript:
  - Math.abs(): Menghasilkan nilai absolut (nilai negatif akan menjadi positif, nilai positif tetap positif)
  - Math.cos(): Menghitung nilai cosinus
  - Math.floor(): Pembulatan kebawah dari sebuah nilai desimal
  - Math.max(): Mencari angka paling besar diantara argumen
  - Math.min(): Mencari angka paling kecil diantara argumen
  - Math.pow(): Mencari hasil pemangkatan
  - Math.sqrt(): Mencari hasil dari akar kuadrat sebuah angka

### Primitive & Non-Primitive
- Tipe data primitive: string, number, Boolean, bigint, null, undefined
- Dalam javascript hampir semua tipe data non-primitif merupakan objek. Array = objek

> Nilai `null` dan `undefined` tidak memiliki objek pembungkus. Jadi, kedua nilai tersebut tidak memiliki method dan properti serta prototype
