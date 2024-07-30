## HTML LIST

The elements below represent HTML Lists that
can be used to group a collection of items with
and/or without order.

### HTML Lists Elements
* ```<ul>``` : defines an unordered list where the order is meaningless and is typically bulleted

* ```<ol>```: defines an ordered list where the order is meaningful and is typically numbered

* ```<li>``` :a child element of both ```<ul>``` and
```<ol>``` elements that defines a list item

Example:

```
<!DOCTYPE html>
<html>
<head>
   <title> Try It Yourself </title>
</head>
<body>
   <!-- Unordered List -->
   <p> Fruits </p>
   <ul>
      <li> Apples </li>
      <li> Oranges </li>
      <li> Grapes </li>
   </ul>
   
   <!-- Ordered List -->
   <p> Fruits </p>
   <ol>
      <li> Apples </li>
      <li> Oranges </li>
      <li> Grapes </li>
   </ol>
</body>
</html>
```

## List Style Type
The appearance of list items can be customized using the list-style-type CSS property. This property defines the type of marker (such as bullets or numbers) that will be used for the list items.

Common Values for list-style-type
```
disc: The default bullet for unordered lists.
circle: An open circle bullet for unordered lists.
square: A square bullet for unordered lists.
decimal: The default numbering for ordered lists (1, 2, 3, ...).
decimal-leading-zero: Numbers with leading zeros (01, 02, 03, ...).
lower-alpha: Lowercase alphabetic characters (a, b, c, ...).
upper-alpha: Uppercase alphabetic characters (A, B, C, ...).
lower-roman: Lowercase Roman numerals (i, ii, iii, ...).
upper-roman: Uppercase Roman numerals (I, II, III, ...).
none: No marker is displayed.
```

```
<!DOCTYPE html>
<html>
<head>
   <title>List Style Example</title>
</head>
<body>
   <!-- Unordered List with square bullets -->
   <p>Fruits</p>
   <ul style="list-style-type: square;">
      <li>Apples</li>
      <li>Oranges</li>
      <li>Grapes</li>
   </ul>
   
   <!-- Ordered List with uppercase Roman numerals -->
   <p>Fruits</p>
   <ol style="list-style-type: upper-roman;">
      <li>Apples</li>
      <li>Oranges</li>
      <li>Grapes</li>
   </ol>
</body>
</html>
```
