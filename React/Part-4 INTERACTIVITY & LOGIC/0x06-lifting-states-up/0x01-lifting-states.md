
---

# 🚀 Lifting State Up in React with TypeScript

In this lesson, we’ll cover:

1. ✅ **What is Lifting State Up?**
2. ✅ **When and Why to Lift State**
3. ✅ **Sharing State Between Components**
4. ✅ **Lifting Callbacks as Props**
5. ✅ **Summary and Key Takeaways**
6. ✅ **Exercises**

---

## ✅ 1. What is Lifting State Up?

In React, **Lifting State Up** means:

> Moving state to the **closest common parent component** so that **multiple child components can access and update the same state**.

This solves the problem where **two or more sibling components need to share or sync data**.

---

## ✅ 2. When and Why to Lift State

### ✅ When:

* When **two sibling components need to read or update the same state**.
* When a **parent needs to control the behavior of its children**.

### ✅ Why:

* React follows a **unidirectional data flow** — **state flows downward from parents to children** via props.
* To keep **data consistent between components**, state must live **higher in the tree**, not scattered across children.

---

## ✅ 3. Example: Sharing State Between Components

### ✅ Without lifting state (not shared):

```tsx
import { useState } from "react";

function Child1() {
  const [count, setCount] = useState<number>(0);
  return <button onClick={() => setCount(count + 1)}>Child1 Count: {count}</button>;
}

function Child2() {
  const [count, setCount] = useState<number>(0);
  return <button onClick={() => setCount(count + 1)}>Child2 Count: {count}</button>;
}

function App() {
  return (
    <div>
      <Child1 />
      <Child2 />
    </div>
  );
}

export default App;
```

> ✅ Problem: `Child1` and `Child2` maintain **independent states** — changes in one don’t reflect in the other.

---

### ✅ Solution: Lift State Up to the Parent

```tsx
import { useState } from "react";

type ChildProps = {
  count: number;
  increment: () => void;
};

function Child1(props: ChildProps) {
  return <button onClick={props.increment}>Child1 Count: {props.count}</button>;
}

function Child2(props: ChildProps) {
  return <button onClick={props.increment}>Child2 Count: {props.count}</button>;
}

function App() {
  const [count, setCount] = useState<number>(0);

  function increment() {
    setCount(prev => prev + 1);
  }

  return (
    <div>
      <h2>Lifting State Example</h2>
      <Child1 count={count} increment={increment} />
      <Child2 count={count} increment={increment} />
    </div>
  );
}

export default App;
```

### ✅ Key Points

* The `count` state lives in the **parent (`App`)**.
* Both `Child1` and `Child2` receive:

  * The current `count`.
  * The `increment` function to update it.
* When either child clicks, both reflect the same **updated count**.

---

## ✅ 4. Lifting Callbacks as Props

When you **lift state**, you also pass **callback functions (like `increment`)** as props to children so they can **modify the parent’s state**.

### ✅ Benefits

* **Centralizes data:** Avoids state duplication.
* **Keeps UI in sync:** All components reflect the latest state.
* **Enhances control:** Parent governs how and when state changes.

---

## ✅ 5. Summary and Key Takeaways

| Concept          | Explanation                                                               |
| ---------------- | ------------------------------------------------------------------------- |
| Lifting State Up | Moving state to the nearest common ancestor.                              |
| When             | When multiple components need to share or update the same data.           |
| How              | Move the `useState` hook to the parent and pass state + updater as props. |
| Callbacks        | Children invoke callbacks to modify parent state.                         |

---