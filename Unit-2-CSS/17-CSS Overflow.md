# 🌊 CSS Overflow

<p align="center">
  <img src="https://img.shields.io/badge/CSS-Overflow-1572B6?style=for-the-badge&logo=css3&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Learn how CSS controls content that is larger than its container.
</p>

---

## 📌 1. What is CSS Overflow?

The CSS `overflow` property controls **what happens when content is too large to fit inside an element's box**.

### Simple Definition

> **Overflow = What should happen when content goes outside the element's boundaries?**

For example, suppose a box has a fixed height:

```css
.box {
  width: 300px;
  height: 100px;
}
```

If the content is larger than `300px × 100px`, some content may extend outside the box.

```text
┌──────────────────────────────┐
│ This content fits inside     │
│ the box, but this additional │
│ content is too large and     │
└──────────────────────────────┘
          ↓
    Content may overflow
```

---

# 🎯 2. Why Do We Use Overflow?

The `overflow` property is useful when:

* 📦 Content is larger than its container
* 📜 We need scrolling
* 🖼️ We want to hide extra content
* 📱 We need responsive layouts
* 📊 We have large tables or code blocks
* 💬 We want to control unwanted content extending outside a box

---

# 🔹 3. CSS Overflow Syntax

```css
selector {
  overflow: value;
}
```

Example:

```css
.box {
  overflow: auto;
}
```

---

# 🔵 4. Main Overflow Values

| Value     | Meaning                              |
| --------- | ------------------------------------ |
| `visible` | Content is allowed to extend outside |
| `hidden`  | Extra content is clipped             |
| `scroll`  | Scrollbars are always provided       |
| `auto`    | Scrollbars appear when needed        |

---

# 🟢 5. `overflow: visible`

`visible` is the **default value**.

The content is not clipped even if it extends outside the box.

```css
.box {
  width: 250px;
  height: 100px;
  overflow: visible;
}
```

### Concept

```text
┌─────────────────────────┐
│ Content inside the box  │
│ More content...         │
└─────────────────────────┘
          │
          │ Extra content
          ↓
       continues
       outside
```

### Important

```css
overflow: visible;
```

means:

> "Allow the content to remain visible outside the box."

---

# 🔴 6. `overflow: hidden`

Extra content is **clipped** and is not visible.

```css
.box {
  width: 250px;
  height: 100px;
  overflow: hidden;
}
```

### Concept

```text
┌─────────────────────────┐
│ Content inside the box  │
│ More content...         │
└─────────────────────────┘
          ✂
      Extra content
       is hidden
```

### Example

```html
<div class="box">
  This is a very long text that is larger than
  the available space inside the box.
</div>
```

```css
.box {
  width: 250px;
  height: 100px;
  overflow: hidden;
}
```

---

# 🟡 7. `overflow: scroll`

Scrollbars are provided so that the user can access overflowing content.

```css
.box {
  width: 250px;
  height: 100px;
  overflow: scroll;
}
```

### Concept

```text
┌────────────────────────────┐
│ Content that is visible    │
│ More content...            │
│                            │
│                       ↕    │
└────────────────────────────┘
       Scrollbar
```

The user can scroll to see the hidden content.

---

# 🟠 8. `overflow: auto`

`auto` provides scrolling **when it is necessary**.

```css
.box {
  width: 250px;
  height: 100px;
  overflow: auto;
}
```

### Easy Understanding

```text
Content fits
     ↓
No scrollbar

Content does not fit
     ↓
Scrollbar appears
```

### ⭐ Commonly Useful

```css
overflow: auto;
```

is commonly used for:

* Responsive tables
* Long text
* Code blocks
* Containers with unpredictable content

---

# 📊 9. Overflow Values Comparison

| Value     | Extra Content           | Scrollbar   |
| --------- | ----------------------- | ----------- |
| `visible` | Visible outside         | ❌           |
| `hidden`  | Hidden/clipped          | ❌           |
| `scroll`  | Accessible by scrolling | ✅           |
| `auto`    | Accessible when needed  | When needed |

