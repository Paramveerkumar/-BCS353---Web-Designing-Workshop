# ↔️ CSS Width



<p align="center">
  <b>📘 Web Designing Workshop</b><br>
  Learn how to control the horizontal size of HTML elements using CSS.
</p>

---

## 🔰 1. What is CSS Width?

The CSS `width` property is used to **set the width of an HTML element**.

### 💡 Easy Definition

> **Width = How wide an element is**

For example:

```css
.box {
    width: 300px;
}
```

This sets the width of the `.box` to **300 pixels**.

---

# 🎯 2. Basic Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS Width</title>

    <style>
        .box {
            width: 300px;
            height: 150px;
            background-color: lightblue;
            border: 2px solid black;
        }
    </style>
</head>

<body>

    <div class="box">
        This box has a width of 300px.
    </div>

</body>
</html>
```

### Result

```text
              Width = 300px
        ←──────────────────→
        ┌──────────────────┐
        │                  │
        │     CONTENT      │
        │                  │
        └──────────────────┘
```

---

# 📐 3. CSS Width Syntax

The basic syntax is:

```css
selector {
    width: value;
}
```

### Example

```css
div {
    width: 400px;
}
```

---

# 📏 4. Width Using Different Units

The `width` property can use different CSS units.

---

## 🔹 Pixels (`px`)

Pixels are useful when you want a specific fixed width.

```css
.box {
    width: 300px;
}
```

The element gets a width of **300 pixels**.

---

## 🔹 Percentage (`%`)

Percentage width is calculated relative to the **containing block**.

```css
.container {
    width: 800px;
}

.box {
    width: 50%;
}
```

Here:

```text
Container width = 800px

Box width = 50% of 800px
          = 400px
```

### Visual Representation

```text
Container = 800px
┌──────────────────────────────────────────┐
│                                          │
│       Box = 50% = 400px                  │
│       ┌──────────────────────┐           │
│       │                      │           │
│       └──────────────────────┘           │
│                                          │
└──────────────────────────────────────────┘
```

---

## 🔹 Viewport Width (`vw`)

`vw` means **viewport width**.

```css
.box {
    width: 50vw;
}
```

> `1vw` = 1% of the viewport width.

Therefore:

```text
50vw = 50% of the browser window width
```

---

## 🔹 `auto`

```css
.box {
    width: auto;
}
```

`auto` allows the browser to calculate the width based on the element's layout rules and available space.

---

# 📚 5. Common Width Values

| Value   | Meaning                             |
| ------- | ----------------------------------- |
| `300px` | Fixed width of 300 pixels           |
| `50%`   | 50% of the containing block's width |
| `50vw`  | 50% of the viewport width           |
| `auto`  | Browser calculates the width        |

---

# 📱 6. Responsive Width

Using percentages can help create responsive layouts.

```css
.box {
    width: 80%;
}
```

This means the element uses **80% of the available containing block width**.

For example:

```text
Desktop
┌────────────────────────────────────────┐
│                                        │
│   ┌──────────────────────────────┐     │
│   │          80% WIDTH           │     │
│   └──────────────────────────────┘     │
│                                        │
└────────────────────────────────────────┘
```

On a smaller screen, the box becomes smaller as the available width changes.

---

# 🚦 7. `width` vs `min-width` vs `max-width`

CSS provides three useful properties for controlling horizontal size.

| Property    | Purpose                |
| ----------- | ---------------------- |
| `width`     | Sets the width         |
| `min-width` | Sets the minimum width |
| `max-width` | Sets the maximum width |

---

## 🔹 `width`

```css
.box {
    width: 400px;
}
```

Sets the element's width to `400px`, subject to the applicable box-sizing and layout rules.

---

## 🔹 `min-width`

```css
.box {
    min-width: 300px;
}
```

The element should not become narrower than **300px** because of this constraint.

---

## 🔹 `max-width`

```css
.box {
    max-width: 600px;
}
```

The element should not become wider than **600px** because of this constraint.

---

# 🧠 8. Why Use `max-width`?

`max-width` is very useful for **responsive websites**.

For example:

```css
.container {
    width: 100%;
    max-width: 1200px;
}
```

This means:

* The container can use the available width.
* It can shrink on smaller screens.
* It will not become wider than `1200px`.

This is commonly used for website content containers.

---

# 📦 9. Width, Padding and Border

An important concept for beginners is that the actual rendered size of an element can be affected by:

* Width
* Padding
* Border
* `box-sizing`

Consider:

```css
.box {
    width: 300px;
    padding: 20px;
    border: 5px solid black;
}
```

With the default:

```css
box-sizing: content-box;
```

the declared `width: 300px` applies to the **content area**.

---

# 📦 10. `box-sizing: border-box`

To make the declared width include the **content + padding + border**, use:

```css
box-sizing: border-box;
```

### Example

```css
.box {
    width: 300px;
    padding: 20px;
    border: 5px solid black;
    box-sizing: border-box;
}
```

Now the **total width of the box is 300px**.

```text
          Total Width = 300px
       ←────────────────────→
       ┌────────────────────┐
       │      Border        │
       │ ┌────────────────┐ │
       │ │    Padding     │ │
       │ │  ┌──────────┐  │ │
       │ │  │ Content  │  │ │
       │ │  └──────────┘  │ │
       │ └────────────────┘ │
       └────────────────────┘
