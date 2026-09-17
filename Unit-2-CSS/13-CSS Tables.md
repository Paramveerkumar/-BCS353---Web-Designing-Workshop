# 📊 CSS Tables

<p align="center">
  <img src="https://img.shields.io/badge/CSS-Tables-1572B6?style=for-the-badge&logo=css3&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Learn how to design and style HTML tables using CSS.
</p>

---

## 1. 🔍 What is a Table?

An **HTML table** is used to display information in **rows and columns**.

For example, a student marks table:

```text
┌────────────┬──────────┬───────┐
│ Name       │ Subject  │ Marks │
├────────────┼──────────┼───────┤
│ Rahul      │ C        │ 85    │
│ Priya      │ C        │ 92    │
│ Aman       │ C        │ 78    │
└────────────┴──────────┴───────┘
```

HTML creates the table structure, while **CSS controls its appearance**.

---

# 2. 🧩 Basic HTML Table

A table uses:

| Tag       | Purpose                |
| --------- | ---------------------- |
| `<table>` | Creates the table      |
| `<tr>`    | Creates a table row    |
| `<th>`    | Creates a heading cell |
| `<td>`    | Creates a data cell    |

### Example

```html id="7q9r5d"
<table>
    <tr>
        <th>Name</th>
        <th>Course</th>
        <th>Marks</th>
    </tr>

    <tr>
        <td>Rahul</td>
        <td>C</td>
        <td>85</td>
    </tr>

    <tr>
        <td>Priya</td>
        <td>C++</td>
        <td>92</td>
    </tr>
</table>
```

---

# 3. 🎨 Why Use CSS with Tables?

A default HTML table is very basic.

CSS can be used to:

* Add borders
* Change colors
* Add spacing
* Align text
* Add padding
* Highlight rows
* Create hover effects
* Control table width
* Make tables responsive

---

# 4. 🟦 Adding Borders

The `border` property adds a border around table elements.

```css id="gq1d7k"
table, th, td {
    border: 1px solid black;
}
```

### HTML

```html id="q0sp8e"
<table>
    <tr>
        <th>Name</th>
        <th>Marks</th>
    </tr>

    <tr>
        <td>Rahul</td>
        <td>85</td>
    </tr>
</table>
```

### Output

```text id="x2iqx3"
┌──────────┬───────┐
│ Name     │ Marks │
├──────────┼───────┤
│ Rahul    │ 85    │
└──────────┴───────┘
```

---

# 5. 🔗 `border-collapse`

By default, table borders may appear as separate borders.

Use:

```css id="j4a6uh"
border-collapse: collapse;
```

### Example

```css id="p8z6hx"
table {
    border-collapse: collapse;
}

table, th, td {
    border: 1px solid black;
}
```

### Without `border-collapse`

```text
┌───────┐ ┌───────┐
│ Name  │ │ Marks │
└───────┘ └───────┘
```

### With `border-collapse: collapse`

```text
┌────────┬───────┐
│ Name   │ Marks │
└────────┴───────┘
```

> ⭐ **`border-collapse: collapse` is commonly used for clean-looking tables.**

---

# 6. 📏 Table Width

Use the `width` property.

```css id="x8u4em"
table {
    width: 100%;
}
```

This makes the table occupy the available width of its containing area.

You can also use:

```css id="j8j4hz"
table {
    width: 600px;
}
```

---

# 7. 📦 Table Cell Padding

`padding` creates space **inside a cell**.

```css id="5m4zws"
th, td {
    padding: 12px;
}
```

### Without padding

```text
┌───────┐
│Name   │
└───────┘
```

### With padding

```text
┌───────────────┐
│    Name       │
└───────────────┘
```

> 💡 **Padding makes table content easier to read.**

---

# 8. ↔️ Text Alignment

The `text-align` property controls horizontal alignment.

```css id="oq5xjt"
th, td {
    text-align: left;
}
```

Other values:

```css id="f6j8xr"
text-align: left;
text-align: center;
text-align: right;
```

### Example

```css id="0w6ef4"
th {
    text-align: center;
}

td {
    text-align: left;
}
```

---

# 9. ↕️ Vertical Alignment

Use the `vertical-align` property.

