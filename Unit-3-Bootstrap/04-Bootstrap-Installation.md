# 🚀 Bootstrap Installation

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Learn how to install and use Bootstrap in an HTML project.
</p>

---

## 📌 1. What is Bootstrap?

**Bootstrap** is a popular front-end framework used to create:

* 📱 Responsive websites
* 🎨 Attractive user interfaces
* 🧩 Buttons, cards, forms, navigation bars, etc.
* 📐 Responsive layouts using a grid system

Bootstrap provides **pre-designed CSS classes and JavaScript components**, so we can build websites faster.

### Simple Example

Instead of writing CSS:

```css
button {
    background-color: blue;
    color: white;
    padding: 10px 20px;
}
```

We can use Bootstrap:

```html
<button class="btn btn-primary">Click Me</button>
```

---

# 🛠️ 2. How to Install Bootstrap?

There are two common ways to use Bootstrap:

### Method 1 – CDN

Use Bootstrap directly from the internet.

### Method 2 – Download Bootstrap

Download Bootstrap files and use them locally.

---

# 🌐 3. Method 1 – Using Bootstrap CDN

**CDN** stands for **Content Delivery Network**.

It allows us to use Bootstrap files without downloading them manually.

### Step 1: Create an HTML File

Create:

```text
index.html
```

### Step 2: Add Bootstrap CSS

Place the Bootstrap CSS `<link>` inside the `<head>`:

```html
<link
    href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"
    rel="stylesheet"
>
```

### Step 3: Add Bootstrap JavaScript

Place this before the closing `</body>` tag:

```html
<script
    src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js">
</script>
```

> 💡 For classroom projects, use the Bootstrap version specified by your course/project requirements.

---

# 📝 4. Complete Bootstrap HTML Example

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">

    <!-- Responsive viewport -->
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <title>Bootstrap Demo</title>

    <!-- Bootstrap CSS -->
    <link
        href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"
        rel="stylesheet">
</head>

<body>

    <div class="container mt-5">

        <h1 class="text-primary">
            Hello Bootstrap!
        </h1>

        <p class="lead">
            Welcome to BCS353 Web Designing Workshop.
        </p>

        <button class="btn btn-success">
            Click Me
        </button>

    </div>

    <!-- Bootstrap JavaScript -->
    <script
        src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js">
    </script>

</body>

</html>
```

---

# 🖥️ 5. Run the Bootstrap Project

### Step 1

Save the file as:

```text
index.html
```

### Step 2

Open the file in a browser.

For example:

```text
Google Chrome
       ↓
index.html
       ↓
Bootstrap CSS
       ↓
Bootstrap Components
       ↓
Webpage
```

### Step 3

You should see:

```text
Hello Bootstrap!

Welcome to BCS353 Web Designing Workshop.

[ Click Me ]
```

---

# 📦 6. Method 2 – Download Bootstrap

Bootstrap can also be downloaded and used **without depending on a CDN**.

### Basic folder structure

```text
MyProject/
│
├── index.html
│
├── css/
│   └── bootstrap.min.css
│
└── js/
    └── bootstrap.bundle.min.js
```

Then link the files:

```html
<link rel="stylesheet" href="css/bootstrap.min.css">
```

and:

```html
<script src="js/bootstrap.bundle.min.js"></script>
```

### Advantage

The Bootstrap files are available locally.

### Disadvantage

You need to download and manage the Bootstrap files yourself.

---

# ⚖️ 7. CDN vs Local Bootstrap

| Feature                     | CDN                         | Local                       |
| --------------------------- | --------------------------- | --------------------------- |
| Installation                | Very easy                   | Requires download           |
| Internet                    | Required to fetch CDN files | Not required after download |
| Setup                       | Simple                      | More files to manage        |
| Beginner friendly           | ⭐⭐⭐⭐⭐                       | ⭐⭐⭐                         |
| File control                | Less                        | More                        |
| Suitable for classroom demo | ✅                           | ✅                           |

---

# 📁 8. Recommended BCS353 Project Structure

For a small Bootstrap project:

```text
OnlineBookStore/
│
├── index.html
├── login.html
├── registration.html
├── catalogue.html
├── cart.html
│
├── css/
│   └── style.css
│
├── images/
│   ├── logo.png
│   └── book1.jpg
│
└── js/
    └── script.js
