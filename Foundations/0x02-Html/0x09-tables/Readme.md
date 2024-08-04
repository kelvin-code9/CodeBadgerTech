
# HTML Tables

## Introduction
HTML tables are used to organize data in rows and columns. Tables are defined with the `<table>` tag.

## Basic Table Structure
A basic HTML table consists of the following elements:
- `<table>`: Defines the table.
- `<thead>`: Groups the heading content.
- `<tbody>`: Groups the body content.
- `<tr>`: Defines a row in the table.
- `<th>`: Defines a heading cell in a table.
- `<td>`: Defines a standard cell in a table.

### Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>HTML Table Example</title>
</head>
<body>
    <table>
        <thead>
            <tr>
                <th>Name</th>
                <th>Age</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>John</td>
                <td>30</td>
            </tr>
            <tr>
                <td>Jane</td>
                <td>25</td>
            </tr>
        </tbody>
    </table>
</body>
</html>
```

### Explanation
- `<table>`: The container for the table.
- `<thead>`: Contains the heading row(s) of the table.
- `<tbody>`: Contains the body rows of the table.
- `<tr>`: Defines a table row.
- `<th>`: Defines a header cell; by default, it's bold and centered.
- `<td>`: Defines a standard cell.

## Adding Borders and Styling
You can use CSS to add borders and style the table.

### Example with CSS

```html
<!DOCTYPE html>
<html>
<head>
    <title>Styled HTML Table</title>
    <style>
        table, th, td {
            border: 1px solid black;
            border-collapse: collapse;
        }
        th, td {
            padding: 8px;
            text-align: left;
        }
    </style>
</head>
<body>
    <table>
        <thead>
            <tr>
                <th>Name</th>
                <th>Age</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>John</td>
                <td>30</td>
            </tr>
            <tr>
                <td>Jane</td>
                <td>25</td>
            </tr>
        </tbody>
    </table>
</body>
</html>
```

### Explanation
- `border: 1px solid black;`: Adds a 1-pixel solid black border to the table, header cells, and standard cells.
- `border-collapse: collapse;`: Ensures that the borders are not doubled.
- `padding: 8px;`: Adds padding inside the table cells.
- `text-align: left;`: Aligns the text to the left inside the table cells.

## Common Mistakes
1. **Missing Closing Tags**: Ensure all `<td>` and `<tr>` tags are properly closed.
2. **Using `<td>` for Headers**: Use `<th>` instead of `<td>` for header cells to provide semantic meaning and default styling.

### Example of a Common Mistake and Correction

#### Incorrect
```html
<tr>
    <td>John<td>
    <td>30</td> 
<tr>
```

#### Correct
```html
<tr>
    <td>John</td>
    <td>30</td>
</tr>
```

## Conclusion
HTML tables are a powerful way to display tabular data on a webpage. By understanding the basic structure and applying some CSS, you can create well-organized and visually appealing tables.
```
