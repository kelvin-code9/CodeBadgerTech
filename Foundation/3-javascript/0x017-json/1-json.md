

# 📦 JSON Tutorial – The Language of Data in Web Development

## 🧠 What Is JSON?

**JSON** stands for **JavaScript Object Notation**.

It is a **text-based data format** used to store and transfer data between applications, especially between a **client** (browser) and a **server**.

It looks like a **JavaScript object**, but it’s actually just a **string**.

---

## 🧪 Why Is JSON Important?

* It’s the **universal format** used in APIs (REST, GraphQL, etc.)
* Used in `localStorage`, `fetch()`, databases, config files, and more
* Lightweight, human-readable, and language-independent

---

## 📄 JSON vs JavaScript Object

| Concept | JavaScript Object                | JSON                     |
| ------- | -------------------------------- | ------------------------ |
| Type    | Actual object                    | String                   |
| Used In | Code logic                       | Data exchange            |
| Syntax  | Can contain functions, variables | Only data (no functions) |
| Example | `{ name: "John" }`               | `'{"name": "John"}'`     |

---

## 📘 Basic JSON Structure

```json
{
  "name": "Alice",
  "age": 25,
  "isStudent": true,
  "skills": ["HTML", "CSS", "JavaScript"]
}
```

### 🔹 Rules:

* Uses **double quotes** for keys and strings
* Data types: string, number, boolean, null, array, object
* No trailing commas

---

## 📁 Example 1: Convert JS Object → JSON

### 📜 `script.js`

```javascript
const user = {
  name: "Bob",
  age: 30,
  isAdmin: false
};

const jsonString = JSON.stringify(user);
console.log(jsonString); // '{"name":"Bob","age":30,"isAdmin":false}'
```

### ✅ `.stringify()` = Converts object to JSON string

---

## 📁 Example 2: Convert JSON → JS Object

```javascript
const jsonStr = '{"name":"Bob","age":30,"isAdmin":false}';
const userObject = JSON.parse(jsonStr);

console.log(userObject.name); // Bob
```

### ✅ `.parse()` = Converts JSON string back to JS object

---

## 📁 Example 3: Nested Objects and Arrays

```javascript
const company = {
  name: "CodeHub",
  employees: [
    { name: "Alice", role: "Frontend" },
    { name: "Bob", role: "Backend" }
  ],
  remote: true
};

const json = JSON.stringify(company);
console.log(json);

const parsed = JSON.parse(json);
console.log(parsed.employees[1].role); // Backend
```

---

## 🧠 JSON in Real-World Apps

You use JSON **whenever you communicate with an API** or save complex data in `localStorage`.

---

### 📁 Example 4: Save JSON to localStorage

```javascript
const book = {
  title: "Atomic Habits",
  author: "James Clear",
  pages: 320
};

localStorage.setItem("bookData", JSON.stringify(book));

const data = JSON.parse(localStorage.getItem("bookData"));
console.log(data.title); // Atomic Habits
```

---

## 🔗 Example 5: Fetching JSON from an API

Let’s use the `fetch()` API to get JSON from a public API.

### 📄 `index.html`

```html
<!DOCTYPE html>
<html>
<head><title>Fetch JSON</title></head>
<body>
  <h2>User Info</h2>
  <button id="loadBtn">Load User</button>
  <pre id="output"></pre>

  <script>
    document.getElementById("loadBtn").addEventListener("click", () => {
      fetch("https://jsonplaceholder.typicode.com/users/1")
        .then(response => response.json())
        .then(data => {
          document.getElementById("output").textContent = JSON.stringify(data, null, 2);
        });
    });
  </script>
</body>
</html>
```

### 🔍 Explanation:

* We `fetch()` a JSON response from an API.
* `.json()` automatically parses the response.
* We display it using `JSON.stringify(data, null, 2)` (for pretty format).

---

## ❗ Common Mistakes

| Mistake                          | Why it’s wrong                                   |
| -------------------------------- | ------------------------------------------------ |
| Using single quotes in JSON      | JSON must use double quotes for keys and strings |
| Trying to parse a real object    | Only strings can be parsed with `JSON.parse()`   |
| Storing JSON without stringify   | Data becomes `[object Object]`                   |
| Forgetting to parse from storage | You get a string instead of an object            |

---

## 🛠 Mini Assignment – "Student Profile Card"

**Goal:**
Build a profile card that reads a JSON object of student info and displays it on the screen.

### 👤 JSON Data Format:

```json
{
  "name": "Jordan",
  "level": "Beginner",
  "skills": ["HTML", "CSS", "JavaScript"],
  "score": 88
}
```

### 💼 Requirements:

* Save the data to `localStorage` as a JSON string
* Retrieve and parse it on page load
* Display all fields on the page
* Use JavaScript to generate the content dynamically

---

## 📊 Summary Table – JSON Methods

| Method             | Purpose                          | Example                          |
| ------------------ | -------------------------------- | -------------------------------- |
| `JSON.stringify()` | Convert JS object → JSON string  | `JSON.stringify(obj)`            |
| `JSON.parse()`     | Convert JSON string → JS object  | `JSON.parse(str)`                |
| `fetch().json()`   | Parse JSON from an HTTP response | `fetch(url).then(r => r.json())` |

---

## ✅ Wrap-Up

**JSON is everywhere** in web development — if you want to build anything dynamic, you need to know it well.

By mastering:

* `JSON.stringify()` / `JSON.parse()`
* JSON structure and rules
* Usage in APIs, storage, and UI display

You’re unlocking the foundation of **data-driven apps**!

---