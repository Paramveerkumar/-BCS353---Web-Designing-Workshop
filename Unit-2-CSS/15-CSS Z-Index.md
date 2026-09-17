# 📚 CSS `z-index`

<p align="center">
  <img src="https://img.shields.io/badge/CSS-Z--Index-1572B6?style=for-the-badge&logo=css3&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Learn how to control which element appears in front of another.
</p>

---

## 1. 🔍 What is `z-index`?

The CSS `z-index` property controls the **stacking order** of overlapping elements.

In simple words:

> 💡 **`z-index` decides which element appears on top when elements overlap.**

Think of elements as **layers**:

```text
        ┌───────────────┐
        │   Element C   │  ← z-index: 3
        └───────────────┘

      ┌───────────────────┐
      │    Element B      │  ← z-index: 2
      └───────────────────┘

    ┌───────────────────────┐
    │      Element A        │  ← z-index: 1
    └───────────────────────┘
```

Higher stacking order generally places an element **in front of** a lower stacking order when they participate in the same stacking context.

---

# 2. 🧩 Syntax

```css
selector {
    z-index: value;
}
```

Example:

```css
.box {
    z-index: 5;
}
```

Common values:

```text
1
2
10
100
999
-1
```

`z-index` can also use `auto`.

---

# 3. 📦 Why Do We Need `z-index`?

Suppose two boxes overlap:

```text
        ┌───────────────┐
        │     Box B     │
        │       ┌───────┼───────┐
        │       │       │       │
        └───────┤       │       │
                │  Box A│       │
                └───────┴───────┘
```

Which box should appear on top?

We can control it using `z-index`.

```css
.box-a {
    z-index: 2;
}

.box-b {
    z-index: 1;
}
```

Therefore:

```text
Box A → Front
Box B → Behind
```

---

# 4. ⭐ Basic Example

### HTML

```html
<div class="box box1">Box 1</div>
<div class="box box2">Box 2</div>
```

### CSS

```css
.box {
    position: absolute;
    width: 150px;
    height: 150px;
}

.box1 {
    background-color: lightblue;
    left: 50px;
    top: 50px;
    z-index: 1;
}

.box2 {
    background-color: lightcoral;
    left: 100px;
    top: 100px;
    z-index: 2;
}
```

### Result

```text
        ┌──────────────┐
        │    Box 1     │
        │      ┌───────┼────────┐
        │      │       │ Box 2  │
        └──────┤       │        │
               └───────┴────────┘
                       ↑
                  Box 2 is on top
                  z-index: 2
```

---

# 5. 🧠 Higher `z-index` = Higher Layer

Suppose:

```css
.box1 {
    z-index: 1;
}

.box2 {
    z-index: 5;
}

.box3 {
    z-index: 10;
}
```

The stacking order is:

```text
        Box 3
      z-index: 10
          ↑
        Box 2
      z-index: 5
          ↑
        Box 1
      z-index: 1
```

So, when these elements overlap:

```text
10 → Front
 5 → Middle
 1 → Back
```

> ⚠️ This comparison applies when the elements are competing within the same relevant stacking context.

---

# 6. 📌 `z-index` and `position`

For beginners, an important rule is:

> `z-index` is commonly used with positioned elements.

For example:

```css
.box {
    position: absolute;
    z-index: 2;
}
```

Positioning can be:

```css
position: relative;
position: absolute;
position: fixed;
position: sticky;
```

### Example

```css
.box1 {
    position: absolute;
    z-index: 1;
}

.box2 {
    position: absolute;
    z-index: 2;
}
```

---

# 7. 🟢 `position: relative` + `z-index`

`position: relative` is often used when you want to control stacking without significantly changing the element's normal position.

```css
.box {
    position: relative;
    z-index: 2;
}
```

Example:

```html
<div class="box1">Box 1</div>
<div class="box2">Box 2</div>
```

```css
.box1 {
    position: relative;
    z-index: 1;
}

.box2 {
    position: relative;
    z-index: 2;
}
```

