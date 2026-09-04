# 🖼️ HTML Images

## 📚 Introduction

Images make a webpage more attractive, informative, and visually appealing.

Websites use images for:

* 🏫 College logos
* 📚 Book covers
* 🛍️ Product images
* 👤 Profile pictures
* 🖼️ Banners
* 🏞️ Background images
* 🏢 Company logos

For example, an **Online Book Store** can display the cover image of each book.

---

# 🖼️ The HTML `<img>` Tag

The HTML `<img>` tag is used to display an image on a webpage.

### Basic Example

```html
<img src="book.jpg" alt="Book Cover">
```

The `<img>` tag is an **empty element**.

This means:

* It does not contain content.
* It does not require a closing tag.

❌ Incorrect:

```html
<img src="book.jpg"></img>
```

✅ Correct:

```html
<img src="book.jpg" alt="Book Cover">
```

---

# 📝 HTML Image Syntax

The general syntax is:

```html
<img src="image-path" alt="description">
```

### Understanding the Syntax

```text
<img src="book.jpg" alt="Programming Book">
 │         │              │
 │         │              └── Alternative text
 │         │
 │         └──────────────── Image location
 │
 └────────────────────────── Image element
```

The two most important attributes are:

| Attribute | Purpose                                 |
| --------- | --------------------------------------- |
| `src`     | Specifies the location of the image     |
| `alt`     | Provides alternative text for the image |

---

# 📁 The `src` Attribute

The `src` attribute specifies the **path or location of the image**.

### Example

```html
<img src="college-logo.png" alt="College Logo">
```

Here:

```text
src="college-logo.png"
```

tells the browser to find and display the image named:

```text
college-logo.png
```

---

# 📚 Example: Online Book Store

Suppose we have a book image named:

```text
cpp-book.jpg
```

We can display it using:

```html
<img src="cpp-book.jpg" alt="C++ Programming Book">
```

The browser will load the image and display it on the webpage.

---

# ⚠️ What Happens if the Image Cannot Be Found?

Suppose the image name is incorrect:

```html
<img src="wrong-image.jpg" alt="C++ Programming Book">
```

The browser cannot find the image.

In this situation, the browser may display:

* A broken image icon
* The alternative text

This is why the `alt` attribute is important.

---

# 📝 The `alt` Attribute

The `alt` attribute provides alternative text describing the image.

### Example

```html
<img src="book.jpg" alt="Web Designing Book">
```

The alternative text is useful when:

* The image cannot be loaded
* The internet connection is slow
* The image file is missing
* A screen reader is being used

---

# ♿ Why is `alt` Important?

The `alt` text improves **accessibility**.

Screen readers can read the alternative text to help visually impaired users understand the image.

### Good Example

```html
<img src="library.jpg" alt="Students studying in a library">
```

### Poor Example

```html
<img src="library.jpg" alt="image">
```

> 💡 Always write meaningful alternative text that describes the image.

---

# 📏 Image Width and Height

You can control the size of an image using:

* `width`
* `height`

### Example

```html
<img 
    src="college-logo.png"
    alt="College Logo"
    width="200"
    height="200"
>
```

The image will have:

```text
Width  = 200 pixels
Height = 200 pixels
```

---

# 🎨 Using the `style` Attribute

You can also control the size using CSS inside the `style` attribute.

### Example

```html
<img 
    src="book.jpg"
    alt="Programming Book"
    style="width:300px; height:400px;"
>
```

---

# 📊 Width and Height vs Style

Both methods are valid.

### Using HTML Attributes

```html
<img src="book.jpg" alt="Book" width="300" height="400">
```

### Using CSS Style

```html
<img 
    src="book.jpg"
    alt="Book"
    style="width:300px; height:400px;"
>
```

As students learn CSS, styling images using CSS becomes more flexible and easier to manage.

---

# 📂 Images in Another Folder

Usually, images are organized inside an `images` folder.

### Project Structure

```text
Online-Book-Store/
│
├── index.html
├── catalogue.html
│
└── images/
    ├── logo.png
    ├── cpp-book.jpg
    └── java-book.jpg
```

To display the logo:

```html
<img src="images/logo.png" alt="College Logo">
```

To display a book:

```html
<img src="images/cpp-book.jpg" alt="C++ Programming Book">
```

---

# 🗂️ Understanding Image Paths

Consider this structure:

```text
Website/
│
├── index.html
│
└── images/
    └── banner.jpg
```

Inside `index.html`:

```html
<img src="images/banner.jpg" alt="Website Banner">
```

### How it works

```text
index.html
     │
     ▼
images folder
     │
     ▼
banner.jpg
```

---

# 🌐 Images from Another Website

An image can also be loaded using a complete URL.

```html
<img 
    src="https://example.com/images/logo.png"
    alt="Website Logo"
>
```

This is called using an **absolute URL**.

