# ⭐ Font Awesome

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-7952B3?style=for-the-badge&logo=fontawesome&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Learn how to add icons to websites using Font Awesome.
</p>

---

## 1. What is Font Awesome?

**Font Awesome** is an icon library that provides thousands of ready-to-use icons for websites and applications.

Examples:

```text
🏠 Home
🔍 Search
👤 User
✉️ Email
📞 Phone
🛒 Shopping Cart
❤️ Like
🔒 Lock
```

Instead of creating icons manually, we can use Font Awesome classes.

---

# 2. Why Use Font Awesome?

Font Awesome makes it easy to add icons to a webpage.

### Without an icon library

We may need to:

* Create icons manually
* Download individual image files
* Resize images
* Manage many image files

### With Font Awesome

```html
<i class="fa-solid fa-house"></i>
```

The icon is displayed using a Font Awesome class.

### Advantages

* ✅ Easy to use
* ✅ Large collection of icons
* ✅ Icons can be resized with CSS
* ✅ Icons can be colored
* ✅ Works well with buttons and navigation bars
* ✅ No need to create individual image files

---

# 3. How to Install Font Awesome?

There are several ways to use Font Awesome.

For beginners, the easiest method is using a **CDN**.

```text
HTML Page
    ↓
Font Awesome CDN
    ↓
Font Awesome CSS
    ↓
Icon Classes
    ↓
Icons
```

---

# 4. Add Font Awesome Using CDN

Add the Font Awesome stylesheet inside the `<head>` section.

```html
<link
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.7.2/css/all.min.css">
```

Then we can use Font Awesome icons.

Example:

```html
<i class="fa-solid fa-house"></i>
```

> 💡 The Font Awesome version in a CDN URL may change. For a project, use the version specified by your course/project requirements.

---

# 5. Basic Font Awesome Syntax

The general syntax is:

```html
<i class="fa-solid fa-icon-name"></i>
```

Example:

```html
<i class="fa-solid fa-house"></i>
```

Here:

```text
fa-solid
   ↓
Icon style

fa-house
   ↓
Specific icon
```

---

# 6. Common Font Awesome Icons

| Icon        | Code                  |
| ----------- | --------------------- |
| 🏠 Home     | `fa-house`            |
| 🔍 Search   | `fa-magnifying-glass` |
| 👤 User     | `fa-user`             |
| ✉️ Email    | `fa-envelope`         |
| 📞 Phone    | `fa-phone`            |
| 🛒 Cart     | `fa-cart-shopping`    |
| ❤️ Heart    | `fa-heart`            |
| 🔒 Lock     | `fa-lock`             |
| ⭐ Star      | `fa-star`             |
| ⚙️ Settings | `fa-gear`             |
| ✏️ Edit     | `fa-pen`              |
| 🗑️ Delete  | `fa-trash`            |

Example:

```html
<i class="fa-solid fa-user"></i>

<i class="fa-solid fa-envelope"></i>

<i class="fa-solid fa-phone"></i>

<i class="fa-solid fa-cart-shopping"></i>
```

---

# 7. Font Awesome in a Button

Icons can be combined with Bootstrap buttons.

```html
<button class="btn btn-primary">
    <i class="fa-solid fa-right-to-bracket"></i>
    Login
</button>
```

Another example:

```html
<button class="btn btn-success">
    <i class="fa-solid fa-cart-shopping"></i>
    Add to Cart
</button>
```

Output conceptually:

```text
┌──────────────────────┐
│ 🛒  Add to Cart      │
└──────────────────────┘
```

---

# 8. Font Awesome in Navigation

Example:

```html
<nav>

    <a href="#">
        <i class="fa-solid fa-house"></i>
        Home
    </a>

    <a href="#">
        <i class="fa-solid fa-book"></i>
        Books
    </a>

    <a href="#">
        <i class="fa-solid fa-user"></i>
        Login
    </a>

</nav>
```

Conceptually:

```text
🏠 Home    📚 Books    👤 Login
```

---

# 9. Changing Icon Size

Font Awesome provides utility classes for icon sizes.

### Small

```html
<i class="fa-solid fa-house fa-sm"></i>
```

### Normal

```html
<i class="fa-solid fa-house"></i>
```

### Large

```html
<i class="fa-solid fa-house fa-lg"></i>
```

