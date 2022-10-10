# WRITING WEEK 3 - DAY 1
## JS INTERMEDIATE - ARRAY
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

### Array - Property
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
- `.push()` untuk menambahkan data baru array pada index terakhir
![image](https://user-images.githubusercontent.com/85722923/194809732-408158f6-66b0-410a-8b77-90de7cf0daf5.png)

- `.unshift()` untuk menambahkan data baru array pada index 0
![image](https://user-images.githubusercontent.com/85722923/194809858-56824060-8e63-4db3-a617-429ca93d505f.png)

- `.pop()` untuk menghapus data array pada index terakhir
![image](https://user-images.githubusercontent.com/85722923/194821259-134dfccf-59d0-49c3-8cd5-e76a52a910ae.png)

- `.shift()` untuk menghapus data array pada index 0
![image](https://user-images.githubusercontent.com/85722923/194821051-6a5f25d2-cd35-4ae5-8c76-fe1586325dd2.png)

- `.splice()` untuk menghapus atau mengganti data array sesuai parameter
![image](https://user-images.githubusercontent.com/85722923/194812939-96295318-6709-4711-8950-5fef35bf6ee7.png)

- `.slice()` untuk menyalin data array tanpa merubah struktur array awal
![image](https://user-images.githubusercontent.com/85722923/194821528-cf31c511-0a07-4443-ba91-a85d4dc03811.png)

- `.sort()` untuk mengurutkan angka secara ascending atau descending
![image](https://user-images.githubusercontent.com/85722923/194820729-dbe8d762-40e3-404e-8e03-ae60430b7275.png)

### Array - Looping
- Array memiliki built in methods untuk melakukan looping, yaitu .map() dan .forEach()
- `.map()` untuk melakukan looping dengan membuat data array baru
    - Gunakan .map() jika ingin melakukan operasi pada array 
    - Contoh:
![image](https://user-images.githubusercontent.com/85722923/194823566-93c6d6fb-cfda-470d-9c15-fdd69f949fb4.png)

- `.foreach()` untuk melakukan looping pada setiap data array
    - .foreach() tidak dapat membuat data array baru
    - Gunakan .foreach() jika hanya memerlukan looping untuk menampilkan saja atau menyimpan ke database
    - Contoh:
![image](https://user-images.githubusercontent.com/85722923/194823311-100c5318-b8ad-42ca-95c9-b42f132c295a.png)

## JS INTERMEDIATE - MULTIDIMENSIONAL ARRAY
### Multidimensional Array - Introduction
- Array of array atau array di dalam array
- Bayangkan multidemensional array seperti tabel, dimana baris tabel merupakan jumlah array dan kolom tabel merupakan isi dari setiap array
```js
        let inventory = [
            ['Kaos', 5],
            ['Jaket', 10],
            ['Topi', 15],
            ['Celana', 20]
        ];
        console.log(inventory[1][0]);   //output: Jaket
        //baris index ke-1 dan kolom index ke-0
```
- Multidimensional juga memiliki property dan built in methods

### Multidimensional Array - Built in Methods
- Contoh penggunaan `.push()`
![image](https://user-images.githubusercontent.com/85722923/194826514-28e8b299-6f39-4ab5-aa20-74f7b22b1d29.png)

### Multidimensional Array - Looping
- Contoh penggunaan `.map()`
```js
        let inventory = [
            ['Kaos', 5],
            ['Jaket', 10],
            ['Topi', 15],
            ['Celana', 20]
        ];

        inventory.map(dataInventory => {
            let terjual = 100 - dataInventory[1];
            dataInventory[2] = terjual;
        });

        console.table(inventory);
```
![image](https://user-images.githubusercontent.com/85722923/194827476-3c9f80e5-f92e-4813-b075-5381a6809c6c.png)
- Contoh penggunaan `.forEach()`
![image](https://user-images.githubusercontent.com/85722923/194827868-888ebdca-37ad-4bb9-9ef3-16d8cb8c2714.png)
