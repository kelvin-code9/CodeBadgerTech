

# HTML Tags: The Basics

HTML Tags are fundamental elements used to structure and format content on web pages. They provide instructions to web browsers on how to display text, images, links, and other media.

## Table of Contents

1. [What Are HTML Tags?](#what-are-html-tags)
2. [HTML Tag Structure](#html-tag-structure)
3. [Self-Closing Tags](#self-closing-tags)
4. [Popular HTML Tags and Their Uses](#popular-html-tags-and-their-uses)
5. [Key Points to Remember](#key-points-to-remember)

---

## What Are HTML Tags?

HTML tags are enclosed in **angle brackets** (`< >`) and usually come in **pairs**: an **opening tag** and a **closing tag**.

- The **opening tag** marks the start of an element.
- The **closing tag** marks the end of that element.

### Example of a Pair of Tags:

- **`<p>`** is the opening tag for a paragraph.
- **`</p>`** is the closing tag.

Here’s a full example:

```html
<p>This is a paragraph of text.</p>
```

In the above code, the `<p>` tag opens the paragraph, and the `</p>` tag closes it.

---

## HTML Tag Structure

Most HTML tags have a **pair structure**, meaning they consist of two tags:

- **Opening tag**: Begins the element (e.g., `<p>`).
- **Closing tag**: Ends the element (e.g., `</p>`).

### Self-Closing Tags

Some HTML tags don’t require a closing tag. These are called **self-closing** tags. For example, the `<img>` tag is used to display images, and it doesn’t need a closing tag.

Example:

```html
<img src="image.jpg" alt="A sample image">
```

Here, `<img>` is a self-closing tag used to insert an image into the webpage.

---

## Popular HTML Tags and Their Uses

| **HTML Tag** | **Purpose**                                                                 |
|--------------|-----------------------------------------------------------------------------|
| `<html>`     | Defines the root element of the HTML document.                             |
| `<head>`     | Contains meta-information about the webpage (e.g., title, styles).         |
| `<title>`    | Specifies the title of the webpage, displayed in the browser’s title bar.  |
| `<body>`     | Contains the visible content of the webpage.                               |
| `<h1>` to `<h6>` | Headings used to define titles, with `<h1>` being the largest and `<h6>` the smallest. |
| `<p>`        | Defines a paragraph of text.                                                |
| `<a>`        | Defines a hyperlink (link to another page or resource).                    |
| `<img>`      | Embeds an image in the page (self-closing).                                 |
| `<ul>`       | Defines an unordered (bulleted) list.                                       |
| `<ol>`       | Defines an ordered (numbered) list.                                         |
| `<li>`       | Defines a list item within an ordered or unordered list.                    |
| `<br>`       | Inserts a line break (self-closing).                                        |
| `<div>`      | Defines a generic container for content (used for layout and styling).      |
| `<span>`     | A generic inline container used for styling parts of the content.           |

---

## Key Points to Remember

1. Tags are used to define elements like headings, paragraphs, links, images, etc.
2. Most tags come in pairs: an opening tag and a closing tag.
3. Some tags are self-closing, meaning they don’t need a closing tag (like `<img>` for images).
4. Tags are enclosed in angle brackets (`< >`).

---