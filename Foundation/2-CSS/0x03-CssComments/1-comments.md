# CSS Comments

CSS comments are useful for adding explanations or notes within your CSS code. Comments are ignored by the browser and do not affect the styling of a webpage.

## Syntax
CSS comments begin with `/*` and end with `*/`. Anything inside this block is not executed by the browser.

### Example:
```css
/* This is a CSS comment */
h1 {
    color: blue; /* This sets the text color to blue */
}
```

## Why Use CSS Comments?
1. **Improve Readability** – Helps explain sections of code for yourself and other developers.
2. **Temporarily Disable Styles** – Commenting out code is useful for debugging.
3. **Organize Code** – Helps structure large stylesheets.

### Example: Organizing CSS Code
```css
/* Reset default margins and paddings */
* {
    margin: 0;
    padding: 0;
}

/* Header styles */
h1 {
    font-size: 24px;
    color: darkblue;
}

/* Paragraph styles */
p {
    font-size: 16px;
    color: gray;
}
```

Using comments wisely keeps your CSS clean, structured, and easier to maintain.
