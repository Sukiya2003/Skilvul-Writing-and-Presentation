# Writing Week 2 Day 1
## JavaScript - Scope
- Scope adalah konsep dalam flow data variabel
- Scope digunakan untuk menentukan suatu variabel apakah bisa diakses atau tidak
- Terdapat 2 macam scope, yaitu global scope dan local scope

### Global Scope
- Global scope merupakan variabel yang dapat diakses dimanapun dalam suatu file
- Variabel harus dideklarasikan di luar blocks `{}`
- Contoh:
```js
    let myName = "Sukiy";

    function greeting() {
        return myName;  //Sukiy
    }
    console.log(myName);  //Output: Sukiy
    
    //variabel myName dideklarasiakan secara global scope
```

### Local Scope
- Local scope merupakan variabel yang hanya dapat diakses di dalam blocks saja
- Variabel harus dideklarasikan di dalam blocks `{}`, seperti function, conditional, dan looping
- Contoh:
```js
    function greeting() {
        let myName = "Sukiy";
        return myName;
    }
    console.log(greeting());  //Output: Sukiy
```

## JavaScript - Function
- Blok kode untuk menyelesaikan 1 task dengan jumlah yang banyak dan berulang kali
- Membuat function
```js
    function sapa() {
      return "Selamat Pagi!";   //function body
    }
```
- Memanggil function
```js
    sapa()  // panggil nama function
    console.log(sapa());    //Output: Selamat Pagi!
```

### Parameter dan Argument
- Parameter: Menerima sebuah inputan data dan menggunakannya untuk melakukan task
- Argument: Nilai yang dimasukan ke dalam suatu function
- Jumlah argumen harus sama dengan jumlah parameter
```js
    function luasPersegi(s) {
        return s * s;
    }
    console.log(luasPersegi(4));  //Output: 16
```
Penjelasan code:
- `s` : parameter
- `4` : argument

### Arrow Function
- Cara lain menuliskan function
- Arrow function merupakan fitur terbaru pada ES6 (JavaScript version)
- Penulisan fungsi menjadi lebih singkat dan lebih mudah dibaca
```js
    const penjumlahan = (bil1, bil2) => {
      const hasil =  bil1 + bil2;
      return hasil;
    };

    console.log(penjumlahan(3, 4)); //Output: 7
```

## JavaScript Error Messages & Debugging
### Error Messages
- Error merupakan pesan yang memberitahu kesalahan yang terjadi pada sebuah sistem
- Apabila terdapat kesalahan walaupun hanya 1 karakter maka akan berpengaruh pada sistem yang dibuat
- Dalam javascript jika terjadi error maka program otomatis dihentikan
- Tipe error javascript:
  - Syntax error: Error yang terjadi jika kita salah input syntax. Contoh: `consle.log("Halo ini Suki");` akan menghasilkan *syntax error* karena salah penulisan dalam syntax `consle` yang seharusnya `console`
  - Runtime error: Error yang terjadi ketika proses eksekusi program. Contoh: Saat pemanggilan nama variabel atau function

### Debugging
- Debugging merupakan proses mencari dan menyelesaikan suatu bug dalam sebuah program atau sistem
- Untuk menyelesaikan bug maka kita harus menangkap bug tersebut
- Keyword yang digunakan dalam debugging adalah `try`-`catch`
  - Tulis code yang mungkin menimbulkan error dalam blok `try`
  - Pada blok `catch` terdapat variabel `error` yang berisi error yang ditangkap
  - Jika terjadi error pada blok `try` maka error akan ditangkap dan dihandle oleh blok `catch`
  - Tetapi jika tidak terjadi error maka blok `catch` akan diabaikan
