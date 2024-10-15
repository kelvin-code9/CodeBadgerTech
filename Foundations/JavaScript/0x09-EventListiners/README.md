
### Lesson 2: **Event Handling**

#### **Introduction to Events**

Events are actions or occurrences that happen in the browser, which you can respond to. Common events include:

- Clicking a button
- Hovering over an image
- Pressing a key on the keyboard

You can use **event listeners** to handle these events and execute code when they occur.

---

#### **Adding Event Listeners**

JavaScript’s `addEventListener()` method lets you listen for specific events (like clicks or key presses) and define the code that should run when the event occurs.

**Syntax**:
```javascript
element.addEventListener('event', function);
```

Here, `element` is the DOM element you want to target, `event` is the type of event (like `'click'`), and `function` is the code you want to execute.

---

#### **Handling the Click Event**

Let’s focus on the **click event**—one of the most common. This event is triggered when a user clicks on an element, like a button.

##### **Example: Changing Background Color on Click**

**HTML:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Button Click Example</title>
</head>
<body>
    <button id="colorButton">Change Background Color</button>
    <script src="script.js"></script>
</body>
</html>
```

**JavaScript (script.js):**
```javascript
// Access the button by its ID
let button = document.getElementById('colorButton');

// Add a click event listener to the button
button.addEventListener('click', function() {
    // Change the background color of the page
    document.body.style.backgroundColor = 'lightblue';
});
```

**Explanation**: When the button is clicked, the background color of the page changes to light blue. This demonstrates how event listeners can make a webpage more interactive.

---

#### **Using the `this` Keyword in Event Handlers**

Inside an event handler, the `this` keyword refers to the element that received the event. This is useful when you want the event handler to affect the element that was clicked, or interacted with, without hardcoding its `id`.

##### **Example: Changing Button Text on Click**

**HTML:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>This Keyword Example</title>
</head>
<body>
    <button id="changeTextButton">Click Me</button>
    <script src="script.js"></script>
</body>
</html>
```

**JavaScript (script.js):**
```javascript
// Access the button by its ID
let button = document.getElementById('changeTextButton');

// Add a click event listener to the button
button.addEventListener('click', function() {
    // Use 'this' to refer to the clicked button
    this.textContent = 'You Clicked Me!';
});
```

**Explanation**: By using `this`, the text content of the button changes to "You Clicked Me!" when clicked. No need to re-select the button with `getElementById()`.

---

#### **Practice Questions:**

1. **Change Text on Button Click**:
   - Create a button that changes the text of a paragraph when clicked. Use `getElementById()` to access both the button and paragraph.

2. **Background Color Toggle**:
   - Create a button that toggles between two background colors each time it is clicked.

3. **Hide/Show Content**:
   - Add a button that hides and shows a div on the page when clicked, using event listeners and the `this` keyword.

