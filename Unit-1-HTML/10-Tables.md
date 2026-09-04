# 📊 HTML Tables

## 📚 Introduction

HTML tables are used to organize and display data in the form of **rows and columns**.

Tables are useful when we want to present structured information clearly.

For example:

* Student information
* Marksheets
* Timetables
* Employee details
* Product catalogues
* Book lists

---

# 🤔 What is an HTML Table?

An HTML table is a collection of:

* **Rows**
* **Columns**
* **Cells**

For example:

| Student Name | Course | Marks |
| ------------ | ------ | ----: |
| राहुल        | B.Tech |    85 |
| Priya        | B.Tech |    90 |
| Amit         | B.Tech |    78 |

In HTML, tables are created using the `<table>` element.

---

# 🧩 Basic Structure of an HTML Table

The basic structure is:

```html
<table>
    <tr>
        <th>Heading 1</th>
        <th>Heading 2</th>
    </tr>

    <tr>
        <td>Data 1</td>
        <td>Data 2</td>
    </tr>
</table>
```

---

# 🔑 Important HTML Table Tags

| Tag         | Meaning      | Purpose                   |
| ----------- | ------------ | ------------------------- |
| `<table>`   | Table        | Creates a table           |
| `<tr>`      | Table Row    | Creates a row             |
| `<th>`      | Table Header | Creates a heading cell    |
| `<td>`      | Table Data   | Creates a data cell       |
| `<caption>` | Caption      | Adds a title to the table |

---

# 1️⃣ The `<table>` Element

The `<table>` element is used to create an HTML table.

### Example

```html
<table>
    <!-- Table content goes here -->
</table>
```

Everything related to the table is placed inside the `<table>` and `</table>` tags.

---

# 2️⃣ Table Rows – `<tr>`

The `<tr>` tag is used to create a **table row**.

`tr` stands for:

> **Table Row**

### Example

```html
<table>
    <tr>
        <td>Rahul</td>
        <td>Computer Science</td>
    </tr>
</table>
```

This creates one row containing two cells.

---

# 3️⃣ Table Data – `<td>`

The `<td>` tag is used to create a normal data cell.

`td` stands for:

> **Table Data**

### Example

```html
<table>
    <tr>
        <td>Rahul</td>
        <td>85</td>
        <td>A</td>
    </tr>
</table>
```

Output:

| Student | Marks | Grade |
| ------- | ----: | ----- |
| Rahul   |    85 | A     |

---

# 4️⃣ Table Headers – `<th>`

The `<th>` tag is used to create a **header cell**.

`th` stands for:

> **Table Header**

Headers usually describe the information in each column.

### Example

```html
<table>
    <tr>
        <th>Name</th>
        <th>Course</th>
        <th>Marks</th>
    </tr>

    <tr>
        <td>Rahul</td>
        <td>B.Tech</td>
        <td>85</td>
    </tr>
</table>
```

By default, `<th>` text is generally displayed **bold and centered** by browsers.

---

# 🎓 Complete Example: Student Information Table

```html
<!DOCTYPE html>
<html>

<head>
    <title>Student Information</title>
</head>

<body>

    <h1>Student Information</h1>

    <table border="1">

        <tr>
            <th>Roll Number</th>
            <th>Name</th>
            <th>Course</th>
            <th>Marks</th>
        </tr>

        <tr>
            <td>101</td>
            <td>Rahul</td>
            <td>B.Tech</td>
            <td>85</td>
        </tr>

        <tr>
            <td>102</td>
            <td>Priya</td>
            <td>B.Tech</td>
            <td>90</td>
        </tr>

        <tr>
            <td>103</td>
            <td>Amit</td>
            <td>B.Tech</td>
            <td>78</td>
        </tr>

    </table>

</body>

</html>
```

---

# 🧠 Understanding the Table Structure

Consider the following structure:

```text
<table>
    │
    ├── <tr>  → First Row
    │      ├── <th>
    │      ├── <th>
    │      └── <th>
    │
    ├── <tr>  → Second Row
    │      ├── <td>
    │      ├── <td>
    │      └── <td>
    │
    └── <tr>  → Third Row
           ├── <td>
           ├── <td>
           └── <td>
```

Remember:

> **`<table>` contains rows, and rows contain cells.**

---

# 📌 Table Caption

The `<caption>` element is used to provide a title for a table.

### Example

```html
<table border="1">

    <caption>
        Student Marks
    </caption>

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

Output:

**Student Marks**

| Name  | Marks |
| ----- | ----: |
| Rahul |    85 |

---

# 📚 Example: College Timetable

```html
<!DOCTYPE html>
<html>

<head>
    <title>College Timetable</title>
</head>

<body>

    <h1>Weekly Timetable</h1>

    <table border="1">

        <tr>
            <th>Day</th>
            <th>9:00 - 10:00</th>
            <th>10:00 - 11:00</th>
            <th>11:00 - 12:00</th>
        </tr>

        <tr>
            <td>Monday</td>
            <td>Web Designing</td>
            <td>Programming</td>
            <td>Database</td>
        </tr>

        <tr>
            <td>Tuesday</td>
            <td>HTML</td>
            <td>CSS</td>
            <td>JavaScript</td>
        </tr>

    </table>

</body>

</html>
```

---

# 📖 Example: Online Book Store

Tables are very useful in your **Online Book Store Experiment**.

```html
<!DOCTYPE html>
<html>

<head>
    <title>Online Book Store</title>
