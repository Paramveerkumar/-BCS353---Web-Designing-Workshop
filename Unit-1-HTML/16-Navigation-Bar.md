# 🧭 HTML Navigation Bar

## 📌 Introduction

A **Navigation Bar**, commonly called a **Navbar**, is used to help users move from one webpage or section to another.

A navigation bar usually contains links such as:

* 🏠 Home
* 📖 About
* 🛠️ Services
* 📞 Contact

You can see navigation bars on almost every website.

---

# 1️⃣ What is a Navigation Bar?

A navigation bar is a collection of links that helps users navigate through a website.

### Example

```text
------------------------------------------------
 Home | About | Courses | Contact
------------------------------------------------
```

When a user clicks a link, they are taken to another webpage or section.

---

# 2️⃣ Creating a Simple Navigation Bar

Navigation links are created using the HTML `<a>` tag.

### Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>Navigation Bar</title>
</head>

<body>

    <a href="home.html">Home</a>
    <a href="about.html">About</a>
    <a href="courses.html">Courses</a>
    <a href="contact.html">Contact</a>

</body>

</html>
```

### 📝 Explanation

The `<a>` tag creates a hyperlink.

```html
<a href="home.html">Home</a>
```

Here:

* `href` → Specifies the destination page.
* `Home` → Text displayed to the user.

---

# 3️⃣ Using the `<nav>` Element

HTML provides the semantic `<nav>` element for navigation links.

### Example

```html
<nav>

    <a href="home.html">Home</a>
    <a href="about.html">About</a>
    <a href="courses.html">Courses</a>
    <a href="contact.html">Contact</a>

</nav>
```

The `<nav>` element tells the browser and developers that these links are mainly used for **navigation**.

---

# 4️⃣ Navigation Bar Using a List

A navigation bar is often created using:

* `<nav>`
* `<ul>`
* `<li>`
* `<a>`

### Structure

```text
<nav>
   │
   └── <ul>
        │
        ├── <li> → Home
        ├── <li> → About
        ├── <li> → Courses
        └── <li> → Contact
```

---

## Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>Navigation Bar</title>
</head>

<body>

    <nav>

        <ul>

            <li>
                <a href="home.html">Home</a>
            </li>

            <li>
                <a href="about.html">About</a>
            </li>

            <li>
                <a href="courses.html">Courses</a>
            </li>

            <li>
                <a href="contact.html">Contact</a>
            </li>

        </ul>

    </nav>

</body>

</html>
```

By default, the navigation links will appear vertically as a list.

---

# 5️⃣ Horizontal Navigation Bar Using CSS

CSS can be used to display navigation links horizontally.

### Example

```html
<!DOCTYPE html>
<html>

<head>

    <title>Horizontal Navigation Bar</title>

    <style>

        ul {
            list-style-type: none;
            margin: 0;
            padding: 0;
        }

        li {
            display: inline;
        }

        a {
            text-decoration: none;
            padding: 10px;
        }

    </style>

</head>

<body>

    <nav>

        <ul>

            <li>
                <a href="home.html">Home</a>
            </li>

            <li>
                <a href="about.html">About</a>
            </li>

            <li>
                <a href="courses.html">Courses</a>
            </li>

            <li>
                <a href="contact.html">Contact</a>
            </li>

        </ul>

    </nav>

</body>

</html>
```

### 📝 Important CSS Properties

| Property                | Purpose                          |
| ----------------------- | -------------------------------- |
| `list-style-type: none` | Removes bullet points            |
| `display: inline`       | Displays list items horizontally |
| `text-decoration: none` | Removes underline from links     |
| `padding`               | Adds space around links          |

---

# 6️⃣ Styled Navigation Bar

Now let's create a more attractive navigation bar.

```html
<!DOCTYPE html>
<html>

<head>

    <title>Styled Navigation Bar</title>

    <style>

        nav {
            background-color: #333;
        }

        ul {
            list-style-type: none;
            margin: 0;
            padding: 0;
            overflow: hidden;
        }

        li {
            float: left;
        }

        li a {
            display: block;
            color: white;
            text-align: center;
            padding: 14px 20px;
            text-decoration: none;
        }

        li a:hover {
            background-color: #555;
        }

    </style>

</head>

<body>

    <nav>

        <ul>

            <li>
                <a href="home.html">Home</a>
            </li>

            <li>
                <a href="about.html">About</a>
            </li>

            <li>
                <a href="courses.html">Courses</a>
            </li>

            <li>
                <a href="contact.html">Contact</a>
            </li>

        </ul>

    </nav>

</body>

</html>
```

---

# 7️⃣ Understanding the Navigation Bar CSS

