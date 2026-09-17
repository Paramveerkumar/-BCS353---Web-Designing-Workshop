
# 🔘 Bootstrap Buttons

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Learn how to create attractive and responsive buttons using Bootstrap.
</p>

---

## 1. What is a Button?

A **button** is a clickable element used to perform an action.

Examples:

* 🔐 Login
* 📝 Register
* 🛒 Add to Cart
* 💾 Save
* 🔍 Search
* 📤 Submit

In normal HTML:

```html
<button>Click Me</button>
```

Bootstrap provides ready-made classes to style buttons.

---

# 2. Basic Bootstrap Button

To create a Bootstrap button, use:

```html
<button class="btn btn-primary">
    Click Me
</button>
```

There are two important classes:

```text
.btn
  ↓
Basic Bootstrap button styling

.btn-primary
  ↓
Button color/style
```

### Structure

```text
<button>
   ↓
 class="btn btn-primary"
        ↓       ↓
      Base    Variant
      Style
```

---

# 3. Bootstrap Button Variants

Bootstrap provides several predefined button styles.

| Class            | Typical Use                |
| ---------------- | -------------------------- |
| `.btn-primary`   | Main/primary action        |
| `.btn-secondary` | Secondary action           |
| `.btn-success`   | Successful/positive action |
| `.btn-danger`    | Delete or dangerous action |
| `.btn-warning`   | Warning                    |
| `.btn-info`      | Information                |
| `.btn-light`     | Light button               |
| `.btn-dark`      | Dark button                |
| `.btn-link`      | Link-style button          |

Example:

```html
<button class="btn btn-primary">Primary</button>
<button class="btn btn-secondary">Secondary</button>
<button class="btn btn-success">Success</button>
<button class="btn btn-danger">Delete</button>
<button class="btn btn-warning">Warning</button>
<button class="btn btn-info">Info</button>
<button class="btn btn-light">Light</button>
<button class="btn btn-dark">Dark</button>
<button class="btn btn-link">Link</button>
```

---

# 4. Button Examples

### 🔵 Primary

```html
<button class="btn btn-primary">
    Login
</button>
```

### 🟢 Success

```html
<button class="btn btn-success">
    Submit
</button>
```

### 🔴 Danger

```html
<button class="btn btn-danger">
    Delete
</button>
```

### 🟡 Warning

```html
<button class="btn btn-warning">
    Warning
</button>
```

---

# 5. Why Use `.btn`?

The `.btn` class provides the **basic Bootstrap button styling**.

For example:

```html
<button class="btn">
    Button
</button>
```

But normally we combine it with a variant:

```html
<button class="btn btn-primary">
    Button
</button>
```

Think:

```text
.btn
 +
.btn-primary
 ↓
Styled Bootstrap Button
```

---

# 6. Button Sizes

Bootstrap provides three common button sizes:

```text
Small
Normal
Large
```

### Small Button

```html
<button class="btn btn-primary btn-sm">
    Small Button
</button>
```

### Normal Button

```html
<button class="btn btn-primary">
    Normal Button
</button>
```

### Large Button

```html
<button class="btn btn-primary btn-lg">
    Large Button
</button>
```

### Classes

| Class     | Size   |
| --------- | ------ |
| `.btn-sm` | Small  |
| `.btn`    | Normal |
| `.btn-lg` | Large  |

---

# 7. Outline Buttons

Bootstrap also provides **outline buttons**.

Instead of a filled background, the button has a border.

```html
<button class="btn btn-outline-primary">
    Primary
</button>

<button class="btn btn-outline-success">
    Success
</button>

<button class="btn btn-outline-danger">
    Delete
</button>
```

### Filled vs Outline

```text
Filled Button

┌─────────────────┐
│     Login       │
└─────────────────┘


Outline Button

┌─────────────────┐
│     Login       │
└─────────────────┘
```

The difference is in the Bootstrap class:

```html
btn-primary
```

vs.

```html
btn-outline-primary
```

---

# 8. Full-Width Button

We can make a button fill the width of its parent using:

```html
<button class="btn btn-primary w-100">
    Login
</button>
```

Here:

```text
.w-100
   ↓
100% width of the parent
```

Example:

