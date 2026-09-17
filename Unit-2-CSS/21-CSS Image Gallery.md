# 🖼️ CSS Image Gallery

<p align="center">
  <img src="https://img.shields.io/badge/CSS-Image%20Gallery-1572B6?style=for-the-badge&logo=css3&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Learn how to display multiple images in a clean, responsive gallery.
</p>

---

## 📌 1. What is a CSS Image Gallery?

A **CSS Image Gallery** is a collection of images displayed together in an organized layout.

CSS can be used to control:

* 📐 Image size
* 📦 Gallery layout
* 🖼️ Borders
* 🔲 Spacing
* 📝 Captions
* 🖱️ Hover effects
* 📱 Responsive behavior

### Simple Definition

> **CSS Image Gallery = A collection of images arranged and styled using HTML and CSS.**

---

# 🎯 2. Why Do We Use Image Galleries?

Image galleries are commonly used for:

* 🏞️ Photography websites
* 🏨 Hotel websites
* 🛍️ Product displays
* 🎓 Student/project portfolios
* 📰 News websites
* 🏢 Company websites
* 🎨 Art and design portfolios

---

# 🧱 3. Basic Image Gallery Structure

A simple gallery can be created using:

```html
<div class="gallery">

  <img src="image1.jpg" alt="Image 1">
  <img src="image2.jpg" alt="Image 2">
  <img src="image3.jpg" alt="Image 3">

</div>
```

CSS:

```css
.gallery {
  display: flex;
  gap: 15px;
}

.gallery img {
  width: 200px;
}
```

### Basic Layout

```text
┌──────────┐  ┌──────────┐  ┌──────────┐
│ Image 1  │  │ Image 2  │  │ Image 3  │
└──────────┘  └──────────┘  └──────────┘
```

---

# 🖼️ 4. Creating a Simple Image Gallery

### HTML

```html
<!DOCTYPE html>
<html>

<head>
  <title>Image Gallery</title>
</head>

<body>

  <h1>My Image Gallery</h1>

  <div class="gallery">

    <img src="image1.jpg" alt="Image 1">
    <img src="image2.jpg" alt="Image 2">
    <img src="image3.jpg" alt="Image 3">
    <img src="image4.jpg" alt="Image 4">

  </div>

</body>

</html>
```

### CSS

```css
.gallery {
  display: flex;
  gap: 15px;
  flex-wrap: wrap;
}

.gallery img {
  width: 200px;
  height: 150px;
  object-fit: cover;
}
```

---

# 📐 5. Image Size

We can control image dimensions using:

```css
.gallery img {
  width: 200px;
  height: 150px;
}
```

### Example

```text
Width  → 200px
Height → 150px

┌──────────────────────┐
│                      │
│       IMAGE          │
│                      │
└──────────────────────┘
```

---

# 🧩 6. `object-fit`

When an image is given a fixed width and height, the original image may not have the same aspect ratio.

The `object-fit` property controls how the image fits inside its box.

### `object-fit: cover`

```css
.gallery img {
  width: 200px;
  height: 150px;
  object-fit: cover;
}
```

The image fills the box while maintaining its aspect ratio. Some parts may be cropped.

```text
Original Image
┌─────────────────────────┐
│                         │
│        IMAGE            │
│                         │
└─────────────────────────┘

Gallery Box
┌──────────────────┐
│      IMAGE       │
│    cropped       │
└──────────────────┘
```

---

# 🔵 7. `object-fit: contain`

```css
.gallery img {
  width: 200px;
  height: 150px;
  object-fit: contain;
}
```

The complete image fits inside the box while maintaining its aspect ratio.

```text
┌──────────────────────┐
│     ┌──────────┐     │
│     │  IMAGE   │     │
│     └──────────┘     │
└──────────────────────┘
```

### Difference

| Value     | Behavior                                    |
| --------- | ------------------------------------------- |
| `cover`   | Fills box; may crop image                   |
| `contain` | Shows complete image; may leave empty space |

---

# 🖱️ 8. Hover Effect

We can change an image when the mouse moves over it.

```css
.gallery img:hover {
  transform: scale(1.05);
}
```

### Smooth effect

```css
.gallery img {
  transition: transform 0.3s;
}

.gallery img:hover {
  transform: scale(1.05);
}
```

### Concept

```text
Normal:

┌──────────────┐
│    IMAGE     │
└──────────────┘

        ↓ Hover

┌────────────────┐
│     IMAGE      │
│    slightly    │
│     larger     │
└────────────────┘
```

---

# 🟣 9. Adding Borders

```css
.gallery img {
  border: 3px solid #ddd;
}
```

### Rounded corners

```css
.gallery img {
  border-radius: 10px;
}
```

You can combine them:

```css
.gallery img {
  border: 2px solid #ddd;
  border-radius: 10px;
}
```

---

# 📝 10. Image Gallery with Captions

A gallery can include a caption below each image.

### HTML

