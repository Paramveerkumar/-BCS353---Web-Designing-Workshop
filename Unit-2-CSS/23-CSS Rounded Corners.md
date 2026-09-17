# 🔵 CSS Rounded Corners

<p align="center">
  <img src="https://img.shields.io/badge/CSS-Rounded%20Corners-1572B6?style=for-the-badge&logo=css3&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Learn how to create rounded corners using the CSS <code>border-radius</code> property.
</p>

---

## 1. 📌 What are Rounded Corners?

By default, HTML elements usually have **square corners**.

CSS provides the `border-radius` property to make these corners **rounded**.

### Example

```css
.box {
    border-radius: 10px;
}
```

### Simple idea

```text
Square Corner              Rounded Corner

┌──────────────┐            ╭──────────────╮
│              │            │              │
│     Box      │            │     Box      │
│              │            │              │
└──────────────┘            ╰──────────────╯
```

> ⭐ **`border-radius` = Controls the roundness of corners.**

---

# 2. 🎯 Basic Syntax

```css
selector {
    border-radius: value;
}
```

Example:

```css
.box {
    border-radius: 20px;
}
```

The larger the value, the more rounded the corners become.

---

# 3. 📏 Different Border Radius Values

### Small radius

```css
.box {
    border-radius: 5px;
}
```

### Medium radius

```css
.box {
    border-radius: 15px;
}
```

### Large radius

```css
.box {
    border-radius: 30px;
}
```

### Visual idea

```text
5px             15px             30px

┌─────────┐     ╭─────────╮      ╭─────────╮
│         │     │         │      │         │
└─────────┘     ╰─────────╯      ╰─────────╯
```

---

# 4. 🔲 Applying Rounded Corners to a Box

HTML:

```html
<div class="box">
    Hello Students
</div>
```

CSS:

```css
.box {
    width: 300px;
    padding: 30px;
    background-color: lightblue;
    border-radius: 15px;
}
```

### Result

```text
╭────────────────────────╮
│                        │
│    Hello Students      │
│                        │
╰────────────────────────╯
```

---

# 5. 🔵 Making a Circle

A very common use of `border-radius` is creating a circle.

```css
.circle {
    width: 150px;
    height: 150px;
    border-radius: 50%;
}
```

### Important

For a perfect circle:

```text
width = height
```

and:

```css
border-radius: 50%;
```

### Example

```html
<div class="circle"></div>
```

```css
.circle {
    width: 150px;
    height: 150px;
    background-color: lightblue;
    border-radius: 50%;
}
```

---

# 6. 🟢 Rounded Button

Buttons look more attractive with rounded corners.

```html
<button>Submit</button>
```

```css
button {
    padding: 10px 25px;
    border: none;
    border-radius: 8px;
    cursor: pointer;
}
```

### More rounded button

```css
button {
    border-radius: 25px;
}
```

This can create a **pill-shaped button**.

```text
╭──────────────────────╮
│       Submit         │
╰──────────────────────╯
```

---

# 7. 💊 Pill-Shaped Elements

A pill shape has highly rounded corners.

```css
.pill {
    padding: 10px 25px;
    border-radius: 50px;
}
```

Example:

```html
<span class="pill">CSS</span>
```

CSS:

```css
.pill {
    display: inline-block;
    padding: 8px 20px;
    background-color: lightblue;
    border-radius: 50px;
}
```

### Common uses

* Tags
* Badges
* Buttons
* Status indicators
* Categories

---

# 8. 🎨 Rounded Image

We can also apply `border-radius` to images.

```html
<img src="student.jpg" class="photo">
```

```css
.photo {
    width: 250px;
    border-radius: 15px;
}
```

### Circular Image

```css
.photo {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    object-fit: cover;
}
```

This is commonly used for:

* Profile pictures
* User avatars
* Team members
* Social media profiles

---

# 9. 🖼️ Different Image Shapes

### Normal

