# 🃏 Bootstrap Cards

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Bootstrap – Cards
</p>

---

## 1. 🃏 What is a Card?

A **Card** is a flexible container used to display related information in a neat and organized format.

A card can contain:

* 🖼️ Image
* 📝 Title
* 📄 Description
* 🔗 Links
* 🔘 Buttons
* 💰 Price
* ⭐ Rating

### Simple Example

```text
┌─────────────────────────┐
│                         │
│       🖼️ Image          │
│                         │
├─────────────────────────┤
│  📚 Web Development     │
│                         │
│  Learn HTML, CSS and    │
│  Bootstrap.             │
│                         │
│       [ Read More ]     │
└─────────────────────────┘
```

---

## 2. 💡 Real-Life Examples

Cards are commonly used for:

* 🛍️ Products
* 📚 Books
* 👨‍🎓 Student profiles
* 📰 News articles
* 💼 Services
* 👨‍💻 Projects
* 🏨 Hotel information
* 🍔 Food items

For example, an online bookstore can display every book as a card.

---

# 3. 🧩 Bootstrap Card

Bootstrap provides a ready-made **Card component**.

Basic syntax:

```html
<div class="card">

    <div class="card-body">
        <h5 class="card-title">Book Title</h5>

        <p class="card-text">
            Book description goes here.
        </p>

        <a href="#" class="btn btn-primary">
            Read More
        </a>
    </div>

</div>
```

---

# 4. 🔑 Important Card Classes

| Class              | Purpose               |
| ------------------ | --------------------- |
| `.card`            | Creates the card      |
| `.card-body`       | Main content area     |
| `.card-title`      | Card title            |
| `.card-text`       | Card description      |
| `.card-img-top`    | Image at the top      |
| `.card-img-bottom` | Image at the bottom   |
| `.card-header`     | Header section        |
| `.card-footer`     | Footer section        |
| `.card-link`       | Link inside card      |
| `.card-group`      | Groups multiple cards |

---

# 5. 🖼️ Card with Image

We can add an image at the top of a card.

```html
<div class="card" style="width: 18rem;">

    <img src="book.jpg"
         class="card-img-top"
         alt="Web Development Book">

    <div class="card-body">

        <h5 class="card-title">
            Web Development
        </h5>

        <p class="card-text">
            Learn HTML, CSS and Bootstrap.
        </p>

        <a href="#" class="btn btn-primary">
            Read More
        </a>

    </div>

</div>
```

### Structure

```text
┌─────────────────────────┐
│                         │
│        🖼️ Image         │
│                         │
├─────────────────────────┤
│ Web Development         │ ← card-title
│                         │
│ Learn HTML, CSS and     │ ← card-text
│ Bootstrap.              │
│                         │
│ [ Read More ]           │
└─────────────────────────┘
```

---

# 6. 📝 Card Title and Text

### Card Title

```html
<h5 class="card-title">
    Web Development
</h5>
```

### Card Text

```html
<p class="card-text">
    Learn HTML, CSS and Bootstrap.
</p>
```

The title identifies the content, while the text provides additional information.

---

# 7. 🔘 Buttons in Cards

Bootstrap buttons can easily be added to cards.

```html
<a href="#" class="btn btn-primary">
    Read More
</a>
```

Multiple buttons can also be used:

```html
<div class="card-body">

    <h5 class="card-title">
        HTML Course
    </h5>

    <p class="card-text">
        Learn HTML from basics.
    </p>

    <a href="#" class="btn btn-primary">
        Start Course
    </a>

    <a href="#" class="btn btn-outline-secondary">
        Details
    </a>

</div>
```

---

# 8. 📌 Card Header and Footer

A card can have a header and footer.

```html
<div class="card">

    <div class="card-header">
        Featured Course
    </div>

    <div class="card-body">

        <h5 class="card-title">
            Bootstrap
        </h5>

        <p class="card-text">
            Learn responsive web design.
        </p>

        <a href="#" class="btn btn-primary">
            Learn More
        </a>

    </div>

    <div class="card-footer">
        BCS353
    </div>

</div>
```

