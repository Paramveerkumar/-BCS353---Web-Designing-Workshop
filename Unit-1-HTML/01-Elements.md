# 🧱 HTML Elements

## 📚 Introduction to HTML

**HTML** is the standard markup language used to create and structure web pages.

When you open a website in your browser, HTML helps define the structure of the content you see, such as:

* Headings
* Paragraphs
* Images
* Links
* Tables
* Lists
* Forms
* Buttons

Think of HTML as the **skeleton of a webpage**. 🦴

> **HTML provides the structure of a webpage.**

---

# 🌐 What is HTML?

HTML stands for:

> **H**yper **T**ext **M**arkup **L**anguage

### Important Points

* HTML is the standard markup language for creating web pages.
* HTML describes the structure of a web page.
* HTML consists of a series of elements.
* HTML elements tell the browser how to display content.
* HTML elements label different types of content.

For example:

```text
Heading
Paragraph
Link
Image
Table
Button
```

---

# 🧩 HTML Elements

An **HTML element** is one of the building blocks of a web page.

Most HTML elements consist of:

```html
<tagname>Content goes here...</tagname>
```

### Example

```html
<h1>My First Heading</h1>

<p>My first paragraph.</p>
```

Here:

```text
<h1>                  → Start Tag
My First Heading      → Content
</h1>                 → End Tag
```

Together, these form an **HTML element**.

---

## 📊 Structure of an HTML Element

| Start Tag | Element Content     | End Tag |
| --------- | ------------------- | ------- |
| `<h1>`    | My First Heading    | `</h1>` |
| `<p>`     | My first paragraph. | `</p>`  |
| `<br>`    | None                | None    |

---

# 🏗️ A Simple HTML Document

Every HTML webpage follows a basic structure.

### Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>Page Title</title>
</head>

<body>

    <h1>My First Heading</h1>
    <p>My first paragraph.</p>

</body>

</html>
```

---

# 🔍 Understanding the HTML Document

Let's understand each part of the above program.

### 1️⃣ `<!DOCTYPE html>`

```html
<!DOCTYPE html>
```

This declaration tells the browser that the document is an **HTML5 document**.

It must appear at the top of the HTML document.

---

### 2️⃣ `<html>` Element

```html
<html>
    ...
</html>
```

The `<html>` element is the **root element** of an HTML document.

All other HTML elements are placed inside the `<html>` element.

---

### 3️⃣ `<head>` Element

```html
<head>
    <title>Page Title</title>
</head>
```

The `<head>` section contains information **about the webpage**.

This information is generally not displayed directly as webpage content.

Examples include:

* Page title
* Character encoding
* CSS links
* Metadata

---

### 4️⃣ `<title>` Element

```html
<title>My Website</title>
```

The `<title>` element specifies the title of the webpage.

The title is generally displayed in the:

* Browser tab
* Browser title area

---

### 5️⃣ `<body>` Element

```html
<body>

    <h1>My First Heading</h1>
    <p>My first paragraph.</p>

</body>
```

The `<body>` contains the **visible content** of the webpage.

It can contain:

* Headings
* Paragraphs
* Images
* Links
* Tables
* Lists
* Forms

Everything that the user sees on the webpage is generally placed inside the `<body>` section.

---

# 🧱 Visual Structure of an HTML Document

```text
HTML Document
│
├── <!DOCTYPE html>
│
└── <html>
    │
    ├── <head>
    │   │
    │   └── <title>
    │
    └── <body>
        │
        ├── <h1>
        │
        └── <p>
```

---

# 📄 HTML Documents

All HTML documents should begin with:

```html
<!DOCTYPE html>
```

The HTML document starts with:

```html
<html>
```

and ends with:

```html
</html>
```

The visible content is placed between:

```html
<body>
```

and:

```html
</body>
```

### Example

```html
<!DOCTYPE html>
<html>

<body>

    <h1>My First Heading</h1>

    <p>My first paragraph.</p>

</body>

</html>
```

---

# 📌 The `<!DOCTYPE html>` Declaration

The `<!DOCTYPE>` declaration represents the document type.

It helps the browser understand how to correctly display the webpage.

### Important Rules

* It appears only once in an HTML document.
* It should appear at the top of the document.
* It comes before the HTML tags.

### HTML5 Declaration

```html
<!DOCTYPE html>
```

---

# 🪆 Nested HTML Elements

HTML elements can be **nested**.

This means that one HTML element can contain another HTML element.

### Example

```html
<html>

<body>

    <h1>My First Heading</h1>

    <p>My first paragraph.</p>

