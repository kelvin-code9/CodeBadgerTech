# 🚀 Handling Events in React with TypeScript — Full Guide

In this tutorial, you’ll learn **how to handle user-driven events** like clicks, input typing, form submission, and more — **all typed safely with TypeScript**.

---

## ✅ What We'll Cover

1. ✅ **What are Events in React?**
2. ✅ **Common Event Types in React + TypeScript**
3. ✅ **Handling Events: `onClick`, `onChange`, `onSubmit`**
4. ✅ **Typing Event Handlers**
5. ✅ **Correctly Typing `event.target`**
6. ✅ **Bonus Tips: Inline Typing**
7. ✅ **Summary & Practice Exercises**

---

## ✅ 1. What Are Events in React?

In React, **events represent user interactions** like:

* Clicking a button
* Typing into a text field
* Submitting a form
* Hovering or focusing

React **wraps browser events in a cross-browser system** called **SyntheticEvent** to ensure consistent behavior in all browsers.

---

## ✅ 2. Common Event Types in React + TypeScript

React provides specific event types for **strong typing in TypeScript**.

| User Action        | TypeScript Event Type                   |
| ------------------ | --------------------------------------- |
| Clicking a button  | `React.MouseEvent<HTMLButtonElement>`   |
| Typing in input    | `React.ChangeEvent<HTMLInputElement>`   |
| Submitting a form  | `React.FormEvent<HTMLFormElement>`      |
| Keyboard key press | `React.KeyboardEvent<HTMLInputElement>` |
| Selecting dropdown | `React.ChangeEvent<HTMLSelectElement>`  |

Knowing these types makes your event handlers **safe and error-free**.

---

## ✅ 3. Handling Events — `onClick`, `onChange`, `onSubmit`

### ✅ Example 1: Handling `onClick`

```tsx
import { useState } from "react";

function App() {
  const [count, setCount] = useState<number>(0);

  function handleClick(event: React.MouseEvent<HTMLButtonElement>) {
    console.log("Button clicked", event);
    setCount(prev => prev + 1);
  }

  return (
    <div>
      <h1>Count: {count}</h1>
      <button onClick={handleClick}>Increment</button>
    </div>
  );
}

export default App;
```

### ✅ Explanation:

* `React.MouseEvent<HTMLButtonElement>`: ensures the event is coming from a button.
* We **increment the counter** safely using `prev => prev + 1`.
* `console.log` prints the event object — useful for debugging.

---

### ✅ Example 2: Handling `onChange` on Inputs

```tsx
import { useState } from "react";

function App() {
  const [name, setName] = useState<string>("");

  function handleChange(event: React.ChangeEvent<HTMLInputElement>) {
    console.log("Current input value:", event.target.value);
    setName(event.target.value);
  }

  return (
    <div>
      <h2>Enter your name:</h2>
      <input type="text" value={name} onChange={handleChange} />
      <p>Hello, {name}!</p>
    </div>
  );
}

export default App;
```

### ✅ Explanation:

* `React.ChangeEvent<HTMLInputElement>`: specifies the input event type.
* `event.target.value` extracts the current text typed by the user.
* The input is **controlled**, meaning the displayed value is always in sync with React state.

---

### ✅ Example 3: Handling `onSubmit` in Forms

```tsx
import { useState } from "react";

function App() {
  const [email, setEmail] = useState<string>("");

  function handleSubmit(event: React.FormEvent<HTMLFormElement>) {
    event.preventDefault(); // Prevent page reload
    alert(`Form submitted with email: ${email}`);
  }

  return (
    <form onSubmit={handleSubmit}>
      <input
        type="email"
        value={email}
        onChange={(e: React.ChangeEvent<HTMLInputElement>) => setEmail(e.target.value)}
        placeholder="Enter email"
      />
      <button type="submit">Submit</button>
    </form>
  );
}

export default App;
```

### ✅ Explanation:

* `React.FormEvent<HTMLFormElement>` safely types the form submit event.
* `event.preventDefault()` stops the browser from refreshing.
* The **email input is controlled**, and the form submission triggers the alert.

---

## ✅ 4. Typing Event Handlers

You can define reusable event handler functions with precise types.

| User Action  | Handler Type Example                    |
| ------------ | --------------------------------------- |
| Button click | `React.MouseEvent<HTMLButtonElement>`   |
| Input change | `React.ChangeEvent<HTMLInputElement>`   |
| Form submit  | `React.FormEvent<HTMLFormElement>`      |
| Key press    | `React.KeyboardEvent<HTMLInputElement>` |

### ✅ Example: Key Press Event

```tsx
function handleKeyPress(event: React.KeyboardEvent<HTMLInputElement>) {
  console.log("Key pressed:", event.key);
}
```

You can attach this to an input field:

```tsx
<input type="text" onKeyDown={handleKeyPress} />
```

---

## ✅ 5. How to Type `event.target` Correctly

By default, `event.target` is treated as a **generic `EventTarget`**, which doesn't have a `.value` property. But with specific event types like `ChangeEvent<HTMLInputElement>`, TypeScript **knows it's an input**, so `.value` is available.

```tsx
function handleChange(event: React.ChangeEvent<HTMLInputElement>) {
  const inputValue = event.target.value;
  console.log("Typed value:", inputValue);
}
```

### ✅ In some cases, if you have an untyped `Event`, you can **cast manually**:

```tsx
const value = (event.target as HTMLInputElement).value;
```

---

## ✅ 6. Bonus: Typing Inline Functions

Sometimes, you may define the function **inline in the JSX**:

```tsx
<input
  type="text"
  onChange={(e: React.ChangeEvent<HTMLInputElement>) => setName(e.target.value)}
/>
```

In this case, TypeScript automatically infers `e`'s type from the context — so you don't always have to annotate it explicitly.

---

## ✅ 7. Summary Table of Events

| Event Handler        | Event Type                              |
| -------------------- | --------------------------------------- |
| `onClick`            | `React.MouseEvent<HTMLButtonElement>`   |
| `onChange`           | `React.ChangeEvent<HTMLInputElement>`   |
| `onSubmit`           | `React.FormEvent<HTMLFormElement>`      |
| `onKeyDown`          | `React.KeyboardEvent<HTMLInputElement>` |
| `onChange` on Select | `React.ChangeEvent<HTMLSelectElement>`  |

---
---
