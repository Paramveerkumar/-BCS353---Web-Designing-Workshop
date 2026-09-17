# 🔤 CSS Fonts

<p align="center">
  <img src="https://img.shields.io/badge/CSS-Fonts-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS Fonts">
</p>

<p align="center">
  <b>📘 Web Designing Workshop</b><br>
  Learn how to control the typeface, size, style, weight, and appearance of text using CSS.
</p>

---

## 🔰 1. What are CSS Fonts?

CSS provides properties to control the **font used to display text** on a webpage.

Using CSS font properties, we can control:

* 🔤 Font type
* 📏 Font size
* ⚖️ Font weight
* ✨ Font style
* 📝 Font variant
* 📐 Font size adjustment

### 💡 Easy Definition

> **CSS Font properties are used to control the appearance and style of text.**

---

# 🎯 2. Important CSS Font Properties

| Property       | Purpose                                |
| -------------- | -------------------------------------- |
| `font-family`  | Specifies the typeface                 |
| `font-size`    | Sets the size of text                  |
| `font-style`   | Makes text normal, italic, etc.        |
| `font-weight`  | Controls the thickness of text         |
| `font-variant` | Controls small-cap text                |
| `font`         | Shorthand for multiple font properties |

---

# 🔤 3. `font-family`

The `font-family` property specifies the **font/typeface** used for text.

### Syntax

```css
selector {
    font-family: font-name;
}
```

### Example

```css
p {
    font-family: Arial;
}
```

Now the paragraph uses the **Arial** font if it is available.

---

# 🛡️ 4. Font Fallback

Different computers may have different fonts installed.

Therefore, it is good practice to provide **fallback fonts**.

```css
p {
    font-family: Arial, Helvetica, sans-serif;
}
```

The browser checks the fonts from **left to right**:

```text
Arial
  ↓
If unavailable
  ↓
Helvetica
  ↓
If unavailable
  ↓
sans-serif
```

### 💡 Why use fallback fonts?

If the first font is not available, the browser can use another suitable font.

---

# 🧩 5. Generic Font Families

CSS provides generic font families that act as broad categories.

| Generic Family | Description                         |
| -------------- | ----------------------------------- |
| `serif`        | Has small finishing strokes         |
| `sans-serif`   | Does not have finishing strokes     |
| `monospace`    | Each character has equal width      |
| `cursive`      | Handwriting-style appearance        |
| `fantasy`      | Decorative font style               |
| `system-ui`    | Uses the operating system's UI font |

---

## 🔹 Serif

Example:

```css
p {
    font-family: Georgia, serif;
}
```

```text
Example Text
```

Serif fonts have small strokes at the ends of characters.

---

## 🔹 Sans-serif

Example:

```css
p {
    font-family: Arial, sans-serif;
}
```

Sans-serif fonts do not have those finishing strokes.

They are commonly used for modern websites.

---

## 🔹 Monospace

Example:

```css
code {
    font-family: "Courier New", monospace;
}
```

In a monospace font, characters generally occupy equal horizontal space.

It is commonly used for:

* 💻 Programming code
* Terminal text
* Technical content

---

# 📏 6. `font-size`

The `font-size` property controls the **size of text**.

### Example

```css
p {
    font-size: 20px;
}
```

This makes the paragraph text `20px` in size.

---

## 🔹 Using Pixels

```css
h1 {
    font-size: 32px;
}
```

---

## 🔹 Using `em`

`em` is relative to the font size of the element's parent.

```css
p {
    font-size: 1.5em;
}
```

If the relevant parent font size is `16px`:

```text
1.5 × 16px = 24px
```

---

## 🔹 Using `rem`

`rem` is relative to the **root (`html`) font size**.

```css
p {
    font-size: 1.5rem;
}
```

If:

```css
html {
    font-size: 16px;
}
```

then:

```text
1.5rem = 24px
```

### 🧠 Easy Difference

