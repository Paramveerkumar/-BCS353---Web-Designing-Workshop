# 📄 HTML Paragraphs

## 📚 Introduction

A **paragraph** is a block of text used to organize written content on a webpage.

In HTML, paragraphs are created using the `<p>` element.

A paragraph:

* Usually starts on a new line.
* Is used to display a block of text.
* Has some default spacing before and after it in most browsers.

---

# 📝 HTML Paragraphs

The HTML `<p>` element defines a paragraph.

### Syntax

```html
<p>Paragraph content goes here.</p>
```

### Example

```html
<p>This is a paragraph.</p>

<p>This is another paragraph.</p>
```

### Output

```text
This is a paragraph.

This is another paragraph.
```

Each paragraph is displayed separately.

---

# 💻 Complete Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML Paragraph Example</title>
</head>

<body>

    <h1>Welcome to My Website</h1>

    <p>
        This is the first paragraph of the webpage.
    </p>

    <p>
        This is the second paragraph of the webpage.
    </p>

</body>

</html>
```

---

# 🖥️ How Browsers Display HTML

HTML webpages can be displayed on different devices, such as:

* Desktop computers
* Laptops
* Tablets
* Mobile phones

Because screen sizes can be different, the appearance of content may change depending on the available screen space.

---

# ⚠️ Extra Spaces and Lines in HTML

Browsers automatically handle extra spaces and line breaks in normal HTML text.

Consider the following example:

```html
<p>
This paragraph
contains many lines
in the HTML source code,
but the browser displays
it as normal paragraph text.
</p>
```

Although the text is written on multiple lines in the HTML file, the browser normally displays it as one continuous paragraph.

---

## Another Example

```html
<p>
This paragraph contains          many spaces
and multiple          spaces in the source code.
</p>
```

The browser normally collapses multiple spaces into a single space.

### Important Point

> 💡 In normal HTML text, extra spaces and line breaks in the source code are generally not displayed exactly as written.

---

# ➖ HTML Horizontal Rules

The `<hr>` element creates a thematic separation between sections of content.

It is commonly displayed as a horizontal line.

### Example

```html
<h1>Computer Science</h1>

<p>
Computer Science focuses on computers, programming, and software development.
</p>

<hr>

<h2>Web Designing</h2>

<p>
Web Designing focuses on creating and designing webpages.
</p>
```

---

## Visual Structure

```text
Computer Science

Computer Science focuses on computers, programming, and software development.

────────────────────────────────────

Web Designing

Web Designing focuses on creating and designing webpages.
```

---

# 📌 Important Point About `<hr>`

The `<hr>` element is an **empty element**.

It does not contain content and does not require a closing tag.

```html
<hr>
```

---

# ↩️ HTML Line Breaks

The `<br>` element inserts a **line break**.

Use `<br>` when you want to move text to a new line without creating a new paragraph.

### Example

```html
<p>
Computer Science Department<br>
ABC College<br>
India
</p>
```

### Output

```text
Computer Science Department
ABC College
India
```

---

# 🆚 Paragraph vs Line Break

Students often confuse `<p>` and `<br>`.

## Using Paragraphs

```html
<p>Welcome Students.</p>

<p>This is the Web Designing Workshop.</p>
```

The two pieces of text are separate paragraphs.

---

## Using Line Breaks

```html
Welcome Students.<br>
This is the Web Designing Workshop.
```

The text moves to the next line without creating a new paragraph structure.

---

# 📊 Difference Between `<p>` and `<br>`

| `<p>`                        | `<br>`                      |
| ---------------------------- | --------------------------- |
| Defines a paragraph          | Inserts a line break        |
| Creates a block of text      | Moves text to the next line |
| Has opening and closing tags | Empty element               |
| Used for paragraphs          | Used for line breaks        |

---

# 📜 The Problem with Preserving Spaces

Suppose you write a poem or formatted text like this:

```html
<p>
Learning HTML is fun.

We create webpages
using different elements.

HTML provides structure
for our website.
</p>
```

The browser will not necessarily preserve the formatting exactly as written in the source code.

---

# ✅ Solution: The `<pre>` Element

The HTML `<pre>` element defines **preformatted text**.

It preserves:

* Spaces
* Line breaks
* Text formatting

### Example

```html
<pre>
Learning HTML is fun.

We create webpages
using different elements.

