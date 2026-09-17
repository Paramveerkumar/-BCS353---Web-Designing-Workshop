# 🖥️ CSS Display

<p align="center">
  <img src="https://img.shields.io/badge/CSS-Display-1572B6?style=for-the-badge&logo=css3&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Learn how CSS controls the layout and visibility of HTML elements.
</p>

---

## 1. 🔍 What is the CSS `display` Property?

The CSS `display` property specifies **how an HTML element should participate in the layout of a webpage**.

In simple words:

> 💡 **`display` tells the browser how an element should behave on the page.**

For example:

* Should elements appear on the same line?
* Should an element take the full width?
* Should an element behave like inline content?
* Should an element be hidden?
* Should an element become a flex or grid container?

### Syntax

```css
selector {
    display: value;
}
```

Example:

```css
div {
    display: block;
}
```

---

# 2. 🧩 Common `display` Values

The most important values for beginners are:

| Value          | Meaning                                    |
| -------------- | ------------------------------------------ |
| `block`        | Starts on a new line                       |
| `inline`       | Stays in the same line                     |
| `inline-block` | Inline but allows width/height             |
| `none`         | Completely removes the element from layout |
| `flex`         | Creates a Flexbox container                |
| `grid`         | Creates a Grid container                   |

---

# 3. 🟦 `display: block`

A **block-level element** normally:

* Starts on a new line
* Takes the available width by default
* Allows `width` and `height`
* Can contain other elements depending on the HTML element

Example:

```html
<div class="box">Box 1</div>
<div class="box">Box 2</div>
```

```css
.box {
    display: block;
    background-color: lightblue;
    margin: 5px;
}
```

### Output concept

```text
┌──────────────────────────────┐
│ Box 1                        │
└──────────────────────────────┘

┌──────────────────────────────┐
│ Box 2                        │
└──────────────────────────────┘
```

Each block appears on a new line.

### Common block-level elements

```text
<div>
<p>
<h1> to <h6>
<section>
<header>
<footer>
<nav>
```

---

# 4. 🟢 `display: inline`

An **inline element** stays within the current line.

Example:

```html
<span>HTML</span>
<span>CSS</span>
<span>JavaScript</span>
```

```css
span {
    display: inline;
}
```

### Output

```text
HTML   CSS   JavaScript
```

Inline elements generally:

* Do not start a new line
* Occupy only the space they need
* Do not behave like block boxes for `width` and `height`

### Common inline elements

```text
<span>
<a>
<strong>
<em>
```

---

# 5. 🟡 `display: inline-block`

`inline-block` combines characteristics of both `inline` and `block`.

It:

* Appears on the same line like `inline`
* Allows `width` and `height` like a block-level box
* Allows padding and margin

Example:

```html
<div class="box">Box 1</div>
<div class="box">Box 2</div>
<div class="box">Box 3</div>
```

```css
.box {
    display: inline-block;
    width: 150px;
    height: 80px;
    background-color: lightblue;
    margin: 10px;
}
```

### Output concept

```text
┌────────────┐  ┌────────────┐  ┌────────────┐
│   Box 1    │  │   Box 2    │  │   Box 3    │
└────────────┘  └────────────┘  └────────────┘
```

### Easy comparison

```text
block
↓
New line

inline
↓
Same line

inline-block
↓
Same line + width/height
```

---

# 6. 🚫 `display: none`

`display: none` completely removes an element from the page layout.

Example:

```html
<p class="hide">This text is hidden.</p>
<p>This text is visible.</p>
```

```css
.hide {
    display: none;
}
```

The first paragraph is not displayed and does not occupy space.

### Important

```text
display: none
      ↓
Element hidden
      ↓
Space also removed
```

---

# 7. 👻 `display: none` vs `visibility: hidden`

These two are often confused.

### `display: none`

```css
.box {
    display: none;
}
```

The element disappears **and its space is removed**.

### `visibility: hidden`

```css
.box {
    visibility: hidden;
}
```

The element becomes invisible, but **its space remains**.

