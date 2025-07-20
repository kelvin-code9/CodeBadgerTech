
---

# 🚀 Forms in React with TypeScript

In this tutorial, we’ll cover:

1. ✅ **What are Controlled Components?**
2. ✅ **Managing Form Input State**
3. ✅ **Form Submission**
4. ✅ **Typing Form Inputs and Event Values**
5. ✅ **Bonus: Handling Multiple Inputs with One Handler**
6. ✅ **Summary Table**
7. ✅ **Exercises**

---

## ✅ 1. What are Controlled Components?

A **controlled component** is an input form element whose **value is controlled by React state**.

> ✅ In controlled components:
>
> * React holds the **source of truth** for the input value.
> * The input's `value` is tied to state.
> * Changing the input triggers `onChange`, which updates state, then re-renders.

---

### ✅ Example: Controlled Input

```tsx
import { useState } from "react";

function App() {
  const [name, setName] = useState<string>("");

  function handleChange(event: React.ChangeEvent<HTMLInputElement>) {
    setName(event.target.value);
  }

  return (
    <div>
      <h2>Controlled Input Example</h2>
      <input
        type="text"
        value={name}
        onChange={handleChange}
        placeholder="Enter your name"
      />
      <p>Your name is: {name}</p>
    </div>
  );
}

export default App;
```

### ✅ Explanation

* The input’s `value` is controlled by `name`.
* When the user types, `onChange` updates the state via `setName`.

---

## ✅ 2. Managing Form Input State

For each form input, you’ll typically:

* **Define a piece of state** for its value.
* **Update state on input change**.
* **Bind state to the input’s `value`**.

### ✅ Example: Managing Multiple Inputs

```tsx
import { useState } from "react";

function App() {
  const [email, setEmail] = useState<string>("");
  const [password, setPassword] = useState<string>("");

  return (
    <div>
      <h2>Login Form</h2>
      <input
        type="email"
        placeholder="Email"
        value={email}
        onChange={(e: React.ChangeEvent<HTMLInputElement>) => setEmail(e.target.value)}
      />
      <input
        type="password"
        placeholder="Password"
        value={password}
        onChange={(e: React.ChangeEvent<HTMLInputElement>) => setPassword(e.target.value)}
      />
      <p>Email: {email}</p>
      <p>Password: {password}</p>
    </div>
  );
}

export default App;
```

---

## ✅ 3. Form Submission

### ✅ Example: Submitting a Form

```tsx
import { useState } from "react";

function App() {
  const [email, setEmail] = useState<string>("");
  const [password, setPassword] = useState<string>("");

  function handleSubmit(event: React.FormEvent<HTMLFormElement>) {
    event.preventDefault(); // prevent form refresh
    console.log("Submitted:", { email, password });
  }

  return (
    <form onSubmit={handleSubmit}>
      <h2>Register</h2>
      <input
        type="email"
        value={email}
        onChange={(e) => setEmail(e.target.value)}
        placeholder="Email"
      />
      <input
        type="password"
        value={password}
        onChange={(e) => setPassword(e.target.value)}
        placeholder="Password"
      />
      <button type="submit">Submit</button>
    </form>
  );
}

export default App;
```

### ✅ Explanation

* `onSubmit` captures the form submission.
* `event.preventDefault()` prevents page refresh.
* We can **send data to an API** or process it.

---

## ✅ 4. Typing Form Inputs and Events

### ✅ Typing Event Handlers

| Input Type | Event Type                            |
| ---------- | ------------------------------------- |
| Text Input | `React.ChangeEvent<HTMLInputElement>` |
| Form       | `React.FormEvent<HTMLFormElement>`    |

### ✅ Accessing Input Values Safely

```tsx
function handleChange(e: React.ChangeEvent<HTMLInputElement>) {
  const inputValue = e.target.value;
}
```

You don’t need extra casting because TS infers the correct types when you specify the **generic type of the event**.

---

## ✅ 5. Bonus: Handling Multiple Inputs with One Handler

### ✅ Example: Dynamic Handler with Input `name`

```tsx
import { useState } from "react";

type FormState = {
  email: string;
  password: string;
};

function App() {
  const [formData, setFormData] = useState<FormState>({ email: "", password: "" });

  function handleChange(e: React.ChangeEvent<HTMLInputElement>) {
    const { name, value } = e.target;

    setFormData((prev) => ({
      ...prev,
      [name]: value
    }));
  }

  function handleSubmit(e: React.FormEvent<HTMLFormElement>) {
    e.preventDefault();
    console.log("Form Data:", formData);
  }

  return (
    <form onSubmit={handleSubmit}>
      <h2>Dynamic Input Handler</h2>
      <input
        name="email"
        type="email"
        value={formData.email}
        onChange={handleChange}
        placeholder="Email"
      />
      <input
        name="password"
        type="password"
        value={formData.password}
        onChange={handleChange}
        placeholder="Password"
      />
      <button type="submit">Submit</button>
    </form>
  );
}

export default App;
```

### ✅ Key Point

* Using `name` in input tags (`<input name="email" />`) lets us **dynamically update the corresponding state field**.

---

## ✅ 6. Summary Table

| Feature                | Example                               |
| ---------------------- | ------------------------------------- |
| Controlled Input       | `value={state}` with `onChange`       |
| Event Typing           | `React.ChangeEvent<HTMLInputElement>` |
| Form Submit            | `React.FormEvent<HTMLFormElement>`    |
| Dynamic Input Handling | Use `name` property + spread operator |

---

