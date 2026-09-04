# 🌐 HTML Favicon

## 📚 Introduction

A **favicon** is a small image associated with a website.

It is usually displayed next to the page title in the browser tab.

For example:

```text
┌──────────────────────────────┐
│ 🟢 My College Website        │
└──────────────────────────────┘
   ↑
 Favicon
```

Favicons help users easily identify a website when multiple browser tabs are open.

---

# 🤔 What is a Favicon?

**Favicon** means:

> **Favorite Icon**

It is a small graphical icon used to represent a website.

A favicon may be:

* 🏫 A college logo
* 📚 A book icon
* 🛒 A shopping icon
* 🏢 A company logo
* 💻 A custom website symbol

---

# 📍 Where Can You See a Favicon?

A favicon can appear in several places, such as:

* Browser tabs
* Bookmarks
* Browser history
* Saved website shortcuts
* Mobile browser shortcuts

The most common location is the **browser tab**.

```text
┌─────────────────────────────────────┐
│ 🌐 My College Website        ×      │
└─────────────────────────────────────┘
  ↑
Favicon
```

---

# 📝 How to Add a Favicon

To add a favicon to a webpage, we use the HTML `<link>` element inside the `<head>` section.

### Basic Syntax

```html
<link rel="icon" href="favicon.ico">
```

---

# 💻 Complete Example

```html
<!DOCTYPE html>
<html>

<head>

    <title>My College Website</title>

    <link rel="icon" href="favicon.ico">

</head>

<body>

    <h1>Welcome to My College Website</h1>

    <p>This webpage uses a favicon.</p>

</body>

</html>
```

---

# 🧠 Understanding the Code

Consider:

```html
<link rel="icon" href="favicon.ico">
```

### Explanation

| Attribute            | Meaning                                            |
| -------------------- | -------------------------------------------------- |
| `<link>`             | Connects the HTML document to an external resource |
| `rel="icon"`         | Specifies that the resource is a website icon      |
| `href="favicon.ico"` | Specifies the location of the favicon              |

---

# 📂 Favicon in the Same Folder

Suppose your project structure is:

```text
My-Website/
│
├── index.html
├── favicon.ico
└── about.html
```

Then use:

```html
<link rel="icon" href="favicon.ico">
```

The browser will find the favicon in the same folder as `index.html`.

---

# 📁 Favicon Inside an Images Folder

It is good practice to organize images inside an `images` folder.

### Project Structure

```text
My-Website/
│
├── index.html
│
└── images/
    └── favicon.ico
```

Then use:

```html
<link rel="icon" href="images/favicon.ico">
```

---

# 🏫 Example: College Website

Suppose you are creating a college website.

### Folder Structure

```text
College-Website/
│
├── index.html
├── about.html
├── courses.html
│
└── images/
    ├── college-logo.png
    └── favicon.png
```

### HTML Code

```html
<!DOCTYPE html>
<html>

<head>

    <title>ABC College</title>

    <link rel="icon" href="images/favicon.png">

</head>

<body>

    <h1>Welcome to ABC College</h1>

    <p>Learn, Explore and Grow.</p>

</body>

</html>
```

---

# 📚 Example: Online Book Store

For your **Online Book Store Experiment**, you can use a book icon as a favicon.

```html
<!DOCTYPE html>
<html>

<head>

    <title>Online Book Store</title>

    <link rel="icon" href="images/book-icon.png">

</head>

<body>

    <h1>📚 Online Book Store</h1>

    <p>Welcome to our online collection of books.</p>

</body>

</html>
```

---

# 🖼️ Common Favicon File Formats

Favicons can be created using different image formats.

Common formats include:

| File Format | Example       |
| ----------- | ------------- |
| ICO         | `favicon.ico` |
| PNG         | `favicon.png` |
| GIF         | `favicon.gif` |
| JPEG/JPG    | `favicon.jpg` |
| SVG         | `favicon.svg` |

### Example using PNG

```html
<link rel="icon" type="image/png" href="images/favicon.png">
```

### Example using ICO

```html
<link rel="icon" type="image/x-icon" href="images/favicon.ico">
```

---

