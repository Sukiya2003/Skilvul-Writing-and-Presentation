# WRITING WEEK 2 FE - DAY 4
## REACT REDUX-TO DO LIST
Membuat aplikasi to do list sederhana dengan redux. Pada aplikasi to do list akan menerapkan aspek CRUD:
- Create (membuat atau menambahkan todo)
- Read (melihat list todo)
- Update (toggle complete todo)
- Delete (menghapus todo)

### Setting Awal
- Buat aplikasi react js atau buka folder aplikasi react js jika sudah ada
- Masukkan code berikut kedalam file App.js
```js
  import React, { useState } from "react";

  const App = () => {
    const [todos, setTodos] = useState([
      { text: "Buy Food" },
      { text: "Learn React" },
      { text: "Build todo app" },
    ]);

    return <div></div>;
  };

  export default App;
```
- Penjelasan:
  - `useState` merupakan react hooks untuk menyimpan suatu data
  - Terdapat sebuah array object untuk menyimpan data todo
  - Code diatas masih mengembalikan div kosong sehingga pada browser tidak akan menampilkan apapun
- Tambahkan code berikut untuk membuat browser memiliki tampilan
```js
  const App = () => {
    // ...

    return (
      <div className="app">
        <div className="todo-list">
          {todos.map((todo) => (
            <div className="todo-item">{todo.text}</div>
          ))}
        </div>
      </div>
    );
  };
```

### Membagi Component
- Pada file App.js kita hanya mengembalikan element HTML seperti biasa
- Pecah component menjadi TodoItem, TodoList, dan lainnya
- Buat folder `components` di dalam folder src dan sebuah file `TodoItem.js`
- Lalu masukkan code berikut
```js
  import React from "react";

  const TodoItem = ({ todo }) => {
    return <div className="todo-item">{todo.text}</div>;
  };

  export default TodoItem;
```
- Render component TodoItem pada file App.js
```js
  import React, { useState } from "react";
  import TodoItem from "./components/TodoItem"; // import TodoItem

  const App = () => {
    const [todos, setTodos] = useState([
      { text: "Buy Food" },
      { text: "Learn React" },
      { text: "Build todo app" },
    ]);

    return (
      <div className="app">
        <div className="todo-list">
          {todos.map((todo) => (
            <TodoItem todo={todo} /> // Panggil TodoItem
          ))}
        </div>
      </div>
    );
  };

  export default App;
```
- Buat sebuah file baru di dalam folder components dengan nama `TodoList.js`
- Lalu masukkan code berikut
```js
  import React from "react";
  import TodoItem from "./TodoItem";  // import TodoItem

  const TodoList = ({ todos }) => {
    return (
      <div className="todo-list">
        {todos.map((todo) => (
          <TodoItem todo={todo} /> // Panggil TodoItem
        ))}
      </div>
    );
  };

  export default TodoList;
```
- Penjelasan:
  - Pada file `TodoList` kita sudah memanggil component `TodoItem` sehingga tidak perlu lagi memanggil `TodoItem` pada file App.js
- File App.js
```js
  import React, { useState } from "react";
  import TodoList from "./components/TodoList"; // Import TodoList

  const App = () => {
    const [todos, setTodos] = useState([
      { text: "Buy Food" },
      { text: "Learn React" },
      { text: "Build todo app" },
    ]);

    return (
      <div className="app">
        <TodoList todos={todos} /> // Panggil TodoList
      </div>
    );
  };

  export default App;
```

### Menambahkan To Do Baru
- Buat file component baru, yaitu `TodoForm.js` untuk fitur menambahkan to do
- Dalam fitur TodoForm ini terdapat beberapa poin, yaitu:
  - Membuat sebuah input field dengan empty value
  - Handling form ketika disubmit
  - Update todos dengan push value ke todos
- Masukkan code berikut ke dalam file TodoForm.js
```js
  import React, { useState } from "react";

  const TodoForm = ({ addTodo }) => {
    const [value, setValue] = React.useState("");

    const handleSubmit = (e) => {
      e.preventDefault();
      if (!value) return;
      addTodo(value);
      setValue("");
    };

    return (
      <form onSubmit={handleSubmit}>
        <input
          type="text"
          className="todo-input"
          placeholder="add todo..."
          value={value}
          onChange={(e) => setValue(e.target.value)}
        />
      </form>
    );
  };

  export default TodoForm;
```
- Lalu, import TodoForm ke file App.js dengan code berikut
```js
  import React, { useState } from "react";
  import TodoList from "./components/TodoList";
  import TodoForm from "./components/TodoForm";

  const App = () => {
    const [todos, setTodos] = useState([
      { text: "Buy Food" },
      { text: "Learn React" },
      { text: "Build todo app" },
    ]);

    return (
      <div className="app">
        <TodoList todos={todos} />
        <TodoForm addTodo={addTodo} />
      </div>
    );
  };

  export default App;
```
- Kemudian tambahkan function `addTodo` ke dalam file TodoForm
```js
  const App = () => {
    // ...

    const addTodo = (value) => {
      const newTodos = [...todos, { text: value }];
      setTodos(newTodos);
    };

    // return ...
  };

  export default App;
```
- Penjelasan:
  - `...todos` merupakan spread operator yang memberi salinan todos
  - variabel `newTodos` mengambil salinan todos yang lama kemudian menambahkan satu todo item baru

