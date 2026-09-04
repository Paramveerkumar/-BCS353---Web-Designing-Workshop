# 🔗 HTML Links

## 📚 Introduction

Links are found on almost every website.

HTML links allow users to move from:

* One webpage to another webpage
* One website to another website
* One section of a webpage to another section
* A webpage to files, images, or other resources

HTML links are also called **hyperlinks**.

---

# 🔗 What is a Hyperlink?

A hyperlink is a clickable element that takes the user to another destination.

For example:

```text
Home → About → Courses → Contact
```

When a user clicks a link, the browser opens the specified destination.

> 💡 A hyperlink does not have to be text. An image or other HTML element can also be used as a link.

---

# 📝 HTML Link Syntax

The HTML `<a>` element is used to create a hyperlink.

### Syntax

```html
<a href="URL">Link Text</a>
```

### Understanding the Syntax

```text
<a href="URL">Link Text</a>
 │       │        │
 │       │        └── Visible clickable text
 │       │
 │       └────────── Destination
 │
 └────────────────── Anchor element
```

The `href` attribute specifies the destination of the link.

---

# 💻 Basic Example

```html
<a href="https://www.google.com">Visit Google</a>
```

When the user clicks **Visit Google**, the browser opens Google.

---

# 🏠 Example: Website Navigation

```html
<a href="index.html">Home</a>

<a href="about.html">About Us</a>

<a href="courses.html">Courses</a>

<a href="contact.html">Contact</a>
```

These links can be used to create a simple website navigation system.

---

# 🎯 How HTML Links Work

```text
User clicks a link
        ↓
Browser reads the href value
        ↓
Browser finds the destination
        ↓
New page or resource is opened
```

For example:

```html
<a href="about.html">About Us</a>
```

```text
Click "About Us"
        ↓
Browser opens
        ↓
about.html
```

---

# 🖱️ Link Appearance

By default, browsers generally display links differently depending on their state:

* 🔵 **Unvisited link** – Usually blue and underlined
* 🟣 **Visited link** – May appear in a different color
* 🔴 **Active link** – May appear differently while being clicked

> 💡 The appearance of links can be changed using CSS.

---

# 🎯 The `target` Attribute

The `target` attribute specifies **where the linked document should open**.

### Syntax

```html
<a href="URL" target="value">Link Text</a>
```

---

# 📌 Types of `target` Values

| Target Value | Description                                   |
| ------------ | --------------------------------------------- |
| `_self`      | Opens the link in the same tab/window         |
| `_blank`     | Opens the link in a new tab/window            |
| `_parent`    | Opens the link in the parent frame            |
| `_top`       | Opens the link in the complete browser window |

---

# 1️⃣ `_self`

This is the default behavior.

The link opens in the same browser tab.

```html
<a href="about.html" target="_self">
    About Us
</a>
```

---

# 2️⃣ `_blank`

The link opens in a new browser tab or window.

```html
<a href="https://www.google.com" target="_blank">
    Open Google
</a>
```

---

# 3️⃣ `_parent`

This is mainly useful when working with frames.

The linked page opens in the parent frame.

```html
<a href="home.html" target="_parent">
    Home
</a>
```

---

# 4️⃣ `_top`

The linked page opens in the complete browser window.

```html
<a href="home.html" target="_top">
    Home
</a>
```

---

# 📊 Understanding Link Targets

```text
                    LINK
                      │
        ┌─────────────┼─────────────┐
        │             │             │
      _self         _blank        _parent
        │             │             │
 Same Tab        New Tab      Parent Frame

                      │
                     _top
                      │
              Full Browser Window
```

---

# 🌐 Absolute URLs

An **absolute URL** contains the complete address of a webpage.

### Example

```html
<a href="https://www.google.com">
    Visit Google
</a>
```

Another example:

```html
<a href="https://www.wikipedia.org">
    Visit Wikipedia
</a>
```

Absolute URLs are generally used when linking to another website.

---

# 📁 Relative URLs

A **relative URL** points to a file within your own website or project.

Suppose your project structure is:

```text
My-Website/
│
├── index.html
├── about.html
├── contact.html
│
└── courses/
    └── html.html
```

From `index.html`, you can create links like:

```html
<a href="about.html">About Us</a>

<a href="contact.html">Contact Us</a>
```

To access a file inside the `courses` folder:

```html
<a href="courses/html.html">
    Learn HTML
</a>
```

---

# 🆚 Absolute URL vs Relative URL

