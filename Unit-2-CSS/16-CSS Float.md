# 🎈 CSS Float

<p align="center">
  <img src="https://img.shields.io/badge/CSS-Float-1572B6?style=for-the-badge&logo=css3&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Learn how elements can be positioned to the left or right of their container.
</p>

---

## 📌 1. What is CSS Float?

The CSS `float` property is used to move an element to the **left or right side** of its container.

It allows other content, especially text, to **wrap around the floated element**.

### Simple Definition

> **Float = Move an element to the left or right and allow surrounding content to flow around it.**

### Example

```css
img {
  float: left;
}
```

The image moves to the left, and text can flow around it.

---

## 🎯 2. Why Do We Use Float?

Float was traditionally used for:

* 🖼️ Wrapping text around images
* 📦 Creating simple layouts
* 🧭 Creating columns
* 📑 Positioning elements side by side

> 💡 **Note:** Modern layouts generally use **Flexbox** and **CSS Grid** instead of float. However, understanding `float` is important because it is still useful for text wrapping and is part of CSS fundamentals.

---

# 🔹 3. CSS Float Syntax

```css
selector {
  float: value;
}
```

Example:

```css
img {
  float: left;
}
```

---

# 🔹 4. Values of Float

The main values are:

| Value     | Meaning                              |
| --------- | ------------------------------------ |
| `left`    | Element moves to the left            |
| `right`   | Element moves to the right           |
| `none`    | Default; element does not float      |
| `inherit` | Gets the float value from its parent |

---

# 🟢 5. `float: left`

The element moves to the **left side**.

```css
img {
  float: left;
}
```

### Example

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    img {
      float: left;
      width: 150px;
      margin-right: 15px;
    }
  </style>
</head>

<body>

  <img src="image.jpg" alt="Example">

  <p>
    This is some text around the image.
    Because the image is floated to the left,
    the text flows around the right side of the image.
  </p>

</body>
</html>
```

### Visual Idea

```text
┌──────────────┐
│    IMAGE     │  This is some text
│              │  flowing around the
│              │  image.
└──────────────┘  More text continues here.
                  More content...
```

---

# 🔵 6. `float: right`

The element moves to the **right side**.

```css
img {
  float: right;
}
```

### Visual Idea

```text
This is some text          ┌──────────────┐
flowing around the image.  │    IMAGE     │
More text continues here.  │              │
                           └──────────────┘
```

---

# ⚪ 7. `float: none`

`none` is the default value.

```css
img {
  float: none;
}
```

The element stays in its normal position.

```css
float: none;
```

means:

> "Do not float this element."

---

# 🔹 8. Floating Multiple Elements

Multiple elements can be floated in the same direction.

```css
.box {
  float: left;
  width: 30%;
}
```

Example:

```html
<div class="box">Box 1</div>
<div class="box">Box 2</div>
<div class="box">Box 3</div>
```

```css
.box {
  float: left;
  width: 30%;
  margin: 1%;
  padding: 20px;
  border: 1px solid black;
}
```

### Result

```text
┌─────────┐  ┌─────────┐  ┌─────────┐
│  Box 1  │  │  Box 2  │  │  Box 3  │
└─────────┘  └─────────┘  └─────────┘
```

This was a common technique for creating **columns before Flexbox and Grid became popular**.

---

# 🖼️ 9. Float with Images

One of the most common uses of float is wrapping text around an image.

### HTML

```html
<img src="student.jpg" alt="Student">

<p>
  A student learns different technologies through
  practice and projects. The image is floated to the
  left, so the text flows around the image.
</p>
```

### CSS

```css
img {
  float: left;
  width: 180px;
  margin-right: 20px;
  margin-bottom: 10px;
}
```

### Concept

```text
┌───────────────┐
│               │  Student learns HTML,
│     IMAGE     │  CSS, JavaScript and
│               │  other technologies.
└───────────────┘  Practice is important.
                   Projects improve skills.
```

---

# ⚠️ 10. What Happens After a Floated Element?

A floated element is taken out of the normal flow in a special way.

Other content can flow around it.

Example:

```css
.image {
  float: left;
}
```

```text
Normal Flow:

┌─────────────────────────────┐
│ IMAGE │ Text Text Text      │
│ IMAGE │ Text Text Text      │
│       │ Text Text Text      │
└─────────────────────────────┘
```

The following content may also move beside the floated element if enough space is available.

---

# 🧹 11. CSS Clear Property

The `clear` property is used to control whether an element can appear next to floated elements.

### Syntax

```css
selector {
  clear: value;
}
```

### Common Values

| Value   | Meaning                                     |
| ------- | ------------------------------------------- |
| `left`  | No floating element allowed on the left     |
| `right` | No floating element allowed on the right    |
| `both`  | No floating elements allowed on either side |
| `none`  | Default                                     |

---

# 🔴 12. `clear: both`

`clear: both` is commonly used after floated elements.

```css
.footer {
  clear: both;
}
```

### Example

```html
<div class="box">Box 1</div>
<div class="box">Box 2</div>