```text
┌──────────────────────────────┐
│            Login             │
└──────────────────────────────┘
```

---

# 9. Button with Different Actions

Example of a login page:

```html
<button class="btn btn-primary">
    Login
</button>

<button class="btn btn-secondary">
    Reset
</button>
```

Example of an online bookstore:

```html
<button class="btn btn-primary">
    View Details
</button>

<button class="btn btn-success">
    Add to Cart
</button>

<button class="btn btn-danger">
    Remove
</button>
```

---

# 10. Button as a Link

An `<a>` element can be styled like a Bootstrap button.

```html
<a href="login.html" class="btn btn-primary">
    Login
</a>
```

This looks like a button but behaves as a **link**.

### Use:

```text
<button>
    For actions

<a>
    For navigation
```

Example:

```html
<a href="catalogue.html" class="btn btn-success">
    View Catalogue
</a>
```

---

# 11. Button with an Icon

You can place an icon or symbol inside a button.

```html
<button class="btn btn-primary">
    🔍 Search
</button>
```

Another example:

```html
<button class="btn btn-success">
    🛒 Add to Cart
</button>
```

Bootstrap's CSS does **not automatically include an icon library**. If you use Bootstrap Icons, they are added separately.

---

# 12. Disabled Buttons

A disabled button cannot normally be interacted with.

```html
<button class="btn btn-primary" disabled>
    Disabled
</button>
```

Example:

```html
<button class="btn btn-secondary" disabled>
    Coming Soon
</button>
```

The `disabled` attribute is an **HTML attribute**, not a Bootstrap class.

---

# 13. Button States

Buttons can have different interaction states.

```text
Normal
   ↓
Hover
   ↓
Active
   ↓
Disabled
```

Example:

```text
┌────────────────┐
│     Login      │  ← Normal
└────────────────┘

       ↓ Mouse over

┌────────────────┐
│     Login      │  ← Hover
└────────────────┘
```

Bootstrap provides styling for common interaction states automatically.

---

# 14. Button Groups

Multiple buttons can be grouped together using:

```html
<div class="btn-group">

    <button class="btn btn-primary">
        Home
    </button>

    <button class="btn btn-primary">
        About
    </button>

    <button class="btn btn-primary">
        Contact
    </button>

</div>
```

Conceptually:

```text
┌────────┬────────┬─────────┐
│  Home  │ About  │ Contact │
└────────┴────────┴─────────┘
```

---

# 15. Vertical Button Group

Use:

```html
<div class="btn-group-vertical">

    <button class="btn btn-primary">
        Home
    </button>

    <button class="btn btn-primary">
        Courses
    </button>

    <button class="btn btn-primary">
        Results
    </button>

</div>
```

Layout:

```text
┌──────────────┐
│     Home     │
├──────────────┤
│   Courses    │
├──────────────┤
│    Results   │
└──────────────┘
```

---

# 16. Button with Bootstrap Grid

Buttons can also be placed inside the Bootstrap Grid.

```html
<div class="container">

    <div class="row">

        <div class="col-md-6">
            <button class="btn btn-primary w-100">
                Login
            </button>
        </div>

        <div class="col-md-6">
            <button class="btn btn-success w-100">
                Register
            </button>
        </div>

    </div>

</div>
```

On smaller screens, the columns can stack depending on the responsive classes.

---

# 17. Complete Example

```html
<!DOCTYPE html>
<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1">

    <title>Bootstrap Buttons</title>

    <!-- Bootstrap CSS -->
    <link
        href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"
        rel="stylesheet">

</head>

<body>

    <div class="container mt-5">

        <h1 class="text-primary mb-4">
            Bootstrap Buttons
        </h1>

        <button class="btn btn-primary">
            Login
        </button>

        <button class="btn btn-success">
            Submit
        </button>

        <button class="btn btn-danger">
            Delete
        </button>

        <button class="btn btn-warning">
            Warning
        </button>

        <hr>

        <h3>Outline Buttons</h3>

        <button class="btn btn-outline-primary">
            Primary
        </button>

        <button class="btn btn-outline-success">
            Success
        </button>

        <button class="btn btn-outline-danger">
            Delete
        </button>

        <hr>

        <h3>Button Sizes</h3>

        <button class="btn btn-primary btn-sm">
            Small
        </button>

        <button class="btn btn-primary">
            Normal
        </button>

        <button class="btn btn-primary btn-lg">
            Large
        </button>

    </div>

</body>

</html>
```

