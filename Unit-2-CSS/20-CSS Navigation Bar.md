# 🧭 CSS Navigation Bar

<p align="center">
  <img src="https://img.shields.io/badge/CSS-Navigation%20Bar-1572B6?style=for-the-badge&logo=css3&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Learn how to create and style navigation menus using HTML and CSS.
</p>

---

## 📌 1. What is a Navigation Bar?

A **Navigation Bar (Navbar)** is a section of a webpage that contains links to important pages or sections.

### Example

```text id="p3a6m9"
┌─────────────────────────────────────────────────┐
│ 🏠 Home │ About │ Courses │ Services │ Contact │
└─────────────────────────────────────────────────┘
```

### Simple Definition

> **Navigation Bar = A collection of links that helps users move between pages or sections of a website.**

---

# 🎯 2. Why Do We Need a Navigation Bar?

A navigation bar helps users:

* 🏠 Go to the Home page
* 👤 Learn About the website
* 📚 View Courses
* 🛠️ View Services
* 📞 Contact the organization
* 🔐 Login or Register

A good navigation bar makes a website easier to use.

---

# 🧩 3. Basic Navigation Bar Structure

A navigation bar can be created using:

```html id="yrv1jp"
<nav>
  <a href="#">Home</a>
  <a href="#">About</a>
  <a href="#">Courses</a>
  <a href="#">Contact</a>
</nav>
```

### Visual Structure

```text id="l9h9y6"
<nav>
   │
   ├── Home
   ├── About
   ├── Courses
   └── Contact
```

The `<nav>` element semantically identifies a navigation section.

---

# 🔹 4. Navigation Bar Using an Unordered List

A common structure is:

```html id="68u2ai"
<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Courses</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
```

By default, the list appears vertically with bullets.

```text id="5t4g8u"
• Home
• About
• Courses
• Contact
```

CSS can change this into a horizontal navigation bar.

---

# 🎨 5. Creating a Horizontal Navigation Bar

### HTML

```html id="1z6w4p"
<ul class="navbar">
  <li><a href="#">Home</a></li>
  <li><a href="#">About</a></li>
  <li><a href="#">Courses</a></li>
  <li><a href="#">Contact</a></li>
</ul>
```

### CSS

```css id="p0m2n7"
.navbar {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

.navbar li {
  display: inline-block;
}

.navbar a {
  display: block;
  padding: 15px 20px;
  text-decoration: none;
}
```

### Result

```text id="1y9f3k"
┌─────────────────────────────────────────┐
│ Home │ About │ Courses │ Contact        │
└─────────────────────────────────────────┘
```

---

# 🧹 6. Removing List Bullets

An unordered list normally displays bullets.

```html id="p7m5je"
<ul>
  <li>Home</li>
  <li>About</li>
  <li>Contact</li>
</ul>
```

Output:

```text id="njyq3c"
• Home
• About
• Contact
```

Remove the bullets using:

```css id="h4r5u7"
ul {
  list-style-type: none;
}
```

Now:

```text id="s6b8m2"
Home
About
Contact
```

---

# 📐 7. Removing Default Margin and Padding

Browsers apply default spacing to lists.

For a navigation bar, we commonly reset it:

```css id="8j2s0h"
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}
```

### Why?

It gives us better control over the navigation layout.

---

# 🧭 8. Horizontal Navigation Bar Using `display`

We can make list items appear horizontally.

```css id="4m9p2a"
li {
  display: inline-block;
}
```

Example:

```text id="b7w4x1"
Home    About    Courses    Contact
```

Another modern approach is Flexbox:

```css id="6g2v8p"
ul {
  display: flex;
}
```

Flexbox provides easier control over spacing and alignment.

---

# 🎨 9. Styling Navigation Links

We can style links using:

```css id="q1c7z9"
.navbar a {
  color: white;
  background-color: #333;
  text-decoration: none;
  padding: 15px 20px;
}
```

### Important Properties

| Property           | Purpose                       |
| ------------------ | ----------------------------- |
| `color`            | Changes text color            |
| `background-color` | Changes link background       |
| `padding`          | Creates space inside the link |
| `text-decoration`  | Removes underline             |
| `font-size`        | Changes text size             |
| `display`          | Controls layout               |

---

# 🖱️ 10. Hover Effect

A hover effect changes the appearance when the mouse moves over a navigation link.

```css id="c9u1b8"
.navbar a:hover {
  background-color: #555;
}
```

### Concept

```text id="5d0r7x"
Normal:

┌─────────┐
│  Home   │
└─────────┘

       ↓ Mouse over

┌─────────┐
│  Home   │  ← Different appearance
└─────────┘
```

### Why use hover?

It gives users visual feedback that an item is clickable.

---

# 🟢 11. Active Navigation Link

The `:active` pseudo-class applies while the link is being activated, such as during a mouse click.

```css id="3s6c4n"
.navbar a:active {
  background-color: green;
}
```

For a navigation bar, a separate class is often used to indicate the **current page**:

```html id="5h7p2x"
<a href="index.html" class="active">Home</a>
```

```css id="w6k2r8"
.navbar a.active {
  background-color: #04AA6D;
}
```

---

# 🔵 12. Vertical Navigation Bar

A navigation bar can also be vertical.

```css id="m8v5q2"
.navbar a {
  display: block;
  padding: 12px 20px;
}
```

### Result

```text id="g2n8w4"
┌──────────────┐
│ Home         │
├──────────────┤
│ About        │
├──────────────┤
│ Courses      │
├──────────────┤
│ Contact      │
└──────────────┘
```

---

# ↔️ 13. Horizontal vs Vertical Navbar

| Type       | Layout                         |
| ---------- | ------------------------------ |
| Horizontal | Links appear side by side      |
| Vertical   | Links appear one below another |

### Horizontal

```text id="o7w4s2"
Home | About | Courses | Contact
```

### Vertical

```text id="z1q8v6"
Home
About
Courses
Contact
```

---

# 🧱 14. Complete Horizontal Navigation Bar

### HTML

```html id="0w9k3p"
<!DOCTYPE html>
<html>

<head>
  <title>Navigation Bar</title>
  <link rel="stylesheet" href="style.css">
</head>

<body>

  <nav class="navbar">

    <ul>

      <li>
        <a href="#" class="active">Home</a>
      </li>

      <li>
        <a href="#">About</a>
      </li>

      <li>
        <a href="#">Courses</a>
      </li>

      <li>
        <a href="#">Services</a>
      </li>

      <li>
        <a href="#">Contact</a>
      </li>

    </ul>

  </nav>

</body>

</html>
```

### CSS

```css id="5s8h1j"
.navbar {
  background-color: #333;
}

.navbar ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  display: flex;
}

.navbar a {
  display: block;
  color: white;
  padding: 15px 20px;
  text-decoration: none;
}

.navbar a:hover {
  background-color: #555;
}

.navbar a.active {
  background-color: #04AA6D;
}
```

### Output

```text id="y5v1q8"
┌─────────────────────────────────────────────────────┐
│ Home │ About │ Courses │ Services │ Contact         │
└─────────────────────────────────────────────────────┘
```

---

#
