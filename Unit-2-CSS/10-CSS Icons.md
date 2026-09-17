# 🎨 CSS Icons

<p align="center">
  <img src="https://img.shields.io/badge/CSS-Icons-1572B6?style=for-the-badge&logo=css3&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Learn how to add and style icons in web pages using CSS.
</p>

---

## 1. 🔍 What are Icons?

**Icons** are small graphical symbols used to represent an action, object, or idea.

For example:

* 🏠 → Home
* 🔍 → Search
* 👤 → User
* ❤️ → Like
* ⚙️ → Settings
* 🛒 → Shopping Cart

Icons make a webpage **more attractive, easier to understand, and user-friendly**.

---

## 2. 💡 Can CSS Create Icons?

CSS itself does not provide a large collection of ready-made icons.

Instead, we commonly use:

1. **Icon libraries**
2. **SVG icons**
3. **Unicode/Emoji characters**
4. **CSS shapes**

For beginners, **icon libraries** are the easiest method.

---

# 3. ⭐ Popular Icon Libraries

Some commonly used icon libraries are:

| Library               | Example            |
| --------------------- | ------------------ |
| Font Awesome          | 🔍 ❤️ 🏠           |
| Bootstrap Icons       | 🏠 📱 ⭐            |
| Google Material Icons | Home, Search, Menu |
| Ionicons              | Mobile/Web icons   |

> **Note:** Icon libraries provide ready-made icons that can be styled using CSS.

---

# 4. 🧰 Font Awesome

**Font Awesome** is one of the most popular icon libraries used in websites.

It provides thousands of icons.

### Step 1: Add Font Awesome

Add the library inside the `<head>` section.

```html
<head>
    <link
        rel="stylesheet"
        href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
</head>
```

### Step 2: Add an Icon

```html
<i class="fa-solid fa-house"></i>
```

The above code displays a **home icon**.

---

# 5. 🏠 Example: Different Icons

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS Icons</title>

    <link
        rel="stylesheet"
        href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
</head>

<body>

    <h2>My Website</h2>

    <i class="fa-solid fa-house"></i>
    <i class="fa-solid fa-user"></i>
    <i class="fa-solid fa-heart"></i>
    <i class="fa-solid fa-magnifying-glass"></i>
    <i class="fa-solid fa-cart-shopping"></i>

</body>
</html>
```

---

# 6. 🎨 Styling Icons with CSS

Icons can be styled just like text.

We can change:

* Color
* Size
* Margin
* Background
* Alignment
* Hover effect

### Example

```html
<!DOCTYPE html>
<html>
<head>

    <title>Styled Icons</title>

    <link
        rel="stylesheet"
        href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

    <style>

        .icon {
            font-size: 40px;
            margin: 20px;
            color: blue;
        }

    </style>

</head>

<body>

    <i class="fa-solid fa-house icon"></i>
    <i class="fa-solid fa-user icon"></i>
    <i class="fa-solid fa-heart icon"></i>

</body>
</html>
```

### Result

```text
       🏠        👤        ❤️
      Home      User      Like
```

The CSS controls the appearance of the icons.

---

# 7. 📏 Changing Icon Size

Use the `font-size` property.

```css
.icon {
    font-size: 50px;
}
```

Example:

```html
<i class="fa-solid fa-house icon"></i>
```

```css
.icon {
    font-size: 50px;
}
```

### Remember

```text
font-size → controls icon size
```

---

# 8. 🎨 Changing Icon Color

Use the `color` property.

```css
.icon {
    color: green;
}
```

Example:

```html
<i class="fa-solid fa-heart icon"></i>
```

```css
.icon {
    color: red;
}
```

---

# 9. 🖱️ Icon Hover Effect

We can change an icon when the mouse pointer moves over it.

```css
.icon {
    font-size: 40px;
    color: blue;
    cursor: pointer;
}

.icon:hover {
    color: red;
}
```

### Concept

```text
Normal
   ↓
🔵 Blue Icon

Mouse Hover
   ↓
🔴 Red Icon
```

---

# 10. 🔘 Icons Inside Buttons

Icons are frequently used inside buttons.

```html
<button>
    <i class="fa-solid fa-download"></i>
    Download
</button>
```

CSS:

```css
button {
    padding: 10px 20px;
    font-size: 18px;
    cursor: pointer;
}
```

Another example:

```html
<button>
    <i class="fa-solid fa-user"></i>
    Login
</button>
```

---

# 11. 🔍 Icons in a Search Box

Icons can make forms easier to understand.

```html
<div class="search">
    <i class="fa-solid fa-magnifying-glass"></i>
    <input type="text" placeholder="Search">
</div>
```

CSS:

```css
.search {
    display: flex;
    align-items: center;
    gap: 10px;
}

.search i {
    font-size: 20px;
}

.search input {
    padding: 10px;
}
```

---

# 12. 🧭 Icons in Navigation Bar

Icons are commonly used in navigation menus.

```html
<nav>

    <a href="#">
        <i class="fa-solid fa-house"></i>
        Home
    </a>

    <a href="#">
        <i class="fa-solid fa-user"></i>
        Profile
    </a>

    <a href="#">
        <i class="fa-solid fa-gear"></i>
        Settings
    </a>

