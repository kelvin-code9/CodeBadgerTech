# Understanding `<span>` and CSS Display Properties: `inline`, `inline-block`, `block`

## 1. **`<span>` Element**

- **Purpose**: The `<span>` element is an inline container used to wrap a portion of text or other inline elements. It does not have any semantic meaning by itself and is often used to apply styling or scripting to a specific part of content without disrupting the flow of text.
- **Behavior**: By default, `<span>` is displayed as an `inline` element, meaning it sits in the same line as text and other inline elements.
- **Use Case**: Typically used to style a portion of text differently or apply event handlers (like on click).

### Example:
```html
<p>This is a normal paragraph, but <span style="color: red;">this part is styled differently</span>.</p>
```
In this example, the `<span>` allows the red color to be applied to a specific part of the text without affecting the rest of the paragraph.

---

## 2. **CSS Display Properties**

### **`inline` (Default for `<span>`)**

- **Behavior**: The element appears on the same line as the surrounding text.
- **Size Control**: `width` and `height` are determined by the content inside, and cannot be manually adjusted.
- **No Line Break**: Does not start on a new line.
- **Common Elements**: `<span>`, `<a>`, `<strong>`.

### Example:
```html
<style>
    .inline-element {
        display: inline;
        background-color: yellow;
    }
</style>

<p>This is a <span class="inline-element">highlighted inline element</span> within a sentence.</p>
```
The `span` element here does not disrupt the flow of the paragraph.

---


### **`block`**

- **Behavior**: The element takes up the full width available and forces a new line before and after itself.
- **Size Control**: You can set the element's `width` and `height`.
- **New Line**: Each block element starts on a new line, taking up the full width of the container.
- **Common Use**: Used for structuring layout sections, such as `<div>`, `<h1>`, `<p>`.

### Example:
```html
<style>
    .block-element {
        display: block;
        width: 300px;
        height: 100px;
        background-color: lightgreen;
        margin-bottom: 10px;
    }
</style>

<div class="block-element">This is a block element.</div>
<div class="block-element">Another block element.</div>
```
Each block element starts on a new line and takes up the full width of the container.

---

### **`inline-block`**

- **Behavior**: The element still appears inline, but it can have block-like properties such as a specified `width` and `height`.
- **Size Control**: You can set the element's `width` and `height`, unlike a typical `inline` element.
- **No Line Break**: The element does not force a new line before or after itself.
- **Common Use**: Useful for creating elements like buttons or formatted boxes that need to align inline but have more control over layout.

### Example:
```html
<style>
    .inline-block-element {
        display: inline-block;
        width: 150px;
        height: 50px;
        background-color: lightblue;
        margin: 10px;
    }
</style>

<span class="inline-block-element">Box 1</span>
<span class="inline-block-element">Box 2</span>
<span class="inline-block-element">Box 3</span>
```
The `inline-block` elements sit next to each other but allow control over their size and layout.

---


## Summary of Differences

| Property        | `inline`                            | `inline-block`                          | `block`                                  |
|-----------------|-------------------------------------|-----------------------------------------|------------------------------------------|
| **Line Break**  | No                                  | No                                      | Yes                                      |
| **Size Control**| No control over `width` and `height`| Control over `width` and `height`       | Control over `width` and `height`        |
| **Use Case**    | Text and elements within paragraphs | Elements like buttons or boxes inline   | Layout elements that take up full width  |

---

By using `<span>` with different display properties, you can effectively control the layout and style of content inline or as a block.