# ⭐ Recommended Favicon

The `.ico` format is commonly used for favicons.

```text
favicon.ico
```

However, PNG and SVG formats are also commonly used.

A favicon should generally be:

* Simple
* Easy to recognize
* Clear at a small size
* High contrast

---

# 🎨 Creating a Good Favicon

Since a favicon is very small, avoid using:

❌ Long text
❌ Too many details
❌ Complex images

Instead, use:

✅ Simple symbols
✅ Clear logos
✅ High-contrast designs
✅ Recognizable icons

### Example

For an Online Book Store:

```text
📚
```

For a College Website:

```text
🏫
```

For a Computer Science Website:

```text
💻
```

---

# 🏗️ Complete Practice Program

```html
<!DOCTYPE html>
<html>

<head>

    <title>Web Designing Workshop</title>

    <!-- Website Favicon -->

    <link 
        rel="icon" 
        type="image/png" 
        href="images/favicon.png"
    >

</head>

<body>

    <h1>Web Designing Workshop</h1>

    <h2>HTML Favicon Example</h2>

    <p>
        Look at the browser tab to see the website favicon.
    </p>

</body>

</html>
```

---

# 🔍 How the Browser Finds the Favicon

```text
Browser Opens Website
        │
        ▼
Reads HTML <head>
        │
        ▼
Finds <link rel="icon">
        │
        ▼
Reads Image Location
        │
        ▼
Loads Favicon
        │
        ▼
Displays Icon in Browser Tab
```

---

# ⚠️ Common Mistakes

## ❌ Wrong Image Path

```html
<link rel="icon" href="favicon.png">
```

If the image is actually inside the `images` folder:

```text
images/favicon.png
```

Then the correct code is:

```html
<link rel="icon" href="images/favicon.png">
```

---

## ❌ Incorrect File Name

Suppose your actual file is:

```text
favicon.png
```

But your HTML code contains:

```html
<link rel="icon" href="fav-icon.png">
```

The browser may not find the favicon.

> 💡 Always check the exact file name and path.

---

# 🧪 Practice Task

Create a simple website containing:

1. A webpage title
2. A favicon
3. A main heading
4. A paragraph

### Suggested Folder Structure

```text
Favicon-Practice/
│
├── index.html
│
└── images/
    └── favicon.png
```

### HTML Code

```html
<!DOCTYPE html>
<html>

<head>

    <title>My First Website</title>

    <link 
        rel="icon" 
        type="image/png" 
        href="images/favicon.png"
    >

</head>

<body>

    <h1>Welcome to My Website</h1>

    <p>This website has a favicon.</p>

</body>

</html>
```

---

# 🎯 Chapter Summary

After completing this topic, students should understand:

* ✅ A favicon is a small icon representing a website.
* ✅ It usually appears in the browser tab.
* ✅ The `<link>` element is used to add a favicon.
* ✅ The favicon code is written inside the `<head>` section.
* ✅ The `rel="icon"` attribute identifies the resource as a favicon.
* ✅ The `href` attribute specifies the favicon location.
* ✅ Favicons can use formats such as ICO, PNG, GIF, JPG, and SVG.
* ✅ Correct file paths are important.

---

# 🧠 Quick Revision

```text
HTML FAVICON
      │
      ▼

<link rel="icon" href="favicon.ico">

      │
      ├── rel
      │     └── Specifies icon relationship
      │
      └── href
            └── Specifies favicon location
```

---

# ❓ Viva Questions

1. What is a favicon?
2. Where is a favicon usually displayed?
3. What does the word favicon mean?
4. Which HTML element is used to add a favicon?
5. Where should the favicon code be placed in an HTML document?
6. What is the purpose of `rel="icon"`?
7. What is the purpose of the `href` attribute?
8. Which file formats can be used for a favicon?
9. Why should a favicon be simple?
10. What happens if the favicon path is incorrect?

---

# ⭐ Remember

> **A favicon is a small icon that represents a website.**

The basic syntax is:

```html
<link rel="icon" href="favicon.ico">
```

> 💡 **The favicon code should be placed inside the `<head>` section of the HTML document.**

