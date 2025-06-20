
# 📦 JavaScript `localStorage`

## 📘 What is `localStorage`?

`localStorage` is part of the **Web Storage API**, which allows you to store **key-value pairs** in a user's browser — **persistently** (even after the page is refreshed or browser is closed).

### ✅ Key Features:

* Stores data **locally in the browser**
* Data **does not expire** (unless cleared manually)
* Can only store **strings** (must use `JSON.stringify()` for objects)
* Has a limit of \~5MB

---

## 🧪 Basic Usage

### 🔹 Methods:

| Method                | Description                         |
| --------------------- | ----------------------------------- |
| `setItem(key, value)` | Stores a value by key               |
| `getItem(key)`        | Retrieves the value for the key     |
| `removeItem(key)`     | Deletes a key and its value         |
| `clear()`             | Clears all localStorage values      |
| `key(index)`          | Gets the key at the specified index |
| `length`              | Returns number of stored keys       |

---

## 📁 Example 1: Save and Get a Simple String

### 📄 `index.html`

```html
<!DOCTYPE html>
<html>
<head><title>localStorage Basic</title></head>
<body>
  <h2>Simple localStorage Example</h2>
  <input type="text" id="nameInput" placeholder="Enter your name">
  <button onclick="saveName()">Save</button>
  <button onclick="loadName()">Load</button>
  <p id="result"></p>

  <script src="script.js"></script>
</body>
</html>
```

### 📜 `script.js`

```javascript
function saveName() {
  const name = document.getElementById("nameInput").value;
  localStorage.setItem("username", name);
  alert("Name saved!");
}

function loadName() {
  const savedName = localStorage.getItem("username");
  const result = document.getElementById("result");
  result.textContent = savedName ? `Welcome back, ${savedName}!` : "No name found.";
}
```

---

## 📁 Example 2: Storing and Retrieving an Object

You must **convert objects to strings** using `JSON.stringify()` before storing, and **parse them** using `JSON.parse()` when retrieving.

---

### 📄 `index.html`

```html
<!DOCTYPE html>
<html>
<head><title>localStorage Object</title></head>
<body>
  <h2>Save User Profile</h2>
  <input type="text" id="age" placeholder="Age">
  <input type="text" id="email" placeholder="Email">
  <button onclick="saveProfile()">Save</button>
  <button onclick="loadProfile()">Load</button>
  <p id="output"></p>

  <script src="script.js"></script>
</body>
</html>
```

### 📜 `script.js`

```javascript
function saveProfile() {
  const user = {
    age: document.getElementById("age").value,
    email: document.getElementById("email").value
  };
  localStorage.setItem("userProfile", JSON.stringify(user));
  alert("Profile saved!");
}

function loadProfile() {
  const data = localStorage.getItem("userProfile");
  const output = document.getElementById("output");

  if (data) {
    const user = JSON.parse(data);
    output.innerHTML = `Age: ${user.age} <br>Email: ${user.email}`;
  } else {
    output.textContent = "No user profile found.";
  }
}
```

---

## 🧹 Example 3: Removing and Clearing

### 📜 `script.js` snippet

```javascript
// Remove one item
localStorage.removeItem("username");

// Clear all localStorage
localStorage.clear();
```

---

## ⚙️ Example 4: `localStorage` and Page Load Events

You can use `window.onload` to check if data exists and auto-load it.

```javascript
window.onload = function () {
  const data = localStorage.getItem("userProfile");
  if (data) {
    const user = JSON.parse(data);
    console.log("Loaded user:", user);
  }
};
```

---

## 🎯 Mini Project: Persistent To-Do List

This mini project shows off the power of `localStorage` by **saving tasks even after page reloads**.

### 📄 `index.html`

```html
<!DOCTYPE html>
<html>
<head>
  <title>Persistent To-Do</title>
  <style>
    body { font-family: sans-serif; }
    li.done { text-decoration: line-through; color: gray; }
  </style>
</head>
<body>
  <h2>To-Do List</h2>
  <input id="taskInput" placeholder="Add a task">
  <button onclick="addTask()">Add</button>
  <ul id="taskList"></ul>

  <script src="script.js"></script>
</body>
</html>
```

### 📜 `script.js`

```javascript
let tasks = [];

function loadTasks() {
  const stored = localStorage.getItem("tasks");
  if (stored) {
    tasks = JSON.parse(stored);
    tasks.forEach(renderTask);
  }
}

function renderTask(text, isDone = false) {
  const li = document.createElement("li");
  li.textContent = text;
  if (isDone) li.classList.add("done");

  li.addEventListener("click", () => {
    li.classList.toggle("done");
    updateStorage();
  });

  document.getElementById("taskList").appendChild(li);
}

function addTask() {
  const input = document.getElementById("taskInput");
  const taskText = input.value.trim();
  if (taskText) {
    tasks.push({ text: taskText, done: false });
    renderTask(taskText);
    updateStorage();
    input.value = "";
  }
}

function updateStorage() {
  const updatedTasks = [];
  document.querySelectorAll("#taskList li").forEach(li => {
    updatedTasks.push({
      text: li.textContent,
      done: li.classList.contains("done")
    });
  });
  localStorage.setItem("tasks", JSON.stringify(updatedTasks));
}

window.onload = loadTasks;
```

---

## 🧠 Tips for Working with `localStorage`

* Always wrap objects in `JSON.stringify()` before saving.
* Always check if the key exists (`if (data)`) before parsing.
* Use `window.onload` to reload data and repopulate the page.
* Don't store sensitive information — it's accessible via browser dev tools.

---

## 📊 Summary Table

| Method                       | Purpose                | Notes                         |
| ---------------------------- | ---------------------- | ----------------------------- |
| `localStorage.setItem(k,v)`  | Save a string          | Must stringify objects        |
| `localStorage.getItem(k)`    | Get saved string       | Parse if it's JSON            |
| `localStorage.removeItem(k)` | Remove specific key    | Good for logout/profile clear |
| `localStorage.clear()`       | Remove all keys        | Use with caution              |
| `localStorage.length`        | Total items in storage | Use in loops or diagnostics   |
| `localStorage.key(index)`    | Get key name by index  | Use for iterating over keys   |

---
