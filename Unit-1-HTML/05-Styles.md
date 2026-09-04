# 🎨 HTML Styles

## 📚 Introduction

HTML is used to create the **structure** of a webpage, while styles are used to control the **appearance** of HTML elements.

The HTML `style` attribute allows us to apply styles directly to an HTML element.

Using styles, we can change:

* 🎨 Text color
* 🖼️ Background color
* 🔤 Font type
* 📏 Text size
* 📍 Text alignment

---

# 📝 The HTML `style` Attribute

The `style` attribute is used to add CSS styling directly to an HTML element.

### Syntax

```html
<tagname style="property: value;">
```

Where:

* **tagname** → The HTML element to style.
* **property** → The CSS property you want to change.
* **value** → The value assigned to that property.

---

## 💡 General Example

```html
<p style="color: red;">
    This text is red.
</p>
```

In this example:

```text
color  → Property
red    → Value
```

---

# 🎨 1. Text Color

The CSS `color` property is used to change the color of text.

### Example

```html
<h1 style="color: blue;">
    Welcome Students
</h1>

<p style="color: red;">
    This paragraph is displayed in red.
</p>
```

### Another Example

```html
<h2 style="color: green;">
    Web Designing Workshop
</h2>
```

---

# 🖼️ 2. Background Color

The `background-color` property is used to change the background color of an HTML element.

## Example: Background Color for the Entire Page

```html
<body style="background-color: lightblue;">

    <h1>Welcome to My Website</h1>

    <p>This webpage has a light blue background.</p>

</body>
```

---

## Example: Background Color for Individual Elements

```html
<h1 style="background-color: yellow;">
    HTML
</h1>

<p style="background-color: lightgreen;">
    HTML is used to create the structure of webpages.
</p>
```

Each element can have its own background color.

---

# 🔤 3. Font Family

The `font-family` property defines the type of font used for text.

### Example

```html
<h1 style="font-family: Arial;">
    Computer Science Department
</h1>

<p style="font-family: Courier New;">
    Welcome to the Web Designing Workshop.
</p>
```

Different fonts can give text a different appearance.

---

# 📏 4. Font Size

The `font-size` property is used to change the size of text.

### Example

```html
<h1 style="font-size: 50px;">
    Welcome Students
</h1>

<p style="font-size: 20px;">
    This is a paragraph with larger text.
</p>
```

Font size can also be specified using percentages.

```html
<h1 style="font-size: 300%;">
    HTML
</h1>

<p style="font-size: 150%;">
    Web Designing
</p>
```

---

# 📍 5. Text Alignment

The `text-align` property is used to control the horizontal alignment of text.

Common values include:

* `left`
* `center`
* `right`

### Example

```html
<h1 style="text-align: center;">
    Welcome to My College
</h1>

<p style="text-align: center;">
    Department of Computer Science and Engineering
</p>
```

---

## Different Text Alignments

```html
<p style="text-align: left;">
    This text is aligned to the left.
</p>

<p style="text-align: center;">
    This text is aligned to the center.
</p>

<p style="text-align: right;">
    This text is aligned to the right.
</p>
```

---

# 💻 Complete Example

The following program demonstrates different HTML styles.

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML Styles</title>
</head>

<body style="background-color: lightyellow;">

    <h1 style="color: blue; text-align: center;">
        Welcome to Web Designing
    </h1>

    <h2 style="color: green;">
        HTML Styles
    </h2>

    <p style="color: red; font-size: 20px;">
        HTML allows us to apply styles to elements.
    </p>

    <p style="font-family: Arial; font-size: 18px;">
        CSS properties can change the appearance of text.
    </p>

    <h2 style="background-color: lightblue;">
        Computer Science Department
    </h2>

</body>

</html>
```

---

# 🧠 Multiple Styles in One Element

We can apply multiple CSS properties to a single HTML element.

### Example

```html
<h1 style="color: white; background-color: blue; text-align: center;">
    Online Book Store
