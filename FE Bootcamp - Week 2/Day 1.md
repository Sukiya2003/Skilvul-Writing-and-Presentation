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
| Object   | {name: 'suki'} | PropTypes.object |
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
| Tipe            | Contoh                               | Penjelasan                   |
| --------------  | ------------------------------------ | ---------------------------- |
| Array           | []                                   | PropTypes.array              |
| Array of number | [1, 2, 3]                            | PropTypes.arrayOf([type])    |
| Array of string | ['Red', 'Blue']                      | PropTypes.oneOf([arr])       |
| Array of object | [PropTypes.string, PropTypes.number] | PropTypes.oneOfType([types]) |
- **Catatan**:
    - `PropTypes.oneOfType([types])` memberikan pilihan tipe data pada sebuah objek
```js
    Count.propTypes = {
      counts: PropTypes.array,
      users: PropTypes.arrayOf(PropTypes.object),
      alarmColor: PropTypes.oneOf(['red', 'blue']),
      description: PropTypes.oneOfType([
      PropTypes.string,
      PropTypes.instanceOf(Title)
      ]),
      }
```

### Tipe Object PropTypes
| Tipe          | Contoh                   | Penjelasan           |
| ------------- | ------------------------ | -------------------- |
| Object        | {name: 'suki'}           | PropTypes.object     |
| Number object | {age: 19}                | PropTypes.objectOf() |
| Instance      | New Message()            | PropTypes.objectOf() |
| Object shape  | {name: PropTypes.string} | PropTypes.shape()    |
- Contoh penggunaan tipe object pada code
```js
    Count.propTypes = {
      basicObject: PropTypes.object,
      numbers: PropTypes.objectOf(PropTypes.numbers),
      messages: PropTypes.instanceOf(Message),
      contactList: PropTypes.shape({
        name: PropTypes.string,
        phone: PropTypes.string,
      }),
    };
```

### Mengecek nilai dan key dari object
```js
    StudentInfo.propTypes = {
        info: PropTypes.exact({
            name: PropTypes.string,
            age: PropTypes.number
        })
    }
```

### Error akan muncul jika prop data tidak diisi
```js
    requiredFunc: PropTypes.func.isRequired
```

### Value dengan tipe data apapun
```js
    requiredAny: PropTypes.any.isRequired
```
