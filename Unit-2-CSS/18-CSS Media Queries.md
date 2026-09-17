# 📱 CSS Media Queries

<p align="center">
  <img src="https://img.shields.io/badge/CSS-Media%20Queries-1572B6?style=for-the-badge&logo=css3&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Learn how to make websites responsive on different screen sizes and devices.
</p>

---

## 📌 1. What is a CSS Media Query?

A **CSS Media Query** is used to apply different CSS styles depending on the **device or screen conditions**, such as:

* 📱 Screen width
* 💻 Screen size
* 🖥️ Device orientation
* 🖨️ Print output
* 🌐 Display characteristics

### Simple Definition

> **Media Query = Apply CSS according to the screen/device condition.**

For example:

```css
@media (max-width: 600px) {
  body {
    background-color: lightblue;
  }
}
```

This means:

> If the screen width is **600px or smaller**, apply these styles.

---

# 🎯 2. Why Do We Use Media Queries?

Media queries are mainly used to create **responsive websites**.

A responsive website adjusts its layout according to the available screen size.

```text
        Responsive Website
               │
       ┌───────┼───────┐
       ↓       ↓       ↓
    📱 Mobile  💻 Laptop  🖥️ Desktop
       │       │       │
       └───────┼───────┘
               ↓
        Suitable Layout
```

### Example

A website may display:

```text
Desktop:
┌────────┬────────┬────────┐
│  Box 1 │  Box 2 │  Box 3 │
└────────┴────────┴────────┘
```

But on mobile:

```text
┌──────────────┐
│    Box 1     │
├──────────────┤
│    Box 2     │
├──────────────┤
│    Box 3     │
└──────────────┘
```

Media queries help us create this behavior.

---

# 🔹 3. Basic Syntax

```css
@media (condition) {

  selector {
    property: value;
  }

}
```

### Example

```css
@media (max-width: 600px) {

  body {
    background-color: lightblue;
  }

}
```

---

# 📏 4. `max-width`

`max-width` means:

> Apply the CSS when the screen width is **less than or equal to** the specified value.

Example:

```css
@media (max-width: 600px) {

  .container {
    width: 100%;
  }

}
```

### Meaning

```text
Screen width ≤ 600px
        ↓
Apply these styles
```

---

# 📐 5. `min-width`

`min-width` means:

> Apply the CSS when the screen width is **greater than or equal to** the specified value.

Example:

```css
@media (min-width: 768px) {

  .container {
    width: 80%;
  }

}
```

### Meaning

```text
Screen width ≥ 768px
        ↓
Apply these styles
```

---

# 🆚 6. `min-width` vs `max-width`

| Condition          | Meaning          |
| ------------------ | ---------------- |
| `max-width: 600px` | 600px or smaller |
| `min-width: 600px` | 600px or larger  |

### Easy Memory

```text
MAX → Up to this size

MIN → From this size and above
```

---

# 📱 7. Mobile Responsive Example

### HTML

```html
<div class="box">
  Responsive Box
</div>
```

### CSS

```css
.box {
  width: 50%;
  padding: 30px;
  background-color: lightgreen;
}

@media (max-width: 600px) {

  .box {
    width: 100%;
    padding: 15px;
  }

}
```

### Result

```text
Desktop
┌──────────────────────┐
│     Responsive Box   │
└──────────────────────┘
       50% width


Mobile
┌────────────────────────────┐
│     Responsive Box         │
└────────────────────────────┘
          100% width
```

---

# 🔄 8. Multiple Media Queries

We can use multiple media queries for different screen sizes.

```css
/* Mobile */
@media (max-width: 600px) {
  body {
    font-size: 14px;
  }
}

/* Tablet */
@media (min-width: 601px) and (max-width: 992px) {
  body {
    font-size: 16px;
  }
}

/* Desktop */
@media (min-width: 993px) {
  body {
    font-size: 18px;
  }
}
```

### Concept

```text
┌─────────────────────────────────────┐
│ Mobile      ≤ 600px                 │
├─────────────────────────────────────┤
│ Tablet      601px – 992px           │
├─────────────────────────────────────┤
│ Desktop     ≥ 993px                 │
└─────────────────────────────────────┘
```

> 💡 These are example breakpoints. There is no single set of screen sizes that every website must use.

---

# 🔗 9. Combining Conditions

