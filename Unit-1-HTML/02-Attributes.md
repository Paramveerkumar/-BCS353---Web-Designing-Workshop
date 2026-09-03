# 🏷️ HTML Attributes

## 📚 Introduction

HTML attributes provide **additional information** about HTML elements.

Attributes help us control or describe the behavior and properties of an HTML element.

For example, an image element can use attributes to specify:

* Which image to display
* The size of the image
* Alternative text for the image

---

# 🤔 What are HTML Attributes?

### Important Points

* All HTML elements can have **attributes**.
* Attributes provide **additional information** about HTML elements.
* Attributes are usually specified in the **start tag**.
* Attributes usually come in **name/value pairs**.

### General Syntax

```html
<tagname attribute="value">Content</tagname>
```

### Example

```html
<p title="This is a paragraph">Welcome Students!</p>
```

Here:

```text
<p                     → HTML Start Tag
title                  → Attribute Name
"This is a paragraph"  → Attribute Value
```

---

# 🧩 Understanding Attributes with an Example

Consider the following code:

```html
<a href="https://www.example.com">Visit Website</a>
```

Here:

| Part                        | Meaning         |
| --------------------------- | --------------- |
| `<a>`                       | Anchor element  |
| `href`                      | Attribute name  |
| `"https://www.example.com"` | Attribute value |
| `Visit Website`             | Link content    |

---

# 🔗 The `href` Attribute

The `<a>` element is used to create a **hyperlink**.

The `href` attribute specifies the destination or URL of the link.

### Example

```html
<a href="https://www.netflix.com/in/">Netflix</a>
```

### Explanation

```text
<a>       → Creates a hyperlink
href      → Specifies the destination
URL       → Address of the webpage
```

When the user clicks the link, the browser opens the specified webpage.

---

# 🖼️ The `src` Attribute

The `<img>` element is used to display an image on a webpage.

The `src` attribute specifies the location or path of the image.

### Example

```html
<img src="img_girl.jpg">
```

Here:

```text
<img>         → Image element
src           → Specifies the image location
img_girl.jpg  → Image file
```

---

# 🌍 Types of URLs in the `src` Attribute

There are two common ways to specify an image location.

## 1️⃣ Absolute URL

An **absolute URL** contains the complete address of a resource.

### Example

```html
<img src="https://example.com/images/photo.jpg">
```

The image is hosted on another website or server.

### Possible Limitation

If the external image is removed or changed, it may no longer appear on your webpage.

---

## 2️⃣ Relative URL

A **relative URL** refers to a file within your website or project.

### Example

```html
<img src="img_girl.jpg">
```

Another example:

```html
<img src="images/img_girl.jpg">
```

### Project Structure

```text
MyWebsite/
│
├── index.html
│
└── images/
    └── img_girl.jpg
```

Then we can write:

```html
<img src="images/img_girl.jpg">
```

> 💡 **Tip:** Relative URLs are commonly used for files that belong to your own website or project.

---

# 📏 The `width` and `height` Attributes

The `<img>` element can use the `width` and `height` attributes to specify image dimensions.

### Example

```html
<img src="img_girl.jpg" width="500" height="600">
```

Here:

```text
width="500"   → Image width
height="600"  → Image height
```

### Another Example

```html
<img src="college.jpg" width="300" height="200">
```

---

# 📝 The `alt` Attribute

The `alt` attribute provides **alternative text** for an image.

The alternative text can be useful when:

* The image cannot be displayed.
* The image path is incorrect.
* There is a network problem.
* A screen reader is used.

### Example

```html
<img src="img_girl.jpg" alt="Girl with a jacket">
```

If the image cannot be displayed, the alternative text helps describe the image.

### Example with Incorrect Image Path

```html
<img src="wrong_image.jpg" alt="Girl with a jacket">
```

The browser cannot find the image, but the `alt` text provides a description.

---

# 🎨 The `style` Attribute

The `style` attribute is used to apply CSS styling directly to an HTML element.

It can be used to change:

* Color
* Font
* Font Size
* Background Color
* Text Alignment

### Example

```html
<p style="color: red;">This is a red paragraph.</p>
```

### Another Example

```html
<h1 style="color: blue; text-align: center;">
    Welcome Students
</h1>
```

> 💡 The `style` attribute is an example of **inline CSS**.

---

# 🌐 The `lang` Attribute

The `lang` attribute specifies the language of the HTML document.

It is generally placed inside the `<html>` element.

### Example: English

```html
<!DOCTYPE html>
<html lang="en">

<body>

    <h1>Welcome</h1>

</body>

</html>
```

The value:

```text
en → English
```

---

## Language and Country Code

A country code can also be included.

### Example

```html
<html lang="en-US">
```

Here:

```text
en → English language
US → United States
```

Another example:

```html
<html lang="en-IN">
```

This indicates English with India as the regional context.

---

# 💬 The `title` Attribute

The `title` attribute provides additional information about an element.

It is commonly displayed as a **tooltip** when the user moves the mouse pointer over the element.

### Example

```html
<p title="I'm a tooltip">
    Move your mouse over this paragraph.
</p>
```

When the user places the mouse pointer over the paragraph, the title information can be displayed.

---

# 🔤 Use Lowercase Attribute Names

Although HTML attribute names may be written in different cases, the recommended practice is:

> ✅ Always use lowercase attribute names.

