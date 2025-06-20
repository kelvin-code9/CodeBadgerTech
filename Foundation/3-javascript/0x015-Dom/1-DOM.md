
## 📘The Document Object Model (DOM)

---

### ✅ What is DOM?

The **Document Object Model (DOM)** is a programming interface that represents the **HTML content of a webpage as a tree structure**. With DOM, JavaScript can:

* Read and change HTML elements and content
* Modify CSS styles dynamically
* Respond to user interactions (clicks, typing, etc.)
* Create or remove elements from the page

Simply put: **DOM = JavaScript’s way of talking to your HTML**.

---

### 🧠 Why Learn DOM?

Without the DOM, JavaScript wouldn't be able to interact with the page. DOM is what makes a static webpage become **interactive and dynamic**.

Examples of what you can do with DOM:

* Show or hide elements
* Update text content live
* Create to-do lists or chat apps
* Validate forms before submission

---

## 🌲 DOM Structure – Tree of Nodes

Here’s how your HTML is seen by JavaScript:

```html
<html>
  <head>
    <title>Page</title>
  </head>
  <body>
    <h1>Hello</h1>
  </body>
</html>
```

This becomes a **tree** like this:

```
Document
 └── html
      ├── head
      │     └── title
      └── body
            └── h1
```

Every element is a **node**, and you can access or manipulate them using JavaScript.

---

## 📌 Accessing Elements in the DOM

JavaScript provides different methods to **select elements**.

```html
<h1 id="heading">Welcome</h1>
<p class="info">Hello World</p>
```

### 1. By ID

```javascript
const title = document.getElementById("heading");
```

### 2. By Class

```javascript
const info = document.getElementsByClassName("info");
```

### 3. By Tag Name

```javascript
const paragraphs = document.getElementsByTagName("p");
```

### 4. Using Query Selector (Modern & Preferred)

```javascript
const heading = document.querySelector("#heading"); // Single match
const allParagraphs = document.querySelectorAll("p"); // All matches
```

---

## 1️⃣ `getElementById()` — Select Element by Unique ID

### 🔸 What It Does

`getElementById()` allows you to select a **single HTML element** using its `id` attribute. Every `id` must be **unique** in the HTML document.

### 🔸 How It Works

The method looks through the DOM tree and returns the **first element** with a matching ID. You can then use that element to read or update its content, style, attributes, etc.

---

### 🧪 Example: Change Heading Text

#### 📄 `index.html`

```html
<!DOCTYPE html>
<html>
<head>
  <title>DOM: getElementById</title>
</head>
<body>
  <h1 id="main-title">Welcome to My Page</h1>
  <button id="change-btn">Change Title</button>

  <script src="script.js"></script>
</body>
</html>
```

#### 📜 `script.js`

```javascript
const button = document.getElementById("change-btn");

button.addEventListener("click", function () {
  const title = document.getElementById("main-title");
  title.textContent = "Title Changed!";
});
```

### 🧠 Explanation

* `document.getElementById("main-title")`: selects the `<h1>` element.
* `title.textContent = "..."`: updates the text inside the element.
* `addEventListener()`: attaches a click handler (more on this in a full section below).

---

## 2️⃣ `getElementsByClassName()` — Select All Elements by Class

### 🔸 What It Does

This method returns **all elements** that have a specific class name. It returns an **HTMLCollection**, which looks like an array but isn't exactly one (you can loop through it).

### 🔸 How It Works

It searches through the DOM and returns every element with the matching class, even if there are dozens.

---

### 🧪 Example: Highlight Multiple Messages

#### 📄 `index.html`

```html
<!DOCTYPE html>
<html>
<head>
  <title>DOM: getElementsByClassName</title>
  <style>
    .highlight {
      background-color: yellow;
    }
  </style>
</head>
<body>
  <p class="message">This is message 1</p>
  <p class="message">This is message 2</p>
  <p class="message">This is message 3</p>
  <button id="highlight-btn">Highlight Messages</button>

  <script src="script.js"></script>
</body>
</html>
```

#### 📜 `script.js`

```javascript
const button = document.getElementById("highlight-btn");

button.addEventListener("click", function () {
  const messages = document.getElementsByClassName("message");
  for (let i = 0; i < messages.length; i++) {
    messages[i].classList.add("highlight");
  }
});
```

---

## 3️⃣ `getElementsByTagName()` — Select by Tag Name

### 🔸 What It Does

