
# HTML Basics: `<div>`, Classes, and IDs

## 1. Introduction to `<div>`

### What is a `<div>`?
- The `<div>` element is a block-level container that is used to group and style sections of HTML.

### Basic Syntax
```html
<div>
  <!-- Content goes here -->
</div>
```

### Example
```html
<div>
  <p>This is a paragraph inside a div.</p>
</div>
```

## 2. Using Classes

### What is a Class?
- A class is an attribute that can be applied to any HTML element to define its styling or behavior in CSS and JavaScript.
- Classes can be reused on multiple elements.

### Basic Syntax
```html
<div class="my-class">
  <!-- Content goes here -->
</div>
```

### Example
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .highlight {
      background-color: yellow;
    }
  </style>
</head>
<body>
  <div class="highlight">
    <p>This div has a yellow background.</p>
  </div>
  <div class="highlight">
    <p>This div also has a yellow background.</p>
  </div>
</body>
</html>
```

## 3. Using IDs

### What is an ID?
- An ID is an attribute that uniquely identifies a single element on the page.
- IDs should be unique within a document, meaning no two elements should have the same ID.

### Basic Syntax
```html
<div id="unique-id">
  <!-- Content goes here -->
</div>
```

### Example
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    #main {
      color: blue;
    }
  </style>
</head>
<body>
  <div id="main">
    <p>This div has blue text.</p>
  </div>
</body>
</html>
```

## 4. Combining Classes and IDs

### Example
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .container {
      border: 1px solid black;
      padding: 10px;
    }
    #header {
      font-size: 24px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <div class="container" id="header">
    <p>This div is styled with both a class and an ID.</p>
  </div>
  <div class="container">
    <p>This div is styled with a class only.</p>
  </div>
</body>
</html>
```

## 5. Practical Example: Styling a Page Layout

### Example
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .container {
      width: 80%;
      margin: auto;
    }
    #header {
      background-color: lightblue;
      padding: 20px;
      text-align: center;
    }
    .content {
      background-color: lightgray;
      padding: 20px;
      margin: 20px 0;
    }
    #footer {
      background-color: lightblue;
      padding: 10px;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="container" id="header">
    <h1>My Website</h1>
  </div>
  <div class="container content">
    <p>This is the main content area.</p>
  </div>
  <div class="container" id="footer">
    <p>Footer information goes here.</p>
  </div>
</body>
</html>
```

## 6. Summary

- **`<div>`**: A versatile container for grouping elements.
- **Classes**: Use for reusable styles across multiple elements.
- **IDs**: Use for unique styling or behavior for a single element.

---

This outline provides a step-by-step guide to introducing `<div>`, classes, and IDs in HTML, complete with examples to illustrate each concept
