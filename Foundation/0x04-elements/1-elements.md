

# HTML Elements

HTML elements are fundamental to creating webpages. In this guide, we will focus on a few important elements: **`<h1>` to `<h6>`** for headings and the **`<p>`** element for paragraphs.

## Table of Contents

1. [What Are HTML Elements?](#what-are-html-elements)
2. [Headings: `<h1>` to `<h6>`](#headings-h1-to-h6)
3. [Paragraphs: `<p>`](#paragraphs-p)
4. [Key Points to Remember](#key-points-to-remember)

---

## What Are HTML Elements?

HTML elements are used to structure and define content on a webpage. They are typically composed of:

- **Start tag**: Opens the element (e.g., `<h1>`).
- **Content**: The content the tag applies to (e.g., text).
- **End tag**: Closes the element (e.g., `</h1>`).

Some elements, like `<img>`, are self-closing and don't need an end tag.

---

## Headings: `<h1>` to `<h6>`

Headings are used to define titles or sections of a webpage. HTML has six levels of headings, `<h1>` being the largest and `<h6>` the smallest. Headings help organize the content on a page and give structure to the information.

### Example of `<h1>` to `<h6>`:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Heading Example</title>
  </head>
  <body>
    <h1>This is a Heading Level 1</h1>
    <h2>This is a Heading Level 2</h2>
    <h3>This is a Heading Level 3</h3>
    <h4>This is a Heading Level 4</h4>
    <h5>This is a Heading Level 5</h5>
    <h6>This is a Heading Level 6</h6>
  </body>
</html>
```

### Expected Output:

- **`<h1>`**: This is the largest heading, often used for the main title of the page.
- **`<h2>` to `<h6>`**: Each subsequent heading (`<h2>`, `<h3>`, etc.) is smaller than the previous one, with `<h6>` being the smallest.

When viewed in a browser, the headings will appear in different sizes, with `<h1>` being the most prominent and `<h6>` the smallest.
<img src="../images/elementh1.png" alt="Expected output of heading levels">

---

## Paragraphs: `<p>`

The `<p>` tag is used to define paragraphs of text. It is one of the most commonly used tags in HTML to display text content in a structured way.

### Example of `<p>`:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Paragraph Example</title>
  </head>
  <body>
    <p>This is the first paragraph. It introduces the content of the webpage.</p>
    <p>This is the second paragraph. Paragraphs are separated by a space and help organize text.</p>
  </body>
</html>
```

### Expected Output:

- The text inside the `<p>` tags will be displayed as paragraphs, with a line break before each new paragraph.
- Browsers automatically add space between paragraphs, making the content easier to read.

**Result in the browser**:

> This is the first paragraph. It introduces the content of the webpage.

> This is the second paragraph. Paragraphs are separated by a space and help organize text.

---

## Key Points to Remember

1. **HTML elements** are the building blocks of webpages. They define how content is structured and displayed.
2. **Headings (`<h1>` to `<h6>`)** are used to define titles and headings of varying importance, with `<h1>` being the largest and `<h6>` the smallest.
3. **Paragraphs (`<p>`)** are used to display blocks of text, and they help organize content into readable chunks.
4. Each of these elements must be placed within the proper HTML structure, which includes the `<!DOCTYPE html>`, `<html>`, `<head>`, and `<body>` tags.

---