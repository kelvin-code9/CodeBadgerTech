
# ⚛️ Component Lifecycle with Hooks (React + `useEffect`)

This module shows **how React's class-based lifecycle methods map to `useEffect`**, and how to control behavior during **mount**, **update**, and **unmount**.

---

## 🧠 What is a Component Lifecycle?

Every React component follows a **lifecycle**:

| Phase      | What it means                            |
| ---------- | ---------------------------------------- |
| Mounting   | Component is being inserted into the DOM |
| Updating   | Component re-renders due to props/state  |
| Unmounting | Component is removed from the DOM        |

In **class components**, you had lifecycle methods like:

* `componentDidMount()`
* `componentDidUpdate()`
* `componentWillUnmount()`

With **functional components**, all of this is done using the `useEffect` hook.

---

## 🔄 Mapping Lifecycle Methods to `useEffect`

| Class Method           | Equivalent in Functional Component        |
| ---------------------- | ----------------------------------------- |
| `componentDidMount`    | `useEffect(() => {...}, [])`              |
| `componentDidUpdate`   | `useEffect(() => {...}, [dep])`           |
| `componentWillUnmount` | `return () => {...}` inside `useEffect()` |

Let’s walk through each case.

---

## ✅ Example 1: Mounting (like `componentDidMount`)

```tsx
import { useEffect } from 'react';

function App() {
  useEffect(() => {
    console.log("📦 Component mounted (runs once)");
  }, []); // empty dependency array

  return <h1>Mounting Example</h1>;
}

export default App;
```

### 🧠 Explanation

* This effect runs **once** when the component is added to the DOM.
* Perfect for: initializing data, setting up listeners, analytics, etc.

---

## ✅ Example 2: Updating (like `componentDidUpdate`)

```tsx
import { useEffect, useState } from 'react';

function App() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    console.log(`🔁 Count updated: ${count}`);
  }, [count]); // runs when count changes

  return (
    <div>
      <h1>Count: {count}</h1>
      <button onClick={() => setCount(c => c + 1)}>Increment</button>
    </div>
  );
}

export default App;
```

### 🧠 Explanation

* This effect runs **every time `count` changes**.
* You can use this to react to prop/state changes and do something like:

  * Update the page title
  * Save to localStorage
  * Send a request when a value changes

---

## ✅ Example 3: Unmounting (like `componentWillUnmount`)

```tsx
import { useEffect, useState } from 'react';

function Timer() {
  useEffect(() => {
    const interval = setInterval(() => {
      console.log("⏱️ Tick");
    }, 1000);

    return () => {
      console.log("🧹 Timer cleanup");
      clearInterval(interval);
    };
  }, []);

  return <p>Running timer...</p>;
}

function App() {
  const [show, setShow] = useState(true);

  return (
    <div>
      <button onClick={() => setShow(prev => !prev)}>
        Toggle Timer
      </button>
      {show && <Timer />}
    </div>
  );
}

export default App;
```

### 🧠 Explanation

* The interval starts when `<Timer />` mounts.
* When we remove the component (toggle `show`), the cleanup runs.
* This is how you prevent **zombie intervals or listeners** from running in the background.

---

## 🧪 Timing and Order of `useEffect`

By default:

1. React **renders** the component.
2. Then it **runs the `useEffect` hook**.
3. On re-renders:

   * It runs cleanup from the previous effect.
   * Then it runs the updated effect again.

> 🧠 `useEffect` always runs **after paint**, which means it's not blocking rendering.

---

## 🚀 Bonus: `useLayoutEffect` vs `useEffect`

| `useEffect`             | `useLayoutEffect`                                                                  |
| ----------------------- | ---------------------------------------------------------------------------------- |
| Runs **after render**   | Runs **after DOM changes but before paint**                                        |
| Non-blocking            | Blocking (synchronous)                                                             |
| Preferred in most cases | Use when you **must measure DOM before screen updates** (e.g., layout shift fixes) |

---

## 🧼 Summary Table

| Pattern           | Code                                             | Description                            |
| ----------------- | ------------------------------------------------ | -------------------------------------- |
| Mount only        | `useEffect(() => {...}, [])`                     | Run once when component mounts         |
| Update only       | `useEffect(() => {...}, [dep])`                  | Run when a specific dependency changes |
| Mount + Cleanup   | `useEffect(() => { return () => {...} }, [])`    | Run on mount and clean on unmount      |
| Full update cycle | `useEffect(() => { return () => {...} }, [dep])` | Run when dep changes, clean old one    |

---

## ⚠️ Common Mistakes

| Mistake                          | What Happens                                                   |
| -------------------------------- | -------------------------------------------------------------- |
| Missing cleanup                  | Listeners or timers keep running even after component unmounts |
| Forgetting dependencies          | Effect doesn’t re-run when it should                           |
| Putting async directly in effect | Causes warning; wrap async in internal function                |

---

## ✅ What You Learned

* `useEffect` can **fully replace class-based lifecycle methods**
* You can control mount, update, and unmount phases with one hook
* Cleanup functions keep your app efficient and bug-free
* Timing matters — `useEffect` runs **after render**, not before

---
