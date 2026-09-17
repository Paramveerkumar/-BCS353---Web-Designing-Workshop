# 📱 Bootstrap – Responsive Web Design

<p align="center">
  <img src="https://img.shields.io/badge/Bootstrap-Responsive%20Web%20Design-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Learn how Bootstrap helps us create websites that work on mobile, tablet, and desktop screens.
</p>

---

## 1. 📌 What is Responsive Web Design?

**Responsive Web Design** means creating a website that automatically adjusts its layout and content according to the **screen size and device**.

A responsive website should work properly on:

* 📱 Mobile phones
* 📟 Tablets
* 💻 Laptops
* 🖥️ Desktop computers

### Simple idea

```text
        RESPONSIVE WEBSITE
                │
        ┌───────┼───────┐
        ▼       ▼       ▼
      Mobile  Tablet  Desktop
        │       │       │
        └───────┼───────┘
                ▼
        Adjusted Layout
```

### Example

```text
Desktop
┌─────────────────────────────────────────┐
│ Logo    Home   About   Services   Login │
├─────────────────────────────────────────┤
│              Main Content               │
└─────────────────────────────────────────┘


Mobile
┌──────────────────┐
│ Logo          ☰  │
├──────────────────┤
│                  │
│   Main Content   │
│                  │
└──────────────────┘
```

---

# 2. 🤔 Why is Responsive Design Important?

Today, users access websites using different devices.

Without responsive design:

```text
Mobile Screen
┌──────────────┐
│ Website      │
│ ──────────── │
│      →→→     │
│ Content gets │
│ cut off      │
└──────────────┘
```

With responsive design:

```text
Mobile Screen
┌──────────────┐
│ Website      │
│              │
│ Content      │
│ fits screen  │
│ properly     │
└──────────────┘
```

### Benefits

| Benefit             | Explanation                                   |
| ------------------- | --------------------------------------------- |
| 📱 Mobile-friendly  | Works on small screens                        |
| 💻 Desktop-friendly | Uses available space                          |
| 📐 Flexible layout  | Elements adjust automatically                 |
| 👆 Better usability | Easier to use on touch screens                |
| 🔧 Less maintenance | One responsive website can serve many devices |

---

# 3. 🅱️ How Bootstrap Helps?

**Bootstrap** is a front-end framework that provides ready-made CSS classes and components.

Bootstrap includes a **responsive grid system** that helps developers create layouts for different screen sizes.

Instead of writing all responsive CSS manually:

```css
@media (max-width: 768px) {
    ...
}
```

we can use Bootstrap's responsive classes.

Example:

```html
<div class="col-md-6">
    Content
</div>
```

---

# 4. 📦 Bootstrap Container

Bootstrap provides containers to organize webpage content.

Two commonly used classes are:

```html
<div class="container">
    ...
</div>
```

and

```html
<div class="container-fluid">
    ...
</div>
```

---

## `.container`

The `.container` class provides a responsive fixed maximum width at Bootstrap's predefined breakpoints.

```html
<div class="container">
    <h1>Hello Bootstrap</h1>
</div>
```

---

## `.container-fluid`

The `.container-fluid` class uses the full available width.

```html
<div class="container-fluid">
    <h1>Hello Bootstrap</h1>
</div>
```

### Comparison

| Class              | Width                          |
| ------------------ | ------------------------------ |
| `.container`       | Responsive max-width container |
| `.container-fluid` | 100% available width           |

---

# 5. 🧱 Bootstrap Grid System

One of the most important features of Bootstrap is its **grid system**.

Bootstrap's grid uses:

```text
Container
   ↓
  Row
   ↓
Columns
```

### Structure

```html
<div class="container">

    <div class="row">

        <div class="col">
            Column 1
        </div>

        <div class="col">
            Column 2
        </div>

    </div>

</div>
```

---

# 6. 🔢 12-Column Grid

Bootstrap's grid is based on **12 columns**.

```text
12-column grid

┌──┬──┬──┬──┬──┬──┬──┬──┬──┬──┬──┬──┐
│1 │2 │3 │4 │5 │6 │7 │8 │9 │10│11│12│
└──┴──┴──┴──┴──┴──┴──┴──┴──┴──┴──┴──┘
```

