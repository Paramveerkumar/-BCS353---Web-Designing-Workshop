# ✍️ CSS Text

<p align="center">
  <img src="https://img.shields.io/badge/CSS-Text-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS Text">
</p>

<p align="center">
  <b>📘 Web Designing Workshop</b><br>
  Learn how to control the appearance, alignment, spacing, and decoration of text using CSS.
</p>

---

## 🔰 1. What is CSS Text?

CSS provides several properties to control how **text looks and appears** on a webpage.

Using CSS Text properties, we can control:

* ↔️ Text alignment
* 🎨 Text color
* 📏 Text spacing
* ✨ Text decoration
* 🔤 Text transformation
* 📐 Text indentation
* ↕️ Line spacing
* 📝 Text direction

### 💡 Easy Definition

> **CSS Text properties are used to control the appearance and layout of text on a webpage.**

---

# 🎯 2. Important CSS Text Properties

| Property          | Purpose                        |
| ----------------- | ------------------------------ |
| `color`           | Changes text color             |
| `text-align`      | Aligns text                    |
| `text-decoration` | Adds/removes decoration        |
| `text-transform`  | Changes letter case            |
| `text-indent`     | Indents the first line         |
| `line-height`     | Controls space between lines   |
| `letter-spacing`  | Controls space between letters |
| `word-spacing`    | Controls space between words   |
| `text-shadow`     | Adds shadow to text            |
| `direction`       | Sets text direction            |

---

# 🎨 3. Text Color

The `color` property is used to change the color of text.

### Syntax

```css
selector {
    color: value;
}
```

### Example

```css
p {
    color: blue;
}
```

### HTML Example

```html
<p class="intro">Welcome to CSS!</p>
```

```css
.intro {
    color: blue;
}
```

Result:

> **Welcome to CSS!** 🔵

---

# ↔️ 4. Text Alignment

The `text-align` property is used to specify the **horizontal alignment of text**.

### Common Values

```text
left
center
right
justify
```

### Example

```css
h1 {
    text-align: center;
}
```

The heading will appear in the center.

---

## 🔹 Left Alignment

```css
p {
    text-align: left;
}
```

```text
| This text starts from the left.
|
```

---

## 🔹 Center Alignment

```css
p {
    text-align: center;
}
```

```text
|          This text is centered.          |
```

---

## 🔹 Right Alignment

```css
p {
    text-align: right;
}
```

```text
|              This text is on the right. |
```

---

## 🔹 Justified Text

```css
p {
    text-align: justify;
}
```

`justify` adjusts spacing so that text lines are aligned with both the left and right edges of the containing block.

This is commonly used for paragraphs.

---

# ✨ 5. Text Decoration

The `text-decoration` property is used to add or remove decoration from text.

### Common Values

```text
underline
overline
line-through
none
```

---

## 🔹 Underline

```css
p {
    text-decoration: underline;
}
```

Result:

> <u>This text is underlined.</u>

---

## 🔹 Overline

```css
p {
    text-decoration: overline;
}
```

---

## 🔹 Line Through

```css
p {
    text-decoration: line-through;
}
```

Result:

> ~~This text has a line through it.~~

---

## 🔹 Remove Decoration

```css
a {
    text-decoration: none;
}
```

This is commonly used to remove the default underline from links.

---

# 🔤 6. Text Transformation

The `text-transform` property controls the **case of letters**.

### Common Values

| Value        | Purpose                                   |
| ------------ | ----------------------------------------- |
| `uppercase`  | Converts text to uppercase                |
| `lowercase`  | Converts text to lowercase                |
| `capitalize` | Capitalizes the first letter of each word |
| `none`       | No transformation                         |

---

## 🔹 Uppercase

```css
p {
    text-transform: uppercase;
}
```

```text
hello students
       ↓
HELLO STUDENTS
```

---

## 🔹 Lowercase

```css
p {
    text-transform: lowercase;
}
```

