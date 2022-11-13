# WRITING FE WEEK 3 - DAY 2
## REACT CONTEXT WITH 'useReducer'
### Membuat Counter dengan React Context
- Buat aplikasi react `npm create vite@latest nama-aplikasi`
- Hapus folder file dan syntax yang tidak dipakai
- Tersisa file App.jsx dan main.jsx di folder src
- Buat folder components di folder src
- Tambahkan file `Counter.jsx` dan masukkan code
![image](https://user-images.githubusercontent.com/85722923/201500539-123e6de1-c15b-4cc5-bba0-5dfc1200d67a.png)
- Lalu panggil counter di file App.jsx
- Buat file `CounterProvider.jsx` yang akan menampung context dengan `const CounterContext = createContext()`
- Lalu `CounterContext` dipanggil di function CounterProvider dalam return div
- Function CounterProvider memiliki data yaitu `const [count, setCount] = useState(0)` dan dipanggil oleh nilai `CounterContext.Provider`
![image](https://user-images.githubusercontent.com/85722923/201500574-e4e55882-df6f-406e-a014-a6d039532258.png)
- Lalu jadikan function `CounterProvider` pembungkus app dalam file main.jsx
![image](https://user-images.githubusercontent.com/85722923/201500596-e22d9df8-afa6-452d-a0b5-bc88cf1d0a5f.png)
- Tambahkan `useContext` dan `state.count` pada file Counter.jsx untuk melakukan perubahan count
![image](https://user-images.githubusercontent.com/85722923/201500608-3b7c563c-5825-40a6-9589-7aee2f6a4c4f.png)
- Dan jangan lupa syntax `createContext` diberi export agar bisa diakses Counter.jsx serta mengimport `useState` di file CounterProvider.jsx
![image](https://user-images.githubusercontent.com/85722923/201500636-a008ec31-3ace-4315-a02c-c8b3cb34b3d4.png)
- Tambahkan kegiatan pada file Counter.jsx
![image](https://user-images.githubusercontent.com/85722923/201500642-f5827292-29be-450a-9918-41e50d3905dc.png)

### Membuat Counter dengan React Context + useReducer
- Pada file CounterProvider.jsx hanya deklarasi state biasa, yaitu `const [count, setCount] = useState = 0`
- `useState` ganti dengan `useReducer` dengan membuat function reducer
-	Di dalam function reducer terdapat parameter yaitu state dan action
-	Lalu switch case function reducer dan buat initialState
![image](https://user-images.githubusercontent.com/85722923/201500717-a465400f-bf0a-4cf7-8c8b-28a883b4823e.png)
![image](https://user-images.githubusercontent.com/85722923/201500719-09f68644-c77f-4ef4-bd36-7999bb894e31.png)
- Penjelasan:
  - `state` di initialkan dan initialState di dapat dari `const initialState`
-	Pada file CounterProvider.jsx buat variable constant yaitu increment dan decrement
![image](https://user-images.githubusercontent.com/85722923/201500732-88858a74-22c5-4ccc-8bf8-e6115e3aa8fc.png)
![image](https://user-images.githubusercontent.com/85722923/201500734-03256c30-63c9-4101-8100-674f9fc5e1a9.png)
![image](https://user-images.githubusercontent.com/85722923/201500736-3fd0103c-fca6-4d3a-a59b-5a56344dd396.png)
- Penjelasan:
  - `state` di baris 25 akan tertuju ke `state` di Counter.jsx
  ![image](https://user-images.githubusercontent.com/85722923/201500752-f493efbe-d83e-4fbc-ba1e-a5d8b9f39d9a.png)
- Ubah code pada file Counter.jsx menjadi
![image](https://user-images.githubusercontent.com/85722923/201505078-b6a80fe6-375b-4f4f-95f7-a5ad1c5c753a.png)
![image](https://user-images.githubusercontent.com/85722923/201505086-9d015417-6c16-4ffe-9909-06526f2f8896.png)
![image](https://user-images.githubusercontent.com/85722923/201505129-f4584455-9b35-4521-8245-584cd3f8476b.png)
-	`dispatch` menerima object type untuk mengubah state

**Catatan**:
- Context biasa menglobalkan data ditambah dengan reducer maka data tersebut bisa dimanage
-	Kelebihan menggunakan context with reducer itu reuse dan gampang maintenance
-	Ini syntax context biasa


![image](https://user-images.githubusercontent.com/85722923/201505161-a6ebc297-e9f0-48c3-a00b-2254dd55ca91.png)
- Ini syntax context with reducer


![image](https://user-images.githubusercontent.com/85722923/201505170-648fdf3f-6035-4ede-8085-99c4ab1fac5f.png)
-	Context biasa logicnya ditaruh di masing-masing component sedangkan reducer diletak pada file dan hanya memanggil `state.count`
![image](https://user-images.githubusercontent.com/85722923/201505178-12ae011b-ec77-43bb-8eb5-a6f2d26499f3.png)

### Membuat To Do dengan React Context + useReducer
- Buat file baru `TodoProvider.jsx`
![image](https://user-images.githubusercontent.com/85722923/201505221-543f0711-4372-4be4-a714-9389df007d8d.png)
-	Tambahkan tag `<TodoProvider>` ke dalam main.jsx yang membungkus tag lain
![image](https://user-images.githubusercontent.com/85722923/201505228-a8088f9b-1e6a-46bb-a18d-fdbcf265a9a2.png)
- Tambahkan initialState dan reducer


![image](https://user-images.githubusercontent.com/85722923/201505247-5eb711bd-a723-490e-9e95-157ca4d99c29.png)
- Dan buat value untuk TodoContext.Provider


![image](https://user-images.githubusercontent.com/85722923/201505262-4a6f4452-fcdb-4d49-bb1e-e8db6935e54d.png)
- Buat file baru yaitu `TodoList.jsx` di dalam folder src/components
![image](https://user-images.githubusercontent.com/85722923/201505270-94c9947e-d53d-4b6d-b897-6939a9cd1748.png)
-	Kalau component mau ambil nilai state gunakan `useContext` pada file componentnya
![image](https://user-images.githubusercontent.com/85722923/201505276-927e838d-dcc5-4465-a2e8-2ebba4298023.png)
-	Tampilkan todos di TodoProvider dalam bentuk list dengan ` state.todos.map`
![image](https://user-images.githubusercontent.com/85722923/201505280-a38445e5-8487-412f-848d-1cf55997e47e.png)


- Menghapus To Do (Complete)
  - Masukkan code berikut ke dalam file TodoList.jsx
![image](https://user-images.githubusercontent.com/85722923/201505336-1d601648-5dab-4b27-8d30-b0d11752913e.png)
  -	Pada file TodoProvider.jsx buat action yang menjalankan dispatch
![image](https://user-images.githubusercontent.com/85722923/201505353-895889e7-968e-4542-b1a3-13f2cf5786b2.png)
![image](https://user-images.githubusercontent.com/85722923/201505355-d01c5ac5-a50d-470c-881a-fd6aa1fcc796.png)
-	Tambahkan action pada TodoProvider.jsx
![image](https://user-images.githubusercontent.com/85722923/201505363-b8a08af1-33ab-4f11-99e5-f7f5c7cb892d.png)
