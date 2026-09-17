# 📏 CSS Height

<p align="center">
  <img src="https://img.shields.io/badge/CSS-Height-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS Height">
</p>

<p align="center">
  <b>📘 Web Designing Workshop</b><br>
  Learn how to control the height of HTML elements using CSS.
</p>

---

## 🔰 1. What is CSS Height?

The CSS `height` property is used to **set the height of an HTML element**.

### 💡 Easy Definition

> **Height = How tall an element is**

For example:

```css
.box {
    height: 200px;
}
```

This sets the height of `.box` to **200 pixels**.

---

## 🎯 2. Basic Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS Height</title>

    <style>
        .box {
            height: 200px;
            background-color: lightblue;
            border: 2px solid black;
        }
    </style>
</head>

<body>

    <div class="box">
        This box has a height of 200px.
    </div>

</body>
</html>
```

### Result

```text
        Height = 200px
             ↓
    ┌──────────────────┐
    │                  │
    │                  │
    │     CONTENT      │
    │                  │
    │                  │
    └──────────────────┘
```

---

# 📐 3. CSS Height Syntax

The basic syntax is:

```css
selector {
    height: value;
}
```

### Example

```css
div {
    height: 300px;
}
```

---

# 📏 4. Height Using Different Units

The `height` property can use different CSS units.

### Pixels (`px`)

```css
.box {
    height: 200px;
}
```

The element gets a fixed height of **200 pixels**.

---

### Percentage (`%`)

```css
.box {
    height: 50%;
}
```

The height is calculated relative to the height of the **containing/parent element**, when that parent has a definite height.

Example:

```css
.container {
    height: 400px;
}

.box {
    height: 50%;
}
```

Here:

```text
Parent height = 400px

Child height = 50% of 400px
             = 200px
```

---

### Viewport Height (`vh`)

`vh` means **viewport height**.

```css
.box {
    height: 50vh;
}
```

> `1vh` = 1% of the viewport height.

Therefore:

```text
50vh = 50% of the browser window height
```

---

### `auto`

```css
.box {
    height: auto;
}
```

`auto` allows the browser to calculate the height based on the element's content and layout.

---

# 🧩 5. Common Height Values

| Value   | Meaning                              |
| ------- | ------------------------------------ |
| `200px` | Fixed height of 200 pixels           |
| `50%`   | 50% of the containing block's height |
| `50vh`  | 50% of the viewport height           |
| `auto`  | Browser calculates the height        |

---

# 📦 6. Height and Content

An important point for beginners:

```css
.box {
    height: 100px;
}
```

This does **not necessarily mean the entire visible box will always be exactly 100px tall**.

The actual rendered size can also be affected by:

* Padding
* Border
* `box-sizing`
* Content
* Overflow

For example:

```css
.box {
    height: 100px;
    padding: 20px;
    border: 5px solid black;
}
```

With the default:

```css
box-sizing: content-box;
```

the `height: 100px` applies to the **content area**.

---

# 📦 7. `box-sizing` and Height

To make the declared height include the padding and border, use:

```css
box-sizing: border-box;
```

### Example

```css
.box {
    height: 200px;
    padding: 20px;
    border: 5px solid black;
    box-sizing: border-box;
}
```

Now the **total height of the box is 200px**.

```text
        Total Height = 200px
    ┌─────────────────────┐
    │       Border        │
    │  ┌───────────────┐  │
    │  │    Padding    │  │
    │  │   ┌───────┐   │  │
    │  │   │Content│   │  │
    │  │   └───────┘   │  │
    │  └───────────────┘  │
    └─────────────────────┘
```

### 🧠 Remember

> `content-box` → height applies to content
> `border-box` → height includes content + padding + border

---

# 🚦 8. `height` vs `min-height` vs `max-height`

CSS provides three useful properties for controlling vertical size.

| Property     | Purpose                   |
| ------------ | ------------------------- |
| `height`     | Sets the element's height |
| `min-height` | Sets the minimum height   |
| `max-height` | Sets the maximum height   |

---

## 🔹 `height`

```css
.box {
    height: 300px;
}
```

Sets the element's height to `300px` under the applicable box-sizing rules.

---

## 🔹 `min-height`

```css
.box {
    min-height: 200px;
}
```

The element should be **at least 200px high**.

If the content needs more space, the element can grow beyond 200px.

```text
Minimum Height = 200px