</h1>
```

In this example, three styles are applied:

```text
color              → white text
background-color   → blue background
text-align         → center alignment
```

Each property is separated using a semicolon (`;`).

---

# 🔍 Understanding Property and Value

Consider the following example:

```html
<p style="color: red;">
    Hello Students
</p>
```

The structure is:

```text
style="property: value;"
```

Therefore:

```text
style="color: red;"
       │       │
       │       └── Value
       │
       └────────── Property
```

---

# 📊 Important Style Properties

| CSS Property       | Purpose                  | Example                     |
| ------------------ | ------------------------ | --------------------------- |
| `color`            | Changes text color       | `color: blue;`              |
| `background-color` | Changes background color | `background-color: yellow;` |
| `font-family`      | Changes font type        | `font-family: Arial;`       |
| `font-size`        | Changes text size        | `font-size: 30px;`          |
| `text-align`       | Aligns text              | `text-align: center;`       |

---

# 🧪 Practice Program

Create a webpage using different HTML styles.

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML Style Practice</title>
</head>

<body style="background-color: lightgray;">

    <h1 style="color: blue; text-align: center;">
        My College Website
    </h1>

    <h2 style="color: green;">
        About the College
    </h2>

    <p style="font-size: 20px;">
        Welcome to our college website.
    </p>

    <h2 style="background-color: yellow; text-align: center;">
        Departments
    </h2>

    <p style="font-family: Arial; color: purple;">
        Computer Science and Engineering
    </p>

    <p style="font-family: Courier New; color: brown;">
        Electronics and Communication Engineering
    </p>

</body>

</html>
```

---

# 🎯 HTML vs CSS

Students should remember:

```text
HTML
↓
Creates Structure

CSS
↓
Controls Appearance
```

### Example

```html
<h1>Welcome</h1>
```

HTML creates the heading.

```html
<h1 style="color: blue;">
    Welcome
</h1>
```

The style changes its appearance.

---

# 📌 Important Points

### 1️⃣ Use `color` for Text Color

```html
<p style="color: red;">Hello</p>
```

---

### 2️⃣ Use `background-color` for Background

```html
<p style="background-color: yellow;">
    Hello
</p>
```

---

### 3️⃣ Use `font-family` for Font Type

```html
<p style="font-family: Arial;">
    Hello
</p>
```

---

### 4️⃣ Use `font-size` for Text Size

```html
<p style="font-size: 25px;">
    Hello
</p>
```

---

### 5️⃣ Use `text-align` for Alignment

```html
<p style="text-align: center;">
    Hello
</p>
```

---

# 🎯 Chapter Summary

After completing this topic, students should understand:

* ✅ The `style` attribute is used to apply styles to HTML elements.
* ✅ CSS properties define what appearance should be changed.
* ✅ `color` changes the text color.
* ✅ `background-color` changes the background color.
* ✅ `font-family` changes the font.
* ✅ `font-size` changes the text size.
* ✅ `text-align` changes text alignment.
* ✅ Multiple styles can be applied to one element.

---

# 🧠 Quick Revision

```text
HTML STYLE ATTRIBUTE
        │
        ▼
style="property: value;"
        │
        ├── color
        │
        ├── background-color
        │
        ├── font-family
        │
        ├── font-size
        │
        └── text-align
```

---

# ❓ Viva Questions

1. What is the purpose of the `style` attribute?
2. What is the syntax of the `style` attribute?
3. Which property is used to change text color?
4. Which property is used to change the background color?
5. Which property is used to change the font type?
6. Which property is used to change text size?
7. Which property is used to align text?
8. How can multiple styles be applied to one HTML element?
9. What is the difference between HTML and CSS?
10. What is a CSS property?

---

# ⭐ Remember

> **HTML creates the structure of a webpage.**

> **CSS controls the appearance of a webpage.**

> **The `style` attribute allows CSS properties to be applied directly to HTML elements.**

