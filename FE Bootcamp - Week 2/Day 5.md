# WRITING WEEK 2 FE - DAY 5
## REACT - ASYNC ACTIONS WITH REDUX THUNK & MIDDLEWARE
### Middleware
- Middleware merupakan sebuah alat yang digunakan untuk merubah hasil dari request sebelum masuk menjadi response
- Redux memungkinkan pengiriman middleware yang berada di antara aksi dan aksi mencapai reducer
- Terdapat 2 pustaka middleware yang populer dan memungkinkan efek samping dan akses asinkron, yaitu:
  - Redux Thunk
  - Redux Saga

### Redux Thunk
- Aslinya, aksi redux dikirimkan secara sinkron (synchronous)
- Thunk adalah konsep pemrograman yang menggunakan fungsi untuk menunda evaluasi/kalkulasi suatu operasi
- Thunk adalah sebuah function yang dapat tersambung dengan dispatch dan state (redux store)
- Redux thunk adalah middleware yang memungkinkan mengelola dan mengiriman action secara asycn melalui suatu fungsi objek
- Fungsi itu menerima metode pengiriman penyimpanan yang kemudian digunakan untuk mengirim aksi sinkron di dalam isi fungsi setelah operasi asinkron selesai
- Redux thunk berguna saat memanfaatkan penyimpanan redux dan mengandalkan API eksternal

### Menambahkan Redux Thunk
- Buat aplikasi react js atau buka folder aplikasi react js jika sudah ada
- Buka terminal (bash) dan install packages redux-thunk dengan `npm install redux-thunk`
- Gunakan `applyMiddleware` dari redux untuk mengaktifkan middleware pada redux
- Buka file index.js pada folder src dan masukkan code berikut
```js
  import React from 'react';
  import ReactDOM from 'react-dom';
  import { Provider } from 'react-redux';
  import { createStore, applyMiddleware } from 'redux';
  import thunk from 'redux-thunk';
  import './index.css';
  import rootReducer from './reducers';
  import App from './App';
  import * as serviceWorker from './serviceWorker';

  // use applyMiddleware to add the thunk middleware to the store
  const store = createStore(rootReducer, applyMiddleware(thunk));

  ReactDOM.render(
    <Provider store={store}>
      <App />
    </Provider>,
    document.getElementById('root')
  );
```
- Redux thunk biasanya digunakan untuk berkomunikasi secara asinkron dengan API eksternal untuk mengambil atau menyimpan data
- Buat sebuah folder `containers` dan tambahkan sebuah file `AddTodo.js`
- Masukkan code berikut
```js
  import { connect } from 'react-redux';
  import { addTodo } from '../actions';
  import NewTodo from '../components/NewTodo';

  const mapDispatchToProps = dispatch => {
    return {
      onAddTodo: todo => {
        dispatch(addTodo(todo));
      }
    };
  };

  export default connect(
    null,
    mapDispatchToProps
  )(NewTodo);
```
- Lalu buat sebuah folder `actions` dan tambahkan sebuah file `index.js`
- Masukkan code berikut
```js
import {
  ADD_TODO_SUCCESS,
  ADD_TODO_FAILURE,
  ADD_TODO_STARTED,
  DELETE_TODO
} from './types';

import axios from 'axios';

export const addTodo = ({ title, userId }) => {
  return dispatch => {
    dispatch(addTodoStarted());

    axios
      .post(`https://jsonplaceholder.typicode.com/todos`, {
        title,
        userId,
        completed: false
      })
      .then(res => {
        dispatch(addTodoSuccess(res.data));
      })
      .catch(err => {
        dispatch(addTodoFailure(err.message));
      });
  };
};

const addTodoSuccess = todo => ({
  type: ADD_TODO_SUCCESS,
  payload: {
    ...todo
  }
});

const addTodoStarted = () => ({
  type: ADD_TODO_STARTED
});

