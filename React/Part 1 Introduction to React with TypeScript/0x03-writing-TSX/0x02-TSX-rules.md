
# 🔹 Essential **TSX Rules** You Must Follow

When writing **TSX in React + TypeScript**, there are some important **rules and constraints** that prevent common errors.

Let’s go through these **3 core rules** with examples.

---

## 🟦 1. One Parent Element (Root Element)

TSX code returned from a component must always be **wrapped in a single parent element**.

### ❌ Incorrect Example

```tsx
function Info() {
  return (
    <h1>Hello</h1>
    <p>Welcome to my page!</p>
  );
}
```

This gives an error because there are **two sibling elements side by side**.

### ✅ Correct Example

Wrap everything in a **`<div>`** or a **Fragment**:

```tsx
function Info() {
  return (
    <div>
      <h1>Hello</h1>
      <p>Welcome to my page!</p>
    </div>
  );
}
```

Or:

```tsx
function Info() {
  return (
    <>
      <h1>Hello</h1>
      <p>Welcome to my page!</p>
    </>
  );
}
```

---

## 🟦 2. Use `className` Instead of `class`

In HTML, we write:

```html
<div class="container"></div>
```

But in **TSX**, `class` is a **reserved keyword in JavaScript**, so React uses:

```tsx
<div className="container"></div>
```

If you mistakenly write `class`, TypeScript will throw an error:

```tsx
<div class="container"></div> // ❌ Error in TSX
```

### ✅ Correct

```tsx
function Box() {
  return <div className="box">I'm styled!</div>;
}
```

---

## 🟦 3. Don’t Render Raw Objects

You cannot directly **render an object** inside TSX.

### ❌ Example That Throws an Error

```tsx
function Demo() {
  const data = { name: "Favour", age: 25 };

  return <p>{data}</p>; // ❌ Error: Objects are not valid as a React child
}
```

React/TSX doesn’t know how to **display an object directly**.

### ✅ Correct: Render Properties Instead

```tsx
function Demo() {
  const data = { name: "Favour", age: 25 };

  return (
    <p>
      Name: {data.name}, Age: {data.age}
    </p>
  );
}
```

Alternatively, you can convert the object to a **JSON string**:

```tsx
<p>{JSON.stringify(data)}</p>
```

---

## 🔍 TSX Rules Recap

| Rule                   | What to Do                            | Why                                 |
| ---------------------- | ------------------------------------- | ----------------------------------- |
| **One Parent Element** | Wrap everything in one root tag       | React needs a single tree           |
| **className**          | Use `className` not `class`           | `class` is reserved in JS           |
| **No Raw Objects**     | Render object properties or stringify | React can’t render objects directly |

---

## ✅ Exercise

1. Create a `MyProfile.tsx` file.
2. Follow the TSX rules to render:

   * A div with `className="profile"`
   * A heading with your name
   * A paragraph with some text
   * An object with properties `hobby` and `country` — but only render the values properly (not the whole object).

---