```text
HELLO STUDENTS
       ↓
hello students
```

---

## 🔹 Capitalize

```css
p {
    text-transform: capitalize;
}
```

```text
hello students
       ↓
Hello Students
```

---

# 📐 7. Text Indentation

The `text-indent` property specifies the indentation of the **first line of a text block**.

### Example

```css
p {
    text-indent: 50px;
}
```

Result:

```text
     This is the first line of the paragraph.
The second line starts normally.
The third line starts normally.
```

Only the **first line** is indented.

---

# ↕️ 8. Line Height

The `line-height` property controls the **vertical space between lines of text**.

### Example

```css
p {
    line-height: 1.8;
}
```

### Without Proper Line Height

```text
This is a paragraph.
The lines are very close.
It can be difficult to read.
```

### With More Line Height

```text
This is a paragraph.

The lines have more space.

The paragraph is easier to read.
```

### Another Example

```css
p {
    line-height: 30px;
}
```

Each line gets a line box of approximately `30px` in this example.

---

# 🔠 9. Letter Spacing

The `letter-spacing` property controls the **space between individual characters**.

### Example

```css
h1 {
    letter-spacing: 3px;
}
```

Normal:

```text
WELCOME
```

With letter spacing:

```text
W E L C O M E
```

### Negative Letter Spacing

```css
h1 {
    letter-spacing: -1px;
}
```

This reduces the spacing between characters.

---

# 📝 10. Word Spacing

The `word-spacing` property controls the **space between words**.

### Example

```css
p {
    word-spacing: 10px;
}
```

Normal:

```text
Welcome to CSS
```

With increased word spacing:

```text
Welcome     to     CSS
```

---

# 🌑 11. Text Shadow

The `text-shadow` property adds a shadow behind text.

### Syntax

```css
text-shadow: horizontal vertical blur color;
```

### Example

```css
h1 {
    text-shadow: 2px 2px 4px gray;
}
```

### Understanding the Values

```text
2px → Horizontal shadow
2px → Vertical shadow
4px → Blur
gray → Shadow color
```

### Example

```html
<h1 class="title">CSS Text</h1>
```

```css
.title {
    text-shadow: 2px 2px 4px gray;
}
```

---

# 🧭 12. Text Direction

The `direction` property specifies the direction in which text should flow.

### Left to Right

```css
p {
    direction: ltr;
}
```

`ltr` = **Left To Right**

Used for languages such as English.

### Right to Left

```css
p {
    direction: rtl;
}
```

`rtl` = **Right To Left**

Used for languages such as Arabic and Hebrew.

---

# 🎨 13. Combining CSS Text Properties

We can use multiple text properties together.

### Example

```css
h1 {
    color: darkblue;
    text-align: center;
    text-transform: uppercase;
    letter-spacing: 2px;
    text-shadow: 2px 2px 4px gray;
}
```

This creates a heading that is:

* 🔵 Dark blue
* 🎯 Center aligned
* 🔤 Uppercase
* ↔️ Has letter spacing
* 🌑 Has a text shadow

---

# 💻 14. Complete Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS Text</title>

    <style>
        h1 {
            color: darkblue;
            text-align: center;
            text-transform: uppercase;
            letter-spacing: 2px;
            text-shadow: 2px 2px 4px gray;
        }

        p {
            color: #333;
            text-align: justify;
            line-height: 1.8;
            word-spacing: 5px;
        }

        .important {
            text-decoration: underline;
        }
    </style>
</head>

<body>

    <h1>CSS Text Properties</h1>

    <p>
        CSS provides many properties to control the appearance
        and layout of text on a webpage. These properties make
        webpages easier to read and visually attractive.
    </p>

    <p class="important">
        Practice CSS text properties regularly.
    </p>

