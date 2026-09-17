# 📝 CSS Forms

<p align="center">
  <img src="https://img.shields.io/badge/CSS-Forms-1572B6?style=for-the-badge&logo=css3&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Learn how to design attractive and user-friendly HTML forms using CSS.
</p>

---

## 1. 📌 What is a CSS Form?

HTML provides the **structure** of a form, while CSS is used to **style and design** the form.

A form can contain:

* Text boxes
* Password fields
* Radio buttons
* Checkboxes
* Drop-down lists
* Text areas
* Submit buttons
* Reset buttons

### Simple idea

```text
HTML Form
   ↓
Structure
   ↓
CSS
   ↓
Design + Layout + Colors + Spacing
```

For example:

```html
<form>
    <label>Name:</label>
    <input type="text">

    <button type="submit">Submit</button>
</form>
```

CSS can make this form more attractive.

---

# 2. 🎨 Styling Input Fields

The `<input>` element is one of the most commonly used form elements.

### Example

```html
<input type="text" placeholder="Enter your name">
```

CSS:

```css
input {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
}
```

### Explanation

| Property        | Purpose                 |
| --------------- | ----------------------- |
| `width`         | Controls input width    |
| `padding`       | Adds space inside input |
| `border`        | Creates boundary        |
| `border-radius` | Makes corners rounded   |

---

# 3. 📏 Input Width

We can control the width of input fields using `width`.

```css
input {
    width: 300px;
}
```

### Responsive width

```css
input {
    width: 100%;
}
```

This allows the input field to use the available width of its container.

---

# 4. 📦 Padding in Input Fields

Padding creates space between the text and the input field's border.

```css
input {
    padding: 12px;
}
```

### Visual idea

```text
┌──────────────────────────────┐
│   Enter your name            │
└──────────────────────────────┘
    ↑
  Padding
```

More padding makes the input field easier to use.

---

# 5. 🔲 Input Border

The `border` property defines the boundary of an input field.

```css
input {
    border: 1px solid gray;
}
```

You can also change the border color:

```css
input {
    border: 2px solid blue;
}
```

---

# 6. 🔵 Rounded Input Fields

Use `border-radius` to create rounded corners.

```css
input {
    border-radius: 8px;
}
```

### Example

```css
input {
    padding: 10px;
    border: 1px solid #aaa;
    border-radius: 8px;
}
```

---

# 7. ✏️ Styling Labels

Labels describe what information the user should enter.

HTML:

```html
<label for="name">Name</label>
```

CSS:

```css
label {
    display: block;
    margin-bottom: 5px;
    font-weight: bold;
}
```

### Why `display: block`?

It places the label on a separate line.

```text
Name
┌─────────────────────┐
│ Enter your name     │
└─────────────────────┘
```

---

# 8. 🎯 Styling Input on Focus

The `:focus` pseudo-class applies CSS when the user clicks inside an input field.

```css
input:focus {
    border: 2px solid blue;
    outline: none;
}
```

### Before Focus

```text
┌─────────────────────┐
│ Enter Name          │
└─────────────────────┘
```

### After Focus

```text
┌─────────────────────┐
│ Enter Name          │
└═════════════════════┘
      ↑
   Focus
```

This helps users know which field they are currently using.

---

# 9. 🔍 Styling Search Inputs

Search boxes can also be styled using CSS.

```html
<input type="search" placeholder="Search...">
```

```css
input[type="search"] {
    width: 300px;
    padding: 10px;
    border: 1px solid #aaa;
    border-radius: 20px;
}
```

---

# 10. 🔐 Styling Password Fields

Password fields can be selected using:

```css
input[type="password"] {
    width: 100%;
    padding: 10px;
    border-radius: 5px;
}
```

HTML:

```html
<input type="password" placeholder="Enter password">
```

---

# 11. 📋 Styling Textarea

`<textarea>` is used when users need to enter multiple lines of text.

HTML:

```html
<textarea placeholder="Write your message"></textarea>
```

CSS:

```css
textarea {
    width: 100%;
    height: 120px;
    padding: 10px;
    border: 1px solid #aaa;
    border-radius: 6px;
    resize: vertical;
}
```

### `resize`

```css
resize: vertical;
```

allows the user to resize the textarea vertically.

Other values:

```css
resize: none;
resize: horizontal;
resize: both;
```

---

# 12. 🔘 Styling Buttons

Buttons are important elements of forms.

HTML:

```html
<button type="submit">Submit</button>
```

CSS:

```css
button {
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}
```

---

# 13. 🖱️ Button Hover Effect

The `:hover` pseudo-class changes the button when the mouse pointer moves over it.

