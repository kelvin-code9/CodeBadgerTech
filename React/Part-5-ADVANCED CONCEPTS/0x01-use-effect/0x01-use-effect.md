
# ⚛️ `useEffect` in React

> ✅ Everything is done in `App.tsx` for simplicity. Once you master the pattern, you can move effects into their own components.

---

## 🎯 What Are Side Effects?

In React:

> A **side effect** is any logic that happens **outside the normal rendering flow**.

### Examples:

* Fetching data from an API
* Setting up a timer (`setInterval`)
* Adding/removing event listeners
* Manually interacting with the DOM
* Subscribing to a socket or stream

🧼 These side effects may require **cleanup** (e.g., clearing timers or removing listeners). If you don’t, you risk **memory leaks**, performance issues, or buggy behavior.

---

## 🔁 Why Use `useEffect`?

React’s `useEffect()` hook lets you run side effects **after the component renders**.

```tsx
useEffect(() => {
  // code to run after render
}, [dependencies]);
```

* **First render**: Runs once.
* **When dependencies change**: Runs again.
* **On unmount**: Runs cleanup code (if defined).

---

## ✅ Example 1: Logging Once on Mount

```tsx
import { useEffect } from 'react';

function App() {
  useEffect(() => {
    console.log("✅ Component mounted!");
  }, []);

  return <h1>Hello, React!</h1>;
}

export default App;
```

### 💡 Explanation

* `useEffect` runs **after the component renders for the first time**.
* The empty `[]` means it won’t run again unless the component unmounts/remounts.
* This is useful for initialization logic like analytics, API calls, or connecting to a WebSocket.

---

## ✅ Example 2: Tracking Window Width with Resize Listener

```tsx
import { useEffect, useState } from 'react';

function App() {
  const [width, setWidth] = useState(window.innerWidth);

  useEffect(() => {
    const handleResize = () => {
      setWidth(window.innerWidth);
    };

    window.addEventListener('resize', handleResize);

    return () => {
      window.removeEventListener('resize', handleResize);
    };
  }, []);

  return <h2>Window width: {width}px</h2>;
}

export default App;
```

### 🧠 Real Explanation

#### `const [width, setWidth] = useState(window.innerWidth);`

* This creates a state variable called `width`.
* It stores the current width of the browser window.
* Initially, we use `window.innerWidth` to get the value.

---

#### `useEffect(() => { ... }, []);`

* This code block runs **once**, right after the first render.
* We want to set up a resize listener when the component mounts.

---

#### Inside the effect:

```tsx
const handleResize = () => {
  setWidth(window.innerWidth);
};
```

* We define a function that gets the current window width and updates the `width` state.

```tsx
window.addEventListener('resize', handleResize);
```

* We tell the browser: "Hey, every time the window is resized, run this function."

---

#### Cleanup:

```tsx
return () => {
  window.removeEventListener('resize', handleResize);
};
```

* This removes the resize listener **when the component unmounts**.
* Without this, the listener stays active forever, even if the component is gone — that’s a **memory leak**.

---

## ✅ Example 3: Fetching Data from an API (with `fetch`)

```tsx
import { useEffect, useState } from 'react';

type Todo = {
  id: number;
  title: string;
};

function App() {
  const [todos, setTodos] = useState<Todo[]>([]);

  useEffect(() => {
    const fetchTodos = async () => {
      const res = await fetch('https://jsonplaceholder.typicode.com/todos?_limit=5');
      const data: Todo[] = await res.json();
      setTodos(data);
    };

    fetchTodos();
  }, []);

  return (
    <div>
      <h2>Todos</h2>
      <ul>
        {todos.map(todo => (
          <li key={todo.id}>{todo.title}</li>
        ))}
      </ul>
    </div>
  );
}

export default App;
```

### 🧠 Real Explanation

* We declare `todos` as a state variable to store the results.
* Inside `useEffect`, we define an **async function** called `fetchTodos`.
* It fetches data from a public API, converts the JSON to a `Todo[]` array, and updates state.
* `useEffect` itself **cannot be async**, so we define and call an async function inside.

---

## ✅ Example 4: Fetching with `axios`

```tsx
import { useEffect, useState } from 'react';
import axios from 'axios';

type User = {
  id: number;
  name: string;
};

function App() {
  const [users, setUsers] = useState<User[]>([]);

  useEffect(() => {
    const getUsers = async () => {
      const res = await axios.get<User[]>('https://jsonplaceholder.typicode.com/users');
      setUsers(res.data);
    };

    getUsers();
  }, []);

  return (
    <div>
      <h2>Users</h2>
      {users.map(user => (
        <p key={user.id}>{user.name}</p>
      ))}
    </div>
  );
}

export default App;
```

### 🤓 Why use `axios`?

* Shorter syntax than `fetch`
* Better default error handling
* You can add interceptors globally (e.g., for auth tokens)

---

## ✅ Example 5: Timer with Cleanup

```tsx
import { useEffect, useState } from 'react';

function App() {
  const [seconds, setSeconds] = useState(0);

  useEffect(() => {
    const interval = setInterval(() => {
      setSeconds(prev => prev + 1);
    }, 1000);

    return () => {
      clearInterval(interval);
    };
  }, []);

  return <h2>Timer: {seconds} seconds</h2>;
}

export default App;
```

### 🧠 Real Explanation

* We start a timer that increments `seconds` every 1000ms (1 second).
* The `setInterval` keeps running until we stop it.
* If we didn’t use `clearInterval`, the timer would keep running even after the component is gone — wasting memory and CPU.
* That’s why the **cleanup function is important**.

---

## 🧼 Summary Table

| Concept              | Meaning                                                             |
| -------------------- | ------------------------------------------------------------------- |
| Side effect          | Code that interacts with external systems or browser APIs           |
| `useEffect`          | A React hook for running side effects after render                  |
| Dependency array     | Controls when the effect runs (`[]` = only once)                    |
| Cleanup function     | Removes listeners, timers, or subscriptions when component unmounts |
| Async in `useEffect` | Wrap in an internal function, not the effect itself                 |

---

## ⚠️ Common Pitfalls

| Problem               | What Happens                                                      |
| --------------------- | ----------------------------------------------------------------- |
| ❌ No dependency array | Effect runs after **every render**, even when not needed          |
| ❌ Wrong dependencies  | Effect may run too often or miss updates                          |
| ❌ No cleanup          | Causes memory leaks, multiple listeners, or overlapping intervals |

---

## ✅ Key Takeaways

* Always clean up event listeners and timers.
* Don’t make `useEffect` directly async — wrap your async code.
* Think carefully about when your effect should re-run (dependencies).
* **Test your assumptions**: resize the window, inspect network calls, and see what runs when.

---