HTML provides structure
for our website.
</pre>
```

### Output

```text
Learning HTML is fun.

We create webpages
using different elements.

HTML provides structure
for our website.
```

---

# 🧠 When Should We Use `<pre>`?

The `<pre>` element can be useful when the formatting and spacing of text are important.

For example:

* Poems
* ASCII art
* Code examples
* Formatted text

---

# 💻 Complete Example Using Paragraph Elements

```html
<!DOCTYPE html>
<html>

<head>
    <title>Paragraph Example</title>
</head>

<body>

    <h1>Web Designing Workshop</h1>

    <p>
        HTML is used to create the structure of webpages.
    </p>

    <p>
        CSS is used to design and style webpages.
    </p>

    <hr>

    <h2>Contact Information</h2>

    <p>
        Computer Science Department<br>
        ABC College<br>
        India
    </p>

</body>

</html>
```

---

# 🧩 Complete Example Using `<pre>`

```html
<!DOCTYPE html>
<html>

<head>
    <title>Preformatted Text</title>
</head>

<body>

    <h1>My Learning Journey</h1>

    <pre>
HTML
    ↓
Creates Structure

CSS
    ↓
Adds Design

JavaScript
    ↓
Adds Interactivity
    </pre>

</body>

</html>
```

---

# 📊 Important HTML Tags

| Tag     | Purpose                                  |
| ------- | ---------------------------------------- |
| `<p>`   | Defines a paragraph                      |
| `<hr>`  | Creates a thematic break between content |
| `<br>`  | Inserts a line break                     |
| `<pre>` | Displays preformatted text               |

---

# 🎯 Key Concepts

## 1️⃣ `<p>` — Paragraph

```html
<p>This is a paragraph.</p>
```

Used for displaying a block of text.

---

## 2️⃣ `<hr>` — Horizontal Rule

```html
<hr>
```

Used to separate sections of content.

---

## 3️⃣ `<br>` — Line Break

```html
First Line<br>
Second Line
```

Moves the next content to a new line.

---

## 4️⃣ `<pre>` — Preformatted Text

```html
<pre>
Text formatting
is preserved here.
</pre>
```

Preserves spaces and line breaks.

---

# 🧪 Practice Program

Create a webpage containing paragraphs, line breaks, horizontal rules, and preformatted text.

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML Paragraph Practice</title>
</head>

<body>

    <h1>About Web Development</h1>

    <p>
        Web development is the process of creating websites and web applications.
    </p>

    <p>
        HTML provides structure for webpages.
    </p>

    <hr>

    <h2>Web Technologies</h2>

    <p>
        HTML - Structure<br>
        CSS - Design<br>
        JavaScript - Interactivity
    </p>

    <hr>

    <h2>Learning Path</h2>

    <pre>
Step 1: Learn HTML
Step 2: Learn CSS
Step 3: Learn JavaScript
Step 4: Build Projects
    </pre>

</body>

</html>
```

---

# 🎯 Chapter Summary

After completing this topic, students should understand:

* ✅ The `<p>` element defines a paragraph.
* ✅ Paragraphs are used to organize blocks of text.
* ✅ Browsers normally collapse extra spaces and line breaks.
* ✅ The `<hr>` element separates sections of content.
* ✅ The `<br>` element creates a line break.
* ✅ `<hr>` and `<br>` are empty elements.
* ✅ The `<pre>` element preserves spaces and line breaks.

---

# 🧠 Quick Revision

```text
HTML TEXT ELEMENTS
│
├── <p>
│     └── Creates a paragraph
│
├── <br>
│     └── Creates a new line
│
├── <hr>
│     └── Separates content
│
└── <pre>
      └── Preserves spaces and line breaks
```

---

# ❓ Viva Questions

1. Which HTML tag is used to create a paragraph?
2. What happens when extra spaces are added inside normal HTML text?
3. What is the purpose of the `<hr>` element?
4. Is `<hr>` an empty element?
5. What is the purpose of the `<br>` element?
6. What is the difference between `<p>` and `<br>`?
7. What is the purpose of the `<pre>` element?
8. Which HTML element preserves spaces and line breaks?
9. Can `<br>` have a closing tag?
10. When should you use a paragraph instead of a line break?

---

# ⭐ Remember

> **`<p>` creates paragraphs.**

> **`<br>` creates line breaks.**

> **`<hr>` separates content.**

> **`<pre>` preserves formatting.**