We can combine conditions using `and`.

```css
@media (min-width: 600px) and (max-width: 900px) {

  body {
    background-color: lightyellow;
  }

}
```

This means:

```text
600px ≤ Screen Width ≤ 900px
             ↓
       Apply the CSS
```

---

# 📱 10. Orientation

Media queries can detect screen orientation.

There are two common values:

* `portrait`
* `landscape`

### Portrait

```css
@media (orientation: portrait) {

  body {
    background-color: lightblue;
  }

}
```

### Landscape

```css
@media (orientation: landscape) {

  body {
    background-color: lightgreen;
  }

}
```

### Understanding

```text
Portrait                  Landscape

┌───────┐                 ┌───────────────┐
│       │                 │               │
│       │                 │               │
│       │                 │               │
└───────┘                 └───────────────┘
```

---

# 🖨️ 11. Media Query for Printing

CSS can also define styles specifically for printed pages.

```css
@media print {

  nav {
    display: none;
  }

}
```

When the page is printed:

```text
Navigation → Hidden
Content    → Printed
```

### Example

```css
@media print {

  body {
    font-size: 12pt;
  }

  .navbar {
    display: none;
  }

}
```

---

# 🧩 12. Media Types

A media query can also specify a media type.

Common examples:

| Media Type | Purpose                                     |
| ---------- | ------------------------------------------- |
| `screen`   | Screens such as mobile, tablet and computer |
| `print`    | Printed documents                           |

Example:

```css
@media screen and (max-width: 600px) {

  body {
    font-size: 14px;
  }

}
```

For printing:

```css
@media print {

  body {
    color: black;
  }

}
```

---

# 📐 13. Responsive Navigation Bar

Media queries are commonly used to change navigation layouts.

### Desktop

```text
┌────────────────────────────────────┐
│ Home | About | Courses | Contact  │
└────────────────────────────────────┘
```

### Mobile

```text
┌──────────────────┐
│ Home             │
│ About            │
│ Courses          │
│ Contact          │
└──────────────────┘
```

### CSS

```css
.nav {
  display: flex;
  gap: 20px;
}

@media (max-width: 600px) {

  .nav {
    flex-direction: column;
  }

}
```

---

# 🧱 14. Responsive Columns

Suppose we have three columns.

### Desktop

```text
┌─────────┬─────────┬─────────┐
│ Column 1│ Column 2│ Column 3│
└─────────┴─────────┴─────────┘
```

On mobile:

```text
┌──────────────┐
│   Column 1   │
├──────────────┤
│   Column 2   │
├──────────────┤
│   Column 3   │
└──────────────┘
```

### CSS

```css
.container {
  display: flex;
}

.column {
  flex: 1;
}

@media (max-width: 600px) {

  .container {
    flex-direction: column;
  }

}
```

---

# 🖼️ 15. Responsive Images

Media queries can also change image size.

```css
.image {
  width: 50%;
}

@media (max-width: 600px) {

  .image {
    width: 100%;
  }

}
```

### Result

```text
Desktop → Image width: 50%

Mobile  → Image width: 100%
```

---

# 🔤 16. Responsive Font Size

We can change font size according to screen width.

```css
h1 {
  font-size: 40px;
}

@media (max-width: 600px) {

  h1 {
    font-size: 28px;
  }

}
```

### Why?

A large heading that looks good on a desktop may take too much space on a small mobile screen.

---

# 📱 17. Mobile-First Approach

A common modern approach is **Mobile First**.

### Idea

> Design for small screens first, then add styles for larger screens.

Example:

```css
/* Default: Mobile */
.container {
  width: 100%;
}

/* Larger screens */
@media (min-width: 768px) {

  .container {
    width: 80%;
  }

}
```

### Concept

```text
Mobile First
     ↓
Basic styles
     ↓
Tablet improvements
     ↓
Desktop improvements
```

---

# 🖥️ 18. Desktop-First Approach

Another approach is to write desktop styles first and modify them for smaller screens.

```css
.container {
  width: 80%;
}

@media (max-width: 600px) {

  .container {
    width: 100%;
  }

}
```

### Comparison

| Approach      | Starting Point |
| ------------- | -------------- |
| Mobile First  | Small screens  |
| Desktop First | Large screens  |

---

# 🌐 19. Viewport Meta Tag