### Structure

```text
┌─────────────────────────┐
│ Featured Course         │ ← Header
├─────────────────────────┤
│ Bootstrap               │
│                         │
│ Learn responsive web    │
│ design.                 │
│                         │
│ [ Learn More ]          │
├─────────────────────────┤
│ BCS353                  │ ← Footer
└─────────────────────────┘
```

---

# 9. 📚 Multiple Cards

We can create multiple cards for different products or courses.

```html
<div class="container">

    <div class="row">

        <div class="col-md-4">

            <div class="card">
                <div class="card-body">

                    <h5 class="card-title">
                        HTML
                    </h5>

                    <p class="card-text">
                        Learn the basics of HTML.
                    </p>

                    <a href="#" class="btn btn-primary">
                        Learn
                    </a>

                </div>
            </div>

        </div>

        <div class="col-md-4">

            <div class="card">
                <div class="card-body">

                    <h5 class="card-title">
                        CSS
                    </h5>

                    <p class="card-text">
                        Learn styling with CSS.
                    </p>

                    <a href="#" class="btn btn-primary">
                        Learn
                    </a>

                </div>
            </div>

        </div>

        <div class="col-md-4">

            <div class="card">
                <div class="card-body">

                    <h5 class="card-title">
                        Bootstrap
                    </h5>

                    <p class="card-text">
                        Build responsive websites.
                    </p>

                    <a href="#" class="btn btn-primary">
                        Learn
                    </a>

                </div>
            </div>

        </div>

    </div>

</div>
```

### Layout

```text
┌──────────────┐ ┌──────────────┐ ┌──────────────┐
│    HTML      │ │     CSS      │ │  Bootstrap   │
│              │ │              │ │              │
│ Learn HTML   │ │ Learn CSS    │ │ Responsive   │
│              │ │              │ │ Web Design   │
│ [ Learn ]    │ │ [ Learn ]    │ │ [ Learn ]    │
└──────────────┘ └──────────────┘ └──────────────┘
```

---

# 10. 📱 Responsive Cards

Bootstrap's Grid System can make cards responsive.

Example:

```html
<div class="col-12 col-md-6 col-lg-4">
```

Meaning:

```text
Mobile  → 1 card per row
Tablet  → 2 cards per row
Desktop → 3 cards per row
```

### Example

```html
<div class="container">

    <div class="row g-4">

        <div class="col-12 col-md-6 col-lg-4">
            <div class="card">
                <div class="card-body">
                    <h5 class="card-title">HTML</h5>
                    <p class="card-text">
                        Learn HTML.
                    </p>
                </div>
            </div>
        </div>

        <div class="col-12 col-md-6 col-lg-4">
            <div class="card">
                <div class="card-body">
                    <h5 class="card-title">CSS</h5>
                    <p class="card-text">
                        Learn CSS.
                    </p>
                </div>
            </div>
        </div>

        <div class="col-12 col-md-6 col-lg-4">
            <div class="card">
                <div class="card-body">
                    <h5 class="card-title">Bootstrap</h5>
                    <p class="card-text">
                        Learn Bootstrap.
                    </p>
                </div>
            </div>
        </div>

    </div>

</div>
```

---

# 11. 🎨 Card Colors

Bootstrap utility classes can be used to style cards.

```html
<div class="card text-bg-primary">
```

Other examples:

```html
<div class="card text-bg-success">
```

```html
<div class="card text-bg-danger">
```

```html
<div class="card text-bg-warning">
```

```html
<div class="card text-bg-dark">
```

### Example

```html
<div class="card text-bg-primary">

    <div class="card-body">

        <h5 class="card-title">
            Bootstrap
        </h5>

        <p class="card-text">
            Responsive web development.
        </p>

    </div>

</div>
```

---

# 12. 🖼️ Card Image Overlay

Text can be displayed over an image.