This method returns **all elements** with a specific tag name (like `div`, `li`, `p`). Like `getElementsByClassName`, it returns a live **HTMLCollection**.

---

### 🧪 Example: Bold All Paragraphs

#### 📄 `index.html`

```html
<!DOCTYPE html>
<html>
<head>
  <title>DOM: getElementsByTagName</title>
</head>
<body>
  <p>Paragraph One</p>
  <p>Paragraph Two</p>
  <p>Paragraph Three</p>
  <button id="bold-btn">Make Bold</button>

  <script src="script.js"></script>
</body>
</html>
```

#### 📜 `script.js`

```javascript
const button = document.getElementById("bold-btn");

button.addEventListener("click", function () {
  const paragraphs = document.getElementsByTagName("p");
  for (let i = 0; i < paragraphs.length; i++) {
    paragraphs[i].style.fontWeight = "bold";
  }
});
```

---

## 🔁 DOM Event Listeners – Interacting with Users

### 🔸 What is an Event?

An **event** is anything that happens in the browser:

* Clicking a button
* Moving the mouse
* Pressing a key
* Submitting a form

### 🔸 What is an Event Listener?

An **event listener** is a function that waits for a specific event to happen and then runs some code in response.

---

### 📌 Syntax:

```javascript
element.addEventListener("eventType", functionToRun);
```

* `"click"` – when the element is clicked
* `"mouseover"` – when the mouse moves over the element
* `"keydown"` – when the user presses a key

---

### 🧪 Example: Click Button to Show Alert

#### 📄 `index.html`

```html
<!DOCTYPE html>
<html>
<head>
  <title>DOM: Event Listeners</title>
</head>
<body>
  <button id="alert-btn">Click Me</button>

  <script src="script.js"></script>
</body>
</html>
```

#### 📜 `script.js`

```javascript
const button = document.getElementById("alert-btn");

button.addEventListener("click", function () {
  alert("Button was clicked!");
});
```
---

## 1️⃣ `mouseover` and `mouseout` — Mouse Hover

### 🔸 Description:

* `mouseover`: When the mouse enters an element.
* `mouseout`: When it leaves.

---

### 🧪 Example: Hover to Change Background

#### 📄 `index.html`

```html
<!DOCTYPE html>
<html>
<head>
  <title>Mouseover</title>
  <style>
    #box {
      width: 200px;
      height: 100px;
      background: lightgray;
      text-align: center;
      line-height: 100px;
    }
  </style>
</head>
<body>
  <div id="box">Hover over me</div>
  <script src="script.js"></script>
</body>
</html>
```

#### 📜 `script.js`

```javascript
const box = document.getElementById("box");

box.addEventListener("mouseover", function () {
  box.style.backgroundColor = "lightgreen";
  box.textContent = "Mouse is over!";
});

box.addEventListener("mouseout", function () {
  box.style.backgroundColor = "lightgray";
  box.textContent = "Hover over me";
});
```

---

## 2️⃣ `keydown` and `keyup` — Keyboard Input

### 🔸 Description:

* `keydown`: Fires when a key is **pressed down**.
* `keyup`: Fires when the key is **released**.

---

### 🧪 Example: Show Key Pressed

#### 📄 `index.html`

```html
<!DOCTYPE html>
<html>
<head><title>Key Press</title></head>
<body>
  <input type="text" id="inputField" placeholder="Type something...">
  <p id="keyInfo">Key pressed: </p>
  <script src="script.js"></script>
</body>
</html>
```

#### 📜 `script.js`

```javascript
const input = document.getElementById("inputField");
const display = document.getElementById("keyInfo");

input.addEventListener("keydown", function (event) {
  display.textContent = "Key pressed: " + event.key;
});
```

---

## 3️⃣ `submit` — Handling Forms

### 🔸 Description:

* `submit`: Triggers when a form is submitted.
* You usually call `event.preventDefault()` to stop the default behavior (like reloading the page).

---

### 🧪 Example: Simple Form Validation

#### 📄 `index.html`

```html
<!DOCTYPE html>
<html>
<head><title>Form Submit</title></head>
<body>
  <form id="myForm">
    <input type="text" id="nameInput" placeholder="Enter name" required>
    <button type="submit">Submit</button>
  </form>
  <p id="message"></p>
  <script src="script.js"></script>
</body>
</html>
```

#### 📜 `script.js`