---

# 8. ➖ Negative `z-index`

`z-index` can also have negative values.

Example:

```css
.box {
    position: relative;
    z-index: -1;
}
```

This can place the element behind other content **within the relevant stacking context**, but negative stacking can interact with parent backgrounds and stacking contexts in ways that make it unsuitable for simple layering.

For beginners:

```text
Positive z-index
      ↓
Usually brings element forward

Negative z-index
      ↓
Can place element behind other content
```

---

# 9. 🖼️ Real-World Example: Image and Text

Suppose we want text to appear over an image.

### HTML

```html
<div class="container">

    <img src="image.jpg" alt="Background">

    <h2>Welcome to My Website</h2>

</div>
```

### CSS

```css
.container {
    position: relative;
}

.container img {
    width: 100%;
}

.container h2 {
    position: absolute;
    top: 50px;
    left: 50px;
    z-index: 2;
}
```

### Concept

```text
┌──────────────────────────────────┐
│                                  │
│       Background Image           │
│                                  │
│        ┌──────────────┐          │
│        │ Welcome!     │          │
│        └──────────────┘          │
│                                  │
└──────────────────────────────────┘
               ↑
          z-index: 2
```

---

# 10. 🧭 Real-World Example: Navigation Bar

A navigation bar may need to appear above other page content.

```css
nav {
    position: fixed;
    top: 0;
    width: 100%;
    z-index: 1000;
}
```

Here:

```text
z-index: 1000
      ↓
Navigation stays above
other overlapping content
```

---

# 11. 🪟 Modal / Popup Example

A popup should normally appear above the page content.

```css
.modal {
    position: fixed;
    top: 50%;
    left: 50%;
    z-index: 9999;
}
```

Concept:

```text
┌────────────────────────────────────┐
│             Web Page               │
│                                    │
│       ┌────────────────┐           │
│       │     LOGIN      │           │
│       │                │           │
│       │   Username     │           │
│       │   Password     │           │
│       └────────────────┘           │
│                                    │
└────────────────────────────────────┘
              ↑
         z-index: 9999
```

---

# 12. 🎯 `z-index: auto`

The default value is:

```css
z-index: auto;
```

Example:

```css
.box {
    z-index: auto;
}
```

`auto` means the element does not establish a numeric stacking level of its own.

---

# 13. 🔢 Does `z-index: 1000` Always Beat `z-index: 10`?

**No—not necessarily.**

This is an important concept.

`z-index` values are compared within their **stacking contexts**.

For example, if an element with `z-index: 1000` is inside a stacking context that itself is behind another stacking context, it cannot simply escape that stacking context because it has a larger number.

### Simplified idea

```text
Parent A
z-index: 1
   │
   └── Child
       z-index: 9999


Parent B
z-index: 2
   │
   └── Child
       z-index: 1
```

The child with `9999` does **not automatically appear above** Parent B's child.

Why?

Because the children are being compared within their respective stacking contexts.

> ⭐ This is one of the most important advanced concepts about `z-index`.

---

# 14. 🧱 What is a Stacking Context?

A **stacking context** is a group of elements that the browser treats as a separate layering environment.

Some CSS properties can create stacking contexts, including certain uses of:

```text
position + z-index
opacity less than 1
transform
filter
isolation
```

For beginner-level work, remember:

```text
Stacking Context
       ↓
A separate layer environment
       ↓
z-index is evaluated within it
```

---

# 15. 🆚 `z-index` vs `position`

These properties have different jobs.

| Property   | Purpose                               |
| ---------- | ------------------------------------- |
| `position` | Controls how an element is positioned |
| `top`      | Moves element vertically              |
| `left`     | Moves element horizontally            |
| `z-index`  | Controls stacking order               |

Example:

```css
.box {
    position: absolute;
    top: 50px;
    left: 100px;
    z-index: 5;
}
```

Meaning:

```text
position → positioning method
top      → vertical position
left     → horizontal position
z-index  → layer order
```

---

# 16. ✨ Complete Example

```html
<!DOCTYPE html>
<html>

<head>

    <title>CSS Z-Index</title>

    <style>

        .container {
            position: relative;
            height: 400px;
        }

        .box {
            position: absolute;
            width: 180px;
            height: 180px;
            padding: 20px;
            color: white;
            font-size: 20px;
        }

        .box1 {
            background-color: blue;
            left: 50px;
            top: 50px;
            z-index: 1;
        }

        .box2 {
            background-color: red;
            left: 130px;
            top: 130px;
            z-index: 2;
        }

        .box3 {
            background-color: green;
            left: 210px;
            top: 210px;
            z-index: 3;
        }

    </style>

</head>

<body>

    <h1>CSS Z-Index Example</h1>

    <div class="container">

        <div class="box box1">
            Box 1<br>
            z-index: 1
        </div>

        <div class="box box2">
            Box 2<br>
            z-index: 2
        </div>

        <div class="box box3">
            Box 3<br>
            z-index: 3
        </div>

    </div>

</body>

</html>
```

### Result

```text
          ┌───────────────┐
          │    Box 1      │
          │      ┌───────────────┐
          │      │    Box 2      │
          │      │      ┌───────────────┐
          └──────┤      │    Box 3      │
                 └──────┤               │
                        └───────────────┘

                     ↑
                  Front
```

---

# 17. 🧠 Easy Real-Life Example

Think about **books placed on a table**.

```text
       📘 Book 3
       z-index: 3
       ──────────

       📗 Book 2
       z-index: 2
       ──────────

       📕 Book 1
       z-index: 1
       ──────────
```

The book with the higher layer is visually on top.

Similarly:

```css
z-index: 1;
z-index: 2;
z-index: 3;
```

Higher stacking level → generally appears in front **within the same stacking context**.

---

# 18. 📊 `z-index` Summary

| Value  | Meaning                                |
| ------ | -------------------------------------- |
| `auto` | Default stacking behavior              |
| `1`    | Lower positive stacking level          |
| `5`    | Higher than 1 in same stacking context |
| `100`  | Higher than 5 in same stacking context |
| `-1`   | Negative stacking level                |

---

# 19. 📝 Practice Questions

### Basic

1. What is the `z-index` property?
2. Why is `z-index` used?
3. What does a higher `z-index` generally mean?
4. What is the default value of `z-index`?
5. What is a stacking context?
6. Can `z-index` have a negative value?
7. What is the difference between `position` and `z-index`?

### Practical

8. Create two overlapping boxes using `position: absolute`.
9. Make the second box appear above the first using `z-index`.
10. Create three overlapping boxes with `z-index` values 1, 2 and 3.
11. Create a text overlay on an image.
12. Create a fixed navigation bar with a high `z-index`.
13. Create a popup/modal using `position: fixed` and `z-index`.
14. Experiment with negative `z-index`.

---

# ⚡ Quick Revision

```text
                     CSS Z-INDEX
                          │
                          ↓
                Controls Layer Order
                          │
             ┌────────────┴────────────┐
             ↓                         ↓
       Lower z-index             Higher z-index
             ↓                         ↓
        Back layer                 Front layer
```

### ⭐ Basic Example

```css
.box1 {
    position: absolute;
    z-index: 1;
}

.box2 {
    position: absolute;
    z-index: 2;
}
```

```text
Box 2
  ↑
Front

Box 1
  ↑
Back
```

### ⭐ Remember

> **`z-index` = Layer control**

> **Higher `z-index` generally means higher stacking order within the same stacking context.**

> **`z-index` becomes especially useful when elements overlap.**

> **Always understand stacking contexts when `z-index` appears not to work as expected.**

---

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-1572B6?style=for-the-badge">
</p>

<p align="center">
  <b>🎓 Learn • Practice • Design • Build</b>
</p>