const addTodoFailure = error => ({
  type: ADD_TODO_FAILURE,
  payload: {
    error
  }
});
```
- Penjelasan:
  - Aksi ini akan menggunakan `axios` untuk mengirim permintaan POST ke titik akhir di JSONPlaceholder `https://jsonplaceholder.typicode.com/todos`
  - JSONPlaceholder merupakan API yang bersifat eksternal
  - `addTodo` mengembalikan fungsi sebagai ganti objek aksi reguler
  - Fungsi itu menerima metode pengiriman dari penyimpanan
  - Di dalam isi fungsi, kita mengirim mengirim aksi sinkron untuk mengindikasikan bahwa kita telah mulai menyimpan agenda bersama API eksternal
  - Kemudian membuat permintaan `post` sesungguhnya ke server menggunakan `axios`
  - Jika respons berhasil maka kita mengirim aksi sinkron yang berhasil bersama data yang diterima dari respons tersebut
  - Jika respons gagal maka kita mengirim tindakan sinkron yang berbeda bersama pesan kesalahan
- Masukkan code berikut ke dalam [src/actions/index.js]
```js
  // ...

  export const addTodo = ({ title, userId }) => {
    return dispatch => {
      dispatch(addTodoStarted());

      axios
        .post(ENDPOINT, {
          title,
          userId,
          completed: false
        })
        .then(res => {
          setTimeout(() => {
            dispatch(addTodoSuccess(res.data));
          }, 2500);
        })
        .catch(err => {
          dispatch(addTodoFailure(err.message));
        });
    };
  };

  // ...
```
- Untuk menguji skenario kesalahan, buatlah kesalahan secara manual
- Tambahkan code berikut ke dalam [src/actions/index.js]
```js
// ...

export const addTodo = ({ title, userId }) => {
  return dispatch => {
    dispatch(addTodoStarted());

    axios
      .post(ENDPOINT, {
        title,
        userId,
        completed: false
      })
      .then(res => {
        throw new Error('addToDo error!');
        // dispatch(addTodoSuccess(res.data));
      })
      .catch(err => {
        dispatch(addTodoFailure(err.message));
      });
  };
};

// ...
```
- Buat sebuah folder `reducers` dan tambahkan sebuah file `todosReducer.js`
- Masukkan code berikut
```js
  import {
    ADD_TODO_SUCCESS,
    ADD_TODO_FAILURE,
    ADD_TODO_STARTED,
    DELETE_TODO
  } from '../actions/types';

  const initialState = {
    loading: false,
    todos: [],
    error: null
  };

  export default function todosReducer(state = initialState, action) {
    switch (action.type) {
      case ADD_TODO_STARTED:
        return {
          ...state,
          loading: true
        };
      case ADD_TODO_SUCCESS:
        return {
          ...state,
          loading: false,
          error: null,
          todos: [...state.todos, action.payload]
        };
      case ADD_TODO_FAILURE:
        return {
          ...state,
          loading: false,
          error: action.payload.error
        };
      default:
        return state;
    }
  }
```
- Selain menerima metode pengiriman dari status, fungsi yang dikembalikan oleh pembuat aksi asinkron bersama redux thunk juga menerima metode `getState` dari penyimpanan
- `getState` digunakan untuk membaca nilai-nilai yang disimpan
- Tambahkan code berikut ke dalam [src/actions/index.js]
```js
  export const addTodo = ({ title, userId }) => {
    return (dispatch, getState) => {
      dispatch(addTodoStarted());

      // ini hanya mencetak status di console saja
      console.log('current state:', getState());

      // ...
    };
  };
```
- Tambahkan code berikut jika ingin membatasi aplikasi pada 4 item agenda saja
```js
  export const addTodo = ({ title, userId }) => {
    return (dispatch, getState) => {
      const { todos } = getState();

      if (todos.length > 4) return;

      dispatch(addTodoStarted());

      // ...
    };
  };
```

- **Catatan**
  - Create store
```js
  const store = createStore(reducer, middleware);
```
  - Middleware fungsi bersarang (nested)
```js
  const loggerMiddleware = (store) => (next) => (action) => {
    console.log("action", action);
    next(action);
  };
```
  - `createAsyncThunk` digunakan untuk membuat action pada aplikasi react