Common values:

```text id="7utv9r"
top
middle
bottom
```

Example:

```css id="u9o5i3"
td {
    vertical-align: middle;
}
```

This controls the position of content vertically inside a table cell.

---

# 10. 🎨 Table Header Styling

The `<th>` element can be styled separately.

```css id="0z5q7q"
th {
    background-color: #333;
    color: white;
    padding: 12px;
}
```

Example:

```text id="2w1g0n"
┌────────────┬─────────┐
│    NAME    │  MARKS  │  ← Header
├────────────┼─────────┤
│ Rahul      │ 85      │
│ Priya      │ 92      │
└────────────┴─────────┘
```

---

# 11. 🟦 Table Row Background

We can add a background color to rows.

```css id="v1qk2h"
tr {
    background-color: #f2f2f2;
}
```

---

# 12. 🦓 Zebra Striped Table

A **zebra-striped table** uses alternating row colors.

This makes large tables easier to read.

Use the `:nth-child()` pseudo-class.

```css id="5t5f7p"
tr:nth-child(even) {
    background-color: #f2f2f2;
}
```

### Example

```text id="x2b0pj"
┌────────┬───────┐
│ Name   │ Marks │
├────────┼───────┤
│ Rahul  │ 85    │
├────────┼───────┤
│ Priya  │ 92    │
├────────┼───────┤
│ Aman   │ 78    │
└────────┴───────┘
```

The even-numbered rows receive a different background.

---

# 13. 🖱️ Table Hover Effect

We can highlight a row when the mouse moves over it.

```css id="n2cg9e"
tr:hover {
    background-color: #ddd;
}
```

### Concept

```text id="7qf7p4"
Normal:
Rahul    85
Priya    92
Aman     78

Mouse over:
──────────────
Priya    92   ← Highlighted
──────────────
```

---

# 14. 🎨 Complete Styled Table

```html id="c8k8jw"
<!DOCTYPE html>
<html>

<head>

    <title>CSS Table</title>

    <style>

        table {
            width: 100%;
            border-collapse: collapse;
        }

        th, td {
            border: 1px solid #333;
            padding: 12px;
            text-align: center;
        }

        th {
            background-color: #333;
            color: white;
        }

        tr:nth-child(even) {
            background-color: #f2f2f2;
        }

        tr:hover {
            background-color: #ddd;
        }

    </style>

</head>

<body>

    <h2>Student Marks</h2>

    <table>

        <tr>
            <th>Name</th>
            <th>Subject</th>
            <th>Marks</th>
        </tr>

        <tr>
            <td>Rahul</td>
            <td>C</td>
            <td>85</td>
        </tr>

        <tr>
            <td>Priya</td>
            <td>C++</td>
            <td>92</td>
        </tr>

        <tr>
            <td>Aman</td>
            <td>Java</td>
            <td>78</td>
        </tr>

    </table>

</body>

</html>
```

---

# 15. 🔲 Table Border Spacing

The `border-spacing` property controls the space between table cells when the table uses separate borders.

```css id="g3zjqe"
table {
    border-spacing: 10px;
}
```

Example:

```text id="4p2fls"
┌──────┐   ┌──────┐
│ Name │   │ Marks│
└──────┘   └──────┘
     ↑
  10px space
```

> ⚠️ `border-spacing` is relevant when borders are separated. If you use `border-collapse: collapse`, the spacing between cell borders is collapsed.

---

# 16. 📐 Table Layout

The `table-layout` property controls how the browser calculates column widths.

Two common values are:

```css id="s8d3tq"
table-layout: auto;
table-layout: fixed;
```

### `auto`

The browser automatically adjusts column widths based on content.

```css
table {
    table-layout: auto;
}
```

### `fixed`

Column widths can be controlled more predictably.

```css
table {
    width: 100%;
    table-layout: fixed;
}
```

---

# 17. 📱 Responsive Tables

Large tables may not fit on small screens.

A common technique is to place the table inside a container with horizontal scrolling.

### HTML

```html id="7n2v0f"
<div class="table-container">

    <table>
        ...
    </table>

</div>
```

### CSS

```css id="2frh5x"
.table-container {
    overflow-x: auto;
}
```

