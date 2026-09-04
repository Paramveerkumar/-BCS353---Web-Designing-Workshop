# HTML Lists

HTML lists are used to **group related items together** in a structured and organized way.

For example, we can use lists to display:

* Programming languages
* Subjects
* Steps in an algorithm
* Features of a product
* Menu items

HTML provides **three main types of lists**:

1. **Unordered List** (`<ul>`)
2. **Ordered List** (`<ol>`)
3. **Description List** (`<dl>`)

---

# 1. Unordered HTML List

An **unordered list** displays items using bullets.

The unordered list starts with the `<ul>` tag, and each item is written using the `<li>` tag.

### Syntax

```html
<ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ul>
```

### Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>Unordered List</title>
</head>

<body>

    <h2>Programming Languages</h2>

    <ul>
        <li>C</li>
        <li>C++</li>
        <li>Java</li>
        <li>Python</li>
    </ul>

</body>
</html>
```

### Output

* C
* C++
* Java
* Python

---

## Types of Bullet Markers

The `list-style-type` CSS property can change the bullet style.

### 1. Disc

This is the default bullet style.

```html
<ul style="list-style-type: disc;">
    <li>C</li>
    <li>C++</li>
    <li>Python</li>
</ul>
```

### 2. Circle

```html
<ul style="list-style-type: circle;">
    <li>C</li>
    <li>C++</li>
    <li>Python</li>
</ul>
```

### 3. Square

```html
<ul style="list-style-type: square;">
    <li>C</li>
    <li>C++</li>
    <li>Python</li>
</ul>
```

### 4. No Marker

```html
<ul style="list-style-type: none;">
    <li>C</li>
    <li>C++</li>
    <li>Python</li>
</ul>
```

---

# 2. Ordered HTML List

An **ordered list** displays items in a specific order.

By default, the items are numbered.

The ordered list starts with the `<ol>` tag, and each item is written using the `<li>` tag.

### Syntax

```html
<ol>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ol>
```

### Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>Ordered List</title>
</head>

<body>

    <h2>Steps to Create a Web Page</h2>

    <ol>
        <li>Open a text editor</li>
        <li>Write HTML code</li>
        <li>Save the file with .html extension</li>
        <li>Open the file in a browser</li>
    </ol>

</body>
</html>
```

### Output

1. Open a text editor
2. Write HTML code
3. Save the file with `.html` extension
4. Open the file in a browser

---

## Types of Ordered Lists

The `type` attribute changes the numbering style.

| Type | Description             |
| ---- | ----------------------- |
| `1`  | Numbers (default)       |
| `A`  | Uppercase letters       |
| `a`  | Lowercase letters       |
| `I`  | Uppercase Roman numbers |
| `i`  | Lowercase Roman numbers |

---

### Numbers

```html
<ol type="1">
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ol>
```

Output:

1. HTML
2. CSS
3. JavaScript

---

### Uppercase Letters

```html
<ol type="A">
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ol>
```

Output:

A. HTML
B. CSS
C. JavaScript

---

### Lowercase Letters

```html
<ol type="a">
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ol>
```

Output:

a. HTML
b. CSS
c. JavaScript

---

### Uppercase Roman Numbers

```html
<ol type="I">
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ol>
```

Output:

I. HTML
II. CSS
III. JavaScript

---

### Lowercase Roman Numbers

```html
<ol type="i">
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ol>
```

Output:

i. HTML
ii. CSS
iii. JavaScript

---

# 3. Description List

A **description list** is used to display a list of terms along with their descriptions.

It uses three tags:

* `<dl>` — Defines the description list
* `<dt>` — Defines the term
* `<dd>` — Defines the description

### Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>Description List</title>
</head>

<body>

    <h2>Web Technologies</h2>

    <dl>
        <dt>HTML</dt>
        <dd>Used to create the structure of a web page.</dd>

        <dt>CSS</dt>
        <dd>Used to design and style a web page.</dd>

        <dt>JavaScript</dt>
        <dd>Used to add interactivity to a web page.</dd>
    </dl>

</body>
</html>
```

---

# 4. Nested HTML Lists

A **nested list** means placing one list inside another list.

### Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>Nested List</title>
</head>

<body>

    <h2>Programming Subjects</h2>

    <ul>
        <li>Programming Languages
            <ul>
                <li>C</li>
                <li>C++</li>
                <li>Java</li>
            </ul>
        </li>

        <li>Web Technologies
            <ul>
                <li>HTML</li>
                <li>CSS</li>
                <li>JavaScript</li>
            </ul>
        </li>
    </ul>

</body>
</html>
```

### Explanation

Here, the second `<ul>` is placed inside an `<li>` element.

This creates a **list inside another list**.

---

# 5. Horizontal List

Lists can also be displayed horizontally. This is commonly used to create a **navigation menu**.

### Example

```html
<!DOCTYPE html>
<html>
<head>

    <title>Horizontal List</title>

    <style>

        ul {
            list-style-type: none;
            margin: 0;
            padding: 0;
            overflow: hidden;
            background-color: black;
        }

        li {
            float: left;
        }

        li a {
            display: block;
            color: white;
            text-align: center;
            padding: 15px;
            text-decoration: none;
        }

        li a:hover {
            background-color: gray;
        }

    </style>

</head>

<body>

    <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Courses</a></li>
        <li><a href="#">Contact</a></li>
    </ul>

</body>
</html>
```

This creates a simple horizontal navigation menu.

---

# Important HTML List Tags

| Tag    | Purpose                           |
| ------ | --------------------------------- |
| `<ul>` | Defines an unordered list         |
| `<ol>` | Defines an ordered list           |
| `<li>` | Defines a list item               |
| `<dl>` | Defines a description list        |
| `<dt>` | Defines a term                    |
| `<dd>` | Defines the description of a term |

---

# Difference Between `<ul>` and `<ol>`

| Unordered List                   | Ordered List                                |
| -------------------------------- | ------------------------------------------- |
| Uses `<ul>`                      | Uses `<ol>`                                 |
| Items are displayed with bullets | Items are displayed with numbers or letters |
| Order is not important           | Order is important                          |

### Example

```html
<!-- Unordered List -->

<ul>
    <li>Mouse</li>
    <li>Keyboard</li>
    <li>Monitor</li>
</ul>


<!-- Ordered List -->

<ol>
    <li>Start Computer</li>
    <li>Open Browser</li>
    <li>Visit Website</li>
</ol>
```

---

# Chapter Summary

* Use `<ul>` to create an **unordered list**
* Use `<ol>` to create an **ordered list**
* Use `<li>` to define a **list item**
* Use `list-style-type` to change unordered list markers
* Use the `type` attribute to change ordered list numbering
* Use `<dl>` to create a **description list**
* Use `<dt>` to define a **term**
* Use `<dd>` to define the **description**
* Lists can be **nested**
* Lists can be styled with CSS to create **navigation menus**

---

# Practice Exercise

Create an HTML page containing:

### 1. An unordered list of four programming languages

### 2. An ordered list showing the steps to run an HTML program

### 3. A description list containing:

* HTML — Structure of a web page
* CSS — Styling of a web page
* JavaScript — Adds interactivity

### Expected Structure

```html
<h2>Programming Languages</h2>

<ul>
    <!-- Add languages here -->
</ul>


<h2>Steps to Run HTML</h2>

<ol>
    <!-- Add steps here -->
</ol>


<h2>Web Technologies</h2>

<dl>
    <!-- Add terms and descriptions here -->
</dl>
```