</body>

</html>
```

The relationship is:

```text
<html>
   │
   └── <body>
          │
          ├── <h1>
          │
          └── <p>
```

### Explanation

The `<html>` element contains the `<body>` element.

The `<body>` element contains:

* `<h1>`
* `<p>`

Therefore, these elements are called **nested HTML elements**.

---

# 🏠 Easy Analogy: HTML Elements as a House

You can understand HTML using a house example:

```text
HTML
│
├── HEAD → Information about the house
│
└── BODY → Visible part of the house
       │
       ├── Heading
       ├── Paragraph
       ├── Image
       └── Button
```

Think of a webpage as a building:

> **HTML elements are the building blocks used to construct the webpage.** 🧱

---

# ⚠️ Never Skip the End Tag

Some HTML elements may still work even if the end tag is missing.

For example:

```html
<p>This is a paragraph

<p>This is another paragraph
```

However:

> ⚠️ **You should always write the closing tag when the element requires one.**

Writing proper HTML makes your code:

* Easier to understand
* Easier to maintain
* Less likely to produce unexpected results

### Correct Example

```html
<p>This is a paragraph.</p>

<p>This is another paragraph.</p>
```

---

# 🚫 Empty HTML Elements

Some HTML elements do not contain any content.

These are called **empty elements** or **void elements**.

### Example: `<br>`

The `<br>` element creates a line break.

```html
<p>
    This is the first line.<br>
    This is the second line.
</p>
```

### Output

```text
This is the first line.
This is the second line.
```

The `<br>` element does not require an end tag.

---

# 🔤 HTML is Not Case Sensitive

HTML tags are generally interpreted without case sensitivity.

For example:

```html
<P>This is a paragraph.</P>
```

and:

```html
<p>This is a paragraph.</p>
```

However, the recommended best practice is:

> ✅ **Always use lowercase HTML tags.**

### Recommended

```html
<h1>Welcome</h1>

<p>This is a paragraph.</p>
```

---

# 📰 HTML Headings

HTML provides six levels of headings:

```html
<h1>This is Heading 1</h1>
<h2>This is Heading 2</h2>
<h3>This is Heading 3</h3>
<h4>This is Heading 4</h4>
<h5>This is Heading 5</h5>
<h6>This is Heading 6</h6>
```

### Heading Hierarchy

```text
<h1> → Most Important Heading
<h2> → Second Level Heading
<h3> → Third Level Heading
<h4> → Fourth Level Heading
<h5> → Fifth Level Heading
<h6> → Least Important Heading
```

> 💡 **Note:** A detailed discussion of HTML Headings will be covered in the next topic.

---

# 💻 Complete Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>My First Webpage</title>
</head>

<body>

    <h1>Welcome to My Website</h1>

    <p>
        This is my first HTML webpage.
    </p>

    <p>
        HTML is used to create the structure of web pages.
    </p>

    <br>

    <p>
        Thank you for visiting!
    </p>

</body>

</html>
```

---

# 🎯 Key Takeaways

After completing this topic, students should understand:

* ✅ What HTML is
* ✅ The meaning of HTML
* ✅ What an HTML element is
* ✅ Start tags and end tags
* ✅ The basic structure of an HTML document
* ✅ The purpose of `<!DOCTYPE html>`
* ✅ Nested HTML elements
* ✅ Empty HTML elements
* ✅ Why closing tags are important
* ✅ HTML heading elements

---

# 🧠 Quick Revision

```text
HTML
│
├── HTML = HyperText Markup Language
│
├── HTML Elements
│      │
│      ├── Start Tag
│      ├── Content
│      └── End Tag
│
├── HTML Document
│      │
│      ├── <!DOCTYPE html>
│      └── <html>
│            ├── <head>
│            └── <body>
│
└── HTML Elements
       │
       ├── Normal Elements
       ├── Nested Elements
       └── Empty Elements
```

---

# ❓ Practice Questions

### 1. What does HTML stand for?

### 2. What is an HTML element?

### 3. What is the difference between a start tag and an end tag?

### 4. What is the purpose of the `<html>` element?

### 5. What is the purpose of the `<head>` element?

### 6. What is the purpose of the `<body>` element?

### 7. What is an empty HTML element?

### 8. Give examples of two HTML elements.

### 9. What is the purpose of `<!DOCTYPE html>`?

### 10. What are nested HTML elements?

---

## ⭐ Remember

> 🧱 **HTML is the structure of a webpage.**

> 🧩 **HTML Elements are the building blocks of a webpage.**