### Recommended

```html
<img src="photo.jpg" alt="Student Photo">
```

### Avoid

```html
<img SRC="photo.jpg" ALT="Student Photo">
```

---

# ✍️ Always Use Quotes Around Attribute Values

It is considered good practice to use quotes around attribute values.

### ✅ Good Practice

```html
<a href="https://www.example.com">
    Visit Website
</a>
```

### ⚠️ Avoid

```html
<a href=https://www.example.com>
    Visit Website
</a>
```

Using quotes makes HTML code easier to read and avoids problems when attribute values contain spaces.

---

# 🔠 Single Quotes vs Double Quotes

Both single and double quotes can be used for attribute values.

### Double Quotes

```html
<p title="Welcome Students">
```

### Single Quotes

```html
<p title='Welcome Students'>
```

Double quotes are commonly used.

---

## When to Use Different Quotes?

If the attribute value contains double quotes, single quotes can be useful.

### Example

```html
<p title='John "ShotGun" Nelson'>
```

Or:

```html
<p title="John 'ShotGun' Nelson">
```

---

# 💻 Complete Example

The following example demonstrates multiple HTML attributes.

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>HTML Attributes Example</title>
</head>

<body>

    <h1 title="Main Heading">
        Welcome to HTML Attributes
    </h1>

    <p style="color: blue;">
        HTML attributes provide additional information about elements.
    </p>

    <a href="https://www.w3schools.com">
        Visit W3Schools
    </a>

    <br><br>

    <img 
        src="img_girl.jpg"
        alt="Girl with a jacket"
        width="250"
        height="300"
    >

</body>

</html>
```

---

# 📊 Common HTML Attributes

| Attribute | Commonly Used With | Purpose                         |
| --------- | ------------------ | ------------------------------- |
| `href`    | `<a>`              | Specifies the link destination  |
| `src`     | `<img>`            | Specifies the file location     |
| `width`   | `<img>`            | Specifies image width           |
| `height`  | `<img>`            | Specifies image height          |
| `alt`     | `<img>`            | Provides alternative text       |
| `style`   | Most HTML elements | Adds inline styling             |
| `lang`    | `<html>`           | Specifies document language     |
| `title`   | Most HTML elements | Provides additional information |

---

# 🎯 Key Difference: Element vs Attribute

Students often confuse **HTML elements** and **HTML attributes**.

### HTML Element

```html
<p>This is a paragraph.</p>
```

The `<p>` is an HTML element.

### HTML Attribute

```html
<p title="Paragraph Information">
    This is a paragraph.
</p>
```

Here:

```text
<p>       → HTML Element
title    → HTML Attribute
```

### Easy Way to Remember 🧠

> 🧱 **HTML Element = What it is**

> 🏷️ **HTML Attribute = Additional information about it**

---

# 🧠 Real-Life Analogy

Think about a student.

```text
Student
│
├── Name
├── Roll Number
├── Age
└── Course
```

Similarly:

```text
HTML Element
│
├── Attribute
├── Attribute
└── Attribute
```

For example:

```html
<img src="student.jpg" alt="Student Photo" width="200">
```

The `<img>` is the element, while `src`, `alt`, and `width` provide additional information.

---

# 🎯 Chapter Summary

After completing this topic, students should understand:

* ✅ HTML attributes provide additional information about elements.
* ✅ Attributes are generally written in the start tag.
* ✅ Attributes usually use the `name="value"` format.
* ✅ `href` specifies the destination of a hyperlink.
* ✅ `src` specifies the location of an image.
* ✅ `width` and `height` specify image dimensions.
* ✅ `alt` provides alternative text for an image.
* ✅ `style` applies inline styling.
* ✅ `lang` specifies the language of the document.
* ✅ `title` provides additional information about an element.
* ✅ Lowercase attribute names are recommended.
* ✅ Quotes around attribute values are recommended.

---

# 📝 Code Challenge: Image Attributes

## 🎯 Challenge

Create an image using HTML attributes.

### Requirements

1. Add an `<img>` element.
2. Set `src` to `img_girl.jpg`.
3. Set `alt` to `Girl with a jacket`.
4. Set `width` to `250`.
5. Set `height` to `300`.

### Expected Code

```html
<img 
    src="img_girl.jpg"
    alt="Girl with a jacket"
    width="250"
    height="300"
>
```

---

# ❓ Practice Questions

### 1. What are HTML attributes?

### 2. Where are HTML attributes specified?

### 3. What is the general syntax of an HTML attribute?

### 4. What is the purpose of the `href` attribute?

### 5. What is the purpose of the `src` attribute?

### 6. What is the difference between an absolute URL and a relative URL?

### 7. Why is the `alt` attribute important?

### 8. What is the purpose of the `style` attribute?

### 9. What does the `lang` attribute specify?

### 10. What is the purpose of the `title` attribute?

---

# ⭐ Quick Revision

```text
HTML Attributes
       │
       ├── href   → Link Destination
       │
       ├── src    → File/Image Location
       │
       ├── width  → Image Width
       │
       ├── height → Image Height
       │
       ├── alt    → Alternative Text
       │
       ├── style  → Inline Styling
       │
       ├── lang   → Document Language
       │
       └── title  → Extra Information
```

> 🏷️ **Remember: HTML attributes provide additional information about HTML elements.**