┌──────────────────┐
│                  │
│     Content      │
│                  │
│                  │
└──────────────────┘

May grow taller if content requires more space.
```

---

## 🔹 `max-height`

```css
.box {
    max-height: 200px;
}
```

The element's height is limited to **200px** by this constraint.

If the content is larger, you may need `overflow` to control what happens to the extra content.

Example:

```css
.box {
    max-height: 200px;
    overflow: auto;
}
```

---

# 🆚 9. Height vs Width

Students often confuse `height` and `width`.

```text
             WIDTH
        ←────────────→
       ┌──────────────┐
       │              │
       │    CONTENT   │  ↑
       │              │  │
       └──────────────┘  │
                         │
                       HEIGHT
```

| Property | Controls          |
| -------- | ----------------- |
| `width`  | Horizontal size ↔ |
| `height` | Vertical size ↕   |

### Example

```css
.box {
    width: 300px;
    height: 200px;
}
```

The box is:

```text
Width  = 300px
Height = 200px
```

---

# 🌐 10. Viewport Height (`vh`)

The viewport is the **visible area of the browser window**.

```css
.hero {
    height: 100vh;
}
```

This makes the element approximately as tall as the viewport.

### Common Example

```css
.hero {
    height: 100vh;
}
```

This is often used for:

* Landing pages
* Full-screen sections
* Hero sections
* Login pages

---

# 💻 11. Complete Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS Height Example</title>

    <style>
        .box {
            width: 300px;
            height: 200px;

            border: 3px solid black;
            padding: 20px;

            background-color: lightblue;
            box-sizing: border-box;
        }
    </style>
</head>

<body>

    <div class="box">
        <h2>CSS Height</h2>
        <p>
            This box has a total height of 200px.
        </p>
    </div>

</body>
</html>
```

---

# 🧪 12. Practical Example

Suppose we want to create a website header:

```css
header {
    height: 80px;
    background-color: lightblue;
}
```

The header will have a height of **80px**.

```text
┌────────────────────────────────────────┐
│             WEBSITE HEADER             │
│                80px                    │
└────────────────────────────────────────┘
```

---

# ⚠️ 13. Important Point: Fixed Height

Be careful when using a fixed height with text-heavy content.

```css
.box {
    height: 100px;
}
```

If the content becomes larger than the available space, it may overflow.

A better approach for flexible content can be:

```css
.box {
    min-height: 100px;
}
```

This allows the box to **grow when necessary**.

---

# 🧠 14. Quick Revision

### Basic Property

```css
height: 200px;
```

### Common Values

```css
height: 200px;
height: 50%;
height: 50vh;
height: auto;
```

### Related Properties

```css
min-height: 200px;
max-height: 500px;
```

### Important Concept

```text
height
   ↓
Controls vertical size ↕
```

---

# 🎯 15. Practice Questions

### Q1. What is the purpose of the CSS `height` property?

### Q2. Write the CSS syntax for setting an element's height to `300px`.

### Q3. What is the difference between `height` and `width`?

### Q4. What does `height: 50vh;` mean?

### Q5. What is the difference between `height` and `min-height`?

### Q6. What is the purpose of `max-height`?

### Q7. What is the difference between `content-box` and `border-box`?

### Q8. Write CSS for a box with:

* Width = `300px`
* Height = `200px`
* Border = `2px solid black`
* Padding = `20px`

---

# ⭐ Key Takeaways

```text
┌─────────────────────────────────────┐
│          CSS HEIGHT 📏               │
├─────────────────────────────────────┤
│                                     │
│  height       → Sets height         │
│  min-height   → Minimum height      │
│  max-height   → Maximum height      │
│                                     │
│  px  → Fixed size                   │
│  %   → Parent/containing height     │
│  vh  → Viewport height              │
│  auto → Automatic                   │
│                                     │
└─────────────────────────────────────┘
```

> 💡 **Easy Definition:**
> **CSS `height` controls how tall an element is.**

<p align="center">
  <b>🎨 CSS → Size → Height → Vertical Space ↕</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Next%20Topic-CSS%20Width-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="Next Topic: CSS Width">
</p>

