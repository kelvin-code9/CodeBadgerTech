## 📘 The Browser Object Model (BOM)

---

### ✅ What is BOM?

The **Browser Object Model (BOM)** allows JavaScript to interact with the **browser itself**, not just the content of a webpage (which is handled by the DOM). While the DOM (Document Object Model) lets you access and manipulate HTML elements, the BOM provides tools to:

* Access browser features (like history, navigation, screen size)
* Work with popup windows
* Handle URLs and page redirections
* Communicate with the browser's environment

The BOM is not standardized like the DOM but is supported by all major browsers.

---

### 🔍 BOM vs DOM – A Quick Comparison

| Feature         | DOM                          | BOM                                    |
| --------------- | ---------------------------- | -------------------------------------- |
| Deals with      | HTML elements (page content) | Browser window and features            |
| Example Object  | `document`                   | `window`, `navigator`, `location`      |
| Standardized by | W3C                          | No (browser vendors implement)         |
| Common Use      | Changing page content        | Redirecting page, popups, browser info |

---

### 🧱 Key Objects in the BOM

Let’s go through the most important BOM objects and how you can use them.

---

## 1️⃣ `window` Object – The Global Boss

In browsers, **everything in the BOM is part of the `window` object**. Even DOM’s `document` is a property of `window`.

```javascript
console.log(window);          // Logs the whole window object
console.log(window.innerWidth);  // Width of the viewport
console.log(window.document);   // The DOM!
```

* All global variables and functions become properties of `window`.

```javascript
var name = "Favour";
console.log(window.name); // "Favour"
```

---

## 2️⃣ `navigator` – Know the User’s Browser

The `navigator` object gives info about the browser and operating system.

```javascript
console.log(navigator.userAgent); // Full browser details
console.log(navigator.language);  // Browser language
console.log(navigator.onLine);    // true if online
```

🧠 Use Cases:

* Detect browser type
* Customize experience for mobile vs desktop
* Check if user is online/offline

---

## 3️⃣ `location` – Control the URL

The `location` object allows you to read and change the current URL.

```javascript
console.log(location.href);    // Full URL
console.log(location.hostname); // Hostname (e.g., example.com)
console.log(location.pathname); // Path (/about.html)

location.href = "https://google.com"; // Redirects to Google
```

🧠 Use Cases:

* Page redirection
* Extract query parameters
* Build dynamic navigation

---

## 4️⃣ `history` – Travel Back in Time 🕓

The `history` object lets you manipulate the browser’s session history (like the Back and Forward buttons).

```javascript
history.back();   // Go back one page
history.forward(); // Go forward
history.go(-2);    // Go two pages back
```

🧠 Use Cases:

* Custom navigation buttons
* SPA (Single Page App) navigation control

---

## 5️⃣ `screen` – User’s Display Info

Provides information about the user’s screen.

```javascript
console.log(screen.width);      // Full screen width
console.log(screen.availHeight); // Height excluding taskbar
```

🧠 Use Case:

* Adjust layout based on screen size (e.g., open popups properly)

---

## 6️⃣ Popups – `alert`, `confirm`, `prompt`

These are technically part of BOM via the `window` object.

```javascript
alert("Hello!");  // Simple alert box
const result = confirm("Are you sure?");  // OK/Cancel
const name = prompt("Enter your name:"); // User input
```

🧠 Use Cases:

* Quick alerts or confirmations
* Temporary user input collection

---

### ✨ Example: A Mini URL Tool Using BOM

```html
<!DOCTYPE html>
<html>
<head>
  <title>BOM Demo</title>
</head>
<body>
  <h2>BOM Demo</h2>
  <button onclick="showURLInfo()">Show URL Info</button>
  <script>
    function showURLInfo() {
      alert("Full URL: " + location.href);
      alert("Hostname: " + location.hostname);
      alert("Pathname: " + location.pathname);
    }
  </script>
</body>
</html>
```

Try this example, and see how BOM lets you access everything about the current page!

---

### 🚨 Security & Best Practices

* Avoid overusing `alert`, `prompt`, and `confirm`; they can be annoying to users.
* Do not trust browser properties like `userAgent` for secure detection—they can be faked.
* Redirects with `location.href` should be used carefully to avoid phishing or unintended navigation.

---

### 🧠 Quick Recap

| BOM Object                 | Purpose                          |
| -------------------------- | -------------------------------- |
| `window`                   | The global browser context       |
| `navigator`                | Info about browser/system        |
| `location`                 | Control and read page URL        |
| `history`                  | Navigate browser history         |
| `screen`                   | Info about user’s screen/display |
| `alert`/`prompt`/`confirm` | Interact with users              |

---

### 🧪 Practice Challenge

**Build a small app** that asks the user for their name (using `prompt`), confirms if they want to continue (using `confirm`), and then redirects them to a greeting page using `location.href`.

---