```text
em  → Relative to parent/context
rem → Relative to root HTML element
```

---

## 🔹 Using Percentage

```css
p {
    font-size: 120%;
}
```

This sets the font size relative to the inherited/parent font size.

---

# ✨ 7. `font-style`

The `font-style` property specifies whether text should be displayed normally or with an italic/slanted style.

### Common Values

```text
normal
italic
oblique
```

### Example

```css
p {
    font-style: italic;
}
```

Result:

> *This text is italic.*

---

## 🔹 Normal

```css
p {
    font-style: normal;
}
```

---

## 🔹 Italic

```css
p {
    font-style: italic;
}
```

---

## 🔹 Oblique

```css
p {
    font-style: oblique;
}
```

`oblique` uses a slanted version of the font when available.

---

# ⚖️ 8. `font-weight`

The `font-weight` property controls the **thickness of text**.

### Common Values

```text
normal
bold
100
200
300
400
500
600
700
800
900
```

### Example

```css
p {
    font-weight: bold;
}
```

Result:

> **This text is bold.**

---

## 📊 Font Weight Scale

```text
100 → Thin
200 → Extra Light
300 → Light
400 → Normal
500 → Medium
600 → Semi Bold
700 → Bold
800 → Extra Bold
900 → Black
```

Actual appearance depends on the font and the weights it provides.

### Example

```css
h1 {
    font-weight: 700;
}
```

---

# 🔠 9. `font-variant`

The `font-variant` property can be used to display text in **small caps**.

### Example

```css
p {
    font-variant: small-caps;
}
```

Text such as:

```text
Web Designing
```

can be displayed with a small-caps appearance.

### Common Values

```css
font-variant: normal;
font-variant: small-caps;
```

---

# 🧩 10. CSS `font` Shorthand

Instead of writing several font properties separately, CSS provides the `font` shorthand property.

For example:

```css
p {
    font-style: italic;
    font-weight: bold;
    font-size: 20px;
    font-family: Arial, sans-serif;
}
```

This can be shortened to:

```css
p {
    font: italic bold 20px Arial, sans-serif;
}
```

### 💡 Basic Pattern

```text
font: style weight size family;
```

Example:

```css
font: italic bold 20px Arial, sans-serif;
```

---

# 📚 11. CSS Font Properties Summary

| Property       | Example                  | Purpose              |
| -------------- | ------------------------ | -------------------- |
| `font-family`  | `Arial, sans-serif`      | Font type            |
| `font-size`    | `20px`                   | Font size            |
| `font-style`   | `italic`                 | Font style           |
| `font-weight`  | `bold`                   | Font thickness       |
| `font-variant` | `small-caps`             | Small-cap appearance |
| `font`         | `italic bold 20px Arial` | Shorthand            |

---

# 🎨 12. Combining Font Properties

We can combine multiple properties to create attractive text.

```css
h1 {
    font-family: Arial, sans-serif;
    font-size: 36px;
    font-style: normal;
    font-weight: 700;
}
```

This creates a heading with:

* 🔤 Arial font
* 📏 36px size
* ✨ Normal style
* ⚖️ Bold weight

---

# 💻 13. Complete Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS Fonts</title>

    <style>
        h1 {
            font-family: Arial, sans-serif;
            font-size: 36px;
            font-weight: 700;
        }

        p {
            font-family: Georgia, serif;
            font-size: 18px;
            font-style: italic;
            line-height: 1.6;
        }

        .code {
            font-family: "Courier New", monospace;
            font-size: 16px;
        }
    </style>
</head>

<body>

    <h1>CSS Fonts</h1>

    <p>
        CSS allows us to control the appearance of text
        using different font properties.
    </p>

    <p class="code">
        This text uses a monospace font.
    </p>

</body>
</html>
```

---

# 🖥️ 14. Font Family Comparison

```text
Arial
This is Arial.

Georgia
This is Georgia.

