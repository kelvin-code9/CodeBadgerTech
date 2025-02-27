# HTML Tables


HTML tables allow you to organize data into rows and columns on a webpage, making it easier to display structured information like schedules, statistics, or records.

## What is an HTML Table?
An HTML table is created using the `<table>` tag. Inside the table, you use:

- `<tr>` to define table rows.
- `<th>` for table headers.
- `<td>` for table data cells.

Each `<tr>` represents a row, and within each row, `<th>` or `<td>` elements define the cells. These cells can contain text, images, lists, or even another table.

---
## HTML Table Example
```html
<!DOCTYPE html>
<html>
<body>
    <table>
        <tr>
            <th>Firstname</th>
            <th>Lastname</th>
            <th>Age</th>
        </tr>
        <tr>
            <td>Priya</td>
            <td>Sharma</td>
            <td>24</td>
        </tr>
        <tr>
            <td>Arun</td>
            <td>Singh</td>
            <td>32</td>
        </tr>
        <tr>
            <td>Sam</td>
            <td>Watson</td>
            <td>41</td>
        </tr>
    </table>
</body>
</html>
```
### Output:
A simple table displaying names and ages.

<!DOCTYPE html>
<html>
<body>
    <table>
        <tr>
            <th>Firstname</th>
            <th>Lastname</th>
            <th>Age</th>
        </tr>
        <tr>
            <td>Priya</td>
            <td>Sharma</td>
            <td>24</td>
        </tr>
        <tr>
            <td>Arun</td>
            <td>Singh</td>
            <td>32</td>
        </tr>
        <tr>
            <td>Sam</td>
            <td>Watson</td>
            <td>41</td>
        </tr>
    </table>
</body>
</html>

### Explanation:
- `<table>`: Defines the table structure.
- `<tr>`: Represents a row.
- `<th>`: Defines a header cell, which is bold and centered by default.
- `<td>`: Defines a standard data cell.

The first `<tr>` contains three `<th>` elements, setting up column titles. The following `<tr>` elements contain `<td>` elements representing the data.

When rendered in a browser, this table will have four rows (one header row and three data rows) and three columns.

---
## Common HTML Table Tags
| **HTML Tag** | **Description** |
|-------------|----------------|
| `<table>` | Defines a table. |
| `<tr>` | Defines a row. |
| `<th>` | Defines a header cell. |
| `<td>` | Defines a standard cell. |
| `<caption>` | Adds a title to the table. |
| `<thead>` | Groups header content. |
| `<tbody>` | Groups main content. |
| `<tfoot>` | Groups footer content. |
| `<col>` | Defines column properties. |
| `<colgroup>` | Groups multiple columns. |

---
## Another Example of an HTML Table
```html
<!DOCTYPE html>
<html>
<body>
    <table>
        <tr>
            <th>Book Name</th>
            <th>Author</th>
            <th>Genre</th>
        </tr>
        <tr>
            <td>The Book Thief</td>
            <td>Markus Zusak</td>
            <td>Historical Fiction</td>
        </tr>
        <tr>
            <td>The Cruel Prince</td>
            <td>Holly Black</td>
            <td>Fantasy</td>
        </tr>
        <tr>
            <td>The Silent Patient</td>
            <td>Alex Michaelides</td>
            <td>Psychological Fiction</td>
        </tr>
    </table>
</body>
</html>
```

### Output:
A table displaying book names, authors, and genres.

<!DOCTYPE html>
<html>
<body>
    <table>
        <tr>
            <th>Book Name</th>
            <th>Author</th>
            <th>Genre</th>
        </tr>
        <tr>
            <td>The Book Thief</td>
            <td>Markus Zusak</td>
            <td>Historical Fiction</td>
        </tr>
        <tr>
            <td>The Cruel Prince</td>
            <td>Holly Black</td>
            <td>Fantasy</td>
        </tr>
        <tr>
            <td>The Silent Patient</td>
            <td>Alex Michaelides</td>
            <td>Psychological Fiction</td>
        </tr>
    </table>
</body>
</html>

---
## Styling HTML Tables with CSS
Styling tables can improve their appearance and readability. You can use CSS to add borders, background colors, spacing, and alignment.

### 1. Adding a Border to a Table
```css
table, th, td {
    border: 1px solid blue;
}
```
#### Example:
```html
<!DOCTYPE html>
<html>
<head>
    <style>
        table, th, td {
            border: 1px solid blue;
        }
    </style>
</head>
<body>
    <table>
        <tr>
            <th>Firstname</th>
            <th>Lastname</th>
            <th>Age</th>
        </tr>
        <tr>
            <td>Priya</td>
            <td>Sharma</td>
            <td>24</td>
        </tr>
    </table>
</body>
</html>
```
![image](https://github.com/user-attachments/assets/ed9d6c75-13ad-45ea-b3f3-88b367269b6a)


---


---

### Summary of other Table Techniques

| Technique | Code | Description |
|-----------|------|-------------|
| **Cell Padding** | `th, td { padding: 20px; }` | Adds space between content and cell border. |
| **Align Headings Left** | `th { text-align: left; }` | Aligns table headers to the left. |
| **Border Spacing** | `table { border-spacing: 5px; }` | Controls space between table cells. |
| **Column Merging (`colspan`)** | `<th colspan="2">Telephone</th>` | Merges two or more columns. |
| **Row Merging (`rowspan`)** | `<th rowspan="2">Telephone</th>` | Merges two or more rows. |
| **Table Caption** | `<caption>DETAILS</caption>` | Adds a caption to a table. |
| **Background Color** | `table#t01 { background-color: #f2f2d1; }` | Changes the table background color. |
| **Nested Tables** | `<table> <tr> <td>Outer</td> <td><table>...</table></td> </tr> </table>` | Embeds one table inside another. |

This guide covers the basics of HTML tables and styling techniques to make them visually appealing and structured properly. 🚀

---


### 10. Creating Nested Tables
```html
<!DOCTYPE html>
<html>
<head>
    <style>
        table, th, td {
            border: 1px solid blue;
        }
    </style>
</head>
<body>
    <table border="1">
        <tr>
            <td>Outer Table</td>
            <td>
                <table border="1">
                    <tr>
                        <td>Inner Table Row 1</td>
                    </tr>
                    <tr>
                        <td>Inner Table Row 2</td>
                    </tr>
                </table>
            </td>
        </tr>
    </table>
</body>
</html>

```
### Output:
A table inside another table.

![image](https://github.com/user-attachments/assets/88ee0a09-370b-4a6e-88ce-60e429f2c4cc)

---