---

# 18. Real-Life Example 🛒

For an **Online Book Store**:

```html
<div class="container">

    <h2>Book Details</h2>

    <p>
        Introduction to Web Designing
    </p>

    <button class="btn btn-primary">
        View Details
    </button>

    <button class="btn btn-success">
        🛒 Add to Cart
    </button>

    <button class="btn btn-danger">
        Remove
    </button>

</div>
```

---

# 19. Important Classes

| Class                  | Purpose                 |
| ---------------------- | ----------------------- |
| `.btn`                 | Basic button style      |
| `.btn-primary`         | Primary button          |
| `.btn-success`         | Success button          |
| `.btn-danger`          | Danger button           |
| `.btn-warning`         | Warning button          |
| `.btn-info`            | Information button      |
| `.btn-light`           | Light button            |
| `.btn-dark`            | Dark button             |
| `.btn-link`            | Link-style button       |
| `.btn-outline-primary` | Outline primary button  |
| `.btn-sm`              | Small button            |
| `.btn-lg`              | Large button            |
| `.w-100`               | 100% width              |
| `.btn-group`           | Horizontal button group |
| `.btn-group-vertical`  | Vertical button group   |

---

# 20. Common Mistakes ⚠️

### ❌ Mistake 1

Using only:

```html
<button class="btn-primary">
    Login
</button>
```

### ✅ Correct

```html
<button class="btn btn-primary">
    Login
</button>
```

You normally need both:

```text
.btn
+
.btn-primary
```

---

### ❌ Mistake 2

Using Bootstrap class without loading Bootstrap.

```html
<button class="btn btn-primary">
    Login
</button>
```

If Bootstrap CSS is not included, the Bootstrap styling will not appear.

---

# 🎯 21. Practice Activity

Create an **Online Book Store** page with:

### Buttons:

```text
[ Home ]

[ Login ]

[ Register ]

[ View Catalogue ]

[ Add to Cart ]

[ Remove ]
```

Requirements:

* Use at least **5 Bootstrap buttons**
* Use different button variants
* Use one outline button
* Use one large button
* Use one disabled button
* Create a button group

---

# ❓ 22. Important Questions

### Q1. Which class is required for a Bootstrap button?

```text
.btn
```

### Q2. What does `.btn-primary` do?

It applies the Bootstrap **primary button variant**.

### Q3. How do you create a small button?

```html
<button class="btn btn-primary btn-sm">
    Small
</button>
```

### Q4. How do you create a large button?

```html
<button class="btn btn-primary btn-lg">
    Large
</button>
```

### Q5. How do you create an outline button?

```html
<button class="btn btn-outline-primary">
    Outline
</button>
```

### Q6. How do you make a button full width?

```html
<button class="btn btn-primary w-100">
    Login
</button>
```

### Q7. Which class creates a button group?

```text
.btn-group
```

---

# ⚡ 23. Quick Revision

```text
              Bootstrap Button
                     │
             ┌───────┴───────┐
             ↓               ↓
           .btn          Variant
                             │
       ┌──────────┬──────────┼──────────┐
       ↓          ↓          ↓          ↓
    primary    success     danger     warning
```

### Most Important Examples

```html
<button class="btn btn-primary">
    Login
</button>
```

```html
<button class="btn btn-success">
    Submit
</button>
```

```html
<button class="btn btn-outline-primary">
    Learn More
</button>
```

```html
<button class="btn btn-primary btn-lg">
    Large Button
</button>
```

```html
<button class="btn btn-primary w-100">
    Full Width
</button>
```

### Golden Rule ⭐

> **Bootstrap Button = `.btn` + Button Variant**

Example:

```text
.btn + .btn-primary
       ↓
Bootstrap Primary Button
```

---

<p align="center">
  <img src="https://img.shields.io/badge/Bootstrap-Buttons-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white">
</p>

<p align="center">
  <b>BCS353 • Web Designing Workshop</b>
</p>
