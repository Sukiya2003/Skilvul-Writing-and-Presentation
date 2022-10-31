# WRITING WEEK 1 FE - DAY 3
## REACT JS EVENTHANDLER
- React dapat menghandle sebuah event yang memiliki perbedaan dengan handling event pada DOM element
- React event menggunakan camelCase, bukan lowercase
- Handler untuk event adalah sebuah function yang ditulis diantara curly braces `{}` dan tidak ditulis dalam bentuk string. Contoh
```js
    import React, { useState } from 'react';

    export default function App() {
      const [state, setState] = useState('brachio');

      const handleChange = () => {
        setState('t-rex');
      };

      return (
        <div>
          <h1>Hello Devsaurus</h1>
          <p>My Name is {state}</p>
          // event react menggunakan {}
          <button onClick={handleChange}>Change Name</button>
        </div>
      );
    }
```
- Penjelasan:
  - Event klik button pada react tidak ditulis onclick tapi **onClick**
  - Event `handleChange` untuk menghandle event onClick
  - Ketika button diklik maka function handleChange akan dieksekusi

### Event Handler dengan Argument
- Event handler dengan argument harus ditulis dengan menggunakan arrow function
- Jika ditulis tanpa arrow function maka event handler tidak dieksekusi sesuai dengan event yang terjadi dalam component
```js
    import React, { useState } from 'react';

    export default function App() {
      const [state, setState] = useState('brachio');

      const handleChange = (name) => {
        setState(name);
      };

      return (
        <div>
          <h1>Hello Devsaurus</h1>
          <p>My Name is {state}</p>
          //event handler ditulis dengan arrow function
          <button onClick={() => handleChange('t-rex')}>Change Name</button>
        </div>
      );
    }
```
