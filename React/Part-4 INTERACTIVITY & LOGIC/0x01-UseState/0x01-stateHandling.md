
# 🚀 State in React with TypeScript — Full Beginner Tutorial

In this lesson, we’ll cover:

1. ✅ **What is State in React?**
2. ✅ **Using `useState` in TypeScript**
3. ✅ **Primitive and Object State**
4. ✅ **Typing `useState` properly**
5. ✅ **Updating State Based on Previous Values**
6. ✅ **Bonus Summary and Exercises**

---

## ✅ 1. What is State?

In React, **state** is a way for a component to **remember information between renders**.

Without state, React components would be **static** — they would only show fixed data.

With state:

* Components can **track changes over time**.
* When state changes, the component **automatically re-renders** to show the updated value.

> ✅ **Simple Definition:**
> State is **data that changes over time** inside a component.

---

### 📌 **Real World Analogy**

Think of state like a **whiteboard**:

* You can write information on it (initial state).
* You can update the info at any time (set state).
* Every time you change it, you **see the latest information** (React re-renders).

---

## ✅ 2. Using `useState` with TypeScript

We use the **`useState` hook** to create state in a **function component**.

### ✅ Example 1 — A Counter

> ✅ Paste this into **App.tsx**:

```tsx
import { useState } from "react";

function App() {
  // Create state variable
  const [count, setCount] = useState<number>(0);

  // Function to update state
  function increment() {
    setCount(count + 1);
  }

  return (
    <div>
      <h1>Counter: {count}</h1>
      <button onClick={increment}>Increment</button>
    </div>
  );
}

export default App;
```

### ✅ Explanation:

| Code                  | Meaning                                                        |
| --------------------- | -------------------------------------------------------------- |
| `useState<number>(0)` | Declare state `count` with type `number` and initial value `0` |
| `setCount`            | Function to **update** the state                               |
| `count + 1`           | Increase current count by 1                                    |
| `onClick={increment}` | When the button is clicked, call `increment`                   |

> Every time you click the button, the component **re-renders with the new value** of `count`.

---

## ✅ 3. Primitive and Object State

State can be:

* **Primitive types:** `number`, `string`, `boolean`
* **Objects and arrays**

---

### ✅ Example 2 — Tracking a Name (Primitive `string`)

```tsx
import { useState } from "react";

function App() {
  const [name, setName] = useState<string>("");

  function handleChange(event: React.ChangeEvent<HTMLInputElement>) {
    setName(event.target.value);
  }

  return (
    <div>
      <h1>Your Name: {name}</h1>
      <input type="text" value={name} onChange={handleChange} />
    </div>
  );
}

export default App;
```

* `useState<string>("")` — state for a string
* As you type in the input, the `name` updates live.

---

### ✅ Example 3 — Using Object State

You can store **objects** in state.

```tsx
import { useState } from "react";

type User = {
  name: string;
  age: number;
};

function App() {
  const [user, setUser] = useState<User>({ name: "", age: 0 });

  function updateName(event: React.ChangeEvent<HTMLInputElement>) {
    setUser({ ...user, name: event.target.value });
  }

  function updateAge(event: React.ChangeEvent<HTMLInputElement>) {
    setUser({ ...user, age: Number(event.target.value) });
  }

  return (
    <div>
      <h2>User Info</h2>
      <p>Name: {user.name}</p>
      <p>Age: {user.age}</p>

      <input type="text" placeholder="Name" value={user.name} onChange={updateName} />
      <input type="number" placeholder="Age" value={user.age} onChange={updateAge} />
    </div>
  );
}

export default App;
```

### ✅ Key Things:

* `useState<User>()` types the state as a `User` object.
* We use the **spread operator `...user`** to keep the other properties while updating one.

---

## ✅ 4. Typing `useState` Properly

### 🟩 For **numbers:**

```tsx
const [count, setCount] = useState<number>(0);
```

### 🟩 For **strings:**

```tsx
const [name, setName] = useState<string>("");
```

### 🟩 For **booleans:**

```tsx
const [isLoggedIn, setIsLoggedIn] = useState<boolean>(false);
```

### 🟩 For **objects:**

```tsx
type User = { name: string; age: number };
const [user, setUser] = useState<User>({ name: "", age: 0 });
```

### 🟩 For **arrays:**

```tsx
const [items, setItems] = useState<string[]>([]);
```

Always provide the **generic type to `useState`** to help TypeScript enforce types.

---

## ✅ 5. Updating State Based on Previous Values

When the new state **depends on the previous state**, you should use the **callback form** of `setState`.

### ✅ Example 4 — Correctly Incrementing a Counter

```tsx
import { useState } from "react";

function App() {
  const [count, setCount] = useState<number>(0);

  function increment() {
    setCount(prevCount => prevCount + 1);
  }

  return (
    <div>
      <h1>Count: {count}</h1>
      <button onClick={increment}>Increment</button>
    </div>
  );
}

export default App;
```

### ✅ Why?

* `setCount(count + 1)` **might fail** if multiple clicks happen fast.
* `setCount(prev => prev + 1)` **guarantees using the latest value**, even when updates are batched.

---

## ✅ Bonus: Multiple State Variables

You can have **multiple separate states** in one component:

```tsx
const [count, setCount] = useState<number>(0);
const [name, setName] = useState<string>("");
const [isLoggedIn, setIsLoggedIn] = useState<boolean>(false);
```

---

## ✅ Summary Table

| Type of State | Example Code                 |
| ------------- | ---------------------------- |
| number        | `useState<number>(0)`        |
| string        | `useState<string>("")`       |
| boolean       | `useState<boolean>(false)`   |
| object        | `useState<User>({...})`      |
| array         | `useState<string[]>([])`     |
| prev value    | `setState(prev => prev + 1)` |

---
---