### Fitur Update Toggle To Do
- Fitur untuk toggle todo apakah sudah selesai
- Dalam mengimplementasikan fitur toggle kita membutuhkan key-value pair serta suatu id atau index unik untuk setiap item
- Tambakah key `isCompleted` dengan value berupa boolean dalam file App.js
```js
  const App = () => {
    const [todos, setTodos] = useState([
      { text: "Buy Food", isCompleted: false },
      { text: "Learn React", isCompleted: false },
      { text: "Build todo app", isCompleted: false },
    ]);

    //...
  };
```
- Buat button pada component TodoItem untuk handling toggle complete todo
```js
  const TodoItem = ({ todo }) => {
    return (
      <div className="todo-item">
        <div>{todo.text}</div>
        <button type="button" className="todo-btn primary">
          toggle
        </button>
      </div>
    );
  };

  export default TodoItem;
```
- Penjelasan:
  - Button toggle masih hanya tampil saja
  - Untuk melakukan toggle todo buat sebuah fungsi `toogleTodo` dan menambahkan properti `onClick` pada sebuah button
  - Fungsi `toogleTodo` membutuhkan sebuah parameter berupa id unik atau index untuk mengenali item mana yang akan ditoggle
- Tambahkan code berikut ke dalam file App.js
```js
  const App = () => {
    //...
    const toggleTodo = (idx) => {
      const newTodos = [...todos];
      newTodos[idx].isCompleted = !newTodos[idx].isCompleted;
      setTodos(newTodos);
    };

    //...
  };
```
- Penjelasan:
  - Membuat salinan dari todos kemudian membalik nilai dari key isCompleted pada suatu idx todo
- Tambahkan `idx` pada file `TodoList.js`
```js
  const TodoList = ({ todos }) => {
    return (
      <div className="todo-list">
        {todos.map((todo, i) => (
          <TodoItem key={i} todo={todo} idx={i} /> // tambahkan props idx.
        ))}
      </div>
    );
  };
```
- Dan pada component TodoItem memiliki akses ke idx dengan menambahkan code berikut
```js
  const TodoItem = ({ todo, idx }) => {
    return (
      <div className="todo-item">
        <div>{todo.text}</div>
        <button
          type="button"
          className="todo-btn primary"
          onClick={toggleTodo(idx)}
        >
          toggle
        </button>
      </div>
    );
  };
```
- Pada tahap ini masih menggunakan props drilling
- Mengirim fungsinya dari App.js dan kirimkan ke TodoList sebagai props kemudian kirim lagi ke TodoItem
- Tambahkan code berikut ke dalam file App.js
```js
  const App = () => {
    const toggleTodo = (idx) => {
      // ...
    };

    return (
      <div className="app">
        <TodoList todos={todos} toggleTodo={toggleTodo} />
        <TodoForm addTodo={addTodo} />
      </div>
    );
  };
```
- Lalu, pada component TodoList kirim kembali props ke TodoItem
```js
  const TodoList = ({ todos, toggleTodo }) => {
    return (
      <div className="todo-list">
        {todos.map((todo, i) => (
          <TodoItem key={i} todo={todo} idx={i} toggleTodo={toggleTodo} />
        ))}
      </div>
    );
  };
```
- Dan pada TodoItem kita dapat menerima props yang dikirim TodoList
```js
  const TodoItem = ({ todo, idx, toggleTodo }) => {
    return (
      <div className="todo-item">
        <div>{todo.text}</div>
        <button
          type="button"
          className="todo-btn primary"
          onClick={() => toggleTodo(idx)}
        >
          toggle
        </button>
      </div>
    );
  };
```

### Menambahkan Style Toggle To Do
- Tambahkan efek strikethrough pada todo yang telah selesai
- Pada component TodoItem tambahkan conditional custom style
```js
  const TodoItem = ({ todo, idx, toggleTodo }) => {
    return (
      <div className="todo-item">
        <div style={{ textDecoration: todo.isCompleted ? "line-through" : "" }}>
          {todo.text}
        </div>
        <button
          type="button"
          className="todo-btn primary"
          onClick={() => toggleTodo(idx)}
        >
          toggle
        </button>
      </div>
    );
  };
```

### Menghapus To Do
- Dengan membuat fungsi `deleteTodo`
- Buat button delete pada component TodoItem
```js
  // add deleteTodo props
  const TodoItem = ({ todo, idx, toggleTodo, deleteTodo }) => {
    return (
      <div className="todo-item">
        <div style={{ textDecoration: todo.isCompleted ? "line-through" : "" }}>
          {todo.text}
        </div>
        <div className="todo-group-btn">
          <button
            type="button"
            className="todo-btn primary"
            onClick={() => toggleTodo(idx)}
          >
            toggle
          </button>
          {/* add delete button */}
          <button
            type="button"
            className="todo-btn danger"
            onClick={() => deleteTodo(idx)}
          >
            delete
          </button>
        </div>
      </div>
    );
  };

  export default TodoItem;
```
- Tambahkan fungsi `deleteTodo` di file App.js
```js
  const App = () => {
    // ...

    const deleteTodo = (idx) => {
      const newTodos = [...todos];
      newTodos.splice(idx, 1);
      setTodos(newTodos);
    };

    return (
      <div className="app">
        <TodoList todos={todos} toggleTodo={toggleTodo} deleteTodo={deleteTodo} />{" "}
        {/* pass deleteTodo */}
        <TodoForm addTodo={addTodo} />
      </div>
    );
  };
```
- Lalu pada TodoList kirim `deleteTodo` tersebut kembali sebagai props ke TodoItem
- Masukkan code berikut ke dalam file `TodoList.js`
```js
  const TodoList = ({ todos, toggleTodo, deleteTodo }) => {
    return (
      <div className="todo-list">
        {todos.map((todo, i) => (
          <TodoItem
            key={i}
            todo={todo}
            idx={i}
            toggleTodo={toggleTodo}
            deleteTodo={deleteTodo}
          />
        ))}
      </div>
    );
  };
```
