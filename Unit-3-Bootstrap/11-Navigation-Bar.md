# 🧭 Bootstrap Navigation Bar

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Bootstrap – Navigation Bar
</p>

---

## 1. 🧭 What is a Navigation Bar?

A **Navigation Bar (Navbar)** is a section of a website that provides links to different pages or sections.

### Example

```text
┌─────────────────────────────────────────────────────┐
│ 📚 Online Book Store   Home  Books  Login  Contact │
└─────────────────────────────────────────────────────┘
```

It helps users **move from one page/section to another**.

---

## 2. 🌐 Real-Life Example

A college website may have:

```text
Home | About | Departments | Courses | Faculty | Contact
```

An online bookstore may have:

```text
Home | Books | Categories | Cart | Login
```

---

# 3. 🧩 Bootstrap Navbar

Bootstrap provides a ready-made responsive navigation bar.

The basic class is:

```html
<nav class="navbar">
```

A commonly used responsive navbar structure is:

```html
<nav class="navbar navbar-expand-lg bg-body-tertiary">

    <div class="container">

        <!-- Brand -->
        <a class="navbar-brand" href="#">
            Online Book Store
        </a>

        <!-- Navigation Links -->
        <div class="navbar-nav">

            <a class="nav-link" href="#">Home</a>
            <a class="nav-link" href="#">Books</a>
            <a class="nav-link" href="#">Contact</a>

        </div>

    </div>

</nav>
```

---

# 4. 🔑 Important Navbar Classes

| Class               | Purpose                         |
| ------------------- | ------------------------------- |
| `.navbar`           | Creates the navigation bar      |
| `.navbar-brand`     | Website/logo/brand name         |
| `.navbar-nav`       | Contains navigation links       |
| `.nav-item`         | Represents a navigation item    |
| `.nav-link`         | Styles a navigation link        |
| `.navbar-expand-lg` | Expands navbar on large screens |
| `.navbar-toggler`   | Creates mobile menu button      |
| `.navbar-collapse`  | Contains collapsible content    |
| `.container`        | Organizes navbar content        |
| `.fixed-top`        | Fixes navbar to top             |
| `.sticky-top`       | Makes navbar sticky             |

---

# 5. 🏷️ Navbar Brand

The brand represents the website name or logo.

```html
<a class="navbar-brand" href="#">
    📚 Online Book Store
</a>
```

Example:

```text
📚 Online Book Store
```

A logo image can also be used:

```html
<a class="navbar-brand" href="#">
    <img src="logo.png"
         alt="Book Store Logo"
         width="40">
    Book Store
</a>
```

---

# 6. 🔗 Navigation Links

Navigation links are usually placed inside:

```html
<div class="navbar-nav">
```

Example:

```html
<div class="navbar-nav">

    <a class="nav-link" href="home.html">
        Home
    </a>

    <a class="nav-link" href="books.html">
        Books
    </a>

    <a class="nav-link" href="about.html">
        About
    </a>

    <a class="nav-link" href="contact.html">
        Contact
    </a>

</div>
```

---

# 7. 📱 Responsive Navbar

One of the biggest advantages of Bootstrap Navbar is **responsive behavior**.

On a large screen:

```text
┌──────────────────────────────────────────────┐
│ 📚 Book Store   Home  Books  About  Contact │
└──────────────────────────────────────────────┘
```

On a small screen:

```text
┌─────────────────────────────┐
│ 📚 Book Store          ☰   │
└─────────────────────────────┘
```

Clicking `☰` opens the navigation links.

---

# 8. ☰ Navbar Toggler

The mobile menu button is created using:

```html
<button class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarContent">

    <span class="navbar-toggler-icon"></span>

</button>
```

The corresponding collapsible area:

```html
<div class="collapse navbar-collapse"
     id="navbarContent">

    ...
    
</div>
```

### Important

The values must match:

```text
data-bs-target="#navbarContent"
             ↓
id="navbarContent"
```

---

# 9. 📱 Complete Responsive Navbar

