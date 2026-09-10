# 🎨 CSS Colors

![HTML](https://img.shields.io/badge/HTML-5-orange)
![CSS](https://img.shields.io/badge/CSS-3-blue)
![Level](https://img.shields.io/badge/Level-Beginner-green)

---

## 🎯 Aim

To study and understand **CSS colors** and learn how to apply different colors to HTML elements using CSS.

---

## 📚 Introduction

CSS provides different ways to specify colors for HTML elements.

Colors can be used for:

* Text
* Backgrounds
* Borders
* Buttons
* Headings
* Links
* Tables
* Other HTML elements

For example:

```css
h1 {
    color: blue;
}
```

Here:

* `h1` → Selector
* `color` → CSS property
* `blue` → CSS value

---

# 🌈 Ways to Specify CSS Colors

CSS colors can be specified using different methods:

1. **Color Names**
2. **RGB Values**
3. **RGBA Values**
4. **HEX Values**
5. **HSL Values**
6. **HSLA Values**

---

# 1️⃣ Color Names

CSS provides predefined color names such as:

* `red`
* `blue`
* `green`
* `yellow`
* `black`
* `white`
* `orange`
* `purple`
* `pink`
* `gray`

## 💻 Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS Color Names</title>

    <style>

        h1 {
            color: blue;
        }

        p {
            color: green;
        }

        body {
            background-color: lightyellow;
        }

    </style>

</head>

<body>

    <h1>CSS Colors</h1>

    <p>This paragraph is green in color.</p>

</body>

</html>
```

### 🔍 Explanation

```css
h1 {
    color: blue;
}
```

This changes the text color of the `<h1>` element to blue.

```css
body {
    background-color: lightyellow;
}
```

This changes the background color of the page.

---

# 2️⃣ RGB Colors

## 📖 Definition

RGB stands for:

> **R = Red, G = Green, B = Blue**

RGB values are specified using three numbers.

```css
rgb(red, green, blue)
```

Each value normally ranges from:

```text
0 to 255
```

## 💻 Examples

```css
p {
    color: rgb(255, 0, 0);
}
```

This produces **red**.

```css
p {
    color: rgb(0, 255, 0);
}
```

This produces **green**.

```css
p {
    color: rgb(0, 0, 255);
}
```

This produces **blue**.

### 📊 RGB Values

| RGB Value            | Color  |
| -------------------- | ------ |
| `rgb(255, 0, 0)`     | Red    |
| `rgb(0, 255, 0)`     | Green  |
| `rgb(0, 0, 255)`     | Blue   |
| `rgb(0, 0, 0)`       | Black  |
| `rgb(255, 255, 255)` | White  |
| `rgb(255, 255, 0)`   | Yellow |

---

# 3️⃣ RGBA Colors

## 📖 Definition

RGBA stands for:

> **Red + Green + Blue + Alpha**

The alpha value controls **transparency**.

Syntax:

```css
rgba(red, green, blue, alpha)
```

The alpha value ranges from:

```text
0 to 1
```

* `0` → Completely transparent
* `0.5` → 50% transparent
* `1` → Completely opaque

## 💻 Example

```css
div {
    background-color: rgba(255, 0, 0, 0.5);
}
```

This creates a red background with **50% transparency**.

### More Examples

```css
background-color: rgba(0, 0, 255, 1);
```

Blue with no transparency.

```css
background-color: rgba(0, 0, 255, 0.5);
```

Blue with 50% transparency.

```css
background-color: rgba(0, 0, 255, 0);
```

Completely transparent blue.

---

# 4️⃣ HEX Colors

## 📖 Definition

HEX stands for **Hexadecimal**.

A HEX color begins with the `#` symbol and is followed by six hexadecimal characters.

Syntax:

```css
#RRGGBB
```

Where:

* `RR` → Red
* `GG` → Green
* `BB` → Blue

Each pair can have values from:

```text
00 to FF
```

## 💻 Examples

```css
p {
    color: #ff0000;
}
```

This produces red.

```css
p {
    color: #00ff00;
}
```

This produces green.

```css
p {
    color: #0000ff;
}
```

This produces blue.

### 📊 HEX Examples

| HEX Value | Color  |
| --------- | ------ |
| `#FF0000` | Red    |
| `#00FF00` | Green  |
| `#0000FF` | Blue   |
| `#000000` | Black  |
| `#FFFFFF` | White  |
| `#FFFF00` | Yellow |
| `#FFA500` | Orange |
| `#800080` | Purple |

---

# 5️⃣ HSL Colors

## 📖 Definition

HSL stands for:

> **Hue, Saturation, Lightness**

Syntax:

```css
hsl(hue, saturation, lightness)
```

### Hue

Hue represents the color.

It is measured in degrees from:

```text
0° to 360°
```

Examples:

* `0°` → Red
* `120°` → Green
* `240°` → Blue

### Saturation

Saturation represents the intensity of the color.

It is expressed as a percentage.

```text
0% → Gray
100% → Full color
```

### Lightness

Lightness represents how light or dark the color is.

```text
0% → Black
50% → Normal color
100% → White
```

## 💻 Example

```css
h1 {
    color: hsl(0, 100%, 50%);
}
```

This creates a red color.

Another example:

```css
p {
    color: hsl(120, 100%, 50%);
}
```

This creates a green color.

---

# 6️⃣ HSLA Colors

## 📖 Definition

HSLA stands for:

> **Hue + Saturation + Lightness + Alpha**

The alpha value controls transparency.

Syntax:

```css
hsla(hue, saturation, lightness, alpha)
```

## 💻 Example

```css
div {
    background-color: hsla(240, 100%, 50%, 0.5);
}
```

This creates a blue color with 50% transparency.

---

# 🧩 CSS Color Properties

The most commonly used CSS color properties are:

| Property           | Purpose                  |
| ------------------ | ------------------------ |
| `color`            | Changes text color       |
| `background-color` | Changes background color |
| `border-color`     | Changes border color     |

---

## 1. `color`

The `color` property changes the color of text.

```css
h1 {
    color: red;
}
```

---

## 2. `background-color`

The `background-color` property changes the background color of an element.

```css
body {
    background-color: lightblue;
}
```

---

## 3. `border-color`

The `border-color` property changes the color of a border.

```css
div {
    border-style: solid;
    border-color: red;
}
```

---

# 💻 Complete Program

The following program demonstrates different CSS color methods.

```html
<!DOCTYPE html>
<html>

<head>

    <title>CSS Colors</title>

    <style>

        body {
            background-color: lightyellow;
        }

        h1 {
            color: blue;
            text-align: center;
        }

        .name {
            color: red;
        }

        .rgb {
            color: rgb(0, 128, 0);
        }

        .rgba {
            color: rgba(255, 0, 0, 0.7);
        }

        .hex {
            color: #800080;
        }

        .hsl {
            color: hsl(240, 100%, 50%);
        }

        .hsla {
            color: hsla(120, 100%, 30%, 0.8);
        }

        .box {
            background-color: #87CEEB;
            border: 3px solid #0000FF;
            padding: 20px;
            text-align: center;
        }

    </style>

</head>

<body>

    <h1>CSS Colors</h1>

    <p class="name">
        This text uses a Color Name.
    </p>

    <p class="rgb">
        This text uses RGB color.
    </p>

    <p class="rgba">
        This text uses RGBA color.
    </p>

    <p class="hex">
        This text uses HEX color.
    </p>

    <p class="hsl">
        This text uses HSL color.
    </p>

    <p class="hsla">
        This text uses HSLA color.
    </p>

    <div class="box">
        This box uses background and border colors.
    </div>

</body>

</html>
```

---

# 🔍 Program Explanation

## `<style>`

```html
<style>
```

The `<style>` element contains Internal CSS.

---

## `body`

```css
body {
    background-color: lightyellow;
}
```

Changes the background color of the complete webpage.

---

## `h1`

```css
h1 {
    color: blue;
    text-align: center;
}
```

* `color: blue` → makes the heading blue.
* `text-align: center` → places the heading in the center.

---

## Class Selector

Example:

```css
.rgb {
    color: rgb(0, 128, 0);
}
```

The `.rgb` selector applies the specified color to an element having:

```html
class="rgb"
```

For example:

```html
<p class="rgb">
    This text uses RGB color.
</p>
```

---

# 🔄 How CSS Colors Work

```text
                CSS COLORS
                    |
       ┌────────────┼────────────┐
       ↓            ↓            ↓
   Text Color   Background     Border
       |            |            |
    color      background-      border-
                 color           color
       |
       ↓
  Color Values
       |
 ┌─────┼─────┬─────┬─────┬─────┐
 ↓     ↓     ↓     ↓     ↓
Name  RGB  RGBA  HEX  HSL  HSLA
```

---

# 🆚 Comparison of Color Methods

| Method     | Example                | Transparency |
| ---------- | ---------------------- | ------------ |
| Color Name | `red`                  | ❌            |
| RGB        | `rgb(255,0,0)`         | ❌            |
| RGBA       | `rgba(255,0,0,0.5)`    | ✅            |
| HEX        | `#FF0000`              | ❌            |
| HSL        | `hsl(0,100%,50%)`      | ❌            |
| HSLA       | `hsla(0,100%,50%,0.5)` | ✅            |

---

# 🎨 Common CSS Colors

| Color | Name   | HEX       |
| ----- | ------ | --------- |
| 🔴    | Red    | `#FF0000` |
| 🟢    | Green  | `#008000` |
| 🔵    | Blue   | `#0000FF` |
| ⚫     | Black  | `#000000` |
| ⚪     | White  | `#FFFFFF` |
| 🟡    | Yellow | `#FFFF00` |
| 🟠    | Orange | `#FFA500` |
| 🟣    | Purple | `#800080` |
| 🩷    | Pink   | `#FFC0CB` |
| 🟤    | Brown  | `#A52A2A` |
| 🩶    | Gray   | `#808080` |

---

# ⚠️ Common Mistakes

## 1. Forgetting `#` in HEX Color

❌ Incorrect:

```css
color: FF0000;
```

✅ Correct:

```css
color: #FF0000;
```

---

## 2. Using Invalid RGB Values

RGB values should normally be between `0` and `255`.

❌ Incorrect:

```css
color: rgb(300, 0, 0);
```

✅ Correct:

```css
color: rgb(255, 0, 0);
```

---

## 3. Forgetting the `%` in HSL

❌ Incorrect:

```css
color: hsl(120, 100, 50);
```

✅ Correct:

```css
color: hsl(120, 100%, 50%);
```

---

## 4. Incorrect Alpha Value

Alpha values range from `0` to `1`.

❌ Incorrect:

```css
color: rgba(255, 0, 0, 5);
```

✅ Correct:

```css
color: rgba(255, 0, 0, 0.5);
```

---

# 🎓 Viva Questions and Answers

### Q1. What is CSS color?

**Answer:**
CSS color is used to specify the color of HTML elements such as text, backgrounds, and borders.

---

### Q2. Which property is used to change text color?

**Answer:**

```css
color
```

Example:

```css
p {
    color: red;
}
```

---

### Q3. Which property is used to change background color?

**Answer:**

```css
background-color
```

Example:

```css
body {
    background-color: yellow;
}
```

---

### Q4. What does RGB stand for?

**Answer:**
RGB stands for **Red, Green, and Blue**.

---

### Q5. What is the range of RGB values?

**Answer:**
Each RGB value normally ranges from **0 to 255**.

---

### Q6. What does RGBA stand for?

**Answer:**
RGBA stands for **Red, Green, Blue, and Alpha**.

---

### Q7. What is Alpha in RGBA?

**Answer:**
Alpha controls the **transparency** of a color.

---

### Q8. What does HEX mean?

**Answer:**
HEX means **Hexadecimal**. A HEX color is represented using six hexadecimal characters preceded by `#`.

Example:

```css
#FF0000
```

---

### Q9. What does HSL stand for?

**Answer:**
HSL stands for **Hue, Saturation, and Lightness**.

---

### Q10. What is the use of `background-color`?

**Answer:**
It is used to set the background color of an HTML element.

---

# ⭐ Key Points

* CSS provides several ways to specify colors.
* Color names are the simplest method.
* RGB uses Red, Green, and Blue values.
* RGBA additionally supports transparency.
* HEX colors use hexadecimal notation.
* HSL uses Hue, Saturation, and Lightness.
* HSLA additionally supports transparency.
* `color` changes text color.
* `background-color` changes background color.
* `border-color` changes border color.
* RGB values normally range from `0` to `255`.
* Alpha values range from `0` to `1`.

---

# 📝 Result

Thus, **CSS colors** were studied and successfully implemented using **Color Names, RGB, RGBA, HEX, HSL, and HSLA** color formats.

---

