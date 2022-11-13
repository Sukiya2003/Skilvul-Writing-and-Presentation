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


