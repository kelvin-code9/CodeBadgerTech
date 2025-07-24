
# ⚛️ React Router Full Tutorial with Real Explanations (TypeScript)

---

## 🎯 What You'll Learn

* How to install and configure `react-router-dom`
* The purpose of `<Routes>`, `<Route>`, `<Link>`, `useParams`, `useNavigate`
* Clean project structure
* Why this all matters for real apps

---

## 🏗 Step 1: Start Fresh

> If you haven't already created a project:

```bash
npx create-react-app my-router-app --template typescript
cd my-router-app
```

Now install React Router:

```bash
npm install react-router-dom
```

✅ This gives you the tools to do client-side routing with `react-router-dom`.

---

## 📁 Step 2: Clean Project Structure

Create folders for clean separation of concerns:

```
src/
├── App.tsx
├── main.tsx
├── components/
│   └── Navbar.tsx
├── pages/
│   ├── Home.tsx
│   ├── About.tsx
│   └── User.tsx
```

### ❓ Why this structure?

* `/pages/` → Actual route destinations
* `/components/` → Reusable components (e.g., Navbar)
* Makes scaling easier

---

## 🔌 Step 3: Set Up Routing in `main.tsx`

### `src/main.tsx`

```tsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import { BrowserRouter } from 'react-router-dom';
import App from './App';

ReactDOM.createRoot(document.getElementById('root')!).render(
  <React.StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </React.StrictMode>
);
```

### 🧠 Why wrap with `BrowserRouter`?

React Router needs a **router context**. Wrapping the app tells React:

> “Track the URL changes and control what appears on screen.”

If you forget this, you'll get errors like:
❌ `useNavigate() may be used only in the context of a Router component`

---

## 🗺 Step 4: Define Routes in `App.tsx`

### `src/App.tsx`

```tsx
import { Routes, Route } from 'react-router-dom';
import Navbar from './components/Navbar';
import Home from './pages/Home';
import About from './pages/About';
import User from './pages/User';

function App() {
  return (
    <>
      <Navbar />

      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
        <Route path="/user/:id" element={<User />} />
      </Routes>
    </>
  );
}

export default App;
```

### 🧠 Explanation

* `<Routes>` is the **newer version of `<Switch>`** (React Router v6+)
* Each `<Route>` connects a `path` to a `component` (via `element`)
* `:id` is a **dynamic route param** (we’ll read it soon)

---

## 🔗 Step 5: Add a Navigation Bar

### `src/components/Navbar.tsx`

```tsx
import { Link } from 'react-router-dom';

function Navbar() {
  return (
    <nav style={{ background: '#eee', padding: '1rem' }}>
      <Link to="/" style={{ marginRight: '1rem' }}>Home</Link>
      <Link to="/about" style={{ marginRight: '1rem' }}>About</Link>
      <Link to="/user/123">User 123</Link>
    </nav>
  );
}

export default Navbar;
```

### 🧠 Explanation

* `<Link>` prevents full page reloads (unlike `<a>`)
* React handles navigation internally
* You can think of it as:

  > “Change the URL and re-render the correct route — without leaving the SPA”

---

## 📄 Step 6: Create Pages with Purpose

### `src/pages/Home.tsx`

```tsx
import { useNavigate } from 'react-router-dom';

function Home() {
  const navigate = useNavigate();

  const goToUser = () => {
    navigate('/user/99');
  };

  return (
    <div>
      <h1>🏠 Home Page</h1>
      <p>This is the main page of the app.</p>
      <button onClick={goToUser}>Go to User 99</button>
    </div>
  );
}

export default Home;
```

### 🧠 What just happened?

* `useNavigate()` is like saying:

  > "Take me to another page from code, not a link"
* Great for things like:

  * redirecting after login
  * redirecting after a successful form

---

### `src/pages/About.tsx`

```tsx
function About() {
  return (
    <div>
      <h1>ℹ️ About Page</h1>
      <p>This explains what the app is for.</p>
    </div>
  );
}

export default About;
```

Simple page, no hooks here — just a static route.

---

### `src/pages/User.tsx`

```tsx
import { useParams } from 'react-router-dom';

function User() {
  const { id } = useParams();

  return (
    <div>
      <h1>👤 User Page</h1>
      <p>This is the page for user with ID: {id}</p>
    </div>
  );
}

export default User;
```

### 🧠 What is `useParams()`?

If your route is `/user/:id`, then:

```tsx
const { id } = useParams();
```

grabs the dynamic part of the URL — e.g., `/user/123` gives `id = "123"`.

You can now:

* fetch user data based on `id`
* display it on the page
* validate input

---

## 🧪 Quick Test Time

Go to your app and try:

1. Clicking “User 123” in the navbar
2. Clicking the button from the Home page
3. Changing the URL manually to `/user/9999`

All should work without reloading the app.

---

## ✅ Summary

| Concept            | What You Used                           |
| ------------------ | --------------------------------------- |
| `BrowserRouter`    | Wraps your app, gives routing context   |
| `Routes` / `Route` | Declares which components go with paths |
| `<Link>`           | Navigates between routes (no reload)    |
| `useParams()`      | Reads `:id` values from the URL         |
| `useNavigate()`    | Lets you navigate from inside JS logic  |

---

## 🧼 Mistakes to Avoid

| Mistake                        | Fix it like this                    |
| ------------------------------ | ----------------------------------- |
| ❌ Using `<a href="/">`         | ✅ Use `<Link to="/">`               |
| ❌ Forgetting `<BrowserRouter>` | ✅ Wrap your app at the top level    |
| ❌ Not handling `:id` properly  | ✅ Always check `useParams()` output |

---
