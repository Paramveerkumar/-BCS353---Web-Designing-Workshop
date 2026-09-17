# 🧭 CSS Navigation Bar

<p align="center">
  <img src="https://img.shields.io/badge/CSS-Navigation%20Bar-1572B6?style=for-the-badge&logo=css3&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Learn how to create horizontal and vertical navigation menus using HTML and CSS.
</p>

---

## 📌 1. What is a Navigation Bar?

A **navigation bar (navbar)** is a section of a webpage that contains links to important pages or sections.

### Example

```text id="9ezh6p"
┌─────────────────────────────────────────────────────┐
│  🏠 Home   📚 Courses   ℹ️ About   📞 Contact       │
└─────────────────────────────────────────────────────┘
```

### Simple Definition

> **Navigation Bar = A menu that helps users move from one webpage or section to another.**

---

# 🎯 2. Why Do We Use Navigation Bars?

Navigation bars help users:

* 🏠 Go to the Home page
* 📚 Find courses or services
* 👤 Open an About page
* 📞 Contact the website
* 🔐 Login/Register
* 🔗 Navigate between sections

A good navigation bar makes a website **easy to use**.

---

# 🧱 3. Basic HTML Structure

A navigation bar can be created using:

```html id="3t6s6n"
<nav>
  <a href="#">Home</a>
  <a href="#">About</a>
  <a href="#">Courses</a>
  <a href="#">Contact</a>
</nav>
```

### Important

The `<nav>` element represents a section containing navigation links.

The `<a>` element creates the actual links.

---

# 🎨 4. Basic CSS Navigation Bar

```html id="x6rr5j"
<!DOCTYPE html>
<html>

<head>

  <style>

    nav {
      background-color: #333;
      padding: 15px;
    }

    nav a {
      color: white;
      text-decoration: none;
      margin-right: 20px;
    }

  </style>

</head>

<body>

  <nav>
    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Courses</a>
    <a href="#">Contact</a>
  </nav>

</body>

</html>
```

### Output

```text id="46b83v"
┌──────────────────────────────────────────────┐
│ Home    About    Courses    Contact          │
└──────────────────────────────────────────────┘
```

---

# 🔹 5. Styling Navigation Links

We can style navigation links using CSS properties such as:

```css id="rxrjqp"
nav a {
  color: white;
  text-decoration: none;
  padding: 10px;
  margin: 5px;
}
```

### Common Properties

| Property           | Purpose                   |
| ------------------ | ------------------------- |
| `color`            | Changes text color        |
| `background-color` | Changes background        |
| `padding`          | Adds space inside link    |
| `margin`           | Adds space outside link   |
| `text-decoration`  | Removes/changes underline |
| `font-size`        | Changes text size         |
| `display`          | Controls layout           |
| `border`           | Adds border               |
| `border-radius`    | Creates rounded corners   |

---

# 🟢 6. Horizontal Navigation Bar

A horizontal navigation bar places links in a row.

```text id="4is0t6"
┌──────────────────────────────────────────┐
│ Home │ About │ Courses │ Contact │ Login │
└──────────────────────────────────────────┘
```

### CSS

```css id="x5x9c2"
nav {
  background-color: #333;
}

nav a {
  display: inline-block;
  color: white;
  padding: 15px 20px;
  text-decoration: none;
}
```

### Why `inline-block`?

It allows the links to:

* Stay on the same line
* Have controlled padding
* Have width/height behavior similar to a block box

---

# 🟡 7. Hover Effect

A navigation bar should usually provide feedback when the user moves the mouse over a link.

Use:

```css id="z5o6t3"
nav a:hover {
  background-color: #555;
}
```

### Example

Normal:

```text id="kmk7jc"
Home   About   Courses   Contact
```

Hovering over **Courses**:

```text id="7u8yba"
Home   About   [ Courses ]   Contact
                    ↑
                  Hover
```

---

# 🔵 8. Active Navigation Link

The `active` class can identify the current page.

```html id="2w5m0b"
<nav>
  <a href="index.html" class="active">Home</a>
  <a href="about.html">About</a>
  <a href="courses.html">Courses</a>
  <a href="contact.html">Contact</a>
</nav>
```

CSS:

```css id="shy4i8"
nav a.active {
  background-color: #04AA6D;
}
```

### Result

```text id="6qlf3p"
[ Home ]   About   Courses   Contact
    ↑
 Current page
```