However, external images may:

* Be removed
* Change location
* Become unavailable

Therefore, for your own website project, it is generally better to store your images inside your project folder.

---

# 🎞️ Animated Images

HTML can display animated GIF images.

### Example

```html
<img 
    src="animation.gif"
    alt="Loading Animation"
    width="100"
    height="100"
>
```

GIF images can be useful for:

* Loading animations
* Simple demonstrations
* Animated banners

---

# 🔗 Image as a Link

An image can also work as a hyperlink.

To create an image link, place the `<img>` tag inside the `<a>` tag.

### Example

```html
<a href="home.html">

    <img 
        src="images/home-icon.png"
        alt="Go to Home Page"
        width="100"
    >

</a>
```

When the user clicks the image, the browser opens:

```text
home.html
```

---

# 🏠 Example: Clickable College Logo

```html
<a href="index.html">

    <img 
        src="images/college-logo.png"
        alt="College Home Page"
        width="150"
        height="150"
    >

</a>
```

Students can click the college logo to return to the homepage.

---

# 📚 Example: Online Book Store

```html
<!DOCTYPE html>
<html>

<head>
    <title>Online Book Store</title>
</head>

<body>

    <h1>Online Book Store</h1>

    <h2>Available Books</h2>

    <img 
        src="images/cpp-book.jpg"
        alt="C++ Programming Book"
        width="150"
        height="200"
    >

    <h3>C++ Programming</h3>

    <img 
        src="images/java-book.jpg"
        alt="Java Programming Book"
        width="150"
        height="200"
    >

    <h3>Java Programming</h3>

</body>

</html>
```

---

# 💻 Complete Practice Program

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML Images Practice</title>
</head>

<body>

    <h1>My College Website</h1>

    <h2>College Logo</h2>

    <img 
        src="images/logo.png"
        alt="College Logo"
        width="200"
        height="200"
    >

    <hr>

    <h2>Computer Science Department</h2>

    <img 
        src="images/computer-lab.jpg"
        alt="Students working in a computer laboratory"
        style="width:400px; height:250px;"
    >

    <hr>

    <h2>Click the Image</h2>

    <a href="home.html">

        <img 
            src="images/home.png"
            alt="Go to Home Page"
            width="100"
        >

    </a>

</body>

</html>
```

---

# 🧠 Important Points

## 1️⃣ `<img>` is an Empty Element

```html
<img src="image.jpg" alt="Description">
```

It does not need a closing tag.

---

## 2️⃣ `src` Specifies the Image Location

```html
<img src="images/book.jpg" alt="Book">
```

---

## 3️⃣ `alt` Describes the Image

```html
<img src="book.jpg" alt="HTML Programming Book">
```

---

## 4️⃣ `width` Controls Image Width

```html
<img src="book.jpg" alt="Book" width="200">
```

---

## 5️⃣ `height` Controls Image Height

```html
<img src="book.jpg" alt="Book" height="300">
```

---

# 🧪 Practice Task

Create a webpage for an **Online Book Store** containing:

1. A main heading
2. A website logo
3. Three book images
4. Appropriate `alt` text for every image
5. Width and height for each image
6. One image that works as a link

### Suggested Structure

```text
Online Book Store
        │
        ├── Website Logo
        │
        ├── HTML Book Image
        │
        ├── CSS Book Image
        │
        └── JavaScript Book Image
```

---

# 🎯 Chapter Summary

After completing this topic, students should understand:

* ✅ The `<img>` tag is used to display images.
* ✅ The `<img>` tag is an empty element.
* ✅ `src` specifies the image location.
* ✅ `alt` provides alternative text.
* ✅ `width` controls image width.
* ✅ `height` controls image height.
* ✅ Images can be stored inside folders.
* ✅ Images can use relative or absolute paths.
* ✅ GIF files can be animated.
* ✅ Images can also be used as hyperlinks.

---

# 🧠 Quick Revision

```text
HTML IMAGES
     │
     ▼

<img src="image.jpg" alt="description">

     │
     ├── src
     │      └── Image Location
     │
     ├── alt
     │      └── Alternative Text
     │
     ├── width
     │      └── Image Width
     │
     └── height
            └── Image Height
```

---

# ❓ Viva Questions

1. Which HTML tag is used to display an image?
2. Is the `<img>` tag an empty element?
3. What is the purpose of the `src` attribute?
4. What is the purpose of the `alt` attribute?
5. Why is alternative text important?
6. How can you change the width of an image?
7. How can you change the height of an image?
8. What is a relative image path?
9. What is an absolute image URL?
10. How can an image be used as a hyperlink?

---

# ⭐ Remember

> **The `<img>` tag is used to display an image on a webpage.**

```html
<img src="image.jpg" alt="Description of the image">
```

> **Always use meaningful `alt` text to describe your images.**

