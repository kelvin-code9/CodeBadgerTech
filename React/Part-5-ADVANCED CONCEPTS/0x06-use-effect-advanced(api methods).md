
# React + `useEffect` + Axios/Fetch: GET, POST, PUT, PATCH, DELETE

## 0) What we’re doing (and why)

* **Goal:** teach how to call APIs from React with **all HTTP methods** and understand what each does.
* **How we’ll *see* it work:** We’ll run a fake local API using `json-server` that **writes to `db.json`** so you can literally watch data change on disk.
* **What you don’t need:** real DB knowledge. `json-server` is a demo tool.

---

## 1) The HTTP verbs (mental model first)

| Method     | What it means (plain English)                         | Example in a todo app    | What changes in `db.json` |
| ---------- | ----------------------------------------------------- | ------------------------ | ------------------------- |
| **GET**    | “Give me data.”                                       | Get all todos            | Nothing (read-only)       |
| **POST**   | “Create a new thing with this body.”                  | Add a todo               | New object appended       |
| **PUT**    | “Replace this whole thing with this new whole thing.” | Replace todo #7 entirely | Object overwritten        |
| **PATCH**  | “Change *only* these fields.”                         | Mark todo #7 completed   | Partial update in place   |
| **DELETE** | “Remove this thing.”                                  | Delete todo #7           | Object removed            |

> TL;DR: **POST adds, PUT replaces, PATCH tweaks, DELETE removes, GET reads.**

---

## 2) Set up the project (exact steps)

```bash
# Create Vite + React + TypeScript app
npm create vite@latest react-crud
cd react-crud

# App deps
npm install
npm i axios

# Dev API (demo DB)
npm i -D json-server
```

Create **`db.json`** in the project root (same folder as `package.json`) you do not need to understand the db setUp just copy and paste:

```json
{
  "todos": [
    { "id": 1, "title": "Learn useEffect", "completed": false },
    { "id": 2, "title": "Write POST request", "completed": true }
  ]
}
```

Add **scripts** in `package.json`:

```json
{
  "scripts": {
    "dev": "vite",
    "api": "json-server --watch db.json --port 5174"
  }
}
```

Run both servers (two terminals):

```bash
# Terminal A (API)
npm run api   # -> http://localhost:5174

# Terminal B (React)
npm run dev   # -> http://localhost:5173
```

Open:

* `http://localhost:5173` (your app)
* `http://localhost:5174/todos` (the API data)
* Keep `db.json` open in your editor to watch it change.

---

## 3) Shared interface (so everything agrees on data shape)

Create **`src/interfaces.tsx`**:

```ts
export interface Todo {
  id: number;
  title: string;
  completed: boolean;
}
```

Why: this is the contract your components and API calls rely on. If something is off, TypeScript tells you early.

---

## 4) Axios instance (central place for base URL + logging)

Create **`src/lib/api.tsx`**:

```ts
import axios from "axios";

export const api = axios.create({
  baseURL: "http://localhost:5174",
  headers: { "Content-Type": "application/json" }
});

// Optional: log requests in the console so learners can *see* what fires
api.interceptors.response.use(
  (res) => {
    console.log(`[API ${res.config.method?.toUpperCase()}]`, res.config.url, res.status);
    return res;
  },
  (err) => {
    console.error("[API ERROR]", err?.response?.status, err?.message);
    return Promise.reject(err);
  }
);
```

---

## 5) The React component (what each effect/handler is doing)

Replace **`src/App.tsx`** with this (comments explain the *why* at each step):