```html
<!DOCTYPE html>
<html>

<head>

    <title>Bootstrap Navbar</title>

    <meta name="viewport"
          content="width=device-width, initial-scale=1">

    <link
        href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"
        rel="stylesheet">

</head>

<body>

<nav class="navbar navbar-expand-lg bg-body-tertiary">

    <div class="container">

        <!-- Brand -->
        <a class="navbar-brand" href="#">
            📚 Online Book Store
        </a>

        <!-- Mobile Button -->
        <button class="navbar-toggler"
                type="button"
                data-bs-toggle="collapse"
                data-bs-target="#navbarContent"
                aria-controls="navbarContent"
                aria-expanded="false"
                aria-label="Toggle navigation">

            <span class="navbar-toggler-icon"></span>

        </button>

        <!-- Navigation Links -->
        <div class="collapse navbar-collapse"
             id="navbarContent">

            <ul class="navbar-nav ms-auto">

                <li class="nav-item">
                    <a class="nav-link active"
                       href="#">
                        Home
                    </a>
                </li>

                <li class="nav-item">
                    <a class="nav-link"
                       href="#">
                        Books
                    </a>
                </li>

                <li class="nav-item">
                    <a class="nav-link"
                       href="#">
                        Categories
                    </a>
                </li>

                <li class="nav-item">
                    <a class="nav-link"
                       href="#">
                        Cart
                    </a>
                </li>

                <li class="nav-item">
                    <a class="nav-link"
                       href="#">
                        Login
                    </a>
                </li>

            </ul>

        </div>

    </div>

</nav>

<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"></script>

</body>
</html>
```

---

# 10. 🎯 Understanding the Structure

```text
<nav>
  │
  └── .container
       │
       ├── .navbar-brand
       │
       ├── .navbar-toggler
       │       ↓
       │      ☰
       │
       └── .navbar-collapse
             │
             └── .navbar-nav
                   │
                   ├── Home
                   ├── Books
                   ├── Categories
                   ├── Cart
                   └── Login
```

---

# 11. 🎨 Navbar Background

Bootstrap utility classes can be used to change the background.

### Light Navbar

```html
<nav class="navbar bg-light">
```

### Dark Navbar

```html
<nav class="navbar bg-dark">
```

For a dark navbar, use:

```html
<nav class="navbar navbar-dark bg-dark">
```

Example:

```html
<nav class="navbar navbar-dark bg-dark">

    <div class="container">

        <a class="navbar-brand" href="#">
            📚 Book Store
        </a>

    </div>

</nav>
```

---

# 12. 🟢 Active Link

The current page can be highlighted using:

```html
<a class="nav-link active" href="#">
    Home
</a>
```

Example:

```text
Home    Books    About    Contact
 ↑
Active
```

The `active` class indicates the currently selected/current navigation item.

---

# 13. 🚫 Disabled Link

A navigation link can be displayed as disabled:

```html
<a class="nav-link disabled"
   aria-disabled="true">
    Coming Soon
</a>
```

Example:

```text
Home | Books | Coming Soon
                ↑
             Disabled
```

---

# 14. 🔍 Navbar with Search Box

A search form can be added to a navbar.

```html
<form class="d-flex">

    <input class="form-control me-2"
           type="search"
           placeholder="Search Books">

    <button class="btn btn-outline-success"
            type="submit">
        Search
    </button>

</form>
```

### Complete Structure

```html
<nav class="navbar bg-body-tertiary">

    <div class="container">

        <a class="navbar-brand" href="#">
            📚 Book Store
        </a>

        <form class="d-flex">

            <input class="form-control me-2"
                   type="search"
                   placeholder="Search">

            <button class="btn btn-outline-success"
                    type="submit">
                Search
            </button>

        </form>

    </div>

</nav>
```

---

# 15. 📂 Dropdown Menu

A navbar can contain a dropdown menu.

```html
<li class="nav-item dropdown">

    <a class="nav-link dropdown-toggle"
       href="#"
       role="button"
       data-bs-toggle="dropdown">

        Categories

    </a>

    <ul class="dropdown-menu">

        <li>
            <a class="dropdown-item" href="#">
                Programming
            </a>
        </li>

        <li>
            <a class="dropdown-item" href="#">
                AI & ML
            </a>
        </li>

        <li>
            <a class="dropdown-item" href="#">
                Data Structures
            </a>
        </li>

    </ul>

</li>
```

### Result

```text
Categories ▼

    ┌─────────────────────┐
    │ Programming         │
    │ AI & ML             │
    │ Data Structures     │
    └─────────────────────┘
```

---

# 16. 📌 Fixed Navbar

A navbar can remain fixed at the top while scrolling.

Use:

```html
<nav class="navbar fixed-top">
```

Example:

```html
<nav class="navbar navbar-dark bg-dark fixed-top">

    <div class="container">

        <a class="navbar-brand" href="#">
            My Website
        </a>

    </div>

</nav>
```

### Important

A fixed navbar is removed from the normal document flow, so page content may need top spacing to prevent it from being hidden behind the navbar.

---

# 17. 📍 Sticky Navbar

A sticky navbar behaves normally until it reaches the top of the screen, then stays there while scrolling.