### Comparison

```text
display: none

┌───────┐  ┌───────┐
│ Box 1 │  │ Box 3 │
└───────┘  └───────┘


visibility: hidden

┌───────┐  ┌───────┐  ┌───────┐
│ Box 1 │  │       │  │ Box 3 │
└───────┘  └───────┘  └───────┘
              ↑
          Space remains
```

---

# 8. 🔄 Changing Block to Inline

CSS can change the default behavior of an element.

Example:

```html
<div>Home</div>
<div>About</div>
<div>Contact</div>
```

Normally:

```text
Home
About
Contact
```

Now use:

```css
div {
    display: inline;
}
```

Result:

```text
Home   About   Contact
```

---

# 9. 🔄 Changing Inline to Block

Example:

```html
<a href="#">Home</a>
<a href="#">About</a>
<a href="#">Contact</a>
```

Normally, links appear inline.

We can make them block elements:

```css
a {
    display: block;
}
```

Result:

```text
Home
About
Contact
```

This technique is useful for **vertical menus**.

---

# 10. 🧭 Navigation Menu Using `display`

### HTML

```html
<nav>
    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Courses</a>
    <a href="#">Contact</a>
</nav>
```

### Horizontal Menu

```css
a {
    display: inline-block;
    padding: 10px 20px;
}
```

Output:

```text
Home    About    Courses    Contact
```

### Vertical Menu

```css
a {
    display: block;
    padding: 10px;
}
```

Output:

```text
Home
About
Courses
Contact
```

---

# 11. 📦 `display: flex`

The `flex` value turns an element into a **Flexbox container**.

Example:

```html
<div class="container">

    <div>Box 1</div>
    <div>Box 2</div>
    <div>Box 3</div>

</div>
```

CSS:

```css
.container {
    display: flex;
}
```

### Output

```text
┌────────┐  ┌────────┐  ┌────────┐
│ Box 1  │  │ Box 2  │  │ Box 3  │
└────────┘  └────────┘  └────────┘
```

Flexbox is commonly used for:

* Navigation bars
* Cards
* Menus
* Aligning items
* Responsive layouts

---

# 12. 🧱 `display: grid`

The `grid` value turns an element into a **CSS Grid container**.

Example:

```html
<div class="container">

    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>

</div>
```

CSS:

```css
.container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 10px;
}
```

### Output

```text
┌────────┐  ┌────────┐
│   1    │  │   2    │
└────────┘  └────────┘

┌────────┐  ┌────────┐
│   3    │  │   4    │
└────────┘  └────────┘
```

Grid is useful for:

* Photo galleries
* Product cards
* Dashboard layouts
* Page layouts

---

# 13. 🧠 Block vs Inline vs Inline-Block

| Feature      | Block    | Inline                                  | Inline-block  |
| ------------ | -------- | --------------------------------------- | ------------- |
| New line     | ✅        | ❌                                       | ❌             |
| Width/Height | ✅        | Limited/doesn't apply as box dimensions | ✅             |
| Same line    | ❌        | ✅                                       | ✅             |
| Common use   | Sections | Text/links                              | Buttons/cards |

### Easy way to remember

```text
BLOCK
↓
One line per element

INLINE
↓
Elements share a line

INLINE-BLOCK
↓
Share a line + control box size
```

---

# 14. 🆚 `display: none` vs `opacity: 0`

These are also different.

### `display: none`

```css
.box {
    display: none;
}
```

* Not displayed
* Does not occupy layout space

### `opacity: 0`

```css
.box {
    opacity: 0;
}
```

* Becomes transparent
* Still participates in layout
* It can still receive pointer events unless other CSS prevents them

```text
display: none
      ↓
Removed from layout

opacity: 0
      ↓
Invisible but still occupies space
```

---

# 15. 🎯 Practical Example: Three Cards

### HTML

```html
<div class="card">HTML</div>
<div class="card">CSS</div>
<div class="card">JavaScript</div>
```

### CSS