```css
button:hover {
    transform: translateY(-1px);
}
```

You can also add a transition:

```css
button {
    transition: 0.3s;
}

button:hover {
    transform: translateY(-1px);
}
```

---

# 14. ☑️ Styling Checkboxes and Radio Buttons

HTML:

```html
<label>
    <input type="checkbox">
    I agree
</label>
```

Radio buttons:

```html
<label>
    <input type="radio" name="gender">
    Male
</label>

<label>
    <input type="radio" name="gender">
    Female
</label>
```

Basic CSS:

```css
input[type="checkbox"],
input[type="radio"] {
    margin-right: 5px;
}
```

> 💡 Modern browsers also support `accent-color` for changing the accent color of checkboxes and radio buttons.

Example:

```css
input[type="checkbox"],
input[type="radio"] {
    accent-color: blue;
}
```

---

# 15. 📑 Styling Select Dropdown

HTML:

```html
<select>
    <option>India</option>
    <option>USA</option>
    <option>UK</option>
</select>
```

CSS:

```css
select {
    width: 100%;
    padding: 10px;
    border: 1px solid #aaa;
    border-radius: 5px;
}
```

---

# 16. 🧱 Form Container

Usually, we place the form inside a container.

```html
<div class="form-container">

    <h2>Registration Form</h2>

    <form>
        ...
    </form>

</div>
```

CSS:

```css
.form-container {
    max-width: 500px;
    margin: 30px auto;
    padding: 25px;
    border: 1px solid #ddd;
    border-radius: 10px;
}
```

### What does `margin: auto` do?

```css
margin: 30px auto;
```

The left and right margins become automatic, which helps center the container horizontally when it has a limited width.

---

# 17. 📐 Box Sizing

A very useful property for forms is:

```css
box-sizing: border-box;
```

Example:

```css
* {
    box-sizing: border-box;
}
```

It makes the declared `width` include:

```text
Width
 ├── Content
 ├── Padding
 └── Border
```

This makes form layouts easier to control.

---

# 18. 🏷️ Styling Placeholder Text

Placeholder text provides a hint about what the user should enter.

HTML:

```html
<input type="text" placeholder="Enter your name">
```

CSS:

```css
input::placeholder {
    opacity: 0.7;
}
```

---

# 19. 🚫 Styling Disabled Inputs

HTML:

```html
<input type="text" disabled value="Not Available">
```

CSS:

```css
input:disabled {
    opacity: 0.6;
    cursor: not-allowed;
}
```

The `:disabled` pseudo-class selects disabled form controls.

---

# 20. 📱 Responsive Form

A good form should work on:

* 📱 Mobile
* 💻 Laptop
* 🖥️ Desktop
* 📟 Tablet

Example:

```css
.form-container {
    width: 90%;
    max-width: 500px;
    margin: auto;
}
```

This prevents the form from becoming too wide on large screens while allowing it to shrink on smaller screens.

---

# 21. 📱 Form with Media Query

We can modify the form for smaller screens.

```css
@media (max-width: 600px) {

    .form-container {
        width: 95%;
        padding: 15px;
    }

    input,
    textarea,
    select {
        width: 100%;
    }
}
```

> 📌 `600px` is only an example breakpoint. Choose breakpoints based on the layout rather than a fixed device list.

---

# 22. 📝 Complete Registration Form

## HTML

```html
<!DOCTYPE html>
<html>
<head>
    <title>Registration Form</title>
    <link rel="stylesheet" href="style.css">
</head>

<body>

<div class="form-container">

    <h2>Registration Form</h2>

    <form>

        <label for="name">Full Name</label>
        <input type="text"
               id="name"
               placeholder="Enter your name">

        <label for="email">Email</label>
        <input type="email"
               id="email"
               placeholder="Enter your email">

        <label for="password">Password</label>
        <input type="password"
               id="password"
               placeholder="Enter your password">

        <label for="course">Course</label>

        <select id="course">
            <option>CSE</option>
            <option>IT</option>
            <option>ECE</option>
            <option>EEE</option>
        </select>

        <label for="message">Message</label>

        <textarea id="message"
                  placeholder="Enter your message"></textarea>

        <label>
            <input type="checkbox">
            I agree to the terms and conditions
        </label>

        <button type="submit">Register</button>

    </form>

</div>

</body>
</html>
```

---

## CSS

