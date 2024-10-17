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

Great! Let's move on to **`querySelector()`**, which is another very useful method in the DOM that allows for more flexibility in selecting elements. Here's a breakdown of how it works.

---

### Lesson 2: **`querySelector()` and `querySelectorAll()`**

#### What is `querySelector()`?

The **`querySelector()`** method allows you to select **the first element** that matches a specified CSS selector. This gives you a lot of flexibility because you can select elements by `id`, `class`, tag name, or even more complex CSS selectors like attribute selectors, pseudo-classes, etc.

- **`querySelector()`**: Selects the **first** element that matches the CSS selector.
- **`querySelectorAll()`**: Selects **all** elements that match the CSS selector and returns a NodeList (which can be looped through).

#### **Syntax**:
```javascript
document.querySelector('CSS selector');
```

Here, `'CSS selector'` refers to any valid CSS selector, such as `#id`, `.class`, or `tag`.

---

### **Examples of Using `querySelector()`**

##### **Example 1: Selecting by Class**

**Objective**: Select an element by its class using `querySelector()`.

**HTML**:
```html
<!DOCTYPE html>
<html>
<head>
    <title>Select by Class Example</title>
</head>
<body>
    <p class="myClass">This is a paragraph with a class.</p>
    <script src="script.js"></script>
</body>
</html>
```

**JavaScript (script.js)**:
```javascript
// Select the first element with class "myClass"
let paragraph = document.querySelector('.myClass');

// Change its text content
paragraph.textContent = 'Text has been changed using querySelector!';
```

**Explanation**: The `querySelector('.myClass')` selects the first element with the class `myClass`, and then we change its content using `textContent`.

---

##### **Example 2: Selecting by Tag Name**

**Objective**: Select an element by its tag name.

**HTML**:
```html
<!DOCTYPE html>
<html>
<head>
    <title>Select by Tag Example</title>
</head>
<body>
    <h1>This is a heading</h1>
    <script src="script.js"></script>
</body>
</html>
```

**JavaScript (script.js)**:
```javascript
// Select the first <h1> tag
let heading = document.querySelector('h1');

// Change the heading color
heading.style.color = 'red';
```

**Explanation**: The `querySelector('h1')` selects the first `<h1>` tag and changes its color to red.

---

##### **Example 3: Selecting by ID (Alternative to `getElementById()`)**

**Objective**: Select an element by its `id` using `querySelector()`.

**HTML**:
```html
<!DOCTYPE html>
<html>
<head>
    <title>Select by ID Example</title>
</head>
<body>
    <div id="uniqueDiv">This is a div with an ID.</div>
    <script src="script.js"></script>
</body>
</html>
```

**JavaScript (script.js)**:
```javascript
// Select the element with ID "uniqueDiv"
let divElement = document.querySelector('#uniqueDiv');

// Change its background color
divElement.style.backgroundColor = 'yellow';
```

**Explanation**: While `getElementById()` can be used to select by ID, you can also use `querySelector('#id')` to achieve the same result, selecting the element with `id="uniqueDiv"`.

---

##### **Example 4: Selecting by Attribute**

**Objective**: Select an element using an attribute selector.

**HTML**:
```html
<!DOCTYPE html>
<html>
<head>
    <title>Select by Attribute Example</title>
</head>
<body>
    <input type="text" name="username" value="John">
    <script src="script.js"></script>
</body>
</html>
```

**JavaScript (script.js)**:
```javascript
// Select the input element with a "name" attribute of "username"
let inputElement = document.querySelector('input[name="username"]');

// Change the value of the input field
inputElement.value = 'Jane';
```

**Explanation**: The `querySelector('input[name="username"]')` selects the `<input>` element with the `name="username"` attribute and changes its value to "Jane".

---

### **`querySelectorAll()` – Selecting Multiple Elements**

If you want to select **all** elements that match a selector (not just the first one), you can use `querySelectorAll()`. This returns a **NodeList** (similar to an array) that you can loop through.

##### **Example 5: Selecting Multiple Elements**

**Objective**: Select all `<p>` elements and change their content.

**HTML**:
```html
<!DOCTYPE html>
<html>
<head>
    <title>Select Multiple Elements Example</title>
</head>
<body>
    <p>This is the first paragraph.</p>
    <p>This is the second paragraph.</p>
    <p>This is the third paragraph.</p>
    <script src="script.js"></script>
</body>
</html>
```

**JavaScript (script.js)**:
```javascript
// Select all <p> elements
let paragraphs = document.querySelectorAll('p');

// Loop through the NodeList and change the text content of each <p>
paragraphs.forEach((p, index) => {
    p.textContent = `This is paragraph ${index + 1}`;
});
```

**Explanation**: `querySelectorAll('p')` selects all `<p>` elements on the page. Then, using `forEach()`, we loop through each element and update its content.

---

#### **Key Differences Between `querySelector()` and `querySelectorAll()`**:
- **`querySelector()`**: Returns the **first matching element**.
- **`querySelectorAll()`**: Returns **all matching elements** as a NodeList, which you can loop through.

---

### **Practice Questions:**

1. **Basic Class Selection**:
   - Create an HTML page with multiple paragraphs and use `querySelector()` to select a specific paragraph by its class and change its color.

2. **Multiple Element Selection**:
   - Use `querySelectorAll()` to select all `<div>` elements on the page and change their background color.

3. **Selecting by Attribute**:
   - Create an HTML form with different `input` fields. Use `querySelector()` to select an input by its `name` attribute and change its value.

---

This should give you a strong understanding of how to use `querySelector()` and `querySelectorAll()` to access elements on a webpage!