```css
.card {
    display: inline-block;
    width: 180px;
    padding: 20px;
    margin: 10px;
    background-color: lightblue;
    text-align: center;
}
```

### Output

```text
┌──────────────┐  ┌──────────────┐  ┌──────────────┐
│     HTML     │  │      CSS     │  │ JavaScript   │
└──────────────┘  └──────────────┘  └──────────────┘
```

---

# 16. ✨ Complete Example

```html
<!DOCTYPE html>
<html>

<head>

    <title>CSS Display</title>

    <style>

        body {
            font-family: Arial, sans-serif;
        }

        .box {
            display: inline-block;
            width: 180px;
            padding: 20px;
            margin: 10px;
            background-color: lightblue;
            text-align: center;
        }

        .box:hover {
            background-color: lightgreen;
        }

    </style>

</head>

<body>

    <h1>CSS Display Property</h1>

    <div class="box">HTML</div>
    <div class="box">CSS</div>
    <div class="box">JavaScript</div>

</body>

</html>
```

---

# 17. 📊 Display Values Summary

| Display        | Behavior               | Common Use        |
| -------------- | ---------------------- | ----------------- |
| `block`        | New line               | Sections          |
| `inline`       | Same line              | Text/links        |
| `inline-block` | Same line + dimensions | Buttons/cards     |
| `none`         | Removed from layout    | Hide elements     |
| `flex`         | Flexbox layout         | Navigation/cards  |
| `grid`         | Grid layout            | Page/card layouts |

---

# 18. 🧩 Important Concept

Suppose we have:

```html
<div>HTML</div>
<div>CSS</div>
<div>JavaScript</div>
```

### Default

```text
HTML
CSS
JavaScript
```

### `display: inline`

```css
div {
    display: inline;
}
```

```text
HTML   CSS   JavaScript
```

### `display: inline-block`

```css
div {
    display: inline-block;
    width: 150px;
}
```

```text
┌────────┐ ┌────────┐ ┌────────────┐
│ HTML   │ │ CSS    │ │ JavaScript │
└────────┘ └────────┘ └────────────┘
```

### `display: none`

```css
div {
    display: none;
}
```

```text
Nothing is displayed.
```

---

# 19. 📝 Practice Questions

### Basic

1. What is the CSS `display` property?
2. What is `display: block`?
3. What is `display: inline`?
4. What is `display: inline-block`?
5. What does `display: none` do?
6. What is the difference between `display: none` and `visibility: hidden`?
7. What is `display: flex`?
8. What is `display: grid`?

### Practical

9. Convert a `<div>` from block to inline.
10. Convert links into a vertical menu using `display: block`.
11. Create three cards using `inline-block`.
12. Hide an element using `display: none`.
13. Create a horizontal navigation bar using `inline-block`.
14. Create three boxes using Flexbox.
15. Create a 2 × 2 layout using CSS Grid.
16. Compare `block`, `inline`, and `inline-block` using one webpage.

---

# ⚡ Quick Revision

```text
                    CSS DISPLAY
                         │
        ┌────────────────┼────────────────┐
        ↓                ↓                ↓
      BLOCK            INLINE       INLINE-BLOCK
        │                │                │
    New line          Same line      Same line
    Full width        Content size   Width/height
        │                │                │
        └────────────────┼────────────────┘
                         ↓
                  Layout Control
                         │
                ┌────────┴────────┐
                ↓                 ↓
               FLEX              GRID
                │                 │
          1-Dimensional      2-Dimensional
             Layout              Layout
```

### ⭐ Most Important Values

```css
display: block;
display: inline;
display: inline-block;
display: none;
display: flex;
display: grid;
```

### ⭐ Remember

> **Block → New line**

> **Inline → Same line**

> **Inline-block → Same line + width/height**

> **None → Element removed from layout**

> **Flex → Flexible one-dimensional layout**

> **Grid → Two-dimensional layout**

---

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-1572B6?style=for-the-badge">
</p>

<p align="center">
  <b>🎓 Learn • Practice • Design • Build</b>
</p>

