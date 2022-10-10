# WRITING WEEK 3 - DAY 1
## JS INTERMEDIATE - ARRAY DAN MULTIDIMENSIONAL ARRAY

<!-- menggunakan struktur data Array -->
### Array - Introduction
- Array merupakan tipe data order list
- Array dapat menyimpan tipe data apapun (string, number, boolean) dalam satu variabel
- Array didefinisikan dengan kurung siku `[...]`
- Data pertama pada array disebut index 0
- Contoh array:
```js
    let random = ['Suki', 19, false];
```
- Memanggil data array:
![image](https://user-images.githubusercontent.com/85722923/194804494-615f3106-75b0-472e-804a-0140ed617fb8.png)
- Mengupdate data array:
![image](https://user-images.githubusercontent.com/85722923/194806410-036107a3-df19-4deb-8da5-69ba33f3be66.png)
- Const di array:
![image](https://user-images.githubusercontent.com/85722923/194806935-b424117a-e9b5-418c-93b4-2deeabc7e939.png)
![image](https://user-images.githubusercontent.com/85722923/194806630-ec85bfda-5e58-4679-85a3-3a17ec3026ef.png)
- Penjelasan:
  - Tidak dapat melakukan update data
  - Namun, dapat melakukan update konten nilai dalam array
- Array memiliki lima properti yang sering digunakan:
  - constructor
  - length
  - index
  - input
  - prototype
- `.length()` untuk mengetahui panjang data pada suatu array
```js
    const random = ['Suki', 19, false];
    console.log(random.length);
    //output: 3
```

### Array - Built-in Methods
- Array memiliki method biasa disebut built-in method
- Contoh:
  - `.push()` untuk menambahkan data baru array pada index terakhir
![image](https://user-images.githubusercontent.com/85722923/194809732-408158f6-66b0-410a-8b77-90de7cf0daf5.png)

  - `.unshift()` untuk menambahkan data baru array pada index pertama atau 0
![image](https://user-images.githubusercontent.com/85722923/194809858-56824060-8e63-4db3-a617-429ca93d505f.png)

  - `.slice()`
  - `.pop()`
  - `.shift()`
  - `.splice()` untuk menghapus atau mengganti data array sesuai parameter
![image](https://user-images.githubusercontent.com/85722923/194812939-96295318-6709-4711-8950-5fef35bf6ee7.png)