```

### ⭐ Common Practice

Many developers use:

```css
* {
    box-sizing: border-box;
}
```

This makes sizing easier to understand because the declared width includes padding and border.

---

# 🆚 11. Width vs Height

Students often confuse these two properties.

```text
             WIDTH
       ←──────────────→
       ┌───────────────┐
       │               │
       │    CONTENT    │
       │               │  ↑
       └───────────────┘  │
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

So:

```text
Width  = 300px
Height = 200px
```

---

# 🌐 12. Viewport Width (`vw`)

The **viewport** is the visible area of the browser window.

```css
.hero {
    width: 100vw;
}
```

This sets the element's width to approximately the viewport width.

### Common Uses

`vw` can be useful for:

* Full-width sections
* Hero sections
* Responsive designs
* Large banners

---

# 💻 13. Complete Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS Width Example</title>

    <style>
        .box {
            width: 300px;
            height: 150px;

            border: 3px solid black;
            padding: 20px;

            background-color: lightblue;

            box-sizing: border-box;
        }
    </style>
</head>

<body>

    <div class="box">
        <h2>CSS Width</h2>
        <p>
            This box has a total width of 300px.
        </p>
    </div>

</body>
</html>
```

---

# 🧪 14. Practical Example: Website Container

A common website layout uses:

```css
.container {
    width: 90%;
    max-width: 1200px;
    margin: auto;
}
```

### What does it mean?

```text
width: 90%;
```

The container can use 90% of the available width.

```text
max-width: 1200px;
```

The container will not become wider than 1200px.

```text
margin: auto;
```

The container can be horizontally centered when there is extra space.

---

# 📱 15. Responsive Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>Responsive Width</title>

    <style>
        .container {
            width: 90%;
            max-width: 1000px;
            margin: auto;
            padding: 20px;
            background-color: lightblue;
            box-sizing: border-box;
        }
    </style>
</head>

<body>

    <div class="container">
        <h2>Responsive Container</h2>
        <p>
            This container adjusts to the available screen width.
        </p>
    </div>

</body>
</html>
```

### 💡 Why is this useful?

The same design can work on:

* 💻 Desktop
* 💻 Laptop
* 📱 Mobile
* 📟 Tablet

---

# ⚠️ 16. Important Point

Be careful when using fixed widths:

```css
.box {
    width: 1000px;
}
```

A `1000px` wide element may not fit on a small mobile screen.

For responsive designs, you can often use:

```css
.box {
    width: 100%;
    max-width: 1000px;
}
```

This allows the element to shrink while limiting its maximum width.

---

# 🧠 17. Quick Revision

### Basic Property

```css
width: 300px;
```

### Common Values

```css
width: 300px;
width: 50%;
width: 50vw;
width: auto;
```

### Related Properties

```css
min-width: 300px;
max-width: 1000px;
```

### Important Concept

```text
width
  ↓
Controls horizontal size ↔
```

---

# 🎯 18. Practice Questions

### Q1. What is the purpose of the CSS `width` property?

### Q2. Write CSS to set an element's width to `500px`.

### Q3. What is the difference between `width` and `height`?

### Q4. What does `width: 50%;` mean?

### Q5. What does `width: 50vw;` mean?

### Q6. What is the difference between `width` and `max-width`?

### Q7. Why is `max-width` useful for responsive websites?

### Q8. Explain the difference between `content-box` and `border-box`.

### Q9. Write CSS for a responsive container with:

* Width = `90%`
* Maximum width = `1200px`
* Center alignment

---

# ⭐ Key Takeaways

```text
┌─────────────────────────────────────┐
│           CSS WIDTH ↔               │
├─────────────────────────────────────┤
│                                     │
│  width       → Sets the width       │
│  min-width   → Minimum width        │
│  max-width   → Maximum width        │
│                                     │
│  px  → Fixed size                   │
│  %   → Containing block width       │
│  vw  → Viewport width               │
│  auto → Automatic                   │
│                                     │
└─────────────────────────────────────┘
```

> 💡 **Easy Definition:**
> **CSS `width` controls how wide an element is.**

---

## 🔥 Quick Comparison

| Property     | Direction    | Example              |
| ------------ | ------------ | -------------------- |
| `width`      | ↔ Horizontal | `width: 300px;`      |
| `height`     | ↕ Vertical   | `height: 200px;`     |
| `min-width`  | ↔ Minimum    | `min-width: 200px;`  |
| `max-width`  | ↔ Maximum    | `max-width: 1200px;` |
| `min-height` | ↕ Minimum    | `min-height: 100px;` |
| `max-height` | ↕ Maximum    | `max-height: 500px;` |

<p align="center">
  <b>🎨 CSS → Size → Width → Horizontal Space ↔</b>
</p>