</body>
</html>
```

---

# 🧩 15. CSS Text Property Example

Here is a quick example using several properties:

```css
.example {
    color: darkgreen;
    text-align: center;
    text-decoration: underline;
    text-transform: capitalize;
    text-indent: 30px;
    line-height: 1.5;
    letter-spacing: 2px;
    word-spacing: 5px;
    text-shadow: 1px 1px 2px gray;
}
```

---

# 📚 16. Quick Reference Table

| Property          | Example                          | Purpose                |
| ----------------- | -------------------------------- | ---------------------- |
| `color`           | `color: blue;`                   | Text color             |
| `text-align`      | `text-align: center;`            | Text alignment         |
| `text-decoration` | `text-decoration: underline;`    | Text decoration        |
| `text-transform`  | `text-transform: uppercase;`     | Letter case            |
| `text-indent`     | `text-indent: 30px;`             | First-line indentation |
| `line-height`     | `line-height: 1.5;`              | Space between lines    |
| `letter-spacing`  | `letter-spacing: 2px;`           | Space between letters  |
| `word-spacing`    | `word-spacing: 5px;`             | Space between words    |
| `text-shadow`     | `text-shadow: 2px 2px 4px gray;` | Text shadow            |
| `direction`       | `direction: rtl;`                | Text direction         |

---

# 🆚 17. Text Alignment vs Text Indentation

Students often confuse these properties.

| Property      | Purpose                                           |
| ------------- | ------------------------------------------------- |
| `text-align`  | Moves/aligns the entire text within its container |
| `text-indent` | Adds space before the first line                  |

### Example

```css
p {
    text-align: center;
    text-indent: 30px;
}
```

These two properties perform **different jobs**.

---

# 🧠 18. Easy Memory Trick

Remember:

```text
COLOR        → What color?
ALIGN        → Where?
DECORATION   → Underline/line?
TRANSFORM    → Upper/lower case?
INDENT       → First line?
LINE HEIGHT  → Line-to-line space?
LETTER SPACE → Character-to-character space?
WORD SPACE   → Word-to-word space?
SHADOW       → Shadow behind text?
```

---

# 🎯 19. Practice Questions

### Q1. What is the purpose of CSS text properties?

### Q2. What is the difference between `text-align` and `text-indent`?

### Q3. Write CSS to center a heading.

### Q4. How can you underline text using CSS?

### Q5. What does `text-transform: uppercase;` do?

### Q6. What is the purpose of `line-height`?

### Q7. What is the difference between `letter-spacing` and `word-spacing`?

### Q8. Write CSS to create a heading with:

* Blue text
* Center alignment
* Uppercase letters
* 2px letter spacing

### Q9. What does `text-shadow` do?

### Q10. What is the difference between `direction: ltr` and `direction: rtl`?

---

# ⭐ 20. Quick Revision

```text
┌─────────────────────────────────────────┐
│            ✍️ CSS TEXT                  │
├─────────────────────────────────────────┤
│                                         │
│  color           → Text color           │
│  text-align      → Text alignment       │
│  text-decoration → Text decoration      │
│  text-transform  → Letter case          │
│  text-indent     → First-line spacing   │
│  line-height     → Line spacing         │
│  letter-spacing  → Letter spacing      │
│  word-spacing    → Word spacing        │
│  text-shadow     → Text shadow         │
│  direction       → Text direction      │
│                                         │
└─────────────────────────────────────────┘
```

> 💡 **Easy Definition:**
> **CSS Text properties control the appearance, alignment, spacing, and decoration of text on a webpage.**

---

## 🚀 One-Minute Revision

```css
p {
    color: blue;
    text-align: center;
    text-decoration: underline;
    text-transform: uppercase;
    line-height: 1.5;
    letter-spacing: 2px;
    word-spacing: 5px;
}
```

### Remember:

> 🎨 **Color → Alignment → Decoration → Transformation → Spacing → Shadow**

<p align="center">
  <b>🎨 CSS → Text → Style → Align → Space → Decorate ✍️</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Web%20Designing-CSS%20Text-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS Text">
</p>