```css
img {
    border-radius: 0;
}
```

### Slightly rounded

```css
img {
    border-radius: 10px;
}
```

### Highly rounded

```css
img {
    border-radius: 30px;
}
```

### Circle

```css
img {
    border-radius: 50%;
}
```

---

# 10. 🎯 Individual Corner Radius

We don't always have to round all four corners equally.

CSS provides four individual properties:

```css
border-top-left-radius
border-top-right-radius
border-bottom-right-radius
border-bottom-left-radius
```

Example:

```css
.box {
    border-top-left-radius: 20px;
    border-top-right-radius: 20px;
}
```

### Diagram

```text
      ╭──────────────╮
     /                \
    │                  │
    │                  │
    └──────────────────┘
```

Only the **top corners** are rounded.

---

# 11. 🔄 Four Different Corner Values

We can give a different radius to each corner.

```css
.box {
    border-radius: 10px 20px 30px 40px;
}
```

The order is:

```text
        TOP
   ┌───────────┐
   │           │
LEFT           RIGHT
   │           │
   └───────────┘
       BOTTOM
```

Remember the order:

```text
Top-left → Top-right → Bottom-right → Bottom-left
```

### Easy trick

> **Start from Top-Left and move clockwise.**

---

# 12. 🔢 Border-Radius Shorthand

Like `padding` and `margin`, `border-radius` supports shorthand.

## One value

```css
border-radius: 10px;
```

All four corners:

```text
10px 10px 10px 10px
```

---

## Two values

```css
border-radius: 10px 20px;
```

Equivalent conceptually to:

```text
Top-left     = 10px
Top-right    = 20px
Bottom-right = 10px
Bottom-left  = 20px
```

---

## Three values

```css
border-radius: 10px 20px 30px;
```

Equivalent to:

```text
Top-left     = 10px
Top-right    = 20px
Bottom-right = 30px
Bottom-left  = 20px
```

---

## Four values

```css
border-radius: 10px 20px 30px 40px;
```

```text
Top-left     → 10px
Top-right    → 20px
Bottom-right → 30px
Bottom-left  → 40px
```

---

# 13. 📐 Using Percentage Values

`border-radius` can also use percentages.

```css
.box {
    border-radius: 50%;
}
```

For a square element, this creates a circle.

Example:

```css
.circle {
    width: 200px;
    height: 200px;
    border-radius: 50%;
}
```

---

# 14. 🟣 Rounded Card

Cards commonly use rounded corners.

```html
<div class="card">
    <h2>Web Designing</h2>
    <p>Learn HTML, CSS and JavaScript.</p>
</div>
```

```css
.card {
    width: 300px;
    padding: 20px;
    background-color: white;
    border: 1px solid #ddd;
    border-radius: 15px;
}
```

### Visual idea

```text
╭────────────────────────────╮
│  Web Designing             │
│                            │
│  Learn HTML, CSS and       │
│  JavaScript.               │
╰────────────────────────────╯
```

---

# 15. 🖼️ Rounded Image Inside Card

```css
.card img {
    width: 100%;
    border-radius: 12px;
}
```

This is commonly used in:

* Product cards
* Blog cards
* Portfolio websites
* Online stores

---

# 16. 🔲 Border + Rounded Corners

Rounded corners can be combined with borders.

```css
.box {
    border: 2px solid black;
    border-radius: 15px;
}
```

The border also follows the rounded shape.

```text
╭──────────────────────╮
│                      │
│       Content        │
│                      │
╰──────────────────────╯
```

---

# 17. 🌈 Rounded Corners with Background

```css
.box {
    background-color: lightblue;
    border-radius: 20px;
}
```

The background is clipped to the rounded shape.

---

# 18. ✂️ Rounded Corners with Images

When an image is inside a container, `overflow: hidden` can be useful if the image itself extends beyond the rounded container.