### 2× Size

```html
<i class="fa-solid fa-house fa-2x"></i>
```

### 3× Size

```html
<i class="fa-solid fa-house fa-3x"></i>
```

Example:

```html
<i class="fa-solid fa-star fa-2x"></i>
```

---

# 10. Changing Icon Color

Icons can be styled using normal CSS.

```html
<i class="fa-solid fa-heart heart-icon"></i>
```

```css
.heart-icon {
    color: red;
}
```

We can also use Bootstrap utility classes when Bootstrap is included:

```html
<i class="fa-solid fa-heart text-danger"></i>
```

```html
<i class="fa-solid fa-circle-check text-success"></i>
```

---

# 11. Font Awesome with CSS

Because Font Awesome icons behave like text glyphs, many text-related CSS properties can be applied.

```html
<i class="fa-solid fa-house my-icon"></i>
```

```css
.my-icon {
    font-size: 40px;
    color: blue;
}
```

Concept:

```text
Font Awesome Icon
       ↓
CSS
       ↓
Size + Color + Spacing + Effects
```

---

# 12. Font Awesome Icon Styles

Font Awesome has different icon styles depending on the icon and the version/licensing available.

Common style prefixes include:

```text
fa-solid
fa-regular
fa-brands
```

### Solid

```html
<i class="fa-solid fa-heart"></i>
```

### Regular

```html
<i class="fa-regular fa-heart"></i>
```

### Brands

Brand icons use:

```html
<i class="fa-brands fa-github"></i>
```

Example:

```html
<i class="fa-brands fa-facebook"></i>
<i class="fa-brands fa-instagram"></i>
<i class="fa-brands fa-youtube"></i>
```

> ⚠️ Not every icon is available in every style.

---

# 13. Font Awesome Brands

Font Awesome also provides icons for many popular brands.

Examples:

```html
<i class="fa-brands fa-github"></i>

<i class="fa-brands fa-linkedin"></i>

<i class="fa-brands fa-youtube"></i>

<i class="fa-brands fa-instagram"></i>
```

These are useful for:

* Social media links
* Footer sections
* Contact pages
* Portfolio websites

---

# 14. Font Awesome in a Card

Example:

```html
<div class="card p-4">

    <i class="fa-solid fa-book fa-3x"></i>

    <h3>Web Designing</h3>

    <p>
        Learn HTML, CSS, JavaScript and Bootstrap.
    </p>

    <button class="btn btn-primary">
        Learn More
    </button>

</div>
```

Concept:

```text
┌─────────────────────────┐
│           📚            │
│                         │
│      Web Designing      │
│                         │
│ Learn HTML, CSS, JS...  │
│                         │
│     [ Learn More ]      │
└─────────────────────────┘
```

---

# 15. Complete Example

```html
<!DOCTYPE html>
<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1">

    <title>Font Awesome Example</title>

    <!-- Bootstrap CSS -->
    <link
        href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"
        rel="stylesheet">

    <!-- Font Awesome -->
    <link
        rel="stylesheet"
        href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.7.2/css/all.min.css">

</head>

<body>

    <div class="container mt-5">

        <h1 class="text-primary">
            <i class="fa-solid fa-icons"></i>
            Font Awesome
        </h1>

        <p>
            Font Awesome provides ready-to-use icons.
        </p>

        <button class="btn btn-primary">
            <i class="fa-solid fa-right-to-bracket"></i>
            Login
        </button>

        <button class="btn btn-success">
            <i class="fa-solid fa-cart-shopping"></i>
            Add to Cart
        </button>

        <button class="btn btn-danger">
            <i class="fa-solid fa-trash"></i>
            Delete
        </button>

    </div>

</body>

</html>
```

---

# 16. Online Book Store Example 🛒

For your BCS353 **Online Book Store** project:

```html
<nav class="navbar">

    <a href="home.html">
        <i class="fa-solid fa-house"></i>
        Home
    </a>

    <a href="catalogue.html">
        <i class="fa-solid fa-book"></i>
        Catalogue
    </a>

    <a href="cart.html">
        <i class="fa-solid fa-cart-shopping"></i>
        Cart
    </a>

    <a href="login.html">
        <i class="fa-solid fa-user"></i>
        Login
    </a>

</nav>
```