<div class="footer">
  Footer
</div>
```

```css
.box {
  float: left;
  width: 40%;
  padding: 20px;
}

.footer {
  clear: both;
}
```

### Concept

```text
┌──────────┐  ┌──────────┐
│  Box 1   │  │  Box 2   │
└──────────┘  └──────────┘
────────────────────────────
          Footer
────────────────────────────
```

The footer starts **below the floated boxes**.

---

# 🟡 13. Difference Between Float and Clear

| Property | Purpose                                                    |
| -------- | ---------------------------------------------------------- |
| `float`  | Moves an element left or right                             |
| `clear`  | Prevents an element from appearing beside floated elements |

### Easy Memory Trick

```text
FLOAT → "Move me left/right"

CLEAR → "Don't let me stay beside the float"
```

---

# 🧩 14. Float with Two Columns

Before Flexbox and Grid, developers often created layouts using float.

```html
<div class="left">Left Column</div>
<div class="right">Right Column</div>
```

```css
.left {
  float: left;
  width: 50%;
}

.right {
  float: right;
  width: 50%;
}
```

### Layout

```text
┌──────────────────────┬──────────────────────┐
│                      │                      │
│     Left Column      │     Right Column     │
│                      │                      │
└──────────────────────┴──────────────────────┘
```

---

# 🧱 15. Float vs Flexbox

| Feature                | Float            | Flexbox                |
| ---------------------- | ---------------- | ---------------------- |
| Original purpose       | Content wrapping | Layout                 |
| Text wrapping          | ✅ Good           | ❌ Not its main purpose |
| One-dimensional layout | Limited          | ✅ Excellent            |
| Alignment              | Limited          | ✅ Easy                 |
| Modern layout          | Older technique  | ✅ Common               |
| Responsive layouts     | More difficult   | Easier                 |

### Remember

```text
Float → Mainly useful for text wrapping

Flexbox → Modern one-dimensional layout

Grid → Modern two-dimensional layout
```

---

# 🧪 16. Complete Example

```html
<!DOCTYPE html>
<html>
<head>

  <title>CSS Float Example</title>

  <style>

    .container {
      border: 2px solid black;
      padding: 15px;
    }

    .image {
      float: left;
      width: 150px;
      margin-right: 20px;
      margin-bottom: 10px;
    }

    .footer {
      clear: both;
      margin-top: 20px;
      padding: 10px;
      background-color: lightgray;
    }

  </style>

</head>

<body>

  <div class="container">

    <img
      src="student.jpg"
      alt="Student"
      class="image"
    >

    <p>
      Web designing is an important skill for computer
      science students. HTML creates the structure,
      CSS provides the style, and JavaScript adds
      interactivity.
    </p>

    <p>
      The image is floated to the left, allowing the
      text to flow around it.
    </p>

    <div class="footer">
      Footer Content
    </div>

  </div>

</body>
</html>
```

---

# 🧠 17. Important Points

> ⭐ `float` moves an element to the left or right.

> ⭐ Text and other inline content can flow around a floated element.

> ⭐ `float: left` moves the element left.

> ⭐ `float: right` moves the element right.

> ⭐ `float: none` is the default.

> ⭐ `clear` controls how an element behaves around floats.

> ⭐ `clear: both` prevents the element from appearing beside left or right floats.

> ⭐ Float was widely used for layouts before Flexbox and Grid.

> ⭐ For modern page layouts, prefer **Flexbox or Grid**.

---

# ❓ 18. Practice Questions

### Q1. What is the purpose of the `float` property?

### Q2. What is the difference between:

```css
float: left;
```

and

```css
float: right;
```

### Q3. What is the default value of `float`?

### Q4. What is the purpose of the `clear` property?

### Q5. What does this mean?

```css
clear: both;
```

### Q6. Write CSS to float an image to the right.

### Q7. How can float be used to create two columns?

### Q8. What is the difference between `float` and `clear`?

### Q9. Why are Flexbox and Grid generally preferred for modern layouts?

---

# ⚡ 19. Quick Revision

```text
                 CSS FLOAT
                     │
          ┌──────────┴──────────┐
          ↓                     ↓
      float: left           float: right
          │                     │
      Move left             Move right
          │                     │
          └──────────┬──────────┘
                     ↓
               Content flows
                around it
                     │
                     ↓
               clear property
                     │
               ┌─────┴─────┐
               ↓           ↓
           clear:left   clear:right
                     │
                     ↓
                clear:both
                     │
             Clear both sides
```

---

## 📌 One-Line Definition

> **CSS `float` is a property used to move an element to the left or right, allowing surrounding content to flow around it.**

---

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-1572B6?style=for-the-badge&logo=html5&logoColor=white">
</p>

<p align="center">
  <b>🎓 BCS353 • Web Designing Workshop</b>
</p>