---

# 🧭 9. Vertical Navigation Bar

A navigation bar can also be displayed vertically.

```text id="50wyjj"
┌─────────────────┐
│ Home            │
├─────────────────┤
│ About           │
├─────────────────┤
│ Courses         │
├─────────────────┤
│ Contact         │
└─────────────────┘
```

### CSS

```css id="w7bh0r"
nav a {
  display: block;
  padding: 15px;
  text-decoration: none;
}
```

`display: block` makes each link start on a new line.

---

# 🆚 10. Horizontal vs Vertical Navigation

| Type       | CSS Approach                       |
| ---------- | ---------------------------------- |
| Horizontal | `inline-block`, Flexbox, or Grid   |
| Vertical   | `display: block` or Flexbox column |

### Horizontal

```css id="w9q4oh"
nav {
  display: flex;
}
```

### Vertical

```css id="4y20vv"
nav {
  display: flex;
  flex-direction: column;
}
```

---

# 🟣 11. Navigation Bar Using Flexbox

Flexbox is a modern way to create navigation bars.

### HTML

```html id="jv2cc9"
<nav class="navbar">

  <a href="#">Home</a>
  <a href="#">About</a>
  <a href="#">Courses</a>
  <a href="#">Contact</a>

</nav>
```

### CSS

```css id="b6k3hz"
.navbar {
  display: flex;
  background-color: #333;
}

.navbar a {
  color: white;
  padding: 15px 20px;
  text-decoration: none;
}
```

### Output

```text id="n7qf8h"
┌─────────────────────────────────────────┐
│ Home │ About │ Courses │ Contact        │
└─────────────────────────────────────────┘
```

---

# 📏 12. Spacing with `gap`

Instead of using margins between flex items, we can use `gap`.

```css id="0x3y5b"
.navbar {
  display: flex;
  gap: 20px;
}
```

### Concept

```text id="g0hljv"
Home    20px    About    20px    Courses
```

`gap` adds consistent space between flex items.

---

# 🎨 13. Button-Style Navigation Links

Navigation links can look like buttons.

```css id="8t6w2n"
.navbar a {
  display: inline-block;
  padding: 10px 20px;
  background-color: #333;
  color: white;
  text-decoration: none;
  border-radius: 5px;
}

.navbar a:hover {
  background-color: #555;
}
```

### Result

```text id="j4gqna"
┌────────┐  ┌────────┐  ┌────────┐
│  Home  │  │ About  │  │ Contact│
└────────┘  └────────┘  └────────┘
```

---

# 🟠 14. Navigation Bar with Logo

A common website navbar contains:

* Logo
* Website name
* Navigation links

```text id="e2j7uh"
┌────────────────────────────────────────────────────┐
│ 🎓 MyWebsite   Home  Courses  About  Contact       │
└────────────────────────────────────────────────────┘
```

### HTML

```html id="x93p5r"
<nav class="navbar">

  <div class="logo">
    🎓 MyWebsite
  </div>

  <div class="links">
    <a href="#">Home</a>
    <a href="#">Courses</a>
    <a href="#">About</a>
    <a href="#">Contact</a>
  </div>

</nav>
```

### CSS

```css id="7j2f1h"
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #333;
  padding: 10px 20px;
}

.logo {
  color: white;
  font-size: 20px;
  font-weight: bold;
}

.links {
  display: flex;
  gap: 20px;
}

.links a {
  color: white;
  text-decoration: none;
}
```

---

# 📱 15. Responsive Navigation Bar

A navigation bar should also work on smaller screens.

### Desktop

```text id="y9t7cs"
Home | About | Courses | Contact | Login
```

### Mobile

```text id="f0b3wk"
Home
About
Courses
Contact
Login
```

We can use a media query:

```css id="h2v0e9"
@media (max-width: 600px) {

  .navbar {
    flex-direction: column;
    align-items: stretch;
  }

  .links {
    flex-direction: column;
    gap: 0;
  }

}
```

---

# 🧩 16. Complete Navigation Bar Example