```css
* {
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f2f2f2;
    margin: 0;
    padding: 20px;
}

.form-container {
    width: 90%;
    max-width: 500px;
    margin: 30px auto;
    padding: 25px;
    background-color: white;
    border-radius: 10px;
}

h2 {
    text-align: center;
}

label {
    display: block;
    margin-top: 15px;
    margin-bottom: 5px;
    font-weight: bold;
}

input[type="text"],
input[type="email"],
input[type="password"],
select,
textarea {
    width: 100%;
    padding: 10px;
    border: 1px solid #aaa;
    border-radius: 5px;
    font-size: 16px;
}

textarea {
    height: 120px;
    resize: vertical;
}

input:focus,
select:focus,
textarea:focus {
    outline: none;
    border: 2px solid #1572B6;
}

input[type="checkbox"] {
    width: auto;
    margin-right: 5px;
    accent-color: #1572B6;
}

button {
    width: 100%;
    margin-top: 20px;
    padding: 12px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
}

button:hover {
    transform: translateY(-1px);
}

@media (max-width: 600px) {

    .form-container {
        width: 95%;
        padding: 15px;
    }
}
```

---

# 23. 🧠 Important Form CSS Properties

| CSS Property       | Purpose                                    |
| ------------------ | ------------------------------------------ |
| `width`            | Controls element width                     |
| `height`           | Controls element height                    |
| `padding`          | Space inside the element                   |
| `margin`           | Space outside the element                  |
| `border`           | Creates boundary                           |
| `border-radius`    | Rounds corners                             |
| `background-color` | Changes background                         |
| `color`            | Changes text color                         |
| `font-size`        | Changes text size                          |
| `text-align`       | Aligns text                                |
| `outline`          | Focus outline                              |
| `cursor`           | Changes mouse cursor                       |
| `resize`           | Controls textarea resizing                 |
| `box-sizing`       | Controls how width/height are calculated   |
| `accent-color`     | Changes accent color of supported controls |

---

# 24. 🔄 Form Styling Flow

```text
             HTML FORM
                 │
                 ▼
       ┌──────────────────┐
       │ Input / Select   │
       │ Textarea / Button│
       └──────────────────┘
                 │
                 ▼
                CSS
                 │
        ┌────────┼────────┐
        ▼        ▼        ▼
      Size    Spacing   Colors
        │        │        │
        └────────┼────────┘
                 ▼
        Attractive Form
```

---

# 25. ⚖️ HTML vs CSS in Forms

| HTML                 | CSS                      |
| -------------------- | ------------------------ |
| Creates the form     | Designs the form         |
| Creates input fields | Changes input appearance |
| Creates buttons      | Styles buttons           |
| Creates labels       | Styles labels            |
| Creates dropdowns    | Styles dropdowns         |
| Provides structure   | Provides visual layout   |

### Remember

> **HTML = Structure**
> **CSS = Style**

---

# 26. ❌ Common Mistakes

### Mistake 1: Forgetting labels

❌

```html
<input type="text">
```

Better:

```html
<label for="name">Name</label>
<input type="text" id="name">
```

---

### Mistake 2: Fixed large width

❌

```css
input {
    width: 800px;
}
```

Better:

```css
input {
    width: 100%;
    max-width: 500px;
}
```

---

### Mistake 3: Removing focus indication

Avoid removing focus styles without providing another clear focus indicator.

Good:

```css
input:focus {
    outline: none;
    border: 2px solid blue;
}
```

Here, the border provides a visible focus indication.

---

# 27. 📝 Practice Questions

### Q1. What is the purpose of CSS in a form?

### Q2. Which property controls the width of an input field?

### Q3. What is the use of `padding`?

### Q4. What does `border-radius` do?

### Q5. What is the purpose of `:focus`?

### Q6. How can you style a button when the mouse pointer moves over it?

### Q7. What is the purpose of `resize` in `<textarea>`?

### Q8. What is the difference between `margin` and `padding`?

### Q9. Why is `box-sizing: border-box` useful in form layouts?

### Q10. How can you make a form responsive?

---

# ⚡ Quick Revision

```text
CSS Forms
│
├── Input Styling
│   ├── width
│   ├── padding
│   ├── border
│   └── border-radius
│
├── Labels
│   └── display
│
├── States
│   ├── :focus
│   ├── :hover
│   └── :disabled
│
├── Controls
│   ├── input
│   ├── textarea
│   ├── select
│   ├── checkbox
│   └── radio
│
├── Layout
│   ├── margin
│   ├── padding
│   ├── width
│   └── box-sizing
│
└── Responsive Design
    └── @media
```

### ⭐ Remember

> **CSS makes an HTML form attractive, organized, responsive, and user-friendly.**

---

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-1572B6?style=for-the-badge&logo=html5&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 • Web Designing Workshop</b>
</p>

