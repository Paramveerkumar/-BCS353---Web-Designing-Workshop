# 🧱 HTML Inline and Block Elements

<p align="center">
  <img src="https://img.shields.io/badge/HTML-Inline%20%26%20Block%20Elements-E34F26?style=for-the-badge&logo=html5&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Understand how HTML elements occupy space on a webpage.
</p>

---

## 📌 1. What are Block and Inline Elements?

HTML elements are commonly categorized by how they behave in the page layout.

The two important types are:

* 🧱 **Block-level elements**
* 📝 **Inline elements**

### Simple Definition

> **Block Element → Starts on a new line and normally takes the available width.**

> **Inline Element → Stays in the same line and takes only the space it needs.**

---

# 🧱 2. Block-Level Elements

A **block-level element** normally:

* Starts on a **new line**
* Takes up the available width by default
* Can contain other elements depending on the HTML rules
* Allows width and height to be controlled with CSS

### Common Block Elements

```text
<div>
<p>
<h1> – <h6>
<section>
<article>
<header>
<footer>
<nav>
<main>
<ul>
<ol>
<li>
<table>
<form>
```

---

## 🎯 3. Example of Block Elements

```html
<h1>Welcome</h1>

<p>This is a paragraph.</p>

<div>This is a division.</div>
```

### Browser Layout

```text
┌─────────────────────────────────────────┐
│ Welcome                                 │
└─────────────────────────────────────────┘

┌─────────────────────────────────────────┐
│ This is a paragraph.                    │
└─────────────────────────────────────────┘

┌─────────────────────────────────────────┐
│ This is a division.                     │
└─────────────────────────────────────────┘
```

Each element starts on a **new line**.

---

# 📝 4. Inline Elements

An **inline element** normally:

* Does **not** start on a new line
* Takes only the space required by its content
* Can appear alongside other inline content
* Is useful for styling or marking a small part of text

### Common Inline Elements

```text
<span>
<a>
<strong>
<b>
<em>
<i>
<u>
<mark>
<small>
<sub>
<sup>
<img>
```

---

## 🎯 5. Example of Inline Elements

```html
<p>
  This is <strong>important</strong> text
  with <em>emphasis</em>.
</p>
```

### Browser Layout

```text
This is important text with emphasis.
       ↑             ↑
    <strong>       <em>
```

They stay within the same line when enough horizontal space is available.

---

# 🆚 6. Block vs Inline

| Feature         | Block Element                 | Inline Element                            |
| --------------- | ----------------------------- | ----------------------------------------- |
| New line        | ✅ Usually                     | ❌ Usually not                             |
| Available width | Usually fills available width | Only required content width               |
| Width/Height    | Can normally be set           | Width/height do not apply in the same way |
| Examples        | `<div>`, `<p>`, `<h1>`        | `<span>`, `<a>`, `<strong>`               |
| Main use        | Page structure/layout         | Text-level content/styling                |

### Easy Memory Trick

```text
BLOCK
↓
New Line
↓
Full Available Width


INLINE
↓
Same Line
↓
Content Width
```

---

# 📦 7. Visual Comparison

### Block Elements

```text
┌──────────────────────────────────────┐
│              DIV                     │
└──────────────────────────────────────┘
┌──────────────────────────────────────┐
│              P                       │
└──────────────────────────────────────┘
```

### Inline Elements

```text
Text  [SPAN] [LINK] [BOLD]  Text
```

---

# 🧩 8. `<div>` – Block Element

`<div>` is one of the most commonly used block-level elements.

```html
<div>
  This is a block element.
</div>

<div>
  This is another block element.
</div>
```

### Output

```text
This is a block element.

This is another block element.
```

Each `<div>` starts on a new line.

---

# 📝 9. `<span>` – Inline Element

`<span>` is one of the most commonly used inline elements.

```html
<p>
  My favorite color is
  <span style="color: blue;">blue</span>.
</p>
```

The `<span>` only covers the required part of the text.

```text
My favorite color is blue.
                     ↑
                   span
```

---

# 🎨 10. Styling Block and Inline Elements

### Block

```html
<div class="box">
  Block Element
</div>
```

```css
.box {
  width: 300px;
  height: 100px;
  background-color: lightblue;
}
```

The width and height can be controlled.

---

### Inline

```html
<span class="text">
  Inline Element
</span>
```

```css
.text {
  background-color: yellow;
}
```

The inline element occupies space according to its content.

---

# 🔄 11. Changing Block to Inline

CSS `display` can change how an element participates in layout.

```css
div {
  display: inline;
}
```

Now the `<div>` behaves like an inline element.

### Example

```html
<div>One</div>
<div>Two</div>
<div>Three</div>
```

Normally:

```text
One
Two
Three
```

After:

```css
div {
  display: inline;
}
```

It can appear like:

```text
One Two Three
```

---

# 🧱 12. Changing Inline to Block

We can also make an inline element behave like a block element.

```css
span {
  display: block;
}
```

Example:

```html
<span>One</span>
<span>Two</span>
<span>Three</span>
```

Normally:

```text
One Two Three
```

After:

```css
span {
  display: block;
}
```

It becomes:

```text
One

Two

Three
```

---

# 🔲 13. Inline-Block

There is another useful value:

```css
display: inline-block;
```

It combines important characteristics of inline and block behavior.

### Inline-block:

* Can stay on the same line
* Allows width and height
* Can have padding and margins
* Useful for buttons, cards and menu items

### Example

