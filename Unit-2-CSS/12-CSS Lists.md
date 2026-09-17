# 📋 CSS Lists

<p align="center">
  <img src="https://img.shields.io/badge/CSS-Lists-1572B6?style=for-the-badge&logo=css3&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Learn how to style HTML lists using CSS.
</p>

---

## 1. 🔍 What is a List?

A **list** is used to display a group of related items in an organized way.

### Example

```text
• C Programming
• Data Structures
• DBMS
• Operating Systems
```

HTML provides three common types of lists:

| List             | HTML Tag | Purpose                    |
| ---------------- | -------- | -------------------------- |
| Unordered List   | `<ul>`   | Items with bullets         |
| Ordered List     | `<ol>`   | Items with numbers/letters |
| Description List | `<dl>`   | Terms and descriptions     |

---

# 2. 🔵 Unordered List

An unordered list displays items using **bullets**.

### HTML

```html
<ul>
    <li>C Programming</li>
    <li>Data Structures</li>
    <li>DBMS</li>
</ul>
```

### Output

```text
• C Programming
• Data Structures
• DBMS
```

---

# 3. 🔢 Ordered List

An ordered list displays items using **numbers or letters**.

```html
<ol>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ol>
```

### Output

```text
1. HTML
2. CSS
3. JavaScript
```

---

# 4. 🎨 CSS List Properties

CSS provides several properties to style lists.

The important properties are:

```text
list-style-type
list-style-image
list-style-position
list-style
```

---

# 5. 🔵 `list-style-type`

The `list-style-type` property specifies the **type of marker** used for list items.

## For Unordered Lists

Common values:

| Value    | Marker    |
| -------- | --------- |
| `disc`   | ●         |
| `circle` | ○         |
| `square` | ■         |
| `none`   | No marker |

### Example

```css
ul {
    list-style-type: square;
}
```

HTML:

```html
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
```

Output:

```text
■ HTML
■ CSS
■ JavaScript
```

---

# 6. ⚪ Circle List

```css
ul {
    list-style-type: circle;
}
```

Output:

```text
○ HTML
○ CSS
○ JavaScript
```

---

# 7. 🚫 Remove List Markers

Use:

```css
list-style-type: none;
```

Example:

```css
ul {
    list-style-type: none;
}
```

Output:

```text
HTML
CSS
JavaScript
```

This is commonly used when creating **navigation bars**.

---

# 8. 🔢 Ordered List Styles

Ordered lists support different marker types.

| Value                  | Example    |
| ---------------------- | ---------- |
| `decimal`              | 1, 2, 3    |
| `decimal-leading-zero` | 01, 02, 03 |
| `lower-alpha`          | a, b, c    |
| `upper-alpha`          | A, B, C    |
| `lower-roman`          | i, ii, iii |
| `upper-roman`          | I, II, III |
| `none`                 | No marker  |

### Example

```css
ol {
    list-style-type: upper-roman;
}
```

Output:

```text
I. HTML
II. CSS
III. JavaScript
```

---

# 9. 🖼️ `list-style-image`

The `list-style-image` property allows us to use an **image as the list marker**.

### Example

```css
ul {
    list-style-image: url("bullet.png");
}
```

HTML:

```html
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
```

Instead of a normal bullet, an image is displayed.

### Concept

```text
🖼️ HTML
🖼️ CSS
🖼️ JavaScript
```

> For modern websites, CSS pseudo-elements or icon libraries are often more flexible than using an image as a list marker.

---

# 10. 📍 `list-style-position`

The `list-style-position` property specifies where the list marker is placed.

It has two common values:

```text
inside
outside
```

---

## `outside`

This is the default.

```css
ul {
    list-style-position: outside;
}
```

Concept:

```text
●  HTML
   CSS
   JavaScript
```

The marker is outside the main content area.

---

## `inside`

```css
ul {
    list-style-position: inside;
}
```

Concept:

```text
● HTML
● CSS
● JavaScript
```

The marker becomes part of the list item's content area.

---

# 11. 🧩 `list-style` Shorthand

Instead of writing multiple properties separately, we can use the shorthand property:

```css
list-style
```

Example:

```css
ul {
    list-style: square inside;
}
```

This combines:

```css
list-style-type: square;
list-style-position: inside;
```

---

# 12. 📦 Styling List Items

We can style `<li>` elements like other HTML elements.

```css
li {
    color: blue;
    font-size: 18px;
    margin: 10px;
}
```

HTML:

```html
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
```

---

# 13. 🎨 Changing List Color

```css
li {
    color: green;
}
```

Output:

```text
● HTML
● CSS
● JavaScript
```

All list content becomes green.

---

# 14. 📏 Adding Spacing

We can use `margin` and `padding`.

```css
li {
    margin-bottom: 10px;
}
```

This creates space between list items.

### Example

```css
ul {
    padding-left: 30px;
}

li {
    margin-bottom: 10px;
}
```

---

# 15. 🧭 Lists as Navigation Bars

One of the most important real-world uses of CSS lists is creating **navigation menus**.

### HTML

```html
<ul class="menu">
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Courses</a></li>
    <li><a href="#">Contact</a></li>
</ul>
```

### CSS

```css
.menu {
    list-style-type: none;
    margin: 0;
    padding: 0;
}

.menu li {
    display: inline;
    margin-right: 20px;
}

.menu a {
    text-decoration: none;
    color: black;
}
```

