# 🔹 3.3 Embedding Expressions in TSX (React + TypeScript)

When building a UI, we don’t want static text all the time — we want content that **comes from data, computations, or conditions**.

In React, this is possible by embedding **expressions, variables, and logic directly inside TSX using curly braces `{}`**.

This chapter will teach you **how to display data dynamically** inside your UI.

---

## 🧩 1. Embedding Variables in TSX

We can insert any **TypeScript variable** directly inside our TSX with `{}`.

### Example

```tsx
function App() {
  const userName: string = "Favour";

  return (
    <div>
      <h2>Embedding Variables</h2>
      <p>Hello, {userName}!</p>
    </div>
  );
}

export default App;
```

### ✅ Output

> Hello, Favour!

**Insight:**
React reads `{userName}` and replaces it with `"Favour"` when rendering the page. It's like inserting a placeholder that dynamically fills in.

---

## 🧩 2. Embedding TypeScript Expressions

You can inject **live computations**, like math or string manipulation.

### Example

```tsx
function App() {
  return (
    <div>
      <h2>Embedding Expressions</h2>
      <p>5 + 3 = {5 + 3}</p>
      <p>{"TypeScript".toUpperCase()} is fun!</p>
    </div>
  );
}

export default App;
```

### ✅ Output

> 5 + 3 = 8
> TYPESCRIPT is fun!

**Insight:**
Anything between `{}` is evaluated by TypeScript/JavaScript, so you can dynamically calculate, transform strings, or even call functions.

---

## 🧩 3. Calling Functions in TSX

Functions can generate values, which is useful when the value is **computed** or **changes dynamically**.

### Example

```tsx
function getCurrentYear(): number {
  return new Date().getFullYear();
}

function App() {
  return (
    <div>
      <h2>Calling Functions in TSX</h2>
      <p>Current Year: {getCurrentYear()}</p>
    </div>
  );
}

export default App;
```

### ✅ Output

> Current Year: 2025

**Insight:**
You can define any function that returns a value, then call it inside TSX to display the result.

---

## 🟧 4. Conditional Rendering — Show Things Only When Certain Conditions are Met

Sometimes you want to display elements **only when a condition is met**. There are two ways in TSX:

### ✅ Method 1: Logical AND (`&&`)

This means: *"If this is true, then show this."*

### Example

```tsx
function App() {
  const isLoggedIn: boolean = true;

  return (
    <div>
      <h2>Conditional Rendering: AND</h2>
      {isLoggedIn && <p>Welcome back!</p>}
    </div>
  );
}

export default App;
```

If `isLoggedIn` is `false`, nothing appears.

---

### ✅ Method 2: Ternary Operator (`? :`)

This lets you show **one of two things depending on a condition**.

### Example

```tsx
function App() {
  const isOnline: boolean = false;

  return (
    <div>
      <h2>Conditional Rendering: Ternary</h2>
      <p>Status: {isOnline ? "Online" : "Offline"}</p>
    </div>
  );
}

export default App;
```

### ✅ Output

> Status: Offline

**Insight:**
The ternary operator is like saying:

> **if `isOnline` is true:** show `"Online"`
> **else:** show `"Offline"`

---

## 🟦 5. Rendering Lists Dynamically with `.map()`

In a UI, you often want to **display many items from an array** — like hobbies, tasks, or messages.

React's `.map()` lets you **loop through an array and create UI for each item.**

### Example

```tsx
function App() {
  const hobbies: string[] = ["Reading", "Coding", "Auditing"];

  return (
    <div>
      <h2>Rendering Lists with map()</h2>
      <ul>
        {hobbies.map((hobby, index) => (
          <li key={index}>{hobby}</li>
        ))}
      </ul>
    </div>
  );
}

export default App;
```

### ✅ Output

* Reading
* Coding
* Auditing

**Insight:**
We add a `key` prop (using `index` here) so React can uniquely track each item. This helps React optimize updates to the UI.

---

## 🟩 6. Combined Example — Building a Full Profile Dynamically

Let’s combine all the techniques into one **User Profile**.

### Example

```tsx
function getCurrentYear(): number {
  return new Date().getFullYear();
}

function App() {
  const userName: string = "Favour Okerri";
  const age: number = 21;
  const hobbies: string[] = ["Auditing", "Programming", "Football"];

  return (
    <div>
      <h2>User Profile</h2>

      <p>Hello, {userName}!</p>
      <p>Age: {age}</p>

      <p>{age >= 18 ? "You are an adult" : "You are a minor"}</p>

      <h3>Hobbies</h3>
      <ul>
        {hobbies.map((hobby, index) => (
          <li key={index}>{hobby}</li>
        ))}
      </ul>

      <footer>© {getCurrentYear()}</footer>
    </div>
  );
}

export default App;
```

---

## 🧠 Summary Table of Embedding Techniques

| Feature                    | Syntax Example                      | Use Case                    |
| -------------------------- | ----------------------------------- | --------------------------- |
| **Variable**               | `{userName}`                        | Inject data                 |
| **Expression**             | `{5 + 3}`                           | Simple calculations         |
| **Function Call**          | `{getCurrentYear()}`                | Dynamic/computed data       |
| **Conditional AND (`&&`)** | `{isLoggedIn && <p>Hi</p>}`         | Show when condition is true |
| **Ternary**                | `{isOnline ? "Online" : "Offline"}` | Two-way conditional         |
| **List `.map()`**          | `{items.map(...)}`                  | Render arrays/lists         |

---