```html id="s7e3l4"
<!DOCTYPE html>
<html>

<head>

  <meta
    name="viewport"
    content="width=device-width, initial-scale=1.0"
  >

  <title>CSS Navigation Bar</title>

  <style>

    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: Arial, sans-serif;
    }

    .navbar {
      display: flex;
      align-items: center;
      justify-content: space-between;
      background-color: #333;
      padding: 10px 20px;
    }

    .logo {
      color: white;
      font-size: 20px;
      font-weight: bold;
    }

    .links {
      display: flex;
    }

    .links a {
      color: white;
      text-decoration: none;
      padding: 14px 18px;
    }

    .links a:hover {
      background-color: #555;
    }

    .links a.active {
      background-color: #04AA6D;
    }

    @media (max-width: 600px) {

      .navbar {
        flex-direction: column;
        align-items: stretch;
      }

      .links {
        flex-direction: column;
      }

      .links a {
        text-align: center;
      }

    }

  </style>

</head>

<body>

  <nav class="navbar">

    <div class="logo">
      🎓 MyWebsite
    </div>

    <div class="links">

      <a href="#" class="active">
        Home
      </a>

      <a href="#">
        About
      </a>

      <a href="#">
        Courses
      </a>

      <a href="#">
        Contact
      </a>

    </div>

  </nav>

</body>

</html>
```

---

# 🔍 17. Important CSS Properties for Navigation

| Property           | Purpose                                  |
| ------------------ | ---------------------------------------- |
| `display: flex`    | Places links in a flexible layout        |
| `flex-direction`   | Controls row/column direction            |
| `justify-content`  | Controls horizontal distribution         |
| `align-items`      | Controls alignment                       |
| `gap`              | Adds space between links                 |
| `padding`          | Adds space inside links                  |
| `background-color` | Sets navbar background                   |
| `color`            | Sets link text color                     |
| `text-decoration`  | Removes underline                        |
| `:hover`           | Changes style when mouse moves over link |
| `@media`           | Makes navbar responsive                  |

---

# ⚠️ 18. Common Mistakes

### ❌ Mistake 1: Forgetting `href`

```html id="f7yqz1"
<a>Home</a>
```

Better:

```html id="y9q2a8"
<a href="index.html">Home</a>
```

---

### ❌ Mistake 2: Default Underline

Links normally have an underline.

```css id="x2f0bc"
text-decoration: none;
```

can remove it when desired.

---

### ❌ Mistake 3: No Hover Feedback

A navigation bar should provide visual feedback.

```css id="j3h4h5"
nav a:hover {
  background-color: #555;
}
```

---

### ❌ Mistake 4: Ignoring Mobile Screens

A horizontal navbar may not fit on a small screen.

Use a media query:

```css id="m4qv1j"
@media (max-width: 600px) {
  .links {
    flex-direction: column;
  }
}
```

---

# 🧠 19. Navigation Bar vs Navigation Menu

These terms are closely related.

### Navigation Menu

The collection of links:

```text
Home | About | Courses | Contact
```

### Navigation Bar

The area containing the navigation menu:

```text
┌─────────────────────────────────────────┐
│ Home | About | Courses | Contact        │
└─────────────────────────────────────────┘
```

---

# ❓ 20. Practice Questions

### Q1. What is a navigation bar?

### Q2. Which HTML element is used to represent a navigation section?

### Q3. Which HTML element creates a navigation link?

### Q4. How can you create a horizontal navigation bar using Flexbox?

### Q5. What is the purpose of `:hover`?

### Q6. What does `display: block` do to navigation links?

### Q7. What is the purpose of `gap` in a Flexbox navigation bar?

### Q8. How can a navigation bar be made responsive?

### Q9. What is the purpose of the `active` class?

### Q10. Create a navigation bar containing:

* Home
* About
* Courses
* Contact

---

# ⚡ 21. Quick Revision

```text id="9gk7wq"
                  NAVIGATION BAR
                        │
              ┌─────────┴─────────┐
              ↓                   ↓
             HTML                CSS
              │                   │
           <nav>              display:flex
              │                   │
           <a href>              gap
              │                   │
              └─────────┬─────────┘
                        ↓
                 Navigation Menu
                        │
          ┌─────────────┼─────────────┐
          ↓             ↓             ↓
        Normal        Hover         Active
          │             │             │
        Link         :hover        .active
                        │
                        ↓
                 Responsive Design
                        │
                     @media
```

---

## 📌 One-Line Definition

> **A CSS navigation bar is a styled collection of navigation links that helps users move between different pages or sections of a website.**

---

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-1572B6?style=for-the-badge&logo=css3&logoColor=white">
</p>

<p align="center">
  <b>🎓 BCS353 • Web Designing Workshop</b>
</p>