### Memory Trick

```text
VISIBLE → Show it

HIDDEN → Hide it

SCROLL → Give scrollbar

AUTO → Decide automatically
```

---

# ↔️ 10. `overflow-x`

`overflow-x` controls overflow in the **horizontal direction**.

```css
.box {
  overflow-x: auto;
}
```

### Example

```text
←────────────────────────────→
       Horizontal content
       can be scrolled
```

This is particularly useful for **wide tables**.

---

# ↕️ 11. `overflow-y`

`overflow-y` controls overflow in the **vertical direction**.

```css
.box {
  overflow-y: auto;
}
```

### Example

```text
┌────────────────────┐
│ Content            │
│ Content            │
│ Content            │
│ Content          ↕ │
└────────────────────┘
```

The user can scroll vertically when necessary.

---

# 🔄 12. `overflow-x` vs `overflow-y`

| Property     | Controls            |
| ------------ | ------------------- |
| `overflow-x` | Horizontal overflow |
| `overflow-y` | Vertical overflow   |
| `overflow`   | Both directions     |

### Example

```css
.box {
  overflow-x: auto;
  overflow-y: hidden;
}
```

Meaning:

> Allow horizontal scrolling but hide vertical overflow.

---

# 🧩 13. Overflow Shorthand

You can control both directions using:

```css
overflow: x y;
```

For example:

```css
.box {
  overflow: auto hidden;
}
```

Here:

```text
First value  → Horizontal (x)
Second value → Vertical (y)
```

So:

```css
overflow: auto hidden;
```

means:

* Horizontal → `auto`
* Vertical → `hidden`

---

# 📱 14. Responsive Tables with Overflow

A common real-world use of overflow is making wide tables responsive.

### HTML

```html
<div class="table-container">

  <table>
    <tr>
      <th>Name</th>
      <th>Department</th>
      <th>Email</th>
      <th>Phone</th>
      <th>Address</th>
    </tr>

    <tr>
      <td>Rahul</td>
      <td>CSE</td>
      <td>rahul@example.com</td>
      <td>9876543210</td>
      <td>Delhi</td>
    </tr>
  </table>

</div>
```

### CSS

```css
.table-container {
  overflow-x: auto;
}

table {
  width: 800px;
  border-collapse: collapse;
}

th,
td {
  border: 1px solid black;
  padding: 10px;
}
```

### Why?

On a small screen:

```text
┌───────────────────────┐
│ Name │ Dept │ Email → │
│──────┼──────┼─────────│
│ Rahul│ CSE  │ ...   → │
└───────────────────────┘
          ↔
       Scroll
```

Instead of breaking the entire page, the table can be **scrolled horizontally**.

---

# 💻 15. Overflow with Code

Overflow is also useful for displaying long lines of code.

```css
.code-box {
  width: 400px;
  overflow-x: auto;
  background-color: #eeeeee;
  padding: 15px;
}
```

### HTML

```html
<div class="code-box">
  const message = "This is a very long line of code...";
</div>
```

The user can scroll horizontally if the line is too long.

---

# 🖼️ 16. Overflow with Images

Suppose an image is larger than its container.

```css
.container {
  width: 300px;
  height: 200px;
  overflow: hidden;
}
```

```html
<div class="container">
  <img src="large-image.jpg" alt="Large Image">
</div>
```

The part of the image outside the container will be clipped.

### Concept

```text
Container
┌───────────────────────┐
│       IMAGE           │
│    ┌──────────────┐   │
│    │              │   │
│    │   Large      │   │
└────┴──────────────┴───┘
     Extra part clipped
```

---

# 🎬 17. Text Truncation with Overflow

Overflow can be combined with other CSS properties to show only one line of text.

```css
.title {
  width: 250px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
```

### Example

```text
Original:

This is a very long title for a webpage

After truncation:

This is a very long title...
```

The `...` is called an **ellipsis**.

---

# 🔥 18. `text-overflow: ellipsis`

The `text-overflow` property can indicate that text has been clipped.

Example:

