# WRITING WEEK 2 FE - DAY 1
## REACT JS - PropTypes
- PropTypes merupakan library yang dapat membantu dalam memeriksa tipe data props
- Apabila tipe data props tidak sesuai maka akan memunculkan pesan error
- Instalasi terlebih dahulu prop-types ke dalam project kita dengan `npm install prop-types`
- Lalu import prop-types pada component yang ingin diberi props dengan `import PropTypes from 'prop-types';`
```js
    import React from 'react';
    import { PropTypes } from "prop-types";

    const Count = (props) => {
      return (
        <>
          ...
        </>
      )
    };

    Count.propTypes = {
      // put props here
      // key is the name of the prop and value is the PropType
    }
    export default Count;
```

### Tipe Data PropTypes
| Tipe     | Contoh        | Kelas            |
| -------- | ------------- | ---------------- |
| String   | 'hello'       | PropTypes.string |
| Number   | 10, 0.1       | PropTypes.number |
| Boolean  | true / false  | PropTypes.bool   |
| Function | console.log() | PropTypes.func   |
| Symbol   | Symbol('msg') | PropTypes.symbol |
| Object   | {name: 'aka'} | PropTypes.object |
- Contoh penggunaan tipe data props pada code
```js
    Count.propTypes = {
      name: PropTypes.string,
      age: PropTypes.number,
      address: PropTypes.object,
    };
```
- Penjelasan: value yang diberikan harus sesuai dengan tipe data yang sudah dideklarasikan, jika berbeda maka akan menampilkan error pada tab console
![image](https://user-images.githubusercontent.com/85722923/200202104-ee65c2af-72de-4a9c-976e-385f0ab85116.png)

### Tipe Array PropTypes
| Tipe                | Contoh          | Penjelasan                |
| ------------------  | --------------- | ------------------------- |
| Array               | []              | PropTypes.array           |
| Array berisi number | [1, 2, 3]       | PropTypes.arrayOf([type]) |
| Array berisi string | ['Red', 'Blue'] | PropTypes.arrayOf([arr])  |
