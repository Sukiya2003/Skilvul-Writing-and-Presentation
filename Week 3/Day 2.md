# WRITING WEEK 3 - DAY 2
## JS INTERMEDIATE - OBJECT
- Objek merupakan sebuah tipe data pada variabel yang pasti menyimpan nilai (properti) dan fungsi (method)
- **Properti**: Ciri khas dari objek atau yang membedakan antara 1 objek dengan objek lain (variabel)
- **Method**: Tingkah laku atau action dari objek (fungsi)
- **Membuat object** person dengan beberapa properti:
```js
    let orang = {
        nama: 'sukiSUki',
        umur: 19,
        isVerified: true
    }
```
- **Mengakses object**:
```js
    let orang = {
        nama: 'sukiSUki',
        umur: 19,
        status: true
    }
    console.log(orang);
    //output: { name: 'sukiSUki', age: 19, status: true }
```
- **Mengakses properti pada object**:
```js
    let orang = {
        nama: 'sukiSuki',
        umur: 19,
        status: true
    }
    console.log(orang.nama)
    //output: sukiSuki
```

### Update Object
- Melakukan update pada variabel dengan tipe data object
- Object dapat mengupdate value dari key yang sudah tersedia
- Object dapat menambah key dan value baru
- Contoh:
```js
    let orang = {
        nama: 'sukiSuki',
        umur: 19,
        status: true
    }
    
    //update key yang sudah ada dengan value baru
    orang.nama = 'Sukiya';
    
    //menambah key dan value baru
    orang.alamat = 'Riso 23';
    console.log(orang);
    
    //output: { nama: 'Sukiya', umur: 19, status: true, alamat: 'Riso 23' }
```

### Delete Object Property
- Menghapus properti dari sebuah object
- Contoh:
```js
    let orang = {
        nama: 'sukiSuki',
        umur: 19,
        status: true
    }
    
    delete orang.status;
    console.log(orang);
    
    //output: { nama: 'sukiSuki', umur: 19 }
```

### Method Object
- Jika value yang dimasukkan pada property dalam bentuk function atau didalam object terdapat function itu disebut method
```js
    const sapa = {
        welcome: function() {
            return "Selamat Datang.."
        }
    }
    
    console.log(sapa.welcome());
    
    //output: Selamat Datang..
```
- `Object.keys(namaObjek)` untuk memanggil property dari object dalam bentuk array
```js
    let mhs = {
        nama: 'Sukiya',
        nim: '201401068',
        mhs_aktif: true
    }
    
    console.log(Object.keys(mhs));
    
    //output: [ 'nama', 'nim', 'mhs_aktif' ]
```
- `Object.values(namaObjek)` untuk memanggil value dari setiap property dalam bentuk array
```js
    let mhs = {
        nama: 'Sukiya',
        nim: '201401068',
        mhs_aktif: true
    }
    
    console.log(Object.values(mhs));
```

### Nested Object
- Data object kompleks, dimana object berasal dari turunan object lainnya
![image](https://user-images.githubusercontent.com/85722923/194835579-5adc9428-26b8-4797-a22c-b410ea1c4498.png)

### Pass by Reference
- Mengubah data pada object melalui function dan memasukkan object sebagai parameter function
- Contoh (mengubah data object number dengan function changeData)
![image](https://user-images.githubusercontent.com/85722923/194836247-84733473-d057-4224-8c58-ace0f049d376.png)

### Looping Object
- Gunakan looping jika ingin menampilkan seluruh object properti yang jumlahnya banyak
```js
    for(let namaVariable in namaObjek) {
        console.log(nnamaObjek[namaVariable]);
    }
```

### Array of Object
- Object sama seperti array yang menyimpan banyak data
- Gunakan array of object untuk menyimpan banyak objek
![image](https://user-images.githubusercontent.com/85722923/194837875-294bf07b-ea93-49a4-bb09-55c7cdf179fa.png)
