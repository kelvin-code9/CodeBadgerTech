
### Page 1: Introduction to CSS

# Introduction to CSS

## What is CSS?

**CSS (Cascading Style Sheets)** is a stylesheet language used to describe the presentation of a document written in HTML or XML. CSS defines how elements should be rendered on screen, paper, in speech, or on other media. It is what brings life to your web pages by controlling the layout, colors, fonts, and overall appearance.

### Key Features of CSS

- **Separation of Content and Presentation**: CSS allows you to separate the structure (HTML) from the design (CSS) of a webpage, making it easier to maintain and update.
- **Reusability**: You can apply the same styles to multiple elements, saving time and effort.
- **Flexibility**: CSS offers a variety of ways to style elements, including setting colors, fonts, spacing, and positioning.
- **Responsiveness**: CSS enables you to create responsive designs that adapt to different screen sizes and devices.

### How CSS Works

CSS is a rule-based language, meaning you define rules specifying groups of styles that should be applied to particular elements or groups of elements on your web pages.

**Example of a CSS rule:**

```css
p {
    color: blue;
    font-size: 16px;
}
```

In this example, all `<p>` (paragraph) elements on the page will have blue text with a font size of 16 pixels.

---

# CSS Syntax

A CSS rule consists of a selector and a declaration block:

- **Selector**: Indicates which HTML elements the style should be applied to.
- **Declaration Block**: Contains one or more declarations separated by semicolons. Each declaration includes a CSS property name and a value, separated by a colon.

```css
selector {
    property: value;
    property: value;
}
```

Example:

```css
h1 {
    color: green;
    text-align: center;
}
```

In this example, all `<h1>` elements will have green text and be centered.

### Types of CSS

1. **Inline CSS**: Directly in the HTML element via the `style` attribute.
2. **Internal CSS**: Within a `<style>` element in the HTML `<head>`.
3. **External CSS**: In a separate `.css` file linked to the HTML document.

---

## Linking CSS to HTML

To link an external CSS file to your HTML document, use the following `<link>` tag in the `<head>` section of your HTML:

```html
<head>
    <link rel="stylesheet" href="styles.css">
</head>
```

Now that you have a basic understanding of CSS, let's move on to learning how to style elements on your web pages.

---

# Next: Styling Basics

### Page 2: Basic Styling with CSS


# Basic Styling with CSS

## Applying Basic Styles

Now that we know what CSS is and how to link it to our HTML, let’s dive into some basic styling techniques.

### 1. **Color**

CSS allows you to set the color of text and other elements using keywords, HEX codes, RGB, RGBA, HSL, or HSLA values.

- **Text Color**:

```css
p {
    color: #3498db; /* HEX code */
}

h1 {
    color: rgb(255, 99, 71); /* RGB value */
}
```

- **Background Color**:

```css
body {
    background-color: #f4f4f4;
}

div {
    background-color: rgba(0, 0, 0, 0.5); /* RGBA value with transparency */
}
```

### 2. **Fonts**

You can change the font type, size, and style using CSS.

- **Font Family**:

```css
body {
    font-family: Arial, sans-serif;
}

h1 {
    font-family: 'Courier New', monospace;
}
```

- **Font Size**:

```css
p {
    font-size: 18px;
}

h1 {
    font-size: 36px;
}
```

- **Font Style & Weight**:

```css
p {
    font-style: italic;
    font-weight: bold;
}
```

### 3. **Text Alignment**

You can align text using the `text-align` property.

```css
h1 {
    text-align: center;
}

p {
    text-align: justify;
}
```

### 4. **Margin and Padding**

Margins and padding are used to create space around elements.

- **Margin**: The space outside the element.
- **Padding**: The space inside the element, between the content and the border.

```css
div {
    margin: 20px;
    padding: 10px;
}
```

### 5. **Borders**

You can style borders around elements.

```css
div {
    border: 2px solid #333;
    border-radius: 10px;
}
```

### 6. **Width and Height**

You can control the dimensions of elements using `width` and `height` properties.

```css
img {
    width: 300px;
    height: auto; /* Maintains aspect ratio */
}
```

### 7. **Display and Visibility**

The `display` property controls the layout of elements.

```css
div {
    display: none; /* Hides the element */
}

span {
    display: inline; /* Displays as an inline element */
}

p {
    display: block; /* Displays as a block element */
}
```

---

## Conclusion

With these basic styling techniques, you can start customizing the appearance of your web pages. Experiment with different properties and values to see how they affect the layout and design.