</nav>
```

CSS:

```css
nav a {
    text-decoration: none;
    margin: 15px;
    font-size: 18px;
}

nav i {
    margin-right: 5px;
}
```

---

# 13. 📦 Icon + Text

A common website design pattern is:

```text
🏠 Home
👤 Profile
⚙️ Settings
📞 Contact
```

HTML:

```html
<p>
    <i class="fa-solid fa-house"></i>
    Home
</p>

<p>
    <i class="fa-solid fa-user"></i>
    Profile
</p>

<p>
    <i class="fa-solid fa-gear"></i>
    Settings
</p>
```

CSS:

```css
p {
    font-size: 20px;
}

p i {
    margin-right: 10px;
}
```

---

# 14. 🖼️ Using SVG Icons

Another common approach is **SVG (Scalable Vector Graphics)**.

Example:

```html
<svg width="50" height="50" viewBox="0 0 24 24">
    <circle cx="12" cy="12" r="10"
            fill="lightblue"
            stroke="black"/>
</svg>
```

SVG icons have an important advantage:

> They can be scaled without losing quality.

---

# 15. 😊 Emoji vs Icon Library

| Feature                | Emoji     | Icon Library |
| ---------------------- | --------- | ------------ |
| Easy to use            | ✅         | ✅            |
| Professional UI        | Sometimes | ✅            |
| Consistent appearance  | ❌         | ✅            |
| CSS styling            | Limited   | ✅            |
| Large collection       | ❌         | ✅            |
| Suitable for modern UI | Sometimes | ✅            |

### Example

Emoji:

```html
😊
```

Icon library:

```html
<i class="fa-solid fa-user"></i>
```

---

# 16. 🧠 Important CSS Properties for Icons

| Property           | Purpose              |
| ------------------ | -------------------- |
| `font-size`        | Changes icon size    |
| `color`            | Changes icon color   |
| `margin`           | Adds outside spacing |
| `padding`          | Adds inside spacing  |
| `background-color` | Adds background      |
| `cursor`           | Changes mouse cursor |
| `text-shadow`      | Adds shadow          |
| `transform`        | Rotates/scales icon  |

Example:

```css
.icon {
    font-size: 40px;
    color: blue;
    margin: 15px;
    cursor: pointer;
}
```

---

# 17. ✨ Complete Example

```html
<!DOCTYPE html>
<html>
<head>

    <title>CSS Icons</title>

    <link
        rel="stylesheet"
        href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

    <style>

        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }

        .icon {
            font-size: 45px;
            margin: 20px;
            color: blue;
            cursor: pointer;
        }

        .icon:hover {
            color: red;
            transform: scale(1.2);
        }

    </style>

</head>

<body>

    <h1>CSS Icons</h1>

    <i class="fa-solid fa-house icon"></i>
    <i class="fa-solid fa-user icon"></i>
    <i class="fa-solid fa-heart icon"></i>
    <i class="fa-solid fa-gear icon"></i>

</body>
</html>
```

### What happens?

```text
        🏠      👤      ❤️      ⚙️
        ↓       ↓       ↓       ↓
      Blue    Blue    Blue    Blue

              Mouse Hover
                   ↓
             Icon becomes
             larger + red
```

---

# 18. 🎯 Real-World Uses

Icons are used in:

* 🌐 Navigation bars
* 🔍 Search boxes
* 🛒 Shopping websites
* 📱 Mobile applications
* 🔐 Login forms
* ⚙️ Settings pages
* ❤️ Like/Favourite buttons
* 📧 Email applications
* 📊 Dashboards
* 🗺️ Maps

---

# 19. 📝 Practice Questions

### Basic

1. What is an icon?
2. Why are icons used in websites?
3. Name any three icon libraries.
4. What is Font Awesome?
5. Which CSS property changes the size of an icon?
6. Which CSS property changes the color of an icon?

### Practical

7. Create a webpage containing Home, User, Search and Settings icons.
8. Change the icon size using CSS.
9. Add a hover effect to an icon.
10. Create a navigation bar containing icons and text.
11. Create a Login button with a user icon.
12. Create a Search box with a search icon.

---

# ⚡ Quick Revision

```text
CSS Icons
    │
    ├── Icon Libraries
    │      ├── Font Awesome
    │      ├── Bootstrap Icons
    │      └── Material Icons
    │
    ├── SVG Icons
    │
    └── Emoji / Unicode
```

### Important CSS Properties

```css
font-size       → Icon size
color           → Icon color
margin          → Outside spacing
padding         → Inside spacing
cursor          → Mouse pointer
background      → Icon background
transform       → Rotate / Scale
```

### Remember

> 💡 **Icons improve the visual appearance and usability of a webpage.**

> 🎨 **CSS can be used to control the size, color, spacing, and effects of icons.**

---

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-1572B6?style=for-the-badge">
</p>

<p align="center">
  <b>🎓 Learn • Practice • Design • Build</b>
</p>