```html
<div class="gallery">

  <div class="item">
    <img src="mountain.jpg" alt="Mountain">
    <p>Beautiful Mountain</p>
  </div>

  <div class="item">
    <img src="forest.jpg" alt="Forest">
    <p>Green Forest</p>
  </div>

  <div class="item">
    <img src="river.jpg" alt="River">
    <p>River View</p>
  </div>

</div>
```

### CSS

```css
.gallery {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
}

.item {
  width: 200px;
  text-align: center;
}

.item img {
  width: 100%;
  height: 150px;
  object-fit: cover;
}

.item p {
  margin: 8px 0;
  font-weight: bold;
}
```

### Result

```text
┌────────────┐  ┌────────────┐  ┌────────────┐
│   IMAGE    │  │   IMAGE    │  │   IMAGE    │
│            │  │            │  │            │
└────────────┘  └────────────┘  └────────────┘
   Mountain        Forest         River
```

---

# 🧱 11. Image Gallery Using CSS Grid

CSS Grid is very useful for creating image galleries.

### HTML

```html
<div class="gallery">

  <img src="image1.jpg" alt="Image 1">
  <img src="image2.jpg" alt="Image 2">
  <img src="image3.jpg" alt="Image 3">
  <img src="image4.jpg" alt="Image 4">
  <img src="image5.jpg" alt="Image 5">
  <img src="image6.jpg" alt="Image 6">

</div>
```

### CSS

```css
.gallery {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 15px;
}

.gallery img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}
```

### Layout

```text
┌─────────┐  ┌─────────┐  ┌─────────┐
│ Image 1 │  │ Image 2 │  │ Image 3 │
└─────────┘  └─────────┘  └─────────┘

┌─────────┐  ┌─────────┐  ┌─────────┐
│ Image 4 │  │ Image 5 │  │ Image 6 │
└─────────┘  └─────────┘  └─────────┘
```

---

# 📱 12. Responsive Image Gallery

A good image gallery should work on different screen sizes.

### Desktop

```text
┌──────┐ ┌──────┐ ┌──────┐ ┌──────┐
│ Img1 │ │ Img2 │ │ Img3 │ │ Img4 │
└──────┘ └──────┘ └──────┘ └──────┘
```

### Mobile

```text
┌──────────────┐
│     Img1     │
└──────────────┘
┌──────────────┐
│     Img2     │
└──────────────┘
┌──────────────┐
│     Img3     │
└──────────────┘
```

### CSS

```css
.gallery {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 15px;
}

.gallery img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

@media (max-width: 800px) {

  .gallery {
    grid-template-columns: repeat(2, 1fr);
  }

}

@media (max-width: 500px) {

  .gallery {
    grid-template-columns: 1fr;
  }

}
```

---

# 🎨 13. Gallery with Hover Overlay

We can create an overlay effect when the user moves the mouse over an image.

### HTML

```html
<div class="gallery-item">

  <img src="mountain.jpg" alt="Mountain">

  <div class="overlay">
    Mountain View
  </div>

</div>
```

### CSS

```css
.gallery-item {
  position: relative;
  width: 300px;
}

.gallery-item img {
  width: 100%;
  display: block;
}

.overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  padding: 15px;
  background-color: rgba(0, 0, 0, 0.7);
  color: white;
  text-align: center;
  opacity: 0;
}

.gallery-item:hover .overlay {
  opacity: 1;
}
```

### Concept

```text
Normal:

┌──────────────────┐
│                  │
│      IMAGE       │
│                  │
└──────────────────┘

       ↓ Hover

┌──────────────────┐
│                  │
│      IMAGE       │
│──────────────────│
│  Mountain View   │
└──────────────────┘
```

---

# 🔲 14. Gallery Cards

A gallery can also be designed as cards.

```css
.gallery-item {
  border: 1px solid #ddd;
  border-radius: 10px;
  overflow: hidden;
  background-color: white;
}

.gallery-item img {
  width: 100%;
  display: block;
}

.gallery-item .caption {
  padding: 10px;
  text-align: center;
}
```

### Layout

```text
┌─────────────────┐
│                 │
│     IMAGE       │
│                 │
├─────────────────┤
│  Image Caption  │
└─────────────────┘
```

---

# 🧪 15. Complete Responsive Image Gallery

```html
<!DOCTYPE html>
<html>

<head>

  <meta
    name="viewport"
    content="width=device-width, initial-scale=1.0"
  >

  <title>CSS Image Gallery</title>

  <style>

    * {
      box-sizing: border-box;
    }

    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 20px;
    }

    h1 {
      text-align: center;
    }

    .gallery {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 15px;
    }

    .gallery-item {
      border: 1px solid #ddd;
      border-radius: 10px;
      overflow: hidden;
      background-color: white;
    }

    .gallery-item img {
      width: 100%;
      height: 200px;
      object-fit: cover;
      display: block;
      transition: transform 0.3s;
    }

    .gallery-item:hover img {
      transform: scale(1.05);
    }

    .caption {
      padding: 10px;
      text-align: center;
      font-weight: bold;
    }

    @media (max-width: 900px) {

      .gallery {
        grid-template-columns: repeat(2, 1fr);
      }

    }

    @media (max-width: 500px) {

      .gallery {
        grid-template-columns: 1fr;
      }

    }

  </style>

</head>

<body>

  <h1>My Image Gallery</h1>

  <div class="gallery">

    <div class="gallery-item">
      <img src="image1.jpg" alt="Mountain">
      <div class="caption">Mountain</div>
    </div>

    <div class="gallery-item">
      <img src="image2.jpg" alt="Forest">
      <div class="caption">Forest</div>
    </div>

    <div class="gallery-item">
      <img src="image3.jpg" alt="River">
      <div class="caption">River</div>
    </div>

    <div class="gallery-item">
      <img src="image4.jpg" alt="Beach">
      <div class="caption">Beach</div>
    </div>

  </div>

</body>

</html>
```

