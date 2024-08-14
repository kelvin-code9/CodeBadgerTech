# CSS Text Properties Cheat Sheet

CSS provides a variety of properties to style and manipulate text. These properties control the appearance of text, including its size, color, spacing, alignment, decoration, and more. This guide covers all the essential text-related properties in CSS.

## 1. **`color`**
- **Description:** Sets the color of the text.
- **Values:** Any valid CSS color value (`color names`, `hex`, `rgb`, `rgba`, `hsl`, etc.).
  
  ```css
  color: #ff6347; /* Tomato color */
  ```

## 2. **`font-family`**
- **Description:** Specifies the font for the text. Multiple font names can be provided as a "fallback" system.
- **Values:** Font name(s) separated by commas. Common fonts include `Arial`, `Verdana`, `Georgia`, `Times New Roman`.
  
  ```css
  font-family: 'Arial', sans-serif;
  ```

## 3. **`font-size`**
- **Description:** Sets the size of the text.
- **Values:** Can be specified in units like `px`, `em`, `rem`, `%`, `vw`, or using keywords like `small`, `large`, `x-large`.
  
  ```css
  font-size: 16px;
  ```

## 4. **`font-weight`**
- **Description:** Sets the weight (thickness) of the text.
- **Values:** Can be a numeric value (`100` to `900`), or keywords like `normal`, `bold`, `bolder`, `lighter`.
  
  ```css
  font-weight: bold;
  ```

## 5. **`font-style`**
- **Description:** Defines whether the text is italicized.
- **Values:** `normal`, `italic`, `oblique`.
  
  ```css
  font-style: italic;
  ```

## 6. **`text-align`**
- **Description:** Specifies the horizontal alignment of the text within its container.
- **Values:** `left`, `right`, `center`, `justify`.
  
  ```css
  text-align: center;
  ```

## 7. **`text-decoration`**
- **Description:** Adds decorations like underlines, overlines, or strike-throughs to text.
- **Values:** `none`, `underline`, `overline`, `line-through`, `blink`.
  
  ```css
  text-decoration: underline;
  ```

## 8. **`text-transform`**
- **Description:** Controls the capitalization of text.
- **Values:** `none`, `capitalize`, `uppercase`, `lowercase`.
  
  ```css
  text-transform: uppercase;
  ```

## 9. **`line-height`**
- **Description:** Sets the height between lines of text (leading).
- **Values:** Can be a number, length, or percentage. The value is relative to the font size.
  
  ```css
  line-height: 1.5;
  ```

## 10. **`letter-spacing`**
- **Description:** Controls the space between characters in the text (tracking).
- **Values:** Length values (`px`, `em`, etc.).
  
  ```css
  letter-spacing: 2px;
  ```

## 11. **`word-spacing`**
- **Description:** Controls the space between words in the text.
- **Values:** Length values (`px`, `em`, etc.).
  
  ```css
  word-spacing: 4px;
  ```

## 12. **`text-indent`**
- **Description:** Indents the first line of text in a block.
- **Values:** Length values (`px`, `em`, etc.), or percentages.
  
  ```css
  text-indent: 50px;
  ```

## 13. **`white-space`**
- **Description:** Controls how white space inside an element is handled.
- **Values:** `normal`, `nowrap`, `pre`, `pre-wrap`, `pre-line`.
  
  ```css
  white-space: nowrap;
  ```

## 14. **`text-shadow`**
- **Description:** Adds shadow to the text. You can specify multiple shadows by separating them with commas.
- **Values:**
  - **`h-offset`**: Horizontal offset of the shadow.
  - **`v-offset`**: Vertical offset of the shadow.
  - **`blur-radius`** (optional): The blur radius of the shadow.
  - **`color`**: The color of the shadow.
  
  ```css
  text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.3);
  ```

### Example:
```css
text-shadow: 2px 2px 2px #888888;
```

## 15. **`direction`**
- **Description:** Sets the text direction.
- **Values:** `ltr` (left-to-right), `rtl` (right-to-left).
  
  ```css
  direction: rtl;
  ```

## 16. **`text-overflow`**
- **Description:** Specifies how overflowed content that is not displayed should be signaled to the user.
- **Values:** `clip`, `ellipsis`.
  
  ```css
  text-overflow: ellipsis;
  ```

## 17. **`font-variant`**
- **Description:** Controls the use of alternate glyphs.
- **Values:** `normal`, `small-caps`.
  
  ```css
  font-variant: small-caps;
  ```

## 18. **`font-stretch`**
- **Description:** Selects a normal, condensed, or expanded face from a font.
- **Values:** `normal`, `condensed`, `expanded`, `extra-condensed`, `semi-condensed`, `semi-expanded`, `extra-expanded`.
  
  ```css
  font-stretch: expanded;
  ```

## Combining Properties: Shorthand Syntax

### `font`
- **Description:** A shorthand for setting all font-related properties in one declaration.
  
  ```css
  font: italic small-caps bold 16px/1.5 'Arial', sans-serif;
  ```

## Conclusion

CSS offers a wide range of properties to style text in any way you desire. By mastering these properties, you can create beautifully formatted and visually appealing text that enhances the user experience on your website.