```tsx
import { useEffect, useMemo, useState } from "react";
import { api } from "./lib/api";
import type { Todo } from "./interfaces";


/**
 * What you’ll observe:
 * - GET on mount loads todos.
 * - POST adds a new todo (you’ll see it appear AND db.json gets a new object).
 * - PUT replaces a todo (forgetting a field overwrites it—on purpose).
 * - PATCH toggles 'completed' only (title untouched).
 * - DELETE removes the todo entirely.
 * 
 * Where to watch:
 * - UI updates in the list below
 * - DevTools > Network (all requests visible)
 * - db.json updates on disk (our demo “database”)
 */

export default function App() {
  const [todos, setTodos] = useState<Todo[]>([]);
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState<string | null>(null);

  // Form state
  const [newTitle, setNewTitle] = useState("");
  const [editId, setEditId] = useState<number | null>(null);
  const [editTitle, setEditTitle] = useState("");

  // Derived example
  const remaining = useMemo(() => todos.filter(t => !t.completed).length, [todos]);

  /** GET: read the list once when component mounts */
  useEffect(() => {
    let cancelled = false; // prevents state writes if the component unmounts mid-flight

    const load = async () => {
      try {
        setLoading(true);
        setError(null);
        const res = await api.get<Todo[]>("/todos");
        if (!cancelled) setTodos(res.data);
      } catch (e: any) {
        if (!cancelled) setError(e?.message ?? "Failed to load todos");
      } finally {
        if (!cancelled) setLoading(false);
      }
    };

    load();
    return () => { cancelled = true; };
  }, []);

  /** POST: create a new record (adds to db.json) */
  const addTodo = async () => {
    const title = newTitle.trim();
    if (!title) return;

    try {
      setError(null);
      // Optimistic UI: show it immediately so the app feels snappy
      const temp: Todo = { id: Date.now(), title, completed: false };
      setTodos(prev => [temp, ...prev]);

      // The server returns the “real” object with a real id
      const res = await api.post<Todo>("/todos", { title, completed: false });
      setTodos(prev => [res.data, ...prev.filter(t => t.id !== temp.id)]);
      setNewTitle("");
    } catch (e: any) {
      setError(e?.message ?? "Failed to add todo");
      // Simple recovery: re-fetch canonical state
      const res = await api.get<Todo[]>("/todos");
      setTodos(res.data);
    }
  };

  /** PUT: replace a record (send all fields) */
  const saveEdit = async () => {
    if (editId == null) return;
    const title = editTitle.trim();
    if (!title) return;

    try {
      setError(null);
      const current = todos.find(t => t.id === editId);
      if (!current) return;

      // PUT is “replace”, so include every field we want to keep
      const res = await api.put<Todo>(`/todos/${editId}`, {
        id: editId,
        title,
        completed: current.completed
      });

      setTodos(prev => prev.map(t => (t.id === editId ? res.data : t)));
      setEditId(null);
      setEditTitle("");
    } catch (e: any) {
      setError(e?.message ?? "Failed to update via PUT");
    }
  };

  /** PATCH: partial update (toggle one field safely) */
  const toggleCompleted = async (todo: Todo) => {
    try {
      setError(null);
      // Optimistic flip
      setTodos(prev => prev.map(t => t.id === todo.id ? { ...t, completed: !t.completed } : t));

      const res = await api.patch<Todo>(`/todos/${todo.id}`, { completed: !todo.completed });

      // Sync with server response
      setTodos(prev => prev.map(t => t.id === todo.id ? res.data : t));
    } catch (e: any) {
      setError(e?.message ?? "Failed to toggle via PATCH");
      // Rollback: reload from truth
      const res = await api.get<Todo[]>("/todos");
      setTodos(res.data);
    }
  };

  /** DELETE: remove from server (and UI) */
  const removeTodo = async (id: number) => {
    try {
      setError(null);
      // Optimistic remove
      const backup = todos;
      setTodos(prev => prev.filter(t => t.id !== id));

      await api.delete(`/todos/${id}`);
      // If it fails, the catch will restore
    } catch (e: any) {
      setError(e?.message ?? "Failed to delete");
      // Restore by reloading truth
      const res = await api.get<Todo[]>("/todos");
      setTodos(res.data);
    }
  };

  return (
    <div style={{ maxWidth: 720, margin: "40px auto", padding: 16, fontFamily: "system-ui, Arial" }}>
      <h1>Todos (GET / POST / PUT / PATCH / DELETE)</h1>
      <p style={{ color: "#555" }}>
        Remaining: <strong>{remaining}</strong>
      </p>

      {/* Create (POST) */}
      <div style={{ display: "flex", gap: 8, marginBottom: 16 }}>
        <input
          value={newTitle}
          onChange={(e) => setNewTitle(e.target.value)}
          placeholder="New todo title"
          style={{ flex: 1, padding: 8, border: "1px solid #ccc", borderRadius: 8 }}
        />
        <button onClick={addTodo} style={{ padding: "8px 12px", borderRadius: 8 }}>
          Add (POST)
        </button>
      </div>

      {loading && <p>Loading…</p>}
      {error && <p style={{ color: "crimson" }}>Error: {error}</p>}

      <ul style={{ listStyle: "none", padding: 0, display: "grid", gap: 8 }}>
        {todos.map((t) => (
          <li key={t.id} style={{ border: "1px solid #eee", borderRadius: 12, padding: 12 }}>
            {/* PATCH (toggle one field) */}
            <label style={{ display: "flex", alignItems: "center", gap: 8 }}>
              <input type="checkbox" checked={t.completed} onChange={() => toggleCompleted(t)} />
              <span style={{ textDecoration: t.completed ? "line-through" : "none" }}>
                {t.title}
              </span>
            </label>

            {/* PUT (replace whole object) + DELETE */}
            {editId === t.id ? (
              <div style={{ marginTop: 8, display: "flex", gap: 8 }}>
                <input
                  value={editTitle}
                  onChange={(e) => setEditTitle(e.target.value)}
                  style={{ flex: 1, padding: 8, border: "1px solid #ccc", borderRadius: 8 }}
                />
                <button onClick={saveEdit} style={{ padding: "6px 10px", borderRadius: 8 }}>
                  Save (PUT)
                </button>
                <button onClick={() => { setEditId(null); setEditTitle(""); }} style={{ padding: "6px 10px", borderRadius: 8 }}>
                  Cancel
                </button>
              </div>
            ) : (
              <div style={{ marginTop: 8, display: "flex", gap: 8 }}>
                <button
                  onClick={() => { setEditId(t.id); setEditTitle(t.title); }}
                  style={{ padding: "6px 10px", borderRadius: 8 }}
                >
                  Edit title
                </button>
                <button onClick={() => removeTodo(t.id)} style={{ padding: "6px 10px", borderRadius: 8 }}>
                  Delete
                </button>
              </div>
            )}
          </li>
        ))}
      </ul>
    </div>
  );
}
```