---

# 🧠 16. Important CSS Properties

| Property                | Purpose                         |
| ----------------------- | ------------------------------- |
| `display: grid`         | Creates a grid layout           |
| `display: flex`         | Creates a flexible layout       |
| `grid-template-columns` | Defines gallery columns         |
| `gap`                   | Creates space between images    |
| `width`                 | Controls image width            |
| `height`                | Controls image height           |
| `object-fit`            | Controls how image fits its box |
| `border`                | Adds border                     |
| `border-radius`         | Creates rounded corners         |
| `overflow: hidden`      | Clips content outside the box   |
| `transform`             | Creates effects such as scaling |
| `transition`            | Makes changes smooth            |
| `@media`                | Makes gallery responsive        |

---

# 🆚 17. `cover` vs `contain`

| `object-fit` | Result                                          |
| ------------ | ----------------------------------------------- |
| `cover`      | Fills the entire box, may crop image            |
| `contain`    | Shows the complete image, may leave empty space |
| `fill`       | Stretches image to fill box                     |
| `none`       | Keeps original image size                       |
| `scale-down` | Uses the smaller of `none` or `contain`         |

### Most Common

```css
object-fit: cover;
```

is commonly useful when all gallery images need to have a consistent visual size.

---

# 📱 18. Responsive Gallery Using `auto-fit`

CSS Grid can automatically adjust the number of columns.

```css
.gallery {
  display: grid;
  grid-template-columns:
    repeat(auto-fit, minmax(200px, 1fr));
  gap: 15px;
}
```

### Meaning

```text
auto-fit
   ↓
Automatically fit available columns

minmax(200px, 1fr)
   ↓
Each column should be at least 200px
and can grow to use available space
```

This can reduce the need for multiple media queries.

---

# ⚠️ 19. Common Mistakes

### ❌ Mistake 1: Missing `alt`

Avoid:

```html
<img src="image.jpg">
```

Prefer:

```html
<img src="image.jpg" alt="Mountain landscape">
```

The `alt` text improves accessibility and provides a description if the image cannot be displayed.

---

### ❌ Mistake 2: Distorted Images

Avoid forcing unsuitable dimensions without controlling the fit.

```css
img {
  width: 200px;
  height: 200px;
}
```

Better for fixed gallery boxes:

```css
img {
  width: 200px;
  height: 200px;
  object-fit: cover;
}
```

---

### ❌ Mistake 3: Gallery Not Responsive

A fixed number of columns may not work well on mobile.

Use:

```css
.gallery {
  grid-template-columns:
    repeat(auto-fit, minmax(200px, 1fr));
}
```

---

# ❓ 20. Practice Questions

### Q1. What is a CSS Image Gallery?

### Q2. Why is `object-fit` used?

### Q3. What is the difference between `cover` and `contain`?

### Q4. How can you create a gallery using CSS Grid?

### Q5. What is the purpose of `gap`?

### Q6. How can you make an image gallery responsive?

### Q7. What does this code do?

```css
.gallery {
  grid-template-columns: repeat(3, 1fr);
}
```

### Q8. What is the purpose of `transform: scale()`?

### Q9. Why is `alt` text important for images?

### Q10. Create a responsive gallery containing six images.

---

# ⚡ 21. Quick Revision

```text
                    CSS IMAGE GALLERY
                           │
             ┌─────────────┼─────────────┐
             ↓             ↓             ↓
            Flex          Grid         Hover
             │             │             │
             ↓             ↓             ↓
        Flexible       Columns       Effects
         Layout         & Rows        │
                                      ↓
                                  transform
                                      │
                           ┌──────────┴──────────┐
                           ↓                     ↓
                        scale()              transition
                           
                           │
                           ↓
                    Responsive Gallery
                           │
                         @media
                           │
                           ↓
                    Mobile / Tablet /
                       Desktop
```

---

## 📌 One-Line Definition

> **A CSS Image Gallery is a collection of images arranged and styled using HTML and CSS, often with layouts, spacing, captions, hover effects, and responsive behavior.**

---

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-1572B6?style=for-the-badge&logo=css3&logoColor=white">
</p>

<p align="center">
  <b>🎓 BCS353 • Web Designing Workshop</b>
</p>