```

If using CDN, you don't need to keep Bootstrap CSS/JS files inside the project.

---

# 🔍 9. Important HTML Code

Always include the viewport meta tag for responsive Bootstrap pages:

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

### Why?

It tells the browser to match the webpage width to the device screen.

```text
Desktop
┌───────────────────────────────┐
│          Webpage              │
└───────────────────────────────┘

Mobile
┌──────────────┐
│   Webpage    │
│              │
└──────────────┘
```

---

# 🎨 10. Test Whether Bootstrap is Working

Try this code:

```html
<button class="btn btn-primary">
    Bootstrap Button
</button>
```

If Bootstrap is loaded correctly, the button will have Bootstrap's styling.

You can also try:

```html
<h1 class="text-success">
    Bootstrap is Working!
</h1>
```

---

# 🧠 11. Important Bootstrap Classes

| Class           | Purpose                        |
| --------------- | ------------------------------ |
| `.container`    | Creates a responsive container |
| `.row`          | Creates a grid row             |
| `.col`          | Creates a column               |
| `.btn`          | Bootstrap button               |
| `.btn-primary`  | Primary button                 |
| `.text-primary` | Primary text color             |
| `.text-center`  | Center-aligns text             |
| `.mt-5`         | Adds top margin                |
| `.p-3`          | Adds padding                   |
| `.img-fluid`    | Makes an image responsive      |

Example:

```html
<div class="container text-center mt-5">

    <h1 class="text-primary">
        Bootstrap
    </h1>

    <button class="btn btn-success">
        Start Learning
    </button>

</div>
```

---

# 🔄 12. How Bootstrap Works

```text
HTML File
    ↓
Bootstrap CSS
    ↓
Bootstrap Classes
    ↓
Pre-designed Styles
    ↓
Responsive Webpage
```

For interactive components:

```text
HTML
  ↓
Bootstrap CSS + Bootstrap JS
  ↓
Components
  ↓
Interactive Webpage
```

---

# 💡 13. Why Use Bootstrap?

### Without Bootstrap

You may need to write:

```text
HTML
   +
CSS
   +
Responsive CSS
   +
Button CSS
   +
Grid CSS
   +
Navbar CSS
```

### With Bootstrap

```text
HTML
   +
Bootstrap Classes
   ↓
Responsive Website
```

Bootstrap reduces the amount of CSS we need to write manually.

---

# 🎯 14. Student Practice

Create a webpage called:

```text
bootstrap-demo.html
```

It should contain:

* ✅ A heading
* ✅ A paragraph
* ✅ Two Bootstrap buttons
* ✅ One Bootstrap card
* ✅ A responsive image
* ✅ A container
* ✅ A row with three columns

### Challenge

Make the three columns behave like this:

```text
Desktop:
┌──────┬──────┬──────┐
│ Col1 │ Col2 │ Col3 │
└──────┴──────┴──────┘

Mobile:
┌──────────────┐
│     Col1     │
├──────────────┤
│     Col2     │
├──────────────┤
│     Col3     │
└──────────────┘
```

Hint:

```html
<div class="col-12 col-md-4">
```

---

# ❓ 15. Important Questions

### Q1. What is Bootstrap?

Bootstrap is a front-end framework used to create responsive and attractive websites.

### Q2. What does CDN stand for?

**CDN = Content Delivery Network**

### Q3. Why do we use Bootstrap CDN?

It allows us to use Bootstrap CSS and JavaScript directly from an online server.

### Q4. What is the purpose of the viewport meta tag?

It helps the webpage display correctly on different screen sizes.

### Q5. Do we always need Bootstrap JavaScript?

No. Basic Bootstrap CSS classes such as buttons, spacing, colors, and grid do not require Bootstrap JavaScript. Interactive components such as modals, carousels, dropdowns, and collapses generally require the Bootstrap JavaScript bundle.

---

# ⚡ Quick Revision

```text
Bootstrap
   ↓
Front-end Framework
   ↓
Responsive + Attractive Websites
```

### Two common methods:

```text
1️⃣ CDN
2️⃣ Local Download
```

### CDN:

```html
<link rel="stylesheet" href="bootstrap.css">
```

### JavaScript:

```html
<script src="bootstrap.bundle.min.js"></script>
```

### Responsive viewport:

```html
<meta name="viewport"
      content="width=device-width, initial-scale=1">
```

### Bootstrap class example:

```html
<button class="btn btn-primary">
    Click Me
</button>
```

---

<p align="center">
  <img src="https://img.shields.io/badge/Bootstrap-Installation-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white">
</p>

<p align="center">
  <b>BCS353 • Web Designing Workshop</b>
</p>