For example:

```html
<div class="col-6">
    Content
</div>
```

uses:

```text
6 / 12 columns = 50%
```

Two `col-6` elements can therefore occupy one row:

```text
┌────────────────────┬────────────────────┐
│      col-6         │       col-6        │
│       50%          │        50%         │
└────────────────────┴────────────────────┘
```

---

# 7. 📐 Bootstrap Columns

Example:

```html
<div class="row">

    <div class="col-4">
        Column 1
    </div>

    <div class="col-4">
        Column 2
    </div>

    <div class="col-4">
        Column 3
    </div>

</div>
```

Calculation:

```text
4 + 4 + 4 = 12
```

So we get:

```text
┌──────────┬──────────┬──────────┐
│ Column 1 │ Column 2 │ Column 3 │
│   4/12   │   4/12   │   4/12   │
└──────────┴──────────┴──────────┘
```

---

# 8. 📱 Responsive Columns

Bootstrap allows us to specify how many columns an element should occupy at different breakpoints.

Example:

```html
<div class="col-12 col-md-6 col-lg-4">
    Content
</div>
```

Meaning:

```text
Small screens
     ↓
12 columns = Full width

Medium screens
     ↓
6 columns = Half width

Large screens
     ↓
4 columns = One-third width
```

### Visual

```text
📱 Mobile

┌────────────────────┐
│      Content       │
│      12/12         │
└────────────────────┘


💻 Medium

┌───────────┬───────────┐
│  Content  │  Content  │
│   6/12    │   6/12    │
└───────────┴───────────┘


🖥️ Large

┌──────┬──────┬──────┐
│      │      │      │
│ 4/12 │ 4/12 │ 4/12 │
└──────┴──────┴──────┘
```

---

# 9. 📊 Bootstrap Breakpoints

Bootstrap provides predefined responsive breakpoints.

| Breakpoint        | Prefix | Typical use          |
| ----------------- | ------ | -------------------- |
| Extra small       | none   | Small mobile screens |
| Small             | `sm`   | Larger mobile        |
| Medium            | `md`   | Tablets              |
| Large             | `lg`   | Laptops              |
| Extra large       | `xl`   | Large desktops       |
| Extra extra large | `xxl`  | Very large screens   |

> 📌 These are **Bootstrap breakpoint categories**, not exact device types.

---

# 10. 🔄 Mobile-First Design

Bootstrap follows a **mobile-first approach**.

This means we first design for smaller screens and then add styles for larger screens.

Example:

```html
<div class="col-12 col-md-6">
    Content
</div>
```

Here:

```text
Mobile
   ↓
col-12

Medium and larger
   ↓
col-md-6
```

### Simple concept

```text
Mobile First
     ↓
Small Screen
     ↓
Tablet
     ↓
Desktop
```

---

# 11. 🖼️ Responsive Images

Bootstrap provides the `.img-fluid` class.

```html
<img src="image.jpg" class="img-fluid" alt="Sample Image">
```

This makes the image responsive.

Conceptually, it applies:

```css
max-width: 100%;
height: auto;
```

### Without responsive image

```text
┌──────────────┐
│   Screen     │
│   ┌───────────────┐
│   │ Large Image   │────→ Overflow
│   └───────────────┘
└──────────────┘
```

### With `.img-fluid`

```text
┌──────────────┐
│   Screen     │
│  ┌──────────┐│
│  │  Image   ││
│  └──────────┘│
└──────────────┘
```

---

# 12. 📱 Responsive Text

Bootstrap provides responsive utility classes for many layout and typography needs.

Example:

```html
<h1 class="display-4">
    Responsive Website
</h1>
```

Bootstrap's display heading classes make large headings easier to style consistently.

You can also combine Bootstrap with CSS media queries when custom responsive behavior is required.

---

# 13. 🧭 Responsive Navigation

A navigation bar can also adapt to smaller screens.

Example:

```html
<nav class="navbar">
    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Contact</a>
</nav>
```

Bootstrap provides a complete responsive navbar component with classes such as:

```html
<nav class="navbar navbar-expand-lg">
    ...
</nav>
```

The `navbar-expand-lg` class controls when the navigation expands into a larger-screen layout.

---

