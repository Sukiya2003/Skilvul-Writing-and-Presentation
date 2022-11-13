# WRITING WEEK 3 FE - DAY 1
## REACT CONTEXT
- Context digunakan ketika beberapa data harus dapat diakses oleh banyak komponen pada tingkat bersarang yang berbeda
- Konsep context sama seperti redux yaitu menghindari props drilling (mengoper props yang sama dari parent ke child-child)
- Redux digunakan untuk project yang benar-benar membutuhkan manage state dan project tersebut termasuk project besar serta kompleks
- Context digunakan untuk project yang tidak terlalu besar dan kompleks
- Context merupakan library eksternal javascript yang digunakan pada react.js
- Dalam context terdapat dua property, yaitu
  - Provider: component untuk tempat menampung value yang didistribusikan kepada `consumer`
```js
    <Provider value={/* some value */}>
```
  - Consumer: component untuk menggunakan data yang disediakan oleh `provider`
```js
    Consumer>
      {value => /* render something based on the context value */}
    </Consumer>
```
- React context biasanya digunakan untuk:
  - Tema (light atau dark mode)
  - User data (authenticated user)
  - Mengatur bahasa (language)
- Dalam menggunakan context tidak perlu menginstall, tinggal mengimport packages yang sudah disediakan folder react


### Menggunakan React Context
- Buat aplikasi react js atau buka folder aplikasi react js jika sudah ada
- Membuat context gunakan `createContext`
```js
  import React, { createContext } from "react";

  const MyContext = createContext(defaultValue);

  export default MyContext;
```

- Menggunakan context
```js
  const componentA = () => {
    return <MyContext.Provider value={'value'}></MyContext.Provider>;
  };
```
- Fungsi `createContext` akan mengembalikan provider dan consumer component

**Tambahan Informasi**
- Alternatif context itu [jotai](https://jotai.org/docs/introduction)
- Jotai membuat semua data bersifat global dengan menggunakan atom