```html
<div class="card text-bg-dark">

    <img src="web.jpg"
         class="card-img"
         alt="Web Development">

    <div class="card-img-overlay">

        <h5 class="card-title">
            Web Development
        </h5>

        <p class="card-text">
            Learn modern web technologies.
        </p>

    </div>

</div>
```

### Visual Idea

```text
┌────────────────────────────┐
│                            │
│       🖼️ BACKGROUND        │
│                            │
│    Web Development         │
│    Learn modern web        │
│    technologies.           │
│                            │
└────────────────────────────┘
```

---

# 13. 🛒 Online Book Store Card

A book can be represented using a Bootstrap card.

```html
<div class="card" style="width: 18rem;">

    <img src="book.jpg"
         class="card-img-top"
         alt="HTML Book">

    <div class="card-body">

        <h5 class="card-title">
            HTML & CSS
        </h5>

        <p class="card-text">
            Complete beginner guide to HTML and CSS.
        </p>

        <h6>₹499</h6>

        <a href="#" class="btn btn-success">
            Add to Cart
        </a>

    </div>

</div>
```

### Result

```text
┌─────────────────────────┐
│       📕 Book Image     │
├─────────────────────────┤
│ HTML & CSS              │
│                         │
│ Complete beginner      │
│ guide to HTML and CSS. │
│                         │
│ ₹499                    │
│                         │
│ [ Add to Cart ]         │
└─────────────────────────┘
```

---

# 14. 📐 Card Width

A card can have a fixed width:

```html
<div class="card" style="width: 18rem;">
```

Here:

```text
18rem
 ↓
Card width
```

However, for responsive layouts, it is generally better to place cards inside Bootstrap's grid columns rather than depending on a fixed width.

---

# 15. 🔗 Card Links

Cards can contain links.

```html
<div class="card-body">

    <h5 class="card-title">
        Web Design
    </h5>

    <p class="card-text">
        Learn web designing.
    </p>

    <a href="#" class="card-link">
        Course
    </a>

    <a href="#" class="card-link">
        Details
    </a>

</div>
```

---

# 16. 🧑‍🎓 Student Profile Card

Cards are useful for displaying student information.

```html
<div class="card" style="width: 18rem;">

    <img src="student.jpg"
         class="card-img-top"
         alt="Student">

    <div class="card-body">

        <h5 class="card-title">
            Rahul Kumar
        </h5>

        <p class="card-text">
            B.Tech CSE Student
        </p>

        <a href="#" class="btn btn-primary">
            View Profile
        </a>

    </div>

</div>
```

---

# 17. 🏗️ Complete Example

```html
<!DOCTYPE html>
<html>

<head>

    <title>Bootstrap Cards</title>

    <meta name="viewport"
          content="width=device-width, initial-scale=1">

    <link
        href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"
        rel="stylesheet">

</head>

<body>

<div class="container py-5">

    <h1 class="text-center mb-4">
        📚 Our Courses
    </h1>

    <div class="row g-4">

        <!-- Card 1 -->
        <div class="col-12 col-md-6 col-lg-4">

            <div class="card h-100">

                <img src="html.jpg"
                     class="card-img-top"
                     alt="HTML">

                <div class="card-body">

                    <h5 class="card-title">
                        HTML
                    </h5>

                    <p class="card-text">
                        Learn the fundamentals of HTML
                        and create web pages.
                    </p>

                    <a href="#"
                       class="btn btn-primary">
                        Learn HTML
                    </a>

                </div>

            </div>

        </div>

        <!-- Card 2 -->
        <div class="col-12 col-md-6 col-lg-4">

            <div class="card h-100">

                <img src="css.jpg"
                     class="card-img-top"
                     alt="CSS">

                <div class="card-body">

                    <h5 class="card-title">
                        CSS
                    </h5>

                    <p class="card-text">
                        Learn how to style and design
                        beautiful web pages.
                    </p>

                    <a href="#"
                       class="btn btn-success">
                        Learn CSS
                    </a>

                </div>

            </div>

        </div>

        <!-- Card 3 -->
        <div class="col-12 col-md-6 col-lg-4">

            <div class="card h-100">

                <img src="bootstrap.jpg"
                     class="card-img-top"
                     alt="Bootstrap">

                <div class="card-body">

                    <h5 class="card-title">
                        Bootstrap
                    </h5>

                    <p class="card-text">
                        Create responsive websites
                        using Bootstrap.
                    </p>

                    <a href="#"
                       class="btn btn-dark">
                        Learn Bootstrap
                    </a>

                </div>

            </div>

        </div>

    </div>

</div>

</body>
</html>
```