# 14. 📝 Responsive Form

Bootstrap form controls can easily be placed inside the grid system.

```html
<div class="container">

    <div class="row">

        <div class="col-12 col-md-6">

            <label class="form-label">
                Name
            </label>

            <input type="text"
                   class="form-control"
                   placeholder="Enter your name">

        </div>

        <div class="col-12 col-md-6">

            <label class="form-label">
                Email
            </label>

            <input type="email"
                   class="form-control"
                   placeholder="Enter your email">

        </div>

    </div>

</div>
```

### Result

```text
📱 Mobile

Name
┌────────────────────┐
│                    │
└────────────────────┘

Email
┌────────────────────┐
│                    │
└────────────────────┘


💻 Medium+

┌──────────────────┬──────────────────┐
│ Name             │ Email            │
│                  │                  │
└──────────────────┴──────────────────┘
```

---

# 15. 🎴 Responsive Cards

Cards can also be arranged using the grid system.

```html
<div class="container">

    <div class="row">

        <div class="col-12 col-md-6 col-lg-4">
            <div class="card">
                <div class="card-body">
                    <h5>HTML</h5>
                    <p>Learn webpage structure.</p>
                </div>
            </div>
        </div>

        <div class="col-12 col-md-6 col-lg-4">
            <div class="card">
                <div class="card-body">
                    <h5>CSS</h5>
                    <p>Learn webpage styling.</p>
                </div>
            </div>
        </div>

        <div class="col-12 col-md-6 col-lg-4">
            <div class="card">
                <div class="card-body">
                    <h5>JavaScript</h5>
                    <p>Learn webpage behavior.</p>
                </div>
            </div>
        </div>

    </div>

</div>
```

### Layout

```text
📱 Mobile

┌───────────────┐
│ HTML          │
└───────────────┘

┌───────────────┐
│ CSS           │
└───────────────┘

┌───────────────┐
│ JavaScript    │
└───────────────┘


💻 Medium

┌────────────┬────────────┐
│ HTML       │ CSS        │
└────────────┴────────────┘
┌────────────┐
│ JavaScript │
└────────────┘


🖥️ Large

┌────────┬────────┬────────┐
│ HTML   │ CSS    │ JS     │
└────────┴────────┴────────┘
```

---

# 16. 🧩 Bootstrap CDN

To use Bootstrap in an HTML page, we can include its CSS from the official CDN.

```html
<link
    href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"
    rel="stylesheet">
```

Then Bootstrap classes can be used directly.

Example:

```html
<button class="btn btn-primary">
    Submit
</button>
```

> 📌 The exact Bootstrap version may change. In a project, use the version specified by your course/project requirements.

---

# 17. 💻 Complete Responsive Webpage

```html
<!DOCTYPE html>
<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta name="viewport"
          content="width=device-width, initial-scale=1">

    <title>Responsive Website</title>

    <link
        href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"
        rel="stylesheet">

</head>

<body>

<div class="container">

    <h1 class="text-center my-4">
        Responsive Web Design
    </h1>

    <div class="row g-4">

        <div class="col-12 col-md-6 col-lg-4">

            <div class="card h-100">

                <div class="card-body">

                    <h2 class="card-title">
                        HTML
                    </h2>

                    <p class="card-text">
                        HTML provides the structure
                        of a webpage.
                    </p>

                    <button class="btn btn-primary">
                        Learn HTML
                    </button>

                </div>

            </div>

        </div>


        <div class="col-12 col-md-6 col-lg-4">

            <div class="card h-100">

                <div class="card-body">

                    <h2 class="card-title">
                        CSS
                    </h2>

                    <p class="card-text">
                        CSS provides styling
                        and layout.
                    </p>

                    <button class="btn btn-success">
                        Learn CSS
                    </button>

                </div>

            </div>

        </div>


        <div class="col-12 col-md-6 col-lg-4">

            <div class="card h-100">

                <div class="card-body">

                    <h2 class="card-title">
                        Bootstrap
                    </h2>

                    <p class="card-text">
                        Bootstrap helps create
                        responsive interfaces.
                    </p>

                    <button class="btn btn-warning">
                        Learn Bootstrap
                    </button>

                </div>

            </div>

        </div>

    </div>

</div>

</body>
</html>
```