| Absolute URL                      | Relative URL                         |
| --------------------------------- | ------------------------------------ |
| Complete web address              | Address within the project           |
| Usually includes `https://`       | Usually does not include domain name |
| Used for external websites        | Used for internal webpages           |
| Example: `https://www.google.com` | Example: `about.html`                |

---

# 🖼️ Using an Image as a Link

A link does not have to contain only text.

You can make an image clickable.

### Example

```html
<a href="home.html">

    <img 
        src="images/logo.png"
        alt="Website Logo"
        width="150"
    >

</a>
```

When the user clicks the image, the browser opens `home.html`.

---

# 🧭 Creating a Simple Navigation Menu

```html
<!DOCTYPE html>
<html>

<head>
    <title>Navigation Example</title>
</head>

<body>

    <h1>My College Website</h1>

    <a href="index.html">Home</a> |

    <a href="about.html">About</a> |

    <a href="courses.html">Courses</a> |

    <a href="contact.html">Contact</a>

</body>

</html>
```

---

# 🛒 Example: Online Book Store Navigation

```html
<a href="home.html">HOME</a>

<a href="login.html">LOGIN</a>

<a href="registration.html">REGISTER</a>

<a href="catalogue.html">CATALOGUE</a>
```

This is similar to the navigation used in the **Online Book Store Experiment**.

---

# 🖼️ Linking to an Image

You can also create a link that opens an image.

```html
<a href="images/book.jpg">
    View Book Cover
</a>
```

When the user clicks the link, the image file opens.

---

# 💻 Complete Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML Links</title>
</head>

<body>

    <h1>My Website</h1>

    <h2>Internal Links</h2>

    <a href="about.html">About Us</a>
    <br><br>

    <a href="contact.html">Contact Us</a>

    <hr>

    <h2>External Link</h2>

    <a href="https://www.google.com" target="_blank">
        Search on Google
    </a>

</body>

</html>
```

---

# 🧠 Important Concepts

## 1️⃣ `<a>` Element

Creates a hyperlink.

```html
<a href="page.html">Click Here</a>
```

---

## 2️⃣ `href` Attribute

Specifies the destination.

```html
<a href="about.html">About Us</a>
```

Here:

```text
href="about.html"
```

tells the browser which page to open.

---

## 3️⃣ `target` Attribute

Specifies where the link should open.

```html
<a href="page.html" target="_blank">
    Open Page
</a>
```

---

# 🧪 Practice Program

Create a simple college website navigation page.

```html
<!DOCTYPE html>
<html>

<head>
    <title>College Navigation</title>
</head>

<body>

    <h1>ABC College</h1>

    <hr>

    <h2>Navigation Menu</h2>

    <a href="home.html">Home</a>
    <br><br>

    <a href="departments.html">Departments</a>
    <br><br>

    <a href="courses.html">Courses</a>
    <br><br>

    <a href="contact.html">Contact Us</a>

    <hr>

    <h2>External Website</h2>

    <a href="https://www.google.com" target="_blank">
        Visit Google
    </a>

</body>

</html>
```

---

# 🎯 Chapter Summary

After completing this topic, students should understand:

* ✅ HTML links are called hyperlinks.
* ✅ The `<a>` element creates a hyperlink.
* ✅ The `href` attribute specifies the destination.
* ✅ Links can open webpages, files, and other resources.
* ✅ Links can contain text or images.
* ✅ The `target` attribute controls where a link opens.
* ✅ `_self` opens in the same tab.
* ✅ `_blank` opens in a new tab.
* ✅ Absolute URLs link to complete web addresses.
* ✅ Relative URLs link to files within a project.

---

# 🧠 Quick Revision

```text
HTML LINKS
    │
    ▼

<a href="URL">Link Text</a>

    │
    ├── href
    │      └── Destination
    │
    ├── target
    │      └── Where to open
    │
    ├── Absolute URL
    │
    └── Relative URL
```

---

# ❓ Viva Questions

1. What is a hyperlink?
2. Which HTML tag is used to create a hyperlink?
3. What is the purpose of the `href` attribute?
4. What is the purpose of the `target` attribute?
5. What is the difference between `_self` and `_blank`?
6. What is an absolute URL?
7. What is a relative URL?
8. Can an image be used as a hyperlink?
9. Which target value opens a page in a new tab?
10. How are hyperlinks used in website navigation?

---

# ⭐ Remember

> **The `<a>` element creates a hyperlink.**

> **The `href` attribute specifies where the link will go.**

```html
<a href="destination.html">
    Click Here
</a>
```