```javascript
const form = document.getElementById("myForm");
const message = document.getElementById("message");

form.addEventListener("submit", function (event) {
  event.preventDefault(); // Prevent page reload
  const name = document.getElementById("nameInput").value;
  message.textContent = `Hello, ${name}!`;
});
```

---

## 4️⃣ `change` — Detect Input Value Change

### 🔸 Description:

* `change`: Fires when the user changes an input, `<select>`, or `<textarea>` **and then leaves focus**.

---

### 🧪 Example: Dropdown Menu

#### 📄 `index.html`

```html
<!DOCTYPE html>
<html>
<head><title>Change Event</title></head>
<body>
  <label for="color">Choose color:</label>
  <select id="color">
    <option value="">--Select--</option>
    <option value="red">Red</option>
    <option value="blue">Blue</option>
    <option value="green">Green</option>
  </select>
  <p id="result"></p>
  <script src="script.js"></script>
</body>
</html>
```

#### 📜 `script.js`

```javascript
const select = document.getElementById("color");
const result = document.getElementById("result");

select.addEventListener("change", function () {
  result.textContent = "You selected: " + select.value;
});
```

---

## 5️⃣ Accessing the `event` Object

When an event occurs, the browser passes an `event` object that contains:

* `event.target`: The element that triggered the event
* `event.type`: The type of event (click, keydown, etc.)
* `event.key`: The key that was pressed (for keyboard events)

---

### 🧪 Example: Show Clicked Element

#### 📄 `index.html`

```html
<!DOCTYPE html>
<html>
<head><title>Event Object</title></head>
<body>
  <button>Click A</button>
  <button>Click B</button>
  <p id="log"></p>
  <script src="script.js"></script>
</body>
</html>
```

#### 📜 `script.js`

```javascript
const buttons = document.querySelectorAll("button");
const log = document.getElementById("log");

buttons.forEach(function (btn) {
  btn.addEventListener("click", function (event) {
    log.textContent = "You clicked: " + event.target.textContent;
  });
});
```

---

## 6️⃣ Removing an Event Listener

You can remove an event listener using `removeEventListener`.

---

### 🧪 Example: Button That Works Only Once

#### 📄 `index.html`

```html
<!DOCTYPE html>
<html>
<head><title>Remove Listener</title></head>
<body>
  <button id="once">Click Me Once</button>
  <script src="script.js"></script>
</body>
</html>
```

#### 📜 `script.js`

```javascript
const button = document.getElementById("once");

function sayHi() {
  alert("You clicked me!");
  button.removeEventListener("click", sayHi); // Remove after first use
}

button.addEventListener("click", sayHi);
```

---

## 7️⃣ Event Propagation – Bubbling vs Capturing (Advanced)

### 🔸 What is it?

When an event happens, it travels through the DOM in two phases:

* **Capturing phase**: Top → down to the target
* **Bubbling phase**: Target → up to the top

By default, events bubble.

---

### 🧪 Example: Nested Clicks

#### 📄 `index.html`

```html
<!DOCTYPE html>
<html>
<head>
  <title>Event Bubbling</title>
  <style>
    #outer { padding: 20px; background: #eee; }
    #inner { padding: 20px; background: #ccc; }
  </style>
</head>
<body>
  <div id="outer">
    Outer
    <div id="inner">Inner</div>
  </div>
  <script src="script.js"></script>
</body>
</html>
```

#### 📜 `script.js`

```javascript
document.getElementById("outer").addEventListener("click", function () {
  alert("Outer clicked!");
});

document.getElementById("inner").addEventListener("click", function (e) {
  alert("Inner clicked!");
  e.stopPropagation(); // Stops event from bubbling
});
```

---

## 📊 Summary Table: Common Event Types

| Event Type  | Description                       | Common Use Case                |
| ----------- | --------------------------------- | ------------------------------ |
| `click`     | User clicks an element            | Buttons, toggles               |
| `mouseover` | Mouse enters element              | Tooltips, hover effects        |
| `mouseout`  | Mouse leaves element              | Resetting hover styles         |
| `keydown`   | Key is pressed                    | Form shortcuts, game controls  |
| `keyup`     | Key is released                   | Live validation                |
| `submit`    | Form is submitted                 | Validation, AJAX submission    |
| `change`    | Input/Select is changed           | Dropdowns, checkboxes          |
| `input`     | User types in a field (real-time) | Live search, character counter |

---

Let me know when you're ready to move on to `querySelector()` / `querySelectorAll()` in depth or start DOM content manipulation (text, attributes, styles, creating elements, etc.).
