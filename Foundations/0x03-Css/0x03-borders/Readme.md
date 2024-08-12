# CSS Borders Cheat Sheet

CSS borders allow you to create visually distinct edges around HTML elements. Borders can be customized in various ways, including their width, style, color, and even by styling each side individually. This guide covers everything you need to know about using borders in CSS.

## Basic Border Properties

### 1. `border-width`
- **Description:** Sets the width of the border.
- **Values:**
  - `thin`, `medium`, `thick` (predefined values)
  - Specific width in units (`px`, `em`, `rem`, `%`, etc.)
  
  ```css
  border-width: 2px;
  ```

### 2. `border-style`
- **Description:** Sets the style of the border.
- **Values:**
  - `none`: No border
  - `solid`: Solid line
  - `dashed`: Dashed line
  - `dotted`: Dotted line
  - `double`: Two solid lines
  - `groove`: Carved into the page
  - `ridge`: Raised above the page
  - `inset`: Embedded look
  - `outset`: Pushed out look
  
  ```css
  border-style: solid;
  ```

### 3. `border-color`
- **Description:** Sets the color of the border.
- **Values:** Any valid color value (`color names`, `hex`, `rgb`, `rgba`, `hsl`, etc.)
  
  ```css
  border-color: #ff0000;
  ```

### 4. `border`
- **Description:** A shorthand property that sets the width, style, and color of the border in one line.
  
  ```css
  border: 2px solid #ff0000;
  ```

## Styling Individual Sides

You can style each side of a border individually using the following properties:

### 1. `border-top`
- **Description:** Sets the top border’s width, style, and color.
  
  ```css
  border-top: 2px dashed blue;
  ```

### 2. `border-right`
- **Description:** Sets the right border’s width, style, and color.
  
  ```css
  border-right: 4px solid green;
  ```

### 3. `border-bottom`
- **Description:** Sets the bottom border’s width, style, and color.
  
  ```css
  border-bottom: 3px double red;
  ```

### 4. `border-left`
- **Description:** Sets the left border’s width, style, and color.
  
  ```
  css
  border-left: 5px groove purple;
  ```

## Border Radius

### 1. `border-radius`
- **Description:** Rounds the corners of the border. You can specify one radius for all corners or individual values for each.
- **Values:**
  - Single value: All corners rounded equally.
  - Two values: First value applies to top-left/bottom-right, second to top-right/bottom-left.
  - Four values: Applies to top-left, top-right, bottom-right, and bottom-left respectively.
  
  ```css
  border-radius: 10px;
  border-radius: 10px 20px;
  border-radius: 10px 20px 30px 40px;
  ```
  