---

# 18. 🧠 Important Bootstrap Responsive Classes

| Class               | Purpose                                |
| ------------------- | -------------------------------------- |
| `.container`        | Responsive max-width container         |
| `.container-fluid`  | Full-width container                   |
| `.row`              | Creates a grid row                     |
| `.col`              | Flexible column                        |
| `.col-12`           | 12-column width                        |
| `.col-md-6`         | 6 columns from `md` breakpoint         |
| `.col-lg-4`         | 4 columns from `lg` breakpoint         |
| `.img-fluid`        | Responsive image                       |
| `.navbar-expand-lg` | Expands navbar from `lg` breakpoint    |
| `.g-4`              | Adds grid gap                          |
| `.h-100`            | Sets height to 100% within its context |

---

# 19. ⚖️ Normal CSS vs Bootstrap

| Normal CSS                    | Bootstrap                           |
| ----------------------------- | ----------------------------------- |
| Write CSS manually            | Use predefined classes              |
| Create media queries yourself | Responsive utilities/grid available |
| More customization            | Faster development                  |
| More code for common layouts  | Less code for common layouts        |
| Full control                  | Ready-made components + utilities   |

### Important

Bootstrap does **not** replace CSS.

```text
HTML
  ↓
Structure

CSS
  ↓
Custom Styling

Bootstrap
  ↓
Ready-made CSS + Components + Responsive Utilities
```

---

# 20. 🔄 Responsive Design Flow

```text
             WEBPAGE
                │
                ▼
        Bootstrap Container
                │
                ▼
               Row
                │
        ┌───────┼────────┐
        ▼       ▼        ▼
      Column  Column   Column
        │       │        │
        └───────┼────────┘
                ▼
       Responsive Classes
                │
        ┌───────┼────────┐
        ▼       ▼        ▼
      Mobile  Tablet  Desktop
```

---

# 21. 📌 Important Points to Remember

1. Responsive design allows a webpage to adapt to different screen sizes.
2. Bootstrap provides a responsive **12-column grid system**.
3. `.container` provides a responsive max-width container.
4. `.container-fluid` uses the full available width.
5. `.row` contains columns.
6. Bootstrap uses responsive breakpoint prefixes such as `sm`, `md`, `lg`, `xl`, and `xxl`.
7. `.col-12 col-md-6` means full width on smaller screens and half width from the `md` breakpoint.
8. `.img-fluid` makes images responsive.
9. Bootstrap follows a **mobile-first** approach.
10. Bootstrap can be combined with custom CSS when additional styling is required.

---

# 22. 📝 Practice Questions

### Q1. What is Responsive Web Design?

### Q2. Why is responsive design important?

### Q3. What is the Bootstrap grid system?

### Q4. How many columns are available in the Bootstrap grid?

### Q5. What is the difference between `.container` and `.container-fluid`?

### Q6. What is the purpose of the `.row` class?

### Q7. What does this class combination mean?

```html
<div class="col-12 col-md-6 col-lg-4">
```

### Q8. What is the purpose of `.img-fluid`?

### Q9. What does mobile-first design mean?

### Q10. What is the purpose of `navbar-expand-lg`?

---

# ⚡ Quick Revision

```text
BOOTSTRAP RESPONSIVE WEB DESIGN
│
├── Responsive Design
│   ├── Mobile
│   ├── Tablet
│   └── Desktop
│
├── Container
│   ├── .container
│   └── .container-fluid
│
├── Grid
│   ├── .row
│   ├── .col
│   ├── .col-12
│   ├── .col-md-6
│   └── .col-lg-4
│
├── Breakpoints
│   ├── sm
│   ├── md
│   ├── lg
│   ├── xl
│   └── xxl
│
├── Responsive Components
│   ├── Navbar
│   ├── Cards
│   └── Forms
│
└── Responsive Images
    └── .img-fluid
```

---

## ⭐ One-Line Definition

> **Responsive Web Design is the practice of creating webpages that automatically adapt their layout and content to different screen sizes and devices.**

<p align="center">
  <img src="https://img.shields.io/badge/Bootstrap-Responsive%20Design-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 • Web Designing Workshop</b>
</p>

