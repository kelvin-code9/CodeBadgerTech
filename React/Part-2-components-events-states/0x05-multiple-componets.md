

# 🚀 Composing with Multiple Components in React + TypeScript

In this lesson, we’ll learn how to:

* Split a UI into multiple reusable components.
* Import and use components inside each other.
* Pass data between components (props drilling).
* Organize components into a proper folder structure.

---

## ✅ Why Split into Multiple Components?

Imagine building a website:
Instead of dumping everything into a single file (`App.tsx`), you **divide the page into parts** like:

* A **Header**
* A **Profile section**
* A **Footer**

Each of these becomes its own **component file**, making your code:

| Advantage | Benefit                    |
| --------- | -------------------------- |
| Organized | Easier to manage and debug |
| Reusable  | Components can be reused   |
| Readable  | Cleaner, clearer structure |
| Scalable  | Easy to grow the project   |

---

## ✅ Folder Structure

First, create a folder inside `src`:

```
/src
  /components
    Header.tsx
    Footer.tsx
    Profile.tsx
    Dashboard.tsx
  App.tsx
```

This structure ensures all UI pieces (components) are in one place.

---

## ✅ Step 1: Create **Header.tsx**

### 🔎 Explanation:

The **Header** is a simple component that displays a title for the app.

```tsx
function Header() {
  return <h1>Welcome to My App</h1>;
}

export default Header;
```

* We define a **function** named `Header`.
* Inside the `return`, we output a heading (`<h1>`).
* We **export default** so we can use it in other files.

---

## ✅ Step 2: Create **Footer.tsx**

### 🔎 Explanation:

The **Footer** is typically at the bottom of a page, often with copyright.

```tsx
function Footer() {
  return <footer>© 2025 My App. All rights reserved.</footer>;
}

export default Footer;
```

* React components can return any valid HTML tag. Here we use `<footer>`.
* Still exporting by **default**.

---

## ✅ Step 3: Create **Profile.tsx**

### 🔎 Explanation:

We want to display a user's **name** and **age**, so this component needs **props**.

First, define a **TypeScript type** for the props:

```tsx
type ProfileProps = {
  name: string;
  age: number;
};
```

Then, define the component with **props destructuring**:

```tsx
function Profile({ name, age }: ProfileProps) {
  return (
    <div>
      <h2>Profile</h2>
      <p>Name: {name}</p>
      <p>Age: {age}</p>
    </div>
  );
}

export default Profile;
```

### ✅ What’s Happening?

* `Profile` takes **props** of type `ProfileProps`.
* Instead of `props.name` and `props.age`, we destructure props directly in the function signature.
* The component displays the data passed to it.

---

## ✅ Step 4: Create **Dashboard.tsx**

### 🔎 What’s the Purpose?

The **Dashboard** component receives a **user object** and passes the user's details to the **Profile** component.
This is a basic example of **props drilling**.

```tsx
import Profile from "./Profile";

type User = {
  name: string;
  age: number;
};

type DashboardProps = {
  user: User;
};

function Dashboard({ user }: DashboardProps) {
  return <Profile name={user.name} age={user.age} />;
}

export default Dashboard;
```

### ✅ What’s Happening?

* `Dashboard` takes a prop called `user` (with `name` and `age`).
* It passes the `name` and `age` to the `Profile` component below it.
* This is **props drilling** — even though `Dashboard` doesn't use the `user` data directly, it **passes it down** to the child (`Profile`).

---

## ✅ Step 5: Compose Everything in **App.tsx**

```tsx
import Header from "./components/Header";
import Footer from "./components/Footer";
import Dashboard from "./components/Dashboard";

function App() {
  const user = { name: "Favour", age: 25 };

  return (
    <div>
      <Header />
      <Dashboard user={user} />
      <Footer />
    </div>
  );
}

export default App;
```

### ✅ Explanation:

* `Header` goes at the top.
* `Dashboard` in the middle, which displays the **Profile**.
* `Footer` at the bottom.

We have successfully **composed the UI using multiple components**.
Data flows **top to bottom**:
`App` → `Dashboard` → `Profile`.

---

## ✅ Why We Pass Data (Props Drilling)

> Props drilling happens when you **pass data down through multiple layers of components**, even if some layers don’t directly use it.

Example:

* **App** has the **user object**.
* It passes it to **Dashboard**.
* **Dashboard** passes it to **Profile**, where it is finally used.

This maintains **one-way data flow** in React, making data predictable and easier to debug.

If drilling becomes too deep, later you can learn about **Context API** or **state management libraries**.

---

## 🧠 Mental Model

React apps are like **LEGO structures**:

* Each component is a **block (brick)**.
* You assemble these blocks to build **complex UIs**.
* Props are like **instructions or decorations for each block**.

---

## ✅ Summary Table

| Concept                   | Description                                |
| ------------------------- | ------------------------------------------ |
| **Component Composition** | Breaking the UI into smaller components    |
| **Props**                 | Passing data into a component              |
| **Props Drilling**        | Passing props from parent → child → child  |
| **Folder Structure**      | Organizing components inside `/components` |

---

## ✅ Final Exercise

1. Create the components (`Header`, `Footer`, `Profile`, `Dashboard`).
2. In `App.tsx`, declare a user object and pass it down to the `Dashboard`.
3. `Dashboard` passes data to `Profile`.
4. `Profile` displays the data.

✅ Your final app should render:

```
Welcome to My App
Profile
Name: Favour
Age: 25
© 2025 My App. All rights reserved.
```

---
