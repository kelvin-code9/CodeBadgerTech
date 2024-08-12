# CSS `box-shadow` Property Cheat Sheet

The `box-shadow` property in CSS is used to add shadows to elements, creating a depth effect that can make them stand out visually. This property allows you to control the size, color, and blur of the shadow, as well as its position relative to the element.

## Basic Syntax

```css
box-shadow: [horizontal offset] [vertical offset] [blur radius] [spread radius] [color];
```

### Example:
```css
box-shadow: 5px 10px 15px 0px rgba(0, 0, 0, 0.5);
```

## Parameters

### 1. **Horizontal Offset (`h-offset`)**
- **Description:** Defines the shadow’s horizontal position.
- **Values:**
  - Positive value: Moves the shadow to the right.
  - Negative value: Moves the shadow to the left.

  ```css
  box-shadow: 10px 0 0 0 black; /* Shadow to the right */
  box-shadow: -10px 0 0 0 black; /* Shadow to the left */
  ```

### 2. **Vertical Offset (`v-offset`)**
- **Description:** Defines the shadow’s vertical position.
- **Values:**
  - Positive value: Moves the shadow down.
  - Negative value: Moves the shadow up.

  ```css
  box-shadow: 0 10px 0 0 black; /* Shadow below */
  box-shadow: 0 -10px 0 0 black; /* Shadow above */
  ```

### 3. **Blur Radius**
- **Description:** Controls the blur of the shadow. The higher the value, the more blurred the shadow will be.
- **Values:**
  - Positive value: Blurs the shadow.
  - Zero value: Sharp shadow edges (no blur).
  
  ```css
  box-shadow: 0 0 15px 0 black; /* Blurry shadow */
  box-shadow: 0 0 0 0 black; /* Sharp shadow */
  ```

### 4. **Spread Radius**
- **Description:** Determines the size of the shadow.
- **Values:**
  - Positive value: Expands the shadow.
  - Negative value: Shrinks the shadow.
  
  ```css
  box-shadow: 0 0 10px 5px black; /* Larger shadow */
  box-shadow: 0 0 10px -5px black; /* Smaller shadow */
  ```

### 5. **Shadow Color**
- **Description:** Defines the color of the shadow. You can use any valid CSS color value (`color names`, `hex`, `rgb`, `rgba`, `hsl`, etc.).
  
  ```css
  box-shadow: 5px 10px 10px 0px rgba(0, 0, 0, 0.5); /* Semi-transparent black */
  box-shadow: 5px 10px 10px 0px red; /* Red shadow */
  ```

## Inset Shadows

### **`inset` Keyword**
- **Description:** By default, shadows are applied outside the element. Using the `inset` keyword moves the shadow inside the element, giving it a recessed effect.
  
  ```css
  box-shadow: inset 5px 5px 10px rgba(0, 0, 0, 0.5);
  ```

### Example:
```css
box-shadow: inset 5px 5px 10px 0px rgba(0, 0, 0, 0.5);
```

## Conclusion

The `box-shadow` property is a versatile tool for adding depth and dimension to your web designs. Whether you're creating subtle shadows to lift elements off the page or dramatic inset shadows for a recessed look, mastering `box-shadow` opens up many creative possibilities in CSS.