---

# 18. 🔄 How Bootstrap Cards Work

```text
             Bootstrap Card
                    │
        ┌───────────┼───────────┐
        ↓           ↓           ↓
      Image       Content      Footer
                    │
             ┌──────┴──────┐
             ↓             ↓
           Title          Text
                           │
                         Button
```

---

# 19. 🆚 Card vs Carousel

| Card                                   | Carousel                               |
| -------------------------------------- | -------------------------------------- |
| Displays information in a container    | Displays content as slides             |
| Multiple cards can be visible together | Usually one slide is visible at a time |
| Good for products and profiles         | Good for banners and featured content  |
| User sees several items simultaneously | Items change automatically/manually    |

Both can also be combined.

### Example

```text
Homepage
   ↓
Carousel
   ↓
Featured Products
   ↓
Multiple Cards
```

---

# 20. ⚠️ Common Mistakes

### ❌ Mistake 1: Forgetting `.card-body`

```html
<div class="card">
    <h5>HTML</h5>
</div>
```

### ✅ Better

```html
<div class="card">

    <div class="card-body">

        <h5 class="card-title">
            HTML
        </h5>

    </div>

</div>
```

---

### ❌ Mistake 2: Missing `alt`

```html
<img src="book.jpg">
```

### ✅ Better

```html
<img src="book.jpg"
     class="card-img-top"
     alt="HTML Book">
```

---

### ❌ Mistake 3: Making every card fixed-width

For responsive layouts, prefer:

```html
<div class="col-12 col-md-6 col-lg-4">
```

and let the card fill the column.

---

# 21. 🧪 Student Practice

### Task 1

Create **3 course cards**:

```text
HTML
CSS
Bootstrap
```

Each card should contain:

* Image
* Title
* Description
* Button

### Task 2

Create an **Online Book Store** with four cards:

```text
📚 C Programming
📚 Data Structures
📚 Web Designing
📚 Artificial Intelligence
```

### Task 3

Make the cards responsive:

```text
Mobile  → 1 card
Tablet  → 2 cards
Desktop → 3 cards
```

Hint:

```html
col-12 col-md-6 col-lg-4
```

---

# 22. 📌 Quick Revision

| Concept                    | Remember                          |
| -------------------------- | --------------------------------- |
| `.card`                    | Creates a card                    |
| `.card-body`               | Main content                      |
| `.card-title`              | Card heading                      |
| `.card-text`               | Card description                  |
| `.card-img-top`            | Image at top                      |
| `.card-header`             | Card header                       |
| `.card-footer`             | Card footer                       |
| `.card-link`               | Link inside card                  |
| `.card-img-overlay`        | Content over image                |
| `.h-100`                   | Makes cards fill available height |
| `.row g-4`                 | Creates spacing between cards     |
| `col-12 col-md-6 col-lg-4` | Responsive card layout            |

---

## ⭐ Golden Rule

```text
Card
 ↓
Image
 ↓
Card Body
 ↓
Title + Text
 ↓
Button / Link
```

> 🎯 **Remember:** A Bootstrap Card is a reusable container for presenting related information in a clean, organized and responsive layout.

---

<p align="center">
  <img src="https://img.shields.io/badge/Bootstrap-Cards-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white">
</p>

<p align="center">
  <b>BCS353 • Web Designing Workshop</b>
</p>