```html
<div class="box">Box 1</div>
<div class="box">Box 2</div>
<div class="box">Box 3</div>
```

```css
.box {
  display: inline-block;
  width: 150px;
  height: 100px;
  margin: 10px;
  padding: 20px;
  background-color: lightblue;
}
```

### Result

```text
┌────────────┐  ┌────────────┐  ┌────────────┐
│   Box 1    │  │   Box 2    │  │   Box 3    │
│            │  │            │  │            │
└────────────┘  └────────────┘  └────────────┘
```

---

# 🆚 14. Block vs Inline vs Inline-Block

| Feature      | Block     | Inline                                  | Inline-block        |
| ------------ | --------- | --------------------------------------- | ------------------- |
| New line     | ✅         | ❌                                       | ❌                   |
| Same line    | ❌ Usually | ✅                                       | ✅                   |
| Width/Height | ✅         | Not in the same way                     | ✅                   |
| Padding      | ✅         | ✅                                       | ✅                   |
| Margin       | ✅         | Horizontal behavior is most predictable | ✅                   |
| Example      | `<div>`   | `<span>`                                | CSS `display` value |

---

# 🧠 15. Easy Real-Life Example

Think about a **notebook page**.

### Block

A block is like a **full row**:

```text
┌──────────────────────────────┐
│          Full Row            │
└──────────────────────────────┘
```

### Inline

Inline content is like **words in a sentence**:

```text
This is a sentence with words.
     ↑    ↑        ↑
```

### Inline-block

Inline-block is like **small boxes placed in one row**:

```text
┌──────┐ ┌──────┐ ┌──────┐
│ Box  │ │ Box  │ │ Box  │
└──────┘ └──────┘ └──────┘
```

---

# 🌐 16. Practical Example – Navigation Menu

HTML:

```html
<nav>
  <a href="#">Home</a>
  <a href="#">About</a>
  <a href="#">Courses</a>
  <a href="#">Contact</a>
</nav>
```

Since links are inline by default, they can appear on the same line.

```text
Home   About   Courses   Contact
```

We can also use Flexbox:

```css
nav {
  display: flex;
  gap: 20px;
}
```

This is a common modern approach for navigation layouts.

---

# 🧪 17. Complete Example

```html
<!DOCTYPE html>
<html>

<head>

  <title>Block and Inline Elements</title>

  <style>

    .block {
      background-color: lightblue;
      padding: 20px;
      margin: 10px 0;
    }

    .inline {
      background-color: yellow;
    }

    .inline-block {
      display: inline-block;
      width: 150px;
      padding: 20px;
      margin: 10px;
      background-color: lightgreen;
    }

  </style>

</head>

<body>

  <h1>Block Elements</h1>

  <div class="block">
    Block 1
  </div>

  <div class="block">
    Block 2
  </div>

  <h1>Inline Element</h1>

  <p>
    This is
    <span class="inline">inline content</span>
    inside a paragraph.
  </p>

  <h1>Inline-Block Elements</h1>

  <div class="inline-block">
    Box 1
  </div>

  <div class="inline-block">
    Box 2
  </div>

  <div class="inline-block">
    Box 3
  </div>

</body>

</html>
```

---

# ⚠️ 18. Important Note

The terms **block** and **inline** describe how elements participate in the CSS layout.

The exact default display behavior comes from the browser's **user-agent stylesheet**, and CSS can change it.

For example:

```css
div {
  display: inline;
}
```

changes the normal behavior of `<div>`.

Similarly:

```css
span {
  display: block;
}
```

changes the normal behavior of `<span>`.

---

# 🧠 19. Quick Revision

```text
                 HTML ELEMENTS
                       │
             ┌─────────┴─────────┐
             ↓                   ↓
           BLOCK               INLINE
             │                   │
        New line            Same line
             │                   │
     Available width       Content width
             │                   │
         <div>              <span>
         <p>                <a>
         <h1>               <strong>
             │
             └──────────┐
                        ↓
                  INLINE-BLOCK
                        │
               Same line + size
                        │
              display: inline-block
```

---

# ❓ 20. Practice Questions

### Q1. What is a block-level element?

### Q2. What is an inline element?

### Q3. Give three examples of block elements.

### Q4. Give three examples of inline elements.

### Q5. What is the difference between `<div>` and `<span>`?

### Q6. What does this CSS do?

```css
div {
  display: inline;
}
```

### Q7. What does this CSS do?

```css
span {
  display: block;
}
```

### Q8. What is `inline-block`?

### Q9. Why is `<span>` useful for styling part of a sentence?

### Q10. What is the difference between `display: block` and `display: inline`?

---

# ⚡ 21. One-Minute Revision

| Concept                 | Remember                                   |
| ----------------------- | ------------------------------------------ |
| **Block**               | Starts on a new line                       |
| **Inline**              | Stays in the same line                     |
| **Inline-block**        | Same line + width/height can be controlled |
| `<div>`                 | Common block element                       |
| `<span>`                | Common inline element                      |
| `display: block`        | Makes an element block-level               |
| `display: inline`       | Makes an element inline                    |
| `display: inline-block` | Inline placement with block-like sizing    |

---

## 📌 One-Line Definition

> **Block elements normally start on a new line and occupy the available width, while inline elements normally stay within the same line and occupy only the space required by their content.**

---

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-E34F26?style=for-the-badge&logo=html5&logoColor=white">
</p>

<p align="center">
  <b>🎓 BCS353 • Web Designing Workshop</b>
</p>