Now users can scroll horizontally when necessary.

### Concept

```text id="q4yk4v"
Desktop
┌───────────────────────────────┐
│ Full Table                    │
└───────────────────────────────┘

Mobile
┌──────────────────┐
│ Table → → →      │
└──────────────────┘
       ↔ Scroll
```

---

# 18. 🎯 Styling Specific Columns

CSS can target specific table columns using selectors such as `:nth-child()`.

Example:

```css id="p0xq3r"
td:nth-child(2) {
    text-align: center;
}
```

This targets the **second cell of each table row**.

Example:

```text id="r0t3sa"
Name        Marks
Rahul       85
Priya       92
```

The second column can be centered.

---

# 19. 🔗 Combining HTML and CSS

Remember:

```text id="s6x9q1"
HTML
  ↓
Creates table structure
  ↓
<table>
<tr>
<th>
<td>

CSS
  ↓
Styles the table
  ↓
Border
Color
Spacing
Alignment
Hover
```

### Simple Rule

> **HTML = Structure**
> **CSS = Presentation**

---

# 20. 📊 Important CSS Table Properties

| Property           | Purpose                           |
| ------------------ | --------------------------------- |
| `border`           | Adds a border                     |
| `border-collapse`  | Combines cell borders             |
| `border-spacing`   | Controls space between cells      |
| `width`            | Sets table width                  |
| `padding`          | Adds space inside cells           |
| `text-align`       | Horizontal alignment              |
| `vertical-align`   | Vertical alignment                |
| `background-color` | Sets background color             |
| `color`            | Sets text color                   |
| `table-layout`     | Controls column layout            |
| `overflow-x`       | Helps create horizontal scrolling |

---

# 21. 🧠 Common Table Selectors

### Table

```css
table {
    width: 100%;
}
```

### Header

```css
th {
    background-color: #333;
}
```

### Data Cells

```css
td {
    padding: 10px;
}
```

### All Rows

```css
tr {
    border-bottom: 1px solid #ddd;
}
```

### Even Rows

```css
tr:nth-child(even) {
    background-color: #f2f2f2;
}
```

### Hover

```css
tr:hover {
    background-color: #ddd;
}
```

---

# 22. 📝 Practice Questions

### Basic

1. What is an HTML table?
2. What is the purpose of `<table>`?
3. What is the difference between `<th>` and `<td>`?
4. What does `border-collapse` do?
5. What is the purpose of `padding` in a table?
6. What does `text-align` do?
7. What is `vertical-align`?
8. What is a zebra-striped table?
9. What does `tr:hover` do?
10. What is the purpose of `overflow-x: auto`?

### Practical

11. Create a student marks table with 5 students.
12. Add borders to the table.
13. Change the header background color.
14. Add padding to every cell.
15. Create a zebra-striped table.
16. Add a hover effect to table rows.
17. Center-align the marks column.
18. Create a responsive table.
19. Create a college timetable using HTML and CSS.
20. Create an employee salary table using CSS.

---

# ⚡ Quick Revision

```text id="g6o7x4"
                  CSS TABLES
                       │
        ┌──────────────┼──────────────┐
        ↓              ↓              ↓
     Borders         Spacing       Colors
        │              │              │
     border          padding      background
     collapse        margin          color
        │
        ↓
     Alignment
        │
   ┌────┴─────┐
   ↓          ↓
text-align  vertical-align
```

### ⭐ Most Important Properties

```css id="7pm8g6"
border
border-collapse
border-spacing
width
padding
text-align
vertical-align
background-color
table-layout
```

### ⭐ Common Effects

```css id="12y0k8"
tr:nth-child(even) {
    background-color: #f2f2f2;
}

tr:hover {
    background-color: #ddd;
}
```

### ⭐ Responsive Table

```css id="w7v6x8"
.table-container {
    overflow-x: auto;
}
```

> 💡 **HTML creates the table structure, while CSS makes the table attractive, readable, and responsive.**

> 🎯 **Remember:** `border` → `padding` → `alignment` → `color` → `hover`

---

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-1572B6?style=for-the-badge">
</p>

<p align="center">
  <b>🎓 Learn • Practice • Design • Build</b>
</p>

