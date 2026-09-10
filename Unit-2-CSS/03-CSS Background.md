# 🎨 CSS Background

![HTML](https://img.shields.io/badge/HTML-5-orange)
![CSS](https://img.shields.io/badge/CSS-3-blue)
![Level](https://img.shields.io/badge/Level-Beginner-green)

---

## 🎯 Aim

To study and understand **CSS background properties** and learn how to apply colors, images, positions, sizes, and other background effects to HTML elements.

---

## 📚 Introduction

CSS provides several properties for controlling the **background of an HTML element**.

Background properties can be used to:

* Set a background color
* Add a background image
* Control image repetition
* Set the position of an image
* Set the size of an image
* Fix or scroll the background image
* Combine multiple background properties

The most commonly used CSS background properties are:

1. `background-color`
2. `background-image`
3. `background-repeat`
4. `background-position`
5. `background-size`
6. `background-attachment`
7. `background`
8. `background-origin`
9. `background-clip`

---

# 1️⃣ `background-color`

## 📖 Definition

The `background-color` property is used to set the background color of an HTML element.

### 💻 Example

```css
body {
    background-color: lightblue;
}
```

This changes the background color of the complete webpage to light blue.

### Another Example

```css
div {
    background-color: yellow;
}
```

This makes the background of the `<div>` element yellow.

---

## 💻 HTML Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>Background Color</title>

    <style>
        body {
            background-color: lightblue;
        }

        h1 {
            background-color: yellow;
        }

        p {
            background-color: lightgreen;
        }
    </style>

</head>

<body>

    <h1>CSS Background</h1>

    <p>This paragraph has a light green background.</p>

</body>

</html>
```

---

# 2️⃣ `background-image`

## 📖 Definition

The `background-image` property is used to set an image as the background of an HTML element.

### Syntax

```css
background-image: url("image.jpg");
```

### Example

```css
body {
    background-image: url("images/background.jpg");
}
```

Here:

* `background-image` → CSS property
* `url()` → specifies the image location
* `"images/background.jpg"` → image path

---

## 📁 Example Project Structure

```text
MyWebsite/
│
├── index.html
│
└── images/
    └── background.jpg
```

If the image is inside the `images` folder:

```css
body {
    background-image: url("images/background.jpg");
}
```

---

# 3️⃣ `background-repeat`

## 📖 Definition

The `background-repeat` property controls whether a background image should repeat.

### Common Values

| Value       | Meaning                             |
| ----------- | ----------------------------------- |
| `repeat`    | Repeats horizontally and vertically |
| `repeat-x`  | Repeats horizontally                |
| `repeat-y`  | Repeats vertically                  |
| `no-repeat` | Does not repeat                     |

### Example

```css
body {
    background-image: url("images/background.jpg");
    background-repeat: no-repeat;
}
```

The image will appear only once.

---

## 🔄 Repeat Example

```css
body {
    background-image: url("images/pattern.png");
    background-repeat: repeat;
}
```

The image repeats in both directions.

### Horizontal Repeat

```css
body {
    background-repeat: repeat-x;
}
```

### Vertical Repeat

```css
body {
    background-repeat: repeat-y;
}
```

### No Repeat

```css
body {
    background-repeat: no-repeat;
}
```

---

# 4️⃣ `background-position`

## 📖 Definition

The `background-position` property specifies the position of the background image.

### Common Values

* `left`
* `right`
* `center`
* `top`
* `bottom`

### Example

```css
body {
    background-image: url("images/background.jpg");
    background-repeat: no-repeat;
    background-position: center;
}
```

The image will be placed in the center.

---

## 📍 Position Examples

### Center

```css
background-position: center;
```

### Top Left

```css
background-position: left top;
```

### Top Right

```css
background-position: right top;
```

### Bottom Left

```css
background-position: left bottom;
```

### Bottom Right

```css
background-position: right bottom;
```

---

# 5️⃣ `background-size`

## 📖 Definition

The `background-size` property specifies the size of the background image.

### Common Values

| Value       | Meaning                                    |
| ----------- | ------------------------------------------ |
| `auto`      | Original image size                        |
| `cover`     | Covers the complete element                |
| `contain`   | Fits the complete image inside the element |
| `100% 100%` | Stretches image to element size            |

### Example

```css
body {
    background-image: url("images/background.jpg");
    background-size: cover;
}
```

The image covers the complete background area.

---

## `cover`

```css
background-size: cover;
```

The image covers the complete element while maintaining its aspect ratio.

---

## `contain`

```css
background-size: contain;
```

The complete image is displayed inside the element while maintaining its aspect ratio.

---

## Fixed Size

```css
background-size: 500px 300px;
```

The background image will have a width of `500px` and height of `300px`.

---

# 6️⃣ `background-attachment`

## 📖 Definition

The `background-attachment` property specifies whether the background image should scroll with the page or remain fixed.

### Common Values

| Value    | Meaning                                       |
| -------- | --------------------------------------------- |
| `scroll` | Background scrolls with the page              |
| `fixed`  | Background remains fixed                      |
| `local`  | Background scrolls with the element's content |

### Example

```css
body {
    background-image: url("images/background.jpg");
    background-attachment: fixed;
}
```

The background remains fixed while the page content scrolls.

---

# 7️⃣ `background` Shorthand Property

## 📖 Definition

The `background` property is a shorthand property used to specify multiple background properties in a single declaration.

### Instead of writing:

```css
body {
    background-color: lightblue;
    background-image: url("images/background.jpg");
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
}
```

We can write:

```css
body {
    background: lightblue url("images/background.jpg") no-repeat center/cover;
}
```

This makes the CSS code shorter.

---

# 8️⃣ `background-origin`

## 📖 Definition

The `background-origin` property specifies where the background image starts.

### Common Values

| Value         | Meaning                            |
| ------------- | ---------------------------------- |
| `border-box`  | Background starts from the border  |
| `padding-box` | Background starts from the padding |
| `content-box` | Background starts from the content |

### Example

```css
div {
    background-origin: content-box;
}
```

---

# 9️⃣ `background-clip`

## 📖 Definition

The `background-clip` property specifies how far the background should extend inside an element.

### Common Values

| Value         | Meaning                              |
| ------------- | ------------------------------------ |
| `border-box`  | Background extends to the border     |
| `padding-box` | Background extends to the padding    |
| `content-box` | Background is limited to the content |

### Example

```css
div {
    background-clip: padding-box;
}
```

---

# 💻 Complete Program

The following program demonstrates several CSS background properties.

```html
<!DOCTYPE html>
<html>

<head>

    <title>CSS Background</title>

    <style>

        body {
            background-color: lightblue;
            background-image: url("images/background.jpg");
            background-repeat: no-repeat;
            background-position: center;
            background-size: cover;
            background-attachment: fixed;
        }

        h1 {
            background-color: white;
            color: darkblue;
            text-align: center;
            padding: 20px;
        }

        p {
            background-color: rgba(255, 255, 255, 0.8);
            padding: 15px;
            font-size: 20px;
        }

        .box {
            background-color: lightgreen;
            background-image: url("images/pattern.png");
            background-repeat: repeat;
            padding: 30px;
            border: 3px solid green;
        }

    </style>

</head>

<body>

    <h1>CSS Background Properties</h1>

    <p>
        CSS background properties are used to style
        the background of HTML elements.
    </p>

    <div class="box">
        This is a box with a background color and image.
    </div>

</body>

</html>
```

---

# 🔍 Program Explanation

## `body`

```css
body {
    background-color: lightblue;
    background-image: url("images/background.jpg");
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    background-attachment: fixed;
}
```

This section applies multiple background properties to the webpage.

### Explanation

| Property                | Purpose                     |
| ----------------------- | --------------------------- |
| `background-color`      | Sets background color       |
| `background-image`      | Adds background image       |
| `background-repeat`     | Controls image repetition   |
| `background-position`   | Sets image position         |
| `background-size`       | Sets image size             |
| `background-attachment` | Controls scrolling behavior |

---

## `h1`

```css
h1 {
    background-color: white;
    color: darkblue;
    text-align: center;
    padding: 20px;
}
```

This:

* Sets a white background
* Makes the text dark blue
* Centers the heading
* Adds space around the heading

---

## `p`

```css
p {
    background-color: rgba(255, 255, 255, 0.8);
    padding: 15px;
    font-size: 20px;
}
```

The paragraph gets:

* A semi-transparent white background
* 15px padding
* 20px font size

---

## `.box`

```css
.box {
    background-color: lightgreen;
    background-image: url("images/pattern.png");
    background-repeat: repeat;
    padding: 30px;
    border: 3px solid green;
}
```

This creates a box containing:

* Light green background
* Background image
* Repeated image
* 30px padding
* Green border

---

# 🔄 How CSS Background Works

```text
                 CSS BACKGROUND
                       |
          ┌────────────┼────────────┐
          ↓            ↓            ↓
        Color         Image       Other
          |             |            |
          ↓             ↓            ↓
 background-color  background-image  repeat
                                  position
                                  size
                                  attachment
```

---

# 🧩 Background Properties Summary

| Property                | Purpose                 | Example         |
| ----------------------- | ----------------------- | --------------- |
| `background-color`      | Background color        | `red`           |
| `background-image`      | Background image        | `url("bg.jpg")` |
| `background-repeat`     | Image repetition        | `no-repeat`     |
| `background-position`   | Image position          | `center`        |
| `background-size`       | Image size              | `cover`         |
| `background-attachment` | Image scrolling         | `fixed`         |
| `background-origin`     | Starting area           | `padding-box`   |
| `background-clip`       | Visible background area | `content-box`   |
| `background`            | Shorthand property      | Multiple values |

---

# 🎨 Background Color Examples

```css
body {
    background-color: red;
}
```

Using HEX:

```css
body {
    background-color: #87CEEB;
}
```

Using RGB:

```css
body {
    background-color: rgb(135, 206, 235);
}
```

Using RGBA:

```css
body {
    background-color: rgba(135, 206, 235, 0.5);
}
```

Using HSL:

```css
body {
    background-color: hsl(197, 71%, 73%);
}
```

---

# 🖼️ Background Image Example

```css
body {
    background-image: url("images/nature.jpg");
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
}
```

This is commonly used for webpage backgrounds.

---

# 📌 Difference Between `background-size: cover` and `contain`

| `cover`                                | `contain`                                    |
| -------------------------------------- | -------------------------------------------- |
| Covers the complete element            | Fits the complete image inside the element   |
| Some parts of the image may be cropped | Complete image remains visible               |
| Useful for full-page backgrounds       | Useful when the entire image must be visible |

---

# ⚠️ Common Mistakes

## 1. Incorrect Image Path

❌ Incorrect:

```css
background-image: url("background.jpg");
```

when the image is actually inside `images`.

✅ Correct:

```css
background-image: url("images/background.jpg");
```

---

## 2. Forgetting `url()`

❌ Incorrect:

```css
background-image: "background.jpg";
```

✅ Correct:

```css
background-image: url("background.jpg");
```

---

## 3. Forgetting the Semicolon

❌ Incorrect:

```css
body {
    background-color: lightblue
    background-image: url("bg.jpg");
}
```

✅ Correct:

```css
body {
    background-color: lightblue;
    background-image: url("bg.jpg");
}
```

---

## 4. Using the Wrong File Name

If your CSS contains:

```css
background-image: url("images/bg.jpg");
```

the actual file should be:

```text
images/
└── bg.jpg
```

The filename and extension must match.

---

# 🎓 Viva Questions and Answers

### Q1. What is a CSS background?

**Answer:**
A CSS background is used to style the background of an HTML element using properties such as color, image, position, and size.

---

### Q2. Which property is used to set background color?

**Answer:**

```css
background-color
```

---

### Q3. Which property is used to add a background image?

**Answer:**

```css
background-image
```

---

### Q4. Which property controls image repetition?

**Answer:**

```css
background-repeat
```

---

### Q5. What is the use of `background-position`?

**Answer:**
It specifies the position of the background image.

---

### Q6. What is the use of `background-size`?

**Answer:**
It specifies the size of the background image.

---

### Q7. What does `background-size: cover` do?

**Answer:**
It makes the background image cover the complete element while maintaining its aspect ratio.

---

### Q8. What does `background-repeat: no-repeat` do?

**Answer:**
It prevents the background image from repeating.

---

### Q9. What is the use of `background-attachment: fixed`?

**Answer:**
It keeps the background image fixed while the webpage content scrolls.

---

### Q10. What is the shorthand background property?

**Answer:**
The `background` property allows multiple background properties to be specified in a single declaration.

Example:

```css
body {
    background: lightblue url("bg.jpg") no-repeat center/cover;
}
```

---

### Q11. What is `background-origin`?

**Answer:**
It specifies the area from which the background image positioning begins.

---

### Q12. What is `background-clip`?

**Answer:**
It specifies how far the background extends within an element.

---

# ⭐ Key Points

* `background-color` sets the background color.
* `background-image` adds an image to the background.
* `background-repeat` controls image repetition.
* `background-position` controls image location.
* `background-size` controls image dimensions.
* `background-attachment` controls scrolling behavior.
* `background-origin` controls the starting area of the background.
* `background-clip` controls the visible background area.
* `background` is a shorthand property.
* `cover` is commonly used for full-area background images.
* `no-repeat` prevents an image from repeating.

---

# 📝 Result

Thus, the **CSS Background properties** were studied and successfully implemented using background colors, background images, image repetition, image position, image size, and attachment properties.

---

# 📌 Conclusion

CSS background properties are useful for designing attractive web pages.

The important background properties are:

```text
background-color
background-image
background-repeat
background-position
background-size
background-attachment
background-origin
background-clip
background
```

By using these properties, we can create visually attractive backgrounds for webpages and individual HTML elements.

---