```html
<div class="card">
    <img src="image.jpg" alt="Sample Image">
</div>
```

```css
.card {
    width: 300px;
    border-radius: 15px;
    overflow: hidden;
}

.card img {
    width: 100%;
    display: block;
}
```

### Why `overflow: hidden`?

It clips overflowing image content to the rounded boundary.

---

# 19. 🧑‍🎨 Complete Example

## HTML

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS Rounded Corners</title>
    <link rel="stylesheet" href="style.css">
</head>

<body>

    <div class="card">

        <div class="profile"></div>

        <h2>Paramveer Kumar</h2>

        <p>
            Web Designing Workshop
        </p>

        <button>View Profile</button>

    </div>

</body>
</html>
```

## CSS

```css
body {
    font-family: Arial, sans-serif;
    background-color: #f2f2f2;
    text-align: center;
    padding: 50px;
}

.card {
    width: 300px;
    margin: auto;
    padding: 25px;
    background-color: white;
    border: 1px solid #ddd;
    border-radius: 20px;
}

.profile {
    width: 120px;
    height: 120px;
    margin: auto;
    background-color: lightblue;
    border-radius: 50%;
}

button {
    padding: 10px 25px;
    border: none;
    border-radius: 25px;
    cursor: pointer;
}
```

---

# 20. 🧠 `border-radius` vs `border`

These two properties have different purposes.

| Property        | Purpose            |
| --------------- | ------------------ |
| `border`        | Creates a boundary |
| `border-radius` | Rounds the corners |

Example:

```css
.box {
    border: 2px solid black;
    border-radius: 15px;
}
```

Here:

```text
border        → Boundary
border-radius → Shape of corners
```

---

# 21. 📊 Common Uses of Rounded Corners

| Element       | Common Radius |
| ------------- | ------------- |
| Card          | `10px – 20px` |
| Button        | `5px – 25px`  |
| Input         | `5px – 10px`  |
| Image         | `10px – 20px` |
| Profile Image | `50%`         |
| Badge         | `20px – 50px` |
| Circle        | `50%`         |

These are examples, not fixed rules.

---

# 22. ❌ Common Mistakes

### Mistake 1: Using `50%` without understanding the shape

```css
.box {
    width: 300px;
    height: 100px;
    border-radius: 50%;
}
```

This creates an **oval**, not a circle.

For a circle:

```css
.box {
    width: 100px;
    height: 100px;
    border-radius: 50%;
}
```

---

### Mistake 2: Forgetting `overflow: hidden`

When content such as an image extends outside a rounded container:

```css
.card {
    border-radius: 20px;
    overflow: hidden;
}
```

can be required to clip that content.

---

# 23. 📝 Practice Questions

### Q1. What is the purpose of `border-radius`?

### Q2. Write CSS to create rounded corners of `20px`.

### Q3. How can you create a circle using CSS?

### Q4. What is the difference between `border` and `border-radius`?

### Q5. What does this code do?

```css
border-radius: 10px 20px 30px 40px;
```

### Q6. How can you create a circular profile image?

### Q7. What is the purpose of `overflow: hidden` with rounded cards?

### Q8. How can you create a pill-shaped button?

---

# ⚡ Quick Revision

```text
CSS Rounded Corners
│
└── border-radius
    │
    ├── 1 value
    │   └── All corners
    │
    ├── 2 values
    │   └── Alternate corners
    │
    ├── 3 values
    │
    ├── 4 values
    │   └── Clockwise
    │
    ├── 50%
    │   └── Circle / Oval
    │
    └── Individual corners
        ├── top-left
        ├── top-right
        ├── bottom-right
        └── bottom-left
```

### ⭐ Remember

> **`border-radius` is used to create rounded corners in HTML elements.**

> **`border-radius: 50%` is commonly used to create circles when the element has equal width and height.**

---

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-1572B6?style=for-the-badge&logo=html5&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 • Web Designing Workshop</b>
</p>