This makes the navigation easier to understand visually.

---

# 17. Font Awesome vs Image Icons

| Feature         | Font Awesome           | Image Icon                             |
| --------------- | ---------------------- | -------------------------------------- |
| Installation    | CDN/local package      | Download images                        |
| Resize          | Easy                   | May affect quality depending on format |
| Color           | Easy with CSS          | Depends on image                       |
| File management | Fewer individual files | Many image files possible              |
| CSS styling     | Easy                   | More limited                           |
| Usage           | Very convenient        | Useful for custom graphics             |

---

# 18. Important Accessibility Point ♿

Icons should not always be the **only way** to communicate an action.

For example:

### Better

```html
<button class="btn btn-primary">
    <i class="fa-solid fa-trash"></i>
    Delete
</button>
```

### Less clear

```html
<button class="btn btn-primary">
    <i class="fa-solid fa-trash"></i>
</button>
```

The word **Delete** makes the purpose clear.

If an icon is purely decorative, it can be hidden from assistive technologies where appropriate.

---

# 19. How Font Awesome Works

```text
HTML
  ↓
Font Awesome CSS / Package
  ↓
Icon Class
  ↓
Font Awesome Icon
  ↓
CSS Styling
```

Example:

```html
<i class="fa-solid fa-house"></i>
```

```text
fa-solid
   +
fa-house
   ↓
🏠 Home Icon
```

---

# 20. Common Mistakes ⚠️

### ❌ Mistake 1: Forgetting Font Awesome CSS

```html
<i class="fa-solid fa-house"></i>
```

If Font Awesome is not loaded, the expected icon will not appear.

### ✅ Add the stylesheet

```html
<link
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.7.2/css/all.min.css">
```

---

### ❌ Mistake 2: Incorrect class name

```html
<i class="fa-solid fa-homee"></i>
```

The icon name must match a Font Awesome icon.

### ✅ Example

```html
<i class="fa-solid fa-house"></i>
```

---

# 🎯 21. Student Practice

Create a webpage called:

```text
fontawesome.html
```

Add icons for:

```text
🏠 Home
👤 User
📚 Books
🔍 Search
🛒 Cart
✉️ Email
📞 Phone
⚙️ Settings
```

Then create these buttons:

```text
[ 🔐 Login ]
[ 🛒 Add to Cart ]
[ 🗑️ Delete ]
[ 🔍 Search ]
```

### Challenge

Create a simple **Online Book Store Navigation Bar** using:

* Font Awesome
* Bootstrap
* HTML
* CSS

---

# ❓ 22. Important Questions

### Q1. What is Font Awesome?

Font Awesome is an icon library that provides ready-to-use icons for websites and applications.

### Q2. How do you add a Font Awesome icon?

```html
<i class="fa-solid fa-house"></i>
```

### Q3. What does `fa-solid` represent?

It specifies the **solid icon style**.

### Q4. What does `fa-house` represent?

It specifies the **house icon**.

### Q5. How can you increase the icon size?

Example:

```html
<i class="fa-solid fa-house fa-2x"></i>
```

### Q6. Can Font Awesome icons be used inside Bootstrap buttons?

**Yes.**

```html
<button class="btn btn-primary">
    <i class="fa-solid fa-user"></i>
    Login
</button>
```

---

# ⚡ 23. Quick Revision

```text
             Font Awesome
                   ↓
              Icon Library
                   ↓
        ┌──────────┼──────────┐
        ↓          ↓          ↓
      Solid      Regular    Brands
```

### Basic Syntax

```html
<i class="fa-solid fa-house"></i>
```

### Icon Size

```html
<i class="fa-solid fa-house fa-2x"></i>
```

### Brand Icon

```html
<i class="fa-brands fa-github"></i>
```

### Bootstrap + Font Awesome

```html
<button class="btn btn-primary">
    <i class="fa-solid fa-user"></i>
    Login
</button>
```

### Golden Rule ⭐

> **Font Awesome = Ready-to-use icons + CSS styling**

---

<p align="center">
  <img src="https://img.shields.io/badge/Font%20Awesome-Icons-528DD7?style=for-the-badge&logo=fontawesome&logoColor=white">
</p>

<p align="center">
  <b>BCS353 • Web Designing Workshop</b>
</p>

