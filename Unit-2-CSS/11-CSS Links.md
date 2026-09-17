# 🔗 CSS Links

<p align="center">
  <img src="https://img.shields.io/badge/CSS-Links-1572B6?style=for-the-badge&logo=css3&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Learn how to style hyperlinks using CSS.
</p>

---

## 1. 🔍 What is a Link?

A **link (hyperlink)** is an element that allows users to move from one webpage or resource to another.

In HTML, links are created using the `<a>` element.

### Example

```html
<a href="https://example.com">Visit Website</a>
```

When the user clicks **Visit Website**, the browser opens the specified URL.

---

# 2. 🎨 Why Use CSS on Links?

By default, browsers usually display links as:

* Blue text
* Underlined
* Different color after visiting

CSS allows us to customize links.

We can change:

* Color
* Underline
* Font size
* Background
* Hover effect
* Border
* Spacing

---

# 3. 🧩 Basic CSS Link Syntax

```css
a {
    color: red;
}
```

HTML:

```html
<a href="#">Home</a>
```

The link will appear in **red**.

---

# 4. ⭐ Four Important Link States

CSS provides four commonly used link states:

| State       | Meaning                       |
| ----------- | ----------------------------- |
| `a:link`    | Normal, unvisited link        |
| `a:visited` | Link already visited          |
| `a:hover`   | Mouse is placed over the link |
| `a:active`  | Link is being clicked         |

### Easy way to remember

```text
Normal
  ↓
:link

Visited
  ↓
:visited

Mouse over
  ↓
:hover

Clicking
  ↓
:active
```

---

# 5. 🔵 `a:link`

The `:link` pseudo-class represents a **normal, unvisited link**.

```css
a:link {
    color: blue;
}
```

HTML:

```html
<a href="https://example.com">Visit Website</a>
```

---

# 6. 🟣 `a:visited`

The `:visited` pseudo-class applies to a link that the user has already visited.

```css
a:visited {
    color: purple;
}
```

Example:

```html
<a href="https://example.com">Example Website</a>
```

After visiting the page, the link may appear purple.

> ⚠️ Browsers restrict some CSS properties that can be applied to `:visited` for privacy reasons.

---

# 7. 🖱️ `a:hover`

The `:hover` pseudo-class applies when the mouse pointer is placed over the link.

```css
a:hover {
    color: red;
}
```

### Example

```html
<a href="#">Move Mouse Here</a>
```

```css
a {
    color: blue;
}

a:hover {
    color: red;
}
```

### Concept

```text
Before Hover
      ↓
🔵 Home

Mouse moves over link
      ↓
🔴 Home
```

---

# 8. 🖱️ `a:active`

The `:active` pseudo-class applies while the link is being clicked.

```css
a:active {
    color: green;
}
```

Example:

```css
a:active {
    color: green;
}
```

---

# 9. 🧠 Correct Order of Link States

When using all four states, remember:

```text
:link
  ↓
:visited
  ↓
:hover
  ↓
:active
```

### Mnemonic

> **LVHA**

```text
L → Link
V → Visited
H → Hover
A → Active
```

So remember:

**L V H A**

---

# 10. 🚫 Removing the Underline

By default, links are usually underlined.

We can remove the underline using:

```css
text-decoration: none;
```

Example:

```css
a {
    text-decoration: none;
}
```

HTML:

```html
<a href="#">Home</a>
```

### Result

```text
Default:
Home
────

After CSS:
Home
```

---

# 11. ➖ Adding Underline

We can add an underline using:

```css
a {
    text-decoration: underline;
}
```

Other values include:

```css
text-decoration: none;
text-decoration: underline;
text-decoration: overline;
text-decoration: line-through;
```

---

# 12. 🎨 Changing Link Color

Use the `color` property.

```css
a {
    color: green;
}
```

Example:

```html
<a href="#">About Us</a>
```

---

# 13. 🔠 Changing Link Font Size

Use `font-size`.

```css
a {
    font-size: 20px;
}
```

---

# 14. 🖌️ Styling Links Like Buttons

CSS can make a normal hyperlink look like a button.

```html
<a href="#" class="button">Login</a>
```

CSS:

```css
.button {
    background-color: blue;
    color: white;
    padding: 10px 20px;
    text-decoration: none;
    border-radius: 5px;
}

.button:hover {
    background-color: darkblue;
}
```

### Visual idea

```text
┌─────────────┐
│    Login    │
└─────────────┘
```

---

# 15. 🔲 Link with Border

We can add a border around a link.

```css
a {
    border: 2px solid blue;
    padding: 8px;
}
```

HTML:

```html
<a href="#">Home</a>
```

---

# 16. 🌈 Link Hover Effect

A hover effect makes a website more interactive.

```css
a {
    color: blue;
    text-decoration: none;
}

a:hover {
    color: red;
    text-decoration: underline;
}
```

### Behavior

```text
Normal
   ↓
🔵 Home

Hover
   ↓
🔴 Home
   └── Underline
```

---

# 17. 🧭 Styling Navigation Links

Links are commonly used in navigation bars.

### HTML

```html
<nav>
    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Services</a>
    <a href="#">Contact</a>
</nav>
```

### CSS

```css
nav a {
    color: black;
    text-decoration: none;
    margin: 15px;
    font-size: 18px;
}

nav a:hover {
    color: blue;
}
```

---

# 18. 📦 Horizontal Navigation Bar

```html
<!DOCTYPE html>
<html>
<head>

    <title>Navigation Bar</title>

    <style>

        nav {
            background-color: #333;
            padding: 15px;
        }

        nav a {
            color: white;
            text-decoration: none;
            margin-right: 25px;
            font-size: 18px;
        }

        nav a:hover {
            color: yellow;
        }

    </style>

</head>

<body>

    <nav>
        <a href="#">Home</a>
        <a href="#">About</a>
        <a href="#">Courses</a>
        <a href="#">Contact</a>
    </nav>

</body>
</html>
```

### Output concept

```text
┌──────────────────────────────────────────────┐
│ Home   About   Courses   Contact             │
└──────────────────────────────────────────────┘
```

When the mouse moves over a link:

```text
Home   About   Courses   Contact
        ↑
     Hover effect
```

---

# 19. 🖱️ Changing Cursor

We can change the mouse cursor when hovering over a link.

```css
a:hover {
    cursor: pointer;
}
```

For normal hyperlinks, browsers already provide a pointer cursor, but `cursor` is useful when creating custom interactive elements.

---

# 20. ✨ Complete Example

```html
<!DOCTYPE html>
<html>

<head>

    <title>CSS Links</title>

    <style>

        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }

        h1 {
            color: #333;
        }

        a {
            color: blue;
            font-size: 20px;
            text-decoration: none;
            margin: 15px;
        }

        a:hover {
            color: red;
            text-decoration: underline;
        }

        a:active {
            color: green;
        }

    </style>

</head>

<body>

    <h1>CSS Link Example</h1>

    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Contact</a>

</body>

</html>
```

---

# 21. 📊 Link States Summary

| Selector    | When it works         | Example |
| ----------- | --------------------- | ------- |
| `a:link`    | Normal unvisited link | Blue    |
| `a:visited` | Already visited       | Purple  |
| `a:hover`   | Mouse over link       | Red     |
| `a:active`  | While clicking        | Green   |

---

# 22. 🔄 Link vs Link State

### Link

```html
<a href="#">Home</a>
```

This creates the hyperlink.

### Link State

```css
a:hover {
    color: red;
}
```

This controls the appearance when the mouse is over the link.

### Remember

> **HTML creates the link. CSS styles the link.**

---

# 23. 📝 Practice Questions

### Basic

1. What is a hyperlink?
2. Which HTML element is used to create a link?
3. What is the purpose of the `href` attribute?
4. What is `a:hover`?
5. What is `a:visited`?
6. What is `a:active`?
7. What does `text-decoration: none` do?
8. What is the LVHA rule?

### Practical

9. Create four links: Home, About, Services and Contact.
10. Change the color of an unvisited link.
11. Add a hover effect to a link.
12. Remove the underline from all links.
13. Create a navigation bar using CSS.
14. Design a hyperlink that looks like a button.
15. Create different colors for normal, visited, hover and active states.

---

# ⚡ Quick Revision

```text
                 CSS LINKS
                     │
        ┌────────────┼────────────┐
        ↓            ↓            ↓
      Color        Size       Decoration
        │            │            │
      color      font-size   text-decoration
        │
        ↓
   Link States
        │
   ┌────┼────┬────┐
   ↓    ↓    ↓    ↓
 :link :visited :hover :active
```

### ⭐ Important Properties

```css
color
font-size
text-decoration
background-color
padding
margin
border
cursor
```

### ⭐ Important States

```css
a:link
a:visited
a:hover
a:active
```

### ⭐ Remember LVHA

```text
L → Link
V → Visited
H → Hover
A → Active
```

> 💡 **HTML creates hyperlinks, while CSS controls their appearance and interactive effects.**

---

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-1572B6?style=for-the-badge">
</p>

<p align="center">
  <b>🎓 Learn • Practice • Design • Build</b>
</p>