Courier New
This is Courier New.

Monospace
This is Monospace.
```

Different fonts can give a webpage a completely different appearance.

---

# 🌐 15. Using Web Fonts

Sometimes we want to use a font that may not be installed on the user's computer.

A common approach is to load a web font.

For example, with Google Fonts:

```html
<link
    href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap"
    rel="stylesheet">
```

Then use it:

```css
body {
    font-family: "Poppins", sans-serif;
}
```

### 💡 Important

A web font is downloaded by the browser so that the webpage can display the selected typeface.

---

# 🧠 16. Font Size vs Font Weight

Students often confuse these two properties.

| Property      | Controls              |
| ------------- | --------------------- |
| `font-size`   | How large the text is |
| `font-weight` | How thick the text is |

### Example

```css
h1 {
    font-size: 40px;
    font-weight: bold;
}
```

```text
font-size  →  LARGE
font-weight → THICK
```

---

# 🆚 17. Font Style vs Font Weight

| Property      | Example  | Meaning                   |
| ------------- | -------- | ------------------------- |
| `font-style`  | `italic` | Slanted/italic appearance |
| `font-weight` | `bold`   | Thickness                 |

Example:

```css
p {
    font-style: italic;
    font-weight: bold;
}
```

Result:

> ***Bold and italic text***

---

# 🎯 18. Practical Website Example

Let's create a simple webpage heading and paragraph.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Student Webpage</title>

    <style>
        body {
            font-family: Arial, sans-serif;
        }

        h1 {
            font-size: 36px;
            font-weight: 700;
        }

        p {
            font-size: 18px;
            font-style: normal;
        }
    </style>
</head>

<body>

    <h1>Welcome to Web Designing</h1>

    <p>
        CSS helps us control the appearance of text,
        including its font, size, style, and weight.
    </p>

</body>
</html>
```

---

# 🧠 19. Easy Memory Trick

Remember:

```text
FAMILY  → Which font?
SIZE    → How big?
STYLE   → Italic or normal?
WEIGHT  → How thick?
VARIANT → Small caps?
FONT    → Shorthand?
```

### ⭐ Think of it like this:

> **Family → Size → Style → Weight**

---

# 🎯 20. Practice Questions

### Q1. What is the purpose of `font-family`?

### Q2. Why should we provide fallback fonts?

### Q3. What is the difference between `font-size` and `font-weight`?

### Q4. What does `font-style: italic;` do?

### Q5. What is a generic font family?

### Q6. Name any three generic font families.

### Q7. What is the difference between `em` and `rem`?

### Q8. What does `font-variant: small-caps;` do?

### Q9. Write CSS to create text with:

* Arial font
* 24px size
* Bold weight
* Italic style

### Q10. Convert the following into shorthand:

```css
font-style: italic;
font-weight: bold;
font-size: 20px;
font-family: Arial, sans-serif;
```

---

# ⭐ 21. Quick Revision

```text
┌──────────────────────────────────────────┐
│              🔤 CSS FONTS                │
├──────────────────────────────────────────┤
│                                          │
│ font-family  → Font type                 │
│ font-size    → Text size                 │
│ font-style   → Normal / Italic / Oblique │
│ font-weight  → Text thickness            │
│ font-variant → Small caps                │
│ font         → Shorthand                 │
│                                          │
└──────────────────────────────────────────┘
```

### 🚀 One-Minute Revision

```css
p {
    font-family: Arial, sans-serif;
    font-size: 20px;
    font-style: italic;
    font-weight: bold;
}
```

> 💡 **Easy Definition:**
> **CSS Font properties control the typeface, size, style, and thickness of text on a webpage.**

---

<p align="center">
  <b>🔤 CSS → Fonts → Family → Size → Style → Weight</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Web%20Designing-CSS%20Fonts-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS Fonts">
</p>

<p align="center">
  <b>📘 BCS353 • Web Designing Workshop</b>
</p>

