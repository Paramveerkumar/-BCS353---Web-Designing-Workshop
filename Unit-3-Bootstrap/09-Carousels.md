# 🎠 Bootstrap Carousels

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Bootstrap – Carousels
</p>

---

## 1. 🎠 What is a Carousel?

A **Carousel** is a component that displays multiple items such as:

* 🖼️ Images
* 📝 Text
* 📢 Announcements
* 🛍️ Products
* 🎞️ Banners

one after another in the same area.

The items can automatically change or be changed manually using **Previous** and **Next** buttons.

### Simple Example

```text
       ←                         →
┌───────────────────────────────┐
│                               │
│        🖼️ Book Image          │
│                               │
│      New Books Available      │
│                               │
└───────────────────────────────┘
          ● ○ ○
```

---

## 2. 💡 Real-Life Example

On an online shopping website, a carousel may show:

```text
Slide 1 → 📚 New Books
Slide 2 → 💻 Laptops
Slide 3 → 🎧 Headphones
Slide 4 → 📱 Mobile Phones
```

Only one slide is normally visible at a time.

---

## 3. 🧩 Bootstrap Carousel

Bootstrap provides a ready-made **Carousel component**.

Basic structure:

```html
<div id="myCarousel" class="carousel slide">

    <div class="carousel-inner">

        <div class="carousel-item active">
            ...
        </div>

        <div class="carousel-item">
            ...
        </div>

    </div>

</div>
```

### Important Classes

| Class                    | Purpose                       |
| ------------------------ | ----------------------------- |
| `.carousel`              | Creates the carousel          |
| `.slide`                 | Adds sliding animation        |
| `.carousel-inner`        | Contains all slides           |
| `.carousel-item`         | Defines one slide             |
| `.active`                | Makes the first slide visible |
| `.carousel-control-prev` | Previous button               |
| `.carousel-control-next` | Next button                   |
| `.carousel-indicators`   | Small indicators/dots         |

---

# 4. 🖼️ Simple Image Carousel

```html
<!DOCTYPE html>
<html>
<head>
    <title>Bootstrap Carousel</title>

    <meta name="viewport" content="width=device-width, initial-scale=1">

    <link
        href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"
        rel="stylesheet">
</head>

<body>

<div id="bookCarousel" class="carousel slide" data-bs-ride="carousel">

    <div class="carousel-inner">

        <!-- Slide 1 -->
        <div class="carousel-item active">
            <img src="book1.jpg" class="d-block w-100" alt="Book 1">
        </div>

        <!-- Slide 2 -->
        <div class="carousel-item">
            <img src="book2.jpg" class="d-block w-100" alt="Book 2">
        </div>

        <!-- Slide 3 -->
        <div class="carousel-item">
            <img src="book3.jpg" class="d-block w-100" alt="Book 3">
        </div>

    </div>

</div>

<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"></script>

</body>
</html>
```

---

# 5. ⭐ Why is `active` Important?

The first slide must contain:

```html
class="carousel-item active"
```

Example:

```html
<div class="carousel-item active">
    <img src="book1.jpg" alt="Book 1">
</div>
```

The `active` class tells Bootstrap:

> **Show this slide first.**

Without an active slide, the carousel may not display correctly.

---

# 6. ⏮️ Previous and Next Buttons

We can add navigation buttons to move between slides.

```html
<button class="carousel-control-prev"
        type="button"
        data-bs-target="#bookCarousel"
        data-bs-slide="prev">

    <span class="carousel-control-prev-icon"></span>

</button>
```

Next button:

```html
<button class="carousel-control-next"
        type="button"
        data-bs-target="#bookCarousel"
        data-bs-slide="next">

    <span class="carousel-control-next-icon"></span>

</button>
```

### Complete Structure

```text
Carousel
│
├── carousel-inner
│   ├── carousel-item active
│   ├── carousel-item
│   └── carousel-item
│
├── Previous Button
│
└── Next Button
```

---

# 7. 🔘 Carousel Indicators

Indicators are the small dots usually displayed at the bottom.