```html
<nav class="navbar sticky-top bg-dark">
```

### Difference

| Fixed                    | Sticky                                  |
| ------------------------ | --------------------------------------- |
| Fixed to viewport        | Sticks after reaching its position      |
| Removed from normal flow | Participates in normal flow until stuck |
| Always stays at top      | Becomes stuck during scrolling          |

---

# 18. 🧭 Navbar Alignment

Bootstrap utility classes can control alignment.

### Align to Right

```html
<ul class="navbar-nav ms-auto">
```

`ms-auto` adds automatic start margin and pushes the navigation toward the opposite side in a standard left-to-right layout.

### Example

```text
📚 Book Store              Home Books Login
                           ← ms-auto →
```

---

# 19. 🏫 College Website Example

A college website may use:

```text
┌──────────────────────────────────────────────────────────────┐
│ 🎓 ABC College   Home  About  Departments  Admissions Contact│
└──────────────────────────────────────────────────────────────┘
```

Possible pages:

```text
Home
About
Departments
Courses
Faculty
Admissions
Contact
```

---

# 20. 🛒 Online Book Store Example

For your BCS353 project:

```text
┌─────────────────────────────────────────────────────────────┐
│ 📚 Online Book Store   Home  Books  Catalogue  Cart  Login │
└─────────────────────────────────────────────────────────────┘
```

Suggested navigation:

| Menu         | Page                |
| ------------ | ------------------- |
| Home         | `home.html`         |
| Books        | `books.html`        |
| Catalogue    | `catalogue.html`    |
| Cart         | `cart.html`         |
| Login        | `login.html`        |
| Registration | `registration.html` |
| Contact      | `contact.html`      |

---

# 21. 🧠 Navbar vs Navigation Bar

There is no major conceptual difference.

```text
Navigation Bar
      ↓
General term for a website navigation area

Bootstrap Navbar
      ↓
Bootstrap's ready-made component for creating it
```

---

# 22. ⚠️ Common Mistakes

### ❌ Mistake 1: Forgetting Bootstrap JavaScript

The mobile toggler and dropdown require Bootstrap's JavaScript.

```html
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"></script>
```

---

### ❌ Mistake 2: Mismatched `id`

Incorrect:

```html
data-bs-target="#menu"
```

but:

```html
id="navbarContent"
```

### ✅ Correct

```html
data-bs-target="#navbarContent"
```

and:

```html
id="navbarContent"
```

---

### ❌ Mistake 3: Forgetting `navbar-expand-lg`

```html
<nav class="navbar">
```

If you want the navbar to expand at a large-screen breakpoint:

```html
<nav class="navbar navbar-expand-lg">
```

---

# 23. 🧪 Student Practice

### Task 1 – College Navbar

Create a responsive navbar containing:

```text
Home
About
Courses
Faculty
Contact
```

---

### Task 2 – Online Book Store

Create a navbar containing:

```text
📚 Book Store
Home
Books
Categories
Cart
Login
```

---

### Task 3 – Add Dropdown

Create:

```text
Categories ▼
    ├── Programming
    ├── AI & ML
    └── Data Structures
```

---

### Task 4 – Add Search

Add:

```text
[ Search Books... ] [ Search ]
```

---

# 24. 📌 Quick Revision

| Concept             | Remember                               |
| ------------------- | -------------------------------------- |
| `.navbar`           | Creates navbar                         |
| `.navbar-brand`     | Website/logo                           |
| `.navbar-nav`       | Navigation links container             |
| `.nav-item`         | Individual menu item                   |
| `.nav-link`         | Navigation link                        |
| `.navbar-expand-lg` | Expands navbar on large screens        |
| `.navbar-toggler`   | Mobile menu button                     |
| `.navbar-collapse`  | Collapsible navigation area            |
| `.active`           | Current/active link                    |
| `.disabled`         | Disabled link                          |
| `.dropdown`         | Creates dropdown                       |
| `.fixed-top`        | Fixed at top                           |
| `.sticky-top`       | Sticky during scrolling                |
| `.ms-auto`          | Pushes content using auto start margin |

---

## ⭐ Golden Rule

```text
Navbar
  ↓
Brand + Toggler + Navigation
  ↓
Responsive Menu
```

> 🎯 **Remember:** A Bootstrap Navbar provides a **responsive and organized way to navigate between pages and sections of a website**.

---

<p align="center">
  <img src="https://img.shields.io/badge/Bootstrap-Navigation%20Bar-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white">
</p>

<p align="center">
  <b>BCS353 • Web Designing Workshop</b>
</p>