---

## 6) “Show me, don’t tell me”: how to *see* each method work

Open three things side-by-side:

1. The app at `http://localhost:5173`
2. The API data at `http://localhost:5174/todos`
3. The file **`db.json`** in your editor

Now:

* **GET** happens on page load — you’ll see the list render. `db.json` unchanged (read-only).
* Click **Add (POST)**: a new object appears in UI *and* `db.json` now includes it.
* Click a checkbox (**PATCH**) on an item: only `completed` flips in `db.json`.
* Click **Edit title → Save (PUT)**: the whole object is replaced (title changed, `completed` preserved because we sent it).
* Click **Delete**: the object disappears *and* is removed from `db.json`.

Also check **DevTools → Network** to watch each request in real time.

---

## 7) “I prefer Fetch”—equivalents you can drop in

Anywhere you see an Axios call, you can use these **Fetch** versions:

```ts
// GET
const res1 = await fetch("http://localhost:5174/todos");
const list: Todo[] = await res1.json();

// POST
const res2 = await fetch("http://localhost:5174/todos", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ title, completed: false })
});
const created: Todo = await res2.json();

// PUT (replace)
await fetch(`http://localhost:5174/todos/${id}`, {
  method: "PUT",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ id, title, completed })
});

// PATCH (partial)
await fetch(`http://localhost:5174/todos/${id}`, {
  method: "PATCH",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ completed: !completed })
});

// DELETE
await fetch(`http://localhost:5174/todos/${id}`, { method: "DELETE" });
```

**When to pick which:**

* **Axios**: nicer defaults, interceptors, automatic JSON, generally less boilerplate.
* **Fetch**: built-in, zero deps, explicit.

---

## 8) Folder map (so learners know *where files go*)

```
react-crud/
├─ db.json                   # ← demo "DB" you can watch change
├─ package.json              # scripts: dev (Vite), api (json-server)
├─ src/
│  ├─ lib/
│  │  └─ api.ts             # Axios client with baseURL + logging
│  ├─ interfaces.ts         # interface Todo
│  ├─ App.tsx               # UI + GET/POST/PUT/PATCH/DELETE
│  └─ main.tsx              # Vite bootstrap
└─ index.html
```

---

## 9) Quick “gotchas” (and how we handled them)

* **“PUT vs PATCH?”**
  PUT = replace everything (send full object), PATCH = change a field or two.

* **“I clicked but nothing changed.”**
  Check DevTools Network for errors, confirm API is running on **5174**, and that the URL matches `baseURL`.

* **“My UI showed something then snapped back.”**
  That’s optimistic UI + server correction. If the server rejects, we re-fetch truth.

* **“Do I need to set up a real database?”**
  **No.** `json-server` is purely for teaching; it writes to `db.json` so you can *see* changes.