```html
<div class="carousel-indicators">

    <button type="button"
            data-bs-target="#bookCarousel"
            data-bs-slide-to="0"
            class="active">
    </button>

    <button type="button"
            data-bs-target="#bookCarousel"
            data-bs-slide-to="1">
    </button>

    <button type="button"
            data-bs-target="#bookCarousel"
            data-bs-slide-to="2">
    </button>

</div>
```

### Example

```text
        Slide
┌──────────────────────┐
│      🖼️ Image        │
└──────────────────────┘

       ●  ○  ○
```

Clicking the second dot displays the second slide.

---

# 8. 📝 Carousel with Captions

A carousel can contain text along with an image.

```html
<div class="carousel-item active">

    <img src="book1.jpg"
         class="d-block w-100"
         alt="Programming Book">

    <div class="carousel-caption">
        <h3>Programming Books</h3>
        <p>Learn C, C++, Java and Python.</p>
    </div>

</div>
```

The caption appears over the image.

---

# 9. 🎯 Complete Carousel Example

```html
<!DOCTYPE html>
<html>
<head>

    <title>Online Book Store</title>

    <meta name="viewport" content="width=device-width, initial-scale=1">

    <link
        href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"
        rel="stylesheet">

</head>

<body>

<div id="bookCarousel"
     class="carousel slide"
     data-bs-ride="carousel">

    <!-- Indicators -->
    <div class="carousel-indicators">

        <button type="button"
                data-bs-target="#bookCarousel"
                data-bs-slide-to="0"
                class="active">
        </button>

        <button type="button"
                data-bs-target="#bookCarousel"
                data-bs-slide-to="1">
        </button>

        <button type="button"
                data-bs-target="#bookCarousel"
                data-bs-slide-to="2">
        </button>

    </div>

    <!-- Slides -->
    <div class="carousel-inner">

        <div class="carousel-item active">

            <img src="book1.jpg"
                 class="d-block w-100"
                 alt="Programming Books">

            <div class="carousel-caption">
                <h3>Programming Books</h3>
                <p>Learn programming easily.</p>
            </div>

        </div>

        <div class="carousel-item">

            <img src="book2.jpg"
                 class="d-block w-100"
                 alt="Data Structures Books">

            <div class="carousel-caption">
                <h3>Data Structures</h3>
                <p>Master important data structures.</p>
            </div>

        </div>

        <div class="carousel-item">

            <img src="book3.jpg"
                 class="d-block w-100"
                 alt="AI Books">

            <div class="carousel-caption">
                <h3>Artificial Intelligence</h3>
                <p>Explore AI and Machine Learning.</p>
            </div>

        </div>

    </div>

    <!-- Previous -->
    <button class="carousel-control-prev"
            type="button"
            data-bs-target="#bookCarousel"
            data-bs-slide="prev">

        <span class="carousel-control-prev-icon"></span>

    </button>

    <!-- Next -->
    <button class="carousel-control-next"
            type="button"
            data-bs-target="#bookCarousel"
            data-bs-slide="next">

        <span class="carousel-control-next-icon"></span>

    </button>

</div>

<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"></script>

</body>
</html>
```

---

# 10. ⏱️ Automatic Sliding

Bootstrap can automatically move from one slide to another.

Use:

```html
data-bs-ride="carousel"
```

Example:

```html
<div id="myCarousel"
     class="carousel slide"
     data-bs-ride="carousel">
```

The carousel will automatically start cycling through the slides.

---

# 11. ⏰ Changing Slide Interval

We can control how long a slide remains visible.

```html
<div class="carousel-item active"
     data-bs-interval="3000">
```

Here:

```text
3000 milliseconds = 3 seconds
```

Example:

```html
<div class="carousel-item active"
     data-bs-interval="3000">

    <img src="book1.jpg" class="d-block w-100" alt="Book">

</div>
```

---

# 12. 📱 Responsive Carousel

Bootstrap makes the carousel responsive.

A common image setup is:

```html
<img src="book.jpg"
     class="d-block w-100 img-fluid"
     alt="Book">
```

### Important Classes

```text
w-100
 ↓
Width = 100%

img-fluid
 ↓
Responsive image
```

---

# 13. 🛒 Online Book Store Example

A carousel can be used on the homepage:

```text
┌─────────────────────────────────────┐
│           ONLINE BOOK STORE          │
├─────────────────────────────────────┤
│                                     │
│       📚 NEW BOOK COLLECTION        │
│                                     │
│          [ View Books ]             │
│                                     │
│              ● ○ ○                  │
│                                     │
└─────────────────────────────────────┘
```

Possible slides:

| Slide | Content              |
| ----- | -------------------- |
| 1     | 📚 New Arrivals      |
| 2     | 💻 Programming Books |
| 3     | 🤖 AI & ML Books     |
| 4     | 🎓 Exam Preparation  |

---

# 14. 🔑 Important Bootstrap Carousel Attributes

| Attribute                 | Purpose                  |
| ------------------------- | ------------------------ |
| `data-bs-ride="carousel"` | Starts automatic cycling |
| `data-bs-slide="prev"`    | Moves to previous slide  |
| `data-bs-slide="next"`    | Moves to next slide      |
| `data-bs-slide-to="0"`    | Goes to specific slide   |
| `data-bs-interval="3000"` | Sets slide interval      |

---

# 15. ⚠️ Common Mistakes

### ❌ Mistake 1: No `active` class

```html
<div class="carousel-item">
```

### ✅ Correct

```html
<div class="carousel-item active">
```

---

### ❌ Mistake 2: Wrong carousel ID

If the carousel is:

```html
<div id="bookCarousel">
```

the buttons should target:

```html
data-bs-target="#bookCarousel"
```

---

### ❌ Mistake 3: Forgetting Bootstrap JavaScript

Carousel controls and automatic behavior require Bootstrap's JavaScript.

```html
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"></script>
```

---

# 16. 🧠 Carousel vs Image Gallery

| Carousel                                      | Image Gallery                          |
| --------------------------------------------- | -------------------------------------- |
| Usually shows one/few items at a time         | Usually shows many images              |
| Items change using controls/automatic cycling | Images are normally displayed together |
| Good for banners and featured content         | Good for collections                   |
| Saves screen space                            | Shows more content simultaneously      |

---

# 17. 🎯 Where Can We Use Carousels?

Carousels are commonly useful for:

* 🏠 Homepage banners
* 🛍️ Product promotions
* 📚 Online book stores
* 📰 News highlights
* 🎓 College announcements
* 🎞️ Image slideshows
* 📢 Offers and advertisements
* 🏆 Featured projects

---

# 18. 🧪 Student Practice

### Task 1

Create a carousel containing **3 college event images**.

### Task 2

Create an **Online Book Store carousel** containing:

```text
Slide 1 → New Books
Slide 2 → Programming
Slide 3 → AI & ML
```

### Task 3

Add:

* Previous button
* Next button
* Indicators
* Captions
* Automatic sliding

### Task 4

Set each slide to remain visible for **5 seconds**.

Hint:

```html
data-bs-interval="5000"
```

---

# 19. 🔄 Carousel Working

```text
       Start
         ↓
  First Slide (active)
         ↓
   Automatic / Manual
         ↓
      Next Slide
         ↓
      Next Slide
         ↓
       Repeat
```

---

# 20. 📌 Quick Revision

| Concept                | Remember                          |
| ---------------------- | --------------------------------- |
| Carousel               | Displays multiple items as slides |
| `.carousel`            | Creates carousel                  |
| `.carousel-inner`      | Holds slides                      |
| `.carousel-item`       | Represents one slide              |
| `.active`              | First/current visible slide       |
| `.carousel-indicators` | Creates slide indicators          |
| Previous               | Moves backward                    |
| Next                   | Moves forward                     |
| `data-bs-ride`         | Automatic cycling                 |
| `data-bs-interval`     | Controls slide timing             |

---

## ⭐ Golden Rule

```text
Carousel
   ↓
carousel
   ↓
carousel-inner
   ↓
carousel-item
   ↓
active = first slide
```

> 🎯 **Remember:** A Bootstrap Carousel is mainly used to display **multiple pieces of content one after another in a limited space**.

---

<p align="center">
  <img src="https://img.shields.io/badge/Bootstrap-Carousels-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white">
</p>

<p align="center">
  <b>BCS353 • Web Designing Workshop</b>
</p>