</head>

<body>

    <h1>Book Catalogue</h1>

    <table border="1">

        <tr>
            <th>Book Name</th>
            <th>Author</th>
            <th>Price</th>
        </tr>

        <tr>
            <td>HTML Basics</td>
            <td>John Smith</td>
            <td>₹350</td>
        </tr>

        <tr>
            <td>Learning CSS</td>
            <td>David Lee</td>
            <td>₹450</td>
        </tr>

        <tr>
            <td>JavaScript Fundamentals</td>
            <td>Alex Brown</td>
            <td>₹550</td>
        </tr>

    </table>

</body>

</html>
```

---

# 🖼️ Table Cells Can Contain Other HTML Elements

A table cell can contain more than just text.

It can contain:

* Images
* Links
* Lists
* Buttons
* Forms
* Other HTML elements

### Example

```html
<table border="1">

    <tr>
        <th>Book</th>
        <th>Action</th>
    </tr>

    <tr>
        <td>
            <img src="images/book.jpg"
                 alt="Book Cover"
                 width="100">
        </td>

        <td>
            <a href="details.html">
                View Details
            </a>
        </td>
    </tr>

</table>
```

---

# ⚠️ Important Rule

Normally, the number of cells in each row should match the number of columns.

For example:

```html
<tr>
    <td>Name</td>
    <td>Course</td>
    <td>Marks</td>
</tr>
```

This row contains **3 cells**.

Another row should normally also contain **3 cells**.

```html
<tr>
    <td>Rahul</td>
    <td>B.Tech</td>
    <td>85</td>
</tr>
```

---

# 🏗️ Modern Table Structure

For larger tables, HTML provides additional elements to organize the table.

```text
<table>
    │
    ├── <caption>
    │
    ├── <thead>
    │       └── Header Section
    │
    ├── <tbody>
    │       └── Main Data
    │
    └── <tfoot>
            └── Footer Information
</table>
```

---

# 🔹 `<thead>`

The `<thead>` element groups the header content of a table.

```html
<thead>
    <tr>
        <th>Name</th>
        <th>Marks</th>
    </tr>
</thead>
```

---

# 🔹 `<tbody>`

The `<tbody>` element groups the main data of the table.

```html
<tbody>

    <tr>
        <td>Rahul</td>
        <td>85</td>
    </tr>

    <tr>
        <td>Priya</td>
        <td>90</td>
    </tr>

</tbody>
```

---

# 🔹 `<tfoot>`

The `<tfoot>` element groups footer information.

```html
<tfoot>
    <tr>
        <td>Total Students</td>
        <td>2</td>
    </tr>
</tfoot>
```

---

# ⭐ Complete Structured Table Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>Student Marks</title>
</head>

<body>

    <table border="1">

        <caption>
            Student Marks Report
        </caption>

        <thead>
            <tr>
                <th>Name</th>
                <th>Subject</th>
                <th>Marks</th>
            </tr>
        </thead>

        <tbody>

            <tr>
                <td>Rahul</td>
                <td>Web Designing</td>
                <td>85</td>
            </tr>

            <tr>
                <td>Priya</td>
                <td>Web Designing</td>
                <td>90</td>
            </tr>

        </tbody>

        <tfoot>

            <tr>
                <td colspan="2">
                    Total Students
                </td>

                <td>2</td>
            </tr>

        </tfoot>

    </table>

</body>

</html>
```

---

# 🎯 Chapter Summary

After completing this topic, students should understand:

* ✅ HTML tables organize data into rows and columns.
* ✅ `<table>` creates a table.
* ✅ `<tr>` creates a table row.
* ✅ `<th>` creates a table header.
* ✅ `<td>` creates a table data cell.
* ✅ `<caption>` provides a table title.
* ✅ `<thead>` groups header content.
* ✅ `<tbody>` groups the main table data.
* ✅ `<tfoot>` groups footer content.
* ✅ Table cells can contain text, images, links, buttons, and other HTML elements.

---

# 🧠 Quick Revision

```text
HTML TABLE
    │
    ▼
<table>
    │
    ├── <caption> → Table Title
    │
    ├── <tr> → Table Row
    │       │
    │       ├── <th> → Header Cell
    │       │
    │       └── <td> → Data Cell
    │
    ├── <thead> → Header Section
    ├── <tbody> → Main Data
    └── <tfoot> → Footer
```

---

# 🧪 Practice Tasks

### Task 1

Create a table showing:

* Roll Number
* Student Name
* Course
* Marks

---

### Task 2

Create a weekly college timetable using an HTML table.

---

### Task 3

Create a **Book Catalogue Table** containing:

* Book Image
* Book Name
* Author
* Publisher
* Price
* Add to Cart Button

---

# ❓ Viva Questions

1. What is an HTML table?
2. Which tag is used to create a table?
3. What does `<tr>` stand for?
4. What does `<td>` stand for?
5. What does `<th>` stand for?
6. What is the difference between `<th>` and `<td>`?
7. Which tag is used to add a caption to a table?
8. What is the purpose of `<thead>`?
9. What is the purpose of `<tbody>`?
10. What is the purpose of `<tfoot>`?
11. Can an HTML table cell contain an image?
12. Can an HTML table cell contain a hyperlink?

---

# ⭐ Remember

> **`<table>` creates the table.**

> **`<tr>` creates a row.**

> **`<th>` creates a heading cell.**

> **`<td>` creates a data cell.**

```html
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