### Output

```text
Home    About    Courses    Contact
```

---

# 16. 🧭 Horizontal Navigation Bar

A more complete example:

```html
<!DOCTYPE html>
<html>

<head>

    <title>Navigation Menu</title>

    <style>

        ul {
            list-style-type: none;
            margin: 0;
            padding: 15px;
            background-color: #333;
        }

        li {
            display: inline;
            margin-right: 25px;
        }

        li a {
            color: white;
            text-decoration: none;
            font-size: 18px;
        }

        li a:hover {
            color: yellow;
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

### Output concept

```text
┌─────────────────────────────────────────────┐
│ Home    About    Courses    Contact         │
└─────────────────────────────────────────────┘
```

---

# 17. 🪜 Nested Lists

A list can contain another list.

### HTML

```html
<ul>
    <li>
        Programming
        <ul>
            <li>C</li>
            <li>C++</li>
            <li>Java</li>
        </ul>
    </li>

    <li>
        Web Development
        <ul>
            <li>HTML</li>
            <li>CSS</li>
            <li>JavaScript</li>
        </ul>
    </li>
</ul>
```

### Output

```text
● Programming
    ○ C
    ○ C++
    ○ Java

● Web Development
    ○ HTML
    ○ CSS
    ○ JavaScript
```

---

# 18. 🎯 Different Styles for Nested Lists

CSS can give different markers to different levels.

```css
ul {
    list-style-type: square;
}

ul ul {
    list-style-type: circle;
}
```

Output:

```text
■ Programming
    ○ C
    ○ C++
    ○ Java
```

---

# 19. 🛒 Real-World Example: Shopping List

### HTML

```html
<ul class="shopping">
    <li>Laptop</li>
    <li>Mouse</li>
    <li>Keyboard</li>
    <li>Headphones</li>
</ul>
```

### CSS

```css
.shopping {
    list-style-type: none;
    padding: 0;
}

.shopping li {
    background-color: #f2f2f2;
    padding: 12px;
    margin-bottom: 5px;
}
```

### Output

```text
┌──────────────────┐
│ Laptop           │
├──────────────────┤
│ Mouse            │
├──────────────────┤
│ Keyboard         │
├──────────────────┤
│ Headphones       │
└──────────────────┘
```

---

# 20. ✨ Complete Example

```html
<!DOCTYPE html>
<html>

<head>

    <title>CSS Lists</title>

    <style>

        body {
            font-family: Arial, sans-serif;
        }

        h2 {
            color: #333;
        }

        ul {
            list-style-type: square;
            padding-left: 30px;
        }

        li {
            margin-bottom: 10px;
            font-size: 18px;
        }

        li:hover {
            color: blue;
        }

    </style>

</head>

<body>

    <h2>Web Development Technologies</h2>

    <ul>
        <li>HTML</li>
        <li>CSS</li>
        <li>JavaScript</li>
        <li>Bootstrap</li>
    </ul>

</body>

</html>
```

---

# 21. 📊 CSS List Properties Summary

| Property              | Purpose                              |
| --------------------- | ------------------------------------ |
| `list-style-type`     | Changes the marker type              |
| `list-style-image`    | Uses an image as marker              |
| `list-style-position` | Controls marker position             |
| `list-style`          | Shorthand property                   |
| `padding`             | Controls spacing around list content |
| `margin`              | Controls outside spacing             |

---

# 22. 🧠 Common List Marker Types

### Unordered List

```text
disc       → ●
circle     → ○
square     → ■
none       → no marker
```

### Ordered List

```text
decimal              → 1, 2, 3
lower-alpha          → a, b, c
upper-alpha          → A, B, C
lower-roman          → i, ii, iii
upper-roman          → I, II, III
```

---

# 23. 📝 Practice Questions

### Basic

1. What is a list?
2. What is the difference between `<ul>` and `<ol>`?
3. What is the purpose of `list-style-type`?
4. What is `list-style-image`?
5. What is `list-style-position`?
6. What is the default marker of an unordered list?
7. What is the default marker of an ordered list?
8. What does `list-style: none` do?

### Practical

9. Create an unordered list of five programming languages.
10. Change the bullets to squares.
11. Create an ordered list using Roman numerals.
12. Remove the bullets from a list.
13. Create a horizontal navigation bar using `<ul>` and `<li>`.
14. Create a nested list of CSE subjects.
15. Create a shopping list and style each item using CSS.
16. Add a hover effect to list items.

---

# ⚡ Quick Revision

```text
                 CSS LISTS
                     │
          ┌──────────┼──────────┐
          ↓          ↓          ↓
         <ul>       <ol>       <dl>
          │          │          │
      Bullets      Numbers    Terms
          │          │
          └──────┬───┘
                 ↓
          CSS List Properties
                 │
       ┌─────────┼──────────┐
       ↓         ↓          ↓
 list-style   position    image
    type
```

### ⭐ Remember

```css
list-style-type
list-style-image
list-style-position
list-style
```

### Most Common Navigation Technique

```css
ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
}

li {
    display: inline;
}
```

> 💡 **HTML creates the list, while CSS controls how the list looks.**

> 🎯 **CSS lists are especially useful for navigation menus, menus, categories, and organized content.**

---

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-1572B6?style=for-the-badge">
</p>

<p align="center">
  <b>🎓 Learn • Practice • Design • Build</b>
</p>