## Remove Bullet Points

```css
ul {
    list-style-type: none;
}
```

This removes the default bullets:

```text
• Home
• About
• Contact
```

---

## Display Items Horizontally

```css
li {
    float: left;
}
```

This places navigation items side by side.

```text
Home   About   Courses   Contact
```

---

## Style Navigation Links

```css
li a {
    display: block;
    color: white;
    padding: 14px 20px;
    text-decoration: none;
}
```

This:

* Changes text color.
* Adds spacing.
* Removes the underline.
* Makes the clickable area larger.

---

# 8️⃣ The `:hover` Effect

The `:hover` selector changes the style when the mouse pointer moves over an element.

### Example

```css
li a:hover {
    background-color: #555;
}
```

When the user moves the mouse over a navigation link, its background color changes.

🎯 This makes the navigation bar more interactive.

---

# 9️⃣ Active Navigation Link

Usually, we highlight the page that the user is currently viewing.

For example, if the user is on the Home page:

```html
<a class="active" href="home.html">Home</a>
```

### CSS

```css
.active {
    background-color: green;
}
```

---

## Complete Example

```html
<!DOCTYPE html>
<html>

<head>

    <title>Navigation Bar with Active Link</title>

    <style>

        body {
            margin: 0;
        }

        nav {
            background-color: #333;
        }

        ul {
            list-style-type: none;
            margin: 0;
            padding: 0;
            overflow: hidden;
        }

        li {
            float: left;
        }

        li a {
            display: block;
            color: white;
            text-align: center;
            padding: 14px 20px;
            text-decoration: none;
        }

        li a:hover {
            background-color: #555;
        }

        .active {
            background-color: green;
        }

    </style>

</head>

<body>

    <nav>

        <ul>

            <li>
                <a class="active" href="home.html">Home</a>
            </li>

            <li>
                <a href="about.html">About</a>
            </li>

            <li>
                <a href="courses.html">Courses</a>
            </li>

            <li>
                <a href="contact.html">Contact</a>
            </li>

        </ul>

    </nav>

    <h1>Welcome to My Website</h1>

</body>

</html>
```

---

# 🔟 Navigation to Sections on the Same Page

A navigation bar can also move users to different sections of the **same webpage**.

### Navigation Links

```html
<nav>

    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#courses">Courses</a>
    <a href="#contact">Contact</a>

</nav>
```

### Sections

```html
<section id="home">
    <h2>Home</h2>
</section>

<section id="about">
    <h2>About</h2>
</section>

<section id="courses">
    <h2>Courses</h2>
</section>

<section id="contact">
    <h2>Contact</h2>
</section>
```

### 📝 How Does It Work?

```text
href="#about"
       ↓
id="about"
```

The link connects to the element with the matching `id`.

---

# 🧠 Easy Concept Map

```text
                   NAVIGATION BAR
                          │
                    <nav> Element
                          │
                         <ul>
                          │
              ┌───────────┼───────────┐
              │           │           │
            <li>        <li>        <li>
              │           │           │
            <a>         <a>         <a>
              │           │           │
            Home       About      Contact
```

---

# 🎯 Important Elements

| Element | Purpose                   |
| ------- | ------------------------- |
| `<nav>` | Defines navigation links  |
| `<ul>`  | Creates an unordered list |
| `<li>`  | Defines a list item       |
| `<a>`   | Creates a hyperlink       |

---

# 🎯 Chapter Summary

* A navigation bar helps users move between webpages or sections.
* The `<nav>` element is used to define navigation links.
* The `<a>` element creates hyperlinks.
* Navigation bars are often created using `<ul>` and `<li>`.
* CSS can make navigation links horizontal.
* The `:hover` selector adds an interactive effect.
* An `active` class can highlight the current page.
* Navigation links can also connect to sections on the same page using `id`.

---

# ❓ Practice Questions

### Question 1

What is the purpose of a navigation bar?

### Question 2

Which HTML element is used to define navigation links?

### Question 3

Which HTML tag is used to create a hyperlink?

### Question 4

Which CSS property removes bullet points from a list?

### Question 5

What is the purpose of the `:hover` selector?

### Question 6

How can you create a link to a section on the same webpage?

---

# 💻 Practice Task

Create a navigation bar containing:

* 🏠 Home
* ℹ️ About
* 📚 Courses
* 📞 Contact

Requirements:

* Display the links horizontally.
* Remove list bullet points.
* Add background color.
* Change the link color.
* Add a `:hover` effect.
* Highlight the active page.

🎯 **Goal:** Learn how to create a simple and attractive navigation bar using **HTML and CSS**.

