### Module 6: The Document Object Model (DOM)

---

### Lesson 1: **Introduction to the DOM**

#### What is the DOM?

The **Document Object Model (DOM)** is a structured representation of an HTML document. Think of it as a tree of nodes, where each node represents an element (like a `<div>`, `<p>`, or `<button>`), attribute, or text. With JavaScript, you can use the DOM to manipulate the structure, content, and styles of a webpage dynamically. This means we can **create interactive and dynamic web pages** that respond to user actions in real-time.

**Key Points:**
- DOM represents your HTML as a structured tree.
- Each HTML element becomes a node in this tree.
- Using JavaScript, you can access, change, and delete these nodes.
  
#### **Accessing Elements in the DOM**

Before we can modify anything on a webpage, we need to **access the elements** in the DOM. There are a few key methods for this:

1. **`getElementById()`** – This method is used to access an element by its unique `id`.
2. **`querySelector()`** – Allows you to select elements using CSS selectors (e.g., classes, tags).
3. **`getElementsByClassName()`** – Selects all elements with a particular class name.
4. **`getElementsByTagName()`** – Selects all elements of a specific type (e.g., all `<div>` elements).

But for this lesson, we’ll focus mainly on **`getElementById()`**, one of the simplest and most commonly used methods.

---

### **Detailed Explanation of `getElementById()`**

#### **What is `getElementById()`?**

The `getElementById()` method allows you to retrieve an element by its unique `id` attribute from the DOM. The `id` must be unique within a document, which ensures that you’re always working with a **single element** when using this method.

**Syntax**:
```javascript
document.getElementById('elementId');
```

Here, `'elementId'` is the `id` of the HTML element you want to manipulate.

#### **How to Use `getElementById()`**

Let’s walk through some common uses of `getElementById()` in detail:

---

##### **Example 1: Changing Text Content**

**Objective:** Modify the text inside an element, like a heading or paragraph, using JavaScript.

**HTML:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Change Text Example</title>
</head>
<body>
    <h1 id="heading">Hello, World!</h1>
    <script src="script.js"></script>
</body>
</html>
```

**JavaScript (script.js):**
```javascript
// Access the element by its ID
let heading = document.getElementById('heading');

// Change the text content of the element
heading.textContent = 'Hello, JavaScript!';
```

**Explanation**: When the page loads, JavaScript will find the `<h1>` element by its `id` (`heading`) and change its text to "Hello, JavaScript!". This is super useful for dynamically updating content on the page.

---

##### **Example 2: Changing Element Style**

**Objective:** Use `getElementById()` to alter the styles of an element dynamically.

**HTML:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Change Style Example</title>
</head>
<body>
    <p id="paragraph">This is a paragraph.</p>
    <script src="script.js"></script>
</body>
</html>
```

**JavaScript (script.js):**
```javascript
// Access the element by its ID
let paragraph = document.getElementById('paragraph');

// Change the style of the element
paragraph.style.color = 'blue';
paragraph.style.fontSize = '20px';
paragraph.style.backgroundColor = 'lightgray';
```

**Explanation**: By accessing the element, we can modify multiple CSS properties such as `color`, `fontSize`, and `backgroundColor`. This is perfect for making style changes based on user interaction.

---

##### **Example 3: Hiding/Showing an Element**

**Objective:** Toggle the visibility of an element by changing its `display` property.

**HTML:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Toggle Visibility Example</title>
</head>
<body>
    <div id="content">Here is some content!</div>
    <button id="toggleButton">Hide/Show Content</button>
    <script src="script.js"></script>
</body>
</html>
```

**JavaScript (script.js):**
```javascript
// Access the button and the content div by their IDs
let content = document.getElementById('content');
let button = document.getElementById('toggleButton');

// Add a click event listener to the button
button.addEventListener('click', function() {
    if (content.style.display === 'none') {
        content.style.display = 'block'; // Show the content
    } else {
        content.style.display = 'none'; // Hide the content
    }
});
```

**Explanation**: When the button is clicked, it toggles the visibility of the content. If the content is visible, it hides it, and vice versa.

---

#### **Practice Questions:**

1. **Basic Text Change**:
   - Create an HTML page with a `<p>` element and use `getElementById()` to change the text content when the page loads.
   
2. **Style Change**:
   - Create an HTML page with a paragraph and use `getElementById()` to modify the font color and background color.

3. **Visibility Toggle**:
   - Create a button that shows or hides a specific `<div>` on the page when clicked.

---
