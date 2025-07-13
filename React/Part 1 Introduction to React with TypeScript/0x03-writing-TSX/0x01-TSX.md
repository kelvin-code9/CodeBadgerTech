
# 🔹 3.2 TSX Syntax and Structure

In **React with TypeScript**, we use a syntax called **TSX** — this is the structure and style of writing UI elements inside **`.tsx` files**.

Even though it looks like HTML, TSX is actually a combination of **TypeScript and JSX-like syntax**, which React understands and compiles into UI code.

> ✅ **Note:** We haven't fully covered React Components yet — for now, just focus on the **syntax structure of TSX itself**. Components will be explained in detail later.

---

## 🧱 What is TSX?

**TSX** is the format that lets us write:

* **TypeScript logic**
* Alongside **HTML-like UI code**

All within files that have the **`.tsx` extension**.

Example:

```tsx
function Hello() {
  return <h1>Hello, world!</h1>;
}
```

This code:

* Uses TypeScript to define a function.
* Uses **TSX syntax** to return a UI element.

---

## 🟩 What is a "Root Element" in TSX?

In TSX, every function that returns TSX code must have **one single outer element** — called the **root element**.

Think of it like the **main wrapper** for everything you're returning.

### ❌ Example Without a Root Element (Incorrect)

```tsx
function Hello() {
  return (
    <h1>Hello</h1>
    <p>Welcome!</p>
  );
}
```

> This is **invalid** because the function is trying to return **two sibling elements side by side**.

### ✅ Example With a Root Element (Correct)

```tsx
function Hello() {
  return (
    <div>
      <h1>Hello</h1>
      <p>Welcome!</p>
    </div>
  );
}
```

Here, the `<div>` is the **root element** that wraps everything.

### ✅ Alternative: Using TSX Fragments

If you don't want to add an extra HTML tag, you can use **Fragments**, written as `<>...</>`, which are invisible in the final output:

```tsx
function Hello() {
  return (
    <>
      <h1>Hello</h1>
      <p>Welcome!</p>
    </>
  );
}
```

---

## 🟨 Nesting in TSX

TSX supports **nested elements**, just like HTML.

Example:

```tsx
function Profile() {
  return (
    <div>
      <h2>Profile</h2>
      <ul>
        <li>Name: Favour</li>
        <li>Occupation: Auditor</li>
      </ul>
    </div>
  );
}
```

This returns a heading and a list nested inside a div.

---

## 🟦 Self-Closing Tags in TSX

In TSX, some elements don't have children and must be **self-closing** using `/`:

```tsx
<img src="avatar.png" alt="User Avatar" />
<input type="text" />
<br />
<hr />
```

If you forget the `/` in self-closing tags, TSX will throw an error.

---

## 🟧 Combined Example of TSX Structure

```tsx
function Example() {
  return (
    <div>
      <h2>My Info</h2>
      <p>I love learning TypeScript with React.</p>
      <img src="https://via.placeholder.com/150" alt="Placeholder Image" />
    </div>
  );
}

export default Example;
```

You don't need to worry about `export default` yet — when we cover **React Components**, you'll see how this works together.

---

## 🧠 TSX Structure Summary

| Concept               | Description                                 |
| --------------------- | ------------------------------------------- |
| **Root element**      | One wrapper element around all TSX elements |
| **Nesting**           | Placing elements inside others              |
| **Self-closing tags** | Tags without content must end with `/`      |
| **Fragments**         | Use `<>...</>` to wrap without extra HTML   |

---

## ✅ Exercise

1. Create a **`FavoriteThings.tsx`** file.
2. It should render:

   * A heading (e.g., "My Favorite Things")
   * A paragraph about yourself
   * A list of 3 things you love
   * A self-closing image tag with any image