```css
.title {
  width: 250px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
```

### Three properties work together:

```text
white-space: nowrap
        ↓
Keep text on one line

overflow: hidden
        ↓
Hide extra text

text-overflow: ellipsis
        ↓
Show "..."
```

---

# ⚠️ 19. Important: Overflow Needs a Reason to Overflow

Overflow becomes noticeable when content is larger than the available space.

For example:

```css
.box {
  width: 200px;
  height: 100px;
  overflow: auto;
}
```

If the content fits:

```text
No overflow
   ↓
No scrolling is needed
```

If the content is larger:

```text
Content exceeds box
   ↓
Overflow occurs
   ↓
auto can provide scrolling
```

---

# 🧠 20. Overflow vs Scroll

A common question is:

### `overflow: scroll`

```css
.box {
  overflow: scroll;
}
```

Scrollbars are provided regardless of whether the content actually needs them.

### `overflow: auto`

```css
.box {
  overflow: auto;
}
```

The browser provides scrolling when needed.

### Easy Memory

```text
scroll → Always provide scrolling mechanism

auto   → Provide it when needed
```

---

# 🆚 21. Overflow vs Float

| Property   | Purpose                                                          |
| ---------- | ---------------------------------------------------------------- |
| `float`    | Moves elements left/right and allows content to flow around them |
| `overflow` | Controls content that exceeds an element's box                   |

### Easy Memory

```text
FLOAT
↓
Where should the element move?

OVERFLOW
↓
What should happen to extra content?
```

---

# 🧪 22. Complete Example

```html
<!DOCTYPE html>
<html>

<head>

  <title>CSS Overflow</title>

  <style>

    .box {
      width: 300px;
      height: 120px;
      border: 2px solid black;
      padding: 10px;
      overflow: auto;
    }

  </style>

</head>

<body>

  <h2>CSS Overflow Example</h2>

  <div class="box">

    This is a very long paragraph.
    When the content becomes larger than
    the available height of the box,
    the overflow property controls how
    the extra content is displayed.

    CSS provides different overflow values
    such as visible, hidden, scroll and auto.

  </div>

</body>

</html>
```

---

# 🎯 23. Real-World Examples

| Situation                     | Useful CSS                           |
| ----------------------------- | ------------------------------------ |
| Wide table                    | `overflow-x: auto`                   |
| Long code                     | `overflow-x: auto`                   |
| Hide extra image              | `overflow: hidden`                   |
| Scrollable content box        | `overflow: auto`                     |
| Single-line text truncation   | `overflow: hidden` + `text-overflow` |
| Content should remain visible | `overflow: visible`                  |

---

# ❓ 24. Practice Questions

### Q1. What is CSS Overflow?

### Q2. What is the default value of `overflow`?

### Q3. Explain the difference between:

```css
overflow: hidden;
```

and

```css
overflow: auto;
```

### Q4. What is the purpose of `overflow-x`?

### Q5. What is the purpose of `overflow-y`?

### Q6. What is the difference between `scroll` and `auto`?

### Q7. How can you make a wide table horizontally scrollable?

### Q8. What does `text-overflow: ellipsis` do?

### Q9. Write CSS to hide content that exceeds a box.

### Q10. Write CSS to allow horizontal scrolling when required.

---

# ⚡ 25. Quick Revision

```text
                    CSS OVERFLOW
                         │
          ┌──────────────┼──────────────┐
          ↓              ↓              ↓
       visible         hidden          scroll
          │              │              │
     Show outside    Hide extra     Provide scroll
                         │
                         ↓
                        auto
                         │
                  Scroll when needed
                         │
             ┌───────────┴───────────┐
             ↓                       ↓
        overflow-x              overflow-y
        Horizontal              Vertical
```

---

## 📌 One-Line Definition

> **CSS `overflow` controls what happens when content is too large to fit inside an element's box.**

---

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-1572B6?style=for-the-badge&logo=html5&logoColor=white">
</p>

<p align="center">
  <b>🎓 BCS353 • Web Designing Workshop</b>
</p>