For responsive websites, the HTML document should normally include the viewport meta tag.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### Example

```html
<!DOCTYPE html>

<html>

<head>

  <meta
    name="viewport"
    content="width=device-width, initial-scale=1.0"
  >

  <title>Responsive Website</title>

</head>

<body>

  <h1>My Website</h1>

</body>

</html>
```

### Why is it important?

It tells the browser to use the device's actual viewport width when displaying the page.

---

# 🧪 20. Complete Responsive Example

```html
<!DOCTYPE html>
<html>

<head>

  <meta
    name="viewport"
    content="width=device-width, initial-scale=1.0"
  >

  <title>Responsive Website</title>

  <style>

    body {
      margin: 0;
      font-family: Arial, sans-serif;
    }

    .container {
      display: flex;
      gap: 20px;
      padding: 20px;
    }

    .box {
      flex: 1;
      padding: 40px;
      text-align: center;
      background-color: lightblue;
    }

    h1 {
      text-align: center;
      font-size: 40px;
    }

    /* Mobile */
    @media (max-width: 600px) {

      .container {
        flex-direction: column;
      }

      .box {
        padding: 20px;
      }

      h1 {
        font-size: 28px;
      }

    }

  </style>

</head>

<body>

  <h1>Responsive Website</h1>

  <div class="container">

    <div class="box">
      Box 1
    </div>

    <div class="box">
      Box 2
    </div>

    <div class="box">
      Box 3
    </div>

  </div>

</body>

</html>
```

### Desktop

```text
┌─────────────────────────────────────┐
│          Responsive Website         │
│                                     │
│ ┌────────┐ ┌────────┐ ┌────────┐  │
│ │ Box 1  │ │ Box 2  │ │ Box 3  │  │
│ └────────┘ └────────┘ └────────┘  │
└─────────────────────────────────────┘
```

### Mobile

```text
┌──────────────────┐
│ Responsive       │
│ Website          │
│                  │
│ ┌──────────────┐ │
│ │    Box 1     │ │
│ └──────────────┘ │
│ ┌──────────────┐ │
│ │    Box 2     │ │
│ └──────────────┘ │
│ ┌──────────────┐ │
│ │    Box 3     │ │
│ └──────────────┘ │
└──────────────────┘
```

---

# 🧠 21. Important Points

> ⭐ Media queries are used to create **responsive designs**.

> ⭐ `max-width` applies styles up to a particular width.

> ⭐ `min-width` applies styles from a particular width upward.

> ⭐ `and` combines multiple conditions.

> ⭐ `orientation` can detect portrait or landscape mode.

> ⭐ `@media print` controls the appearance of printed pages.

> ⭐ Mobile-first design starts with small-screen styles.

> ⭐ The viewport meta tag is important for responsive pages.

> ⭐ Media queries work together with CSS properties such as Flexbox, Grid, width, height and display.

---

# ❓ 22. Practice Questions

### Q1. What is a CSS Media Query?

### Q2. Why are media queries used?

### Q3. What is the difference between `min-width` and `max-width`?

### Q4. Write a media query that changes the background color when the screen width is 600px or less.

### Q5. What does this code mean?

```css
@media (max-width: 768px) {
  body {
    font-size: 14px;
  }
}
```

### Q6. How can you detect portrait orientation using CSS?

### Q7. What is the purpose of `@media print`?

### Q8. What is Mobile First design?

### Q9. Why is the viewport meta tag used?

### Q10. Create a responsive layout that displays three columns on desktop and one column on mobile.

---

# ⚡ 23. Quick Revision

```text
                  CSS MEDIA QUERIES
                         │
             ┌───────────┴───────────┐
             ↓                       ↓
       Screen Conditions          Print
             │                       │
      ┌──────┼──────┐                │
      ↓      ↓      ↓                ↓
   Width  Height Orientation      @media print
      │
  ┌───┴────┐
  ↓        ↓
 min      max
 width    width
  │        │
  ↓        ↓
Larger   Smaller
screens  screens
```

---

## 📌 One-Line Definition

> **CSS Media Query is a CSS technique used to apply different styles based on screen size, device conditions, orientation, or media type.**

---

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-1572B6?style=for-the-badge&logo=html5&logoColor=white">
</p>

<p align="center">
  <b>🎓 BCS353 • Web Designing Workshop</b>
</p>

