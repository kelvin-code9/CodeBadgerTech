

# 🚀 Rendering Lists in React with TypeScript

In this tutorial, we'll learn:

1. ✅ **Mapping Over Arrays**
2. ✅ **Using the `key` Prop Correctly**
3. ✅ **Typing Arrays and List Items in TypeScript**
4. ✅ **Bonus: Conditional Rendering in Lists**
5. ✅ **Summary Table**
6. ✅ **Exercises**

---

## ✅ 1. Mapping Over Arrays

In React, to render multiple items (like users, tasks, products), we **map over an array** and return JSX for each item.

---

### ✅ Example 1: Basic Mapping

```tsx
import React from "react";

function App() {
  const fruits: string[] = ["Apple", "Banana", "Cherry"];

  return (
    <div>
      <h1>Fruit List</h1>
      <ul>
        {fruits.map((fruit, index) => (
          <li key={index}>{fruit}</li>
        ))}
      </ul>
    </div>
  );
}

export default App;
```

### ✅ Explanation:

* `fruits.map()` loops through the array.
* Each `fruit` is rendered as a `<li>`.
* `key={index}` gives a **unique key** (we’ll explain shortly).

---

## ✅ 2. Using the `key` Prop Correctly

### ✅ Why `key`?

* React uses the `key` prop to **track elements** when updating the UI.
* It helps React **identify which items changed, added, or removed**.

### ✅ Best Practice:

* **Don't use `index` as the key if the list can change order or items can be removed.**
* Use a **unique identifier (like `id`)** whenever possible.

---

### ✅ Example 2: Using Unique Keys

```tsx
type User = {
  id: number;
  name: string;
};

function App() {
  const users: User[] = [
    { id: 1, name: "Favour" },
    { id: 2, name: "Amaka" },
    { id: 3, name: "Chinedu" }
  ];

  return (
    <div>
      <h1>Users</h1>
      <ul>
        {users.map((user) => (
          <li key={user.id}>{user.name}</li>
        ))}
      </ul>
    </div>
  );
}

export default App;
```

> ✅ **Key Rule:** `key` should be **stable, predictable, and unique** for each item.

---

## ✅ 3. Typing Arrays and List Items in TypeScript

### ✅ Typing Arrays

* For a list of **primitive types**:

```ts
const fruits: string[] = ["Apple", "Banana"];
```

* For an **array of objects**:

```ts
type User = { id: number; name: string };
const users: User[] = [{ id: 1, name: "Alice" }];
```

### ✅ Typing Inside `map()`

You can type items when mapping:

```tsx
users.map((user: User) => (
  <li key={user.id}>{user.name}</li>
));
```

However, TypeScript **often infers** the type from the array itself, so manual typing in `.map()` is optional.

---

## ✅ 4. Bonus: Conditional Rendering in Lists

You can also **conditionally render lists**.

### ✅ Example: Show message if list is empty

```tsx
function App() {
  const tasks: string[] = [];

  return (
    <div>
      <h1>Tasks</h1>
      {tasks.length === 0 ? (
        <p>No tasks available</p>
      ) : (
        <ul>
          {tasks.map((task, index) => (
            <li key={index}>{task}</li>
          ))}
        </ul>
      )}
    </div>
  );
}

export default App;
```

---

## ✅ 5. Summary Table

| Concept                  | Example                              |
| ------------------------ | ------------------------------------ |
| Map over array           | `items.map(item => <li>{item}</li>)` |
| Provide unique key       | `key={item.id}`                      |
| Type array of primitives | `const items: string[]`              |
| Type array of objects    | `const items: ItemType[]`            |
| Conditional rendering    | `array.length === 0 ? msg : list`    |


---
