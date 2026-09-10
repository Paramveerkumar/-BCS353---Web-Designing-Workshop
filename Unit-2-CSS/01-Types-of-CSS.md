# 🎨 Types of CSS

![HTML](https://img.shields.io/badge/HTML-5-orange)
![CSS](https://img.shields.io/badge/CSS-3-blue)
![Level](https://img.shields.io/badge/Level-Beginner-green)

---

## 🎯 Aim

To study and understand the **different types of CSS (Cascading Style Sheets)** and their implementation in HTML web pages.

---

## 📚 Introduction

**CSS (Cascading Style Sheets)** is a stylesheet language used to control the appearance and layout of HTML web pages.

CSS is used to change:

* Text color
* Font size
* Font style
* Background color
* Borders
* Width and height
* Text alignment
* Page layout
* Spacing between elements

There are **three main types of CSS**:

1. **Inline CSS**
2. **Internal CSS**
3. **External CSS**

---

# 1️⃣ Inline CSS

## 📖 Definition

**Inline CSS** is CSS written directly inside an HTML element using the `style` attribute.

## 💻 Program

```html
<!DOCTYPE html>
<html>
<head>
    <title>Inline CSS</title>
</head>

<body>

    <h1 style="color: blue;">Welcome to My Website</h1>

    <p style="color: green; font-size: 20px;">
        This paragraph uses Inline CSS.
    </p>

</body>
</html>
```

## 🔍 Explanation

The following code:

```html
<h1 style="color: blue;">
```

means that the `<h1>` heading will have **blue text**.

The following code:

```html
<p style="color: green; font-size: 20px;">
```

applies two CSS properties:

* `color: green` → changes text color to green.
* `font-size: 20px` → changes the font size to 20 pixels.

### CSS Structure

```text
style="property: value;"
```

Example:

```text
style="color: blue;"
       │       │
       │       └── Value
       └────────── Property
```

## ✅ Advantages

* Easy to understand
* Easy to apply
* Useful for styling a single HTML element
* No separate CSS file is required

## ❌ Disadvantages

* Makes HTML code lengthy
* Difficult to maintain
* Cannot be easily reused
* Not suitable for large websites

---

# 2️⃣ Internal CSS

## 📖 Definition

**Internal CSS** is written inside the `<style>` tag in the `<head>` section of an HTML document.

## 💻 Program

```html
<!DOCTYPE html>
<html>

<head>

    <title>Internal CSS</title>

    <style>

        body {
            background-color: lightyellow;
        }

        h1 {
            color: blue;
            text-align: center;
        }

        p {
            color: green;
            font-size: 20px;
        }

    </style>

</head>

<body>

    <h1>Welcome to My Website</h1>

    <p>This paragraph uses Internal CSS.</p>

</body>

</html>
```

## 🔍 Explanation

The CSS is written inside:

```html
<style>
    ...
</style>
```

The `<style>` tag is generally placed inside the `<head>` section.

### Example

```css
h1 {
    color: blue;
    text-align: center;
}
```

Here:

| CSS Part     | Meaning      |
| ------------ | ------------ |
| `h1`         | Selector     |
| `color`      | CSS Property |
| `blue`       | CSS Value    |
| `text-align` | CSS Property |
| `center`     | CSS Value    |

---

## 🧩 CSS Syntax

The basic CSS syntax is:

```css
selector {
    property: value;
}
```

Example:

```css
p {
    color: green;
    font-size: 20px;
}
```

### Explanation

```text
p
│
└── Selector

color: green;
│       │
│       └── Value
└────────── Property

font-size: 20px;
│          │
│          └── Value
└───────────── Property
```

## ✅ Advantages

* Easy to write
* Useful for styling a single web page
* Multiple elements can use the same CSS rules
* Cleaner than using many inline styles

## ❌ Disadvantages

* Cannot be easily reused across different HTML files
* Increases the size of the HTML file
* Not ideal for large websites

---

# 3️⃣ External CSS

## 📖 Definition

**External CSS** is written in a separate file with the `.css` extension.

The CSS file is connected to the HTML page using the `<link>` tag.

External CSS is commonly preferred when a website contains multiple pages.

---

## 📁 Project Structure

```text
MyWebsite/
│
├── index.html
│
└── style.css
```

---

## 💻 HTML File — `index.html`

```html
<!DOCTYPE html>
<html>

<head>

    <title>External CSS</title>

    <link rel="stylesheet" href="style.css">

</head>

<body>

    <h1>Welcome to My Website</h1>

    <p>This page uses External CSS.</p>

</body>

</html>
```

---

## 💻 CSS File — `style.css`

```css
body {
    background-color: lightblue;
}

h1 {
    color: darkblue;
    text-align: center;
}

p {
    color: green;
    font-size: 20px;
}
```

---

## 🔍 Explanation

The following line connects the HTML file with the external CSS file:

```html
<link rel="stylesheet" href="style.css">
```

### Important Attributes

| Attribute          | Meaning                                        |
| ------------------ | ---------------------------------------------- |
| `link`             | Connects an external resource                  |
| `rel="stylesheet"` | Specifies that the linked file is a stylesheet |
| `href="style.css"` | Specifies the location of the CSS file         |

If the CSS file is inside a folder:

```text
MyWebsite/
│
├── index.html
│
└── css/
    └── style.css
```

Then use:

```html
<link rel="stylesheet" href="css/style.css">
```

---

# 🔄 How External CSS Works

```text
        index.html
             |
             |
       <link> tag
             |
             ↓
         style.css
             |
             ↓
       CSS properties
             |
             ↓
        Styled Page
```

---

## ✅ Advantages

* Easy to maintain
* CSS can be reused
* One CSS file can style multiple HTML pages
* Keeps HTML code clean
* Suitable for large websites
* Avoids repeating the same CSS code

## ❌ Disadvantages

* Requires a separate CSS file
* Incorrect file paths can prevent styles from loading
* Requires management of an additional file

---

# 🆚 Comparison of Three Types of CSS

| Feature                 | Inline CSS          | Internal CSS         | External CSS         |
| ----------------------- | ------------------- | -------------------- | -------------------- |
| Location                | Inside HTML element | Inside `<style>` tag | Separate `.css` file |
| Main Method             | `style=""`          | `<style>`            | `<link>`             |
| Reusability             | Low                 | Medium               | High                 |
| Maintenance             | Difficult           | Moderate             | Easy                 |
| Suitable for            | One element         | One page             | Multiple pages       |
| Separate file           | No                  | No                   | Yes                  |
| Best for large websites | ❌                   | ❌                    | ✅                    |

---

# 🧠 Easy Way to Remember

```text
                 TYPES OF CSS
                      |
          ┌───────────┼───────────┐
          ↓           ↓           ↓
       INLINE      INTERNAL    EXTERNAL
          |           |           |
       style=""     <style>     style.css
          |           |           |
      One Element   One Page   Multiple Pages
```

---

# 💡 Example of All Three Types

## Inline CSS

```html
<p style="color: red;">
    This is Inline CSS.
</p>
```

---

## Internal CSS

```html
<style>

    h1 {
        color: blue;
    }

</style>
```

---

## External CSS

### HTML

```html
<link rel="stylesheet" href="style.css">
```

### CSS

```css
body {
    background-color: lightgreen;
}
```

---

# 🔥 Important CSS Properties

| Property           | Purpose                  | Example                     |
| ------------------ | ------------------------ | --------------------------- |
| `color`            | Changes text color       | `color: red;`               |
| `background-color` | Changes background color | `background-color: yellow;` |
| `font-size`        | Changes font size        | `font-size: 20px;`          |
| `font-family`      | Changes font             | `font-family: Arial;`       |
| `text-align`       | Aligns text              | `text-align: center;`       |
| `border`           | Adds border              | `border: 1px solid black;`  |
| `width`            | Sets width               | `width: 500px;`             |
| `height`           | Sets height              | `height: 200px;`            |

---

# ⚠️ Common Mistakes

## 1. Forgetting the Semicolon

❌ Incorrect:

```css
p {
    color: red
    font-size: 20px
}
```

✅ Correct:

```css
p {
    color: red;
    font-size: 20px;
}
```

---

## 2. Incorrect CSS File Name

If the HTML contains:

```html
<link rel="stylesheet" href="style.css">
```

the CSS file should be named:

```text
style.css
```

---

## 3. Incorrect File Path

If the CSS file is inside a folder:

```text
project/
│
├── index.html
└── css/
    └── style.css
```

Use:

```html
<link rel="stylesheet" href="css/style.css">
```

---

## 4. Forgetting the `<style>` Tag

For Internal CSS, the CSS must be placed inside:

```html
<style>

    h1 {
        color: blue;
    }

</style>
```

---

# 🎓 Viva Questions and Answers

### Q1. What is CSS?

**Answer:**
CSS stands for **Cascading Style Sheets**. It is used to style and design HTML web pages.

---

### Q2. How many types of CSS are there?

**Answer:**
There are three main types:

1. Inline CSS
2. Internal CSS
3. External CSS

---

### Q3. What is Inline CSS?

**Answer:**
Inline CSS is written directly inside an HTML element using the `style` attribute.

Example:

```html
<p style="color: red;">Hello</p>
```

---

### Q4. What is Internal CSS?

**Answer:**
Internal CSS is written inside the `<style>` tag in the `<head>` section of an HTML document.

---

### Q5. What is External CSS?

**Answer:**
External CSS is written in a separate `.css` file and connected to an HTML document using the `<link>` tag.

---

### Q6. Which type of CSS is best for multiple web pages?

**Answer:**
**External CSS** is best because one CSS file can be used by multiple HTML pages.

---

### Q7. Which attribute is used for Inline CSS?

**Answer:**
The `style` attribute.

---

### Q8. Which tag is used for Internal CSS?

**Answer:**

```html
<style>
```

---

### Q9. Which tag is used to connect External CSS?

**Answer:**

```html
<link>
```

---

### Q10. What is the extension of a CSS file?

**Answer:**

```text
.css
```

Example:

```text
style.css
```

---

### Q11. What is a CSS selector?

**Answer:**
A CSS selector identifies the HTML element to which the CSS rules should be applied.

Example:

```css
p {
    color: red;
}
```

Here, `p` is the selector.

---

### Q12. What is a CSS property?

**Answer:**
A CSS property specifies what aspect of an HTML element should be changed.

Example:

```css
color
```

---

### Q13. What is a CSS value?

**Answer:**
A CSS value specifies the setting given to a CSS property.

Example:

```css
color: blue;
```

Here, `blue` is the value.

---

# ⭐ Key Points

* CSS stands for **Cascading Style Sheets**.
* CSS is used to style HTML web pages.
* There are **three main types of CSS**.
* Inline CSS uses the `style` attribute.
* Internal CSS uses the `<style>` tag.
* External CSS uses a separate `.css` file.
* The `<link>` tag connects an external CSS file to HTML.
* External CSS provides better reusability.
* External CSS is generally preferred for larger websites.
* CSS follows the basic syntax:

```css
selector {
    property: value;
}
```

---

# 📝 Result

Thus, the **three types of CSS — Inline CSS, Internal CSS, and External CSS** were studied and successfully implemented using HTML examples.

---

# 📌 Conclusion

CSS is an important part of web development because it separates the **content of a web page from its presentation**.

The three types of CSS are:

| Type             | Usage                             |
| ---------------- | --------------------------------- |
| **Inline CSS**   | Styling a particular HTML element |
| **Internal CSS** | Styling a single HTML page        |
| **External CSS** | Styling multiple HTML pages       |

For small changes, Inline CSS can be useful. Internal CSS is suitable for a single page, while External CSS is generally the best choice for larger websites because it is reusable and easier to maintain.

---

## 📂 Recommended GitHub Project Structure

```text
CSS-Experiment/
│
├── types-of-css.md
├── index.html
├── style.css
│
└── images/
    └── image.png
```


