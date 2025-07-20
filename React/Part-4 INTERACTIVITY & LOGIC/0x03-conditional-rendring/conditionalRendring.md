# 🚀 Conditional Rendering in React with TypeScript

In this tutorial, you'll learn how to **conditionally render** UI elements in React based on state, props, or logic.

We will cover:

1. ✅ **What is Conditional Rendering?**
2. ✅ **Ternary Operator**
3. ✅ **Short-Circuiting with `&&`**
4. ✅ **Returning `null` to Hide Components**
5. ✅ **Conditional Styling**
6. ✅ **Bonus Tips and Summary**

---

## ✅ 1. What is Conditional Rendering?

> Conditional Rendering is the **technique of displaying different UI elements based on some condition** (e.g. user logged in, data loaded, feature enabled).

React allows us to write JavaScript logic inside JSX to decide **what to show or hide**.

### 📌 **Why Use It?**

* To show different UI for different states
* To prevent rendering unnecessary components
* To enhance UX by showing loaders, errors, etc.

---

## ✅ 2. Ternary Operator

### ✅ Example — Show Greeting Based on `isLoggedIn`

```tsx
import { useState } from 'react';

function App() {
  const [isLoggedIn, setIsLoggedIn] = useState<boolean>(false);

  return (
    <div>
      <h1>Welcome</h1>
      {isLoggedIn ? (
        <p>Hello, User! 🎉</p>
      ) : (
        <p>Please log in. 🔐</p>
      )}

      <button onClick={() => setIsLoggedIn(!isLoggedIn)}>
        {isLoggedIn ? 'Logout' : 'Login'}
      </button>
    </div>
  );
}

export default App;
```

### ✅ Explanation

| Code                         | Purpose                        |
| ---------------------------- | ------------------------------ |
| `isLoggedIn ? <A> : <B>`     | Show `<A>` if true, else `<B>` |
| `setIsLoggedIn(!isLoggedIn)` | Toggle the login state         |

---

## ✅ 3. Short-Circuiting with `&&`

Use `&&` to render **something only when a condition is true**.

### ✅ Example — Show Admin Panel if Admin

```tsx
import { useState } from 'react';

function App() {
  const [isAdmin, setIsAdmin] = useState<boolean>(false);

  return (
    <div>
      <h1>Dashboard</h1>
      {isAdmin && <p>Welcome, Admin! 👑</p>}

      <button onClick={() => setIsAdmin(!isAdmin)}>
        Toggle Admin
      </button>
    </div>
  );
}

export default App;
```

### ✅ Explanation

* If `isAdmin` is **true**, it renders the `<p>` tag.
* If `isAdmin` is **false**, it renders **nothing**.

---

## ✅ 4. Returning `null` in Components

A component can **return `null` instead of JSX**, meaning **render nothing**.

### ✅ Example — Hidden Message Component

```tsx
type MessageProps = {
  isVisible: boolean;
};

function SecretMessage({ isVisible }: MessageProps) {
  if (!isVisible) {
    return null; // render nothing
  }

  return <p>This is a secret message! 🤫</p>;
}

export default SecretMessage;
```

### ✅ Usage:

```tsx
<SecretMessage isVisible={true} />
```

If `isVisible` is false, the component outputs **nothing to the UI**.

---

## ✅ 5. Conditional Styling

You can apply **different CSS styles conditionally**.

### ✅ Example — Toggle Button Color

```tsx
import { useState } from 'react';

function App() {
  const [isActive, setIsActive] = useState<boolean>(false);

  const buttonStyle = {
    backgroundColor: isActive ? 'green' : 'gray',
    color: 'white',
    padding: '10px 20px',
    border: 'none',
  };

  return (
    <button style={buttonStyle} onClick={() => setIsActive(!isActive)}>
      {isActive ? 'Active' : 'Inactive'}
    </button>
  );
}

export default App;
```

### ✅ Explanation

* `buttonStyle` is **calculated based on `isActive`**.
* The background color toggles between **green** and **gray**.

---

## ✅ 6. Bonus: Combining Techniques

```tsx
{isLoggedIn && isAdmin ? <AdminDashboard /> : <LoginPrompt />}
```

You can **combine `&&` and ternary** for complex conditions.

---

## ✅ Summary Table

| Technique         | Example Code                                       | Effect                |
| ----------------- | -------------------------------------------------- | --------------------- |
| Ternary           | `condition ? <A> : <B>`                            | Render A or B         |
| Short-circuit     | `condition && <Element>`                           | Render only if true   |
| Return `null`     | `if (!visible) return null`                        | Render nothing        |
| Conditional Style | `{ backgroundColor: isActive ? 'green' : 'gray' }` | Change style by state |

---

---