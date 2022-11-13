# WRITING WEEK 3 FE - DAY 1
## REACT CONTEXT
- Konsep context sama seperti redux yaitu menghindari props drilling (mengoper props yang sama dari parent ke child-child)
- Selain menghindari props drilling, context digunakan ketika beberapa data harus dapat diakses oleh banyak komponen pada tingkat bersarang yang berbeda
- Redux digunakan untuk project yang benar-benar membutuhkan manage state dan project tersebut termasuk project besar serta kompleks
- Context digunakan untuk project yang tidak terlalu besar dan kompleks
- Context merupakan library eksternal javascript yang digunakan pada react.js
- Dalam context terdapat dua istilah, yaitu
  - Provider: untuk tempat menampung value
  - Consumer: untuk menggunakan nilai dari value provider
- Dalam menggunakan context tidak perlu menginstall, tinggal mengimport packages yang sudah disediakan folder react


### Menggunakan React Context
- Buat aplikasi react js atau buka folder aplikasi react js jika sudah ada
- Membuat context
```js
  import React, { createContext } from "react";

  const MyContext = createContext(defaultValue);

  export default UserContext;
```

- Menggunakan context
```js
  const componentA = () => {
    return <MyContext.Provider value={'value'}></MyContext.Provider>;
  };
```

**Tambahan Informasi**
- Alternatif context itu [jotai](https://jotai.org/docs/introduction)
- Jotai membuat semua data bersifat global dengan menggunakan atom
