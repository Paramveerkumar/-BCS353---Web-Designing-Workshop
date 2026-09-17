# 📐 Bootstrap Grid System

<p align="center">
  <img src="https://img.shields.io/badge/BCS353-Web%20Designing%20Workshop-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white">
</p>

<p align="center">
  <b>📘 BCS353 – Web Designing Workshop</b><br>
  Learn how to create responsive layouts using the Bootstrap Grid System.
</p>

---

## 📌 1. What is the Bootstrap Grid System?

The **Bootstrap Grid System** is a layout system used to arrange webpage content into **rows and columns**.

Bootstrap divides a row into **12 columns**.

```text
┌────┬────┬────┬────┬────┬────┬────┬────┬────┬────┬────┬────┐
│ 1  │ 2  │ 3  │ 4  │ 5  │ 6  │ 7  │ 8  │ 9  │ 10 │ 11 │ 12 │
└────┴────┴────┴────┴────┴────┴────┴────┴────┴────┴────┴────┘
                    12 Columns
```

We use these 12 columns to create different webpage layouts.

---

# 🎯 2. Basic Structure

The Bootstrap Grid follows this structure:

```text
Container
   ↓
  Row
   ↓
Columns
```

Example:

```html
<div class="container">

    <div class="row">

        <div class="col">
            Column 1
        </div>

        <div class="col">
            Column 2
        </div>

    </div>

</div>
```

### Remember:

```text
.container
     ↓
   .row
     ↓
   .col
```

---

# 📦 3. `.container`

The `.container` class creates a responsive fixed-width container.

```html
<div class="container">
    Content goes here
</div>
```

Conceptually:

```text
Browser Window
┌───────────────────────────────────────┐
│                                       │
│     ┌───────────────────────────┐     │
│     │        Container          │     │
│     │                           │     │
│     └───────────────────────────┘     │
│                                       │
└───────────────────────────────────────┘
```

---

# 🌐 4. `.container-fluid`

`.container-fluid` uses the **full available width**.

```html
<div class="container-fluid">
    Full Width Content
</div>
```

### Difference

| Class              | Width                    |
| ------------------ | ------------------------ |
| `.container`       | Responsive maximum width |
| `.container-fluid` | 100% available width     |

---

# ➡️ 5. `.row`

The `.row` class creates a horizontal row for columns.

```html
<div class="container">

    <div class="row">

        <!-- Columns -->

    </div>

</div>
```

Think of a row as a **box containing columns**.

```text
┌─────────────────────────────────────────┐
│                  ROW                    │
│ ┌──────────┐ ┌──────────┐ ┌──────────┐ │
│ │ Column 1 │ │ Column 2 │ │ Column 3 │ │
│ └──────────┘ └──────────┘ └──────────┘ │
└─────────────────────────────────────────┘
```

---

# 🧩 6. Columns

Bootstrap provides a **12-column grid**.

For example:

```html
<div class="row">

    <div class="col-4">
        Column 1
    </div>

    <div class="col-4">
        Column 2
    </div>

    <div class="col-4">
        Column 3
    </div>

</div>
```

Calculation:

```text
4 + 4 + 4 = 12
```

So the three columns occupy the complete row.

```text
┌────────────┬────────────┬────────────┐
│   col-4    │   col-4    │   col-4    │
│    33.33%  │    33.33%  │    33.33%  │
└────────────┴────────────┴────────────┘
```

---

# 🔢 7. Understanding Column Numbers

The number after `col-` represents how many of the **12 columns** the element occupies.

### Example:

```html
<div class="col-6">
    Content
</div>
```

It occupies:

```text
6 / 12 columns
```

Therefore:

```text
6 ÷ 12 × 100 = 50%
```

### Common Examples

| Class     | Grid Space | Approx. Width |
| --------- | ---------: | ------------: |
| `.col-1`  |       1/12 |         8.33% |
| `.col-2`  |       2/12 |        16.67% |
| `.col-3`  |       3/12 |           25% |
| `.col-4`  |       4/12 |        33.33% |
| `.col-6`  |       6/12 |           50% |
| `.col-8`  |       8/12 |        66.67% |
| `.col-12` |      12/12 |          100% |

---

# 🖥️ 8. Two-Column Layout

To create two equal columns:

```html
<div class="row">

    <div class="col-6">
        Left Side
    </div>

    <div class="col-6">
        Right Side
    </div>

</div>
```

Calculation:

```text
6 + 6 = 12
```

Layout:

```text
┌────────────────────┬────────────────────┐
│     Left Side      │     Right Side     │
│       col-6        │       col-6        │
└────────────────────┴────────────────────┘
```

---

# 🖥️ 9. Three-Column Layout

```html
<div class="row">

    <div class="col-4">Column 1</div>
    <div class="col-4">Column 2</div>
    <div class="col-4">Column 3</div>

</div>
```

```text
4 + 4 + 4 = 12
```

```text
┌────────────┬────────────┬────────────┐
│  Column 1  │  Column 2  │  Column 3  │
│   col-4    │   col-4    │   col-4    │
└────────────┴────────────┴────────────┘
```

---

# 📱 10. Responsive Grid

One of the most important features of Bootstrap is **responsive design**.

We can specify different column sizes for different screen sizes.

Example:

```html
<div class="row">

    <div class="col-12 col-md-6 col-lg-4">
        Column 1
    </div>

    <div class="col-12 col-md-6 col-lg-4">
        Column 2
    </div>

    <div class="col-12 col-md-6 col-lg-4">
        Column 3
    </div>

</div>
```

### Meaning

```text
Mobile
↓
col-12
↓
1 column per row

Tablet
↓
col-md-6
↓
2 columns per row

Large screen
↓
col-lg-4
↓
3 columns per row
```

Visual representation:

### 📱 Mobile

```text
┌──────────────────────┐
│      Column 1        │
├──────────────────────┤
│      Column 2        │
├──────────────────────┤
│      Column 3        │
└──────────────────────┘
```

### 📱 Tablet

```text
┌─────────────┬─────────────┐
│  Column 1   │  Column 2   │
├─────────────┼─────────────┤
│  Column 3   │             │
└─────────────┴─────────────┘
```

### 💻 Large Screen

```text
┌────────────┬────────────┬────────────┐
│  Column 1  │  Column 2  │  Column 3  │
└────────────┴────────────┴────────────┘
```

---

# 📊 11. Bootstrap Breakpoints

Bootstrap provides responsive breakpoints such as:

| Breakpoint        | Class Prefix |
| ----------------- | ------------ |
| Extra small       | `.col-*`     |
| Small             | `.col-sm-*`  |
| Medium            | `.col-md-*`  |
| Large             | `.col-lg-*`  |
| Extra large       | `.col-xl-*`  |
| Extra extra large | `.col-xxl-*` |

Example:

```html
<div class="col-12 col-md-6 col-lg-4">
    Product
</div>
```

This means:

```text
Small screens → 12 columns
Medium screens → 6 columns
Large screens → 4 columns
```

> 💡 The breakpoints represent screen-width ranges; they should not be interpreted as specific physical devices.

---

# 🔄 12. How Responsive Grid Works

```text
                Bootstrap Grid
                      │
          ┌───────────┴───────────┐
          ↓                       ↓
       Screen Size            Column Size
          │                       │
    ┌─────┼─────┐           ┌─────┼─────┐
    ↓     ↓     ↓           ↓     ↓     ↓
 Mobile Tablet Desktop      12     6     4
```

Bootstrap automatically applies the appropriate class according to the viewport width.

---

# ⚖️ 13. `.col` vs `.col-6`

### `.col`

Columns automatically share the available row space.

```html
<div class="row">

    <div class="col">A</div>
    <div class="col">B</div>
    <div class="col">C</div>

</div>
```

Result:

```text
┌────────────┬────────────┬────────────┐
│     A      │     B      │     C      │
└────────────┴────────────┴────────────┘
```

### `.col-6`

Each column gets 6 of 12 grid units.

```html
<div class="row">

    <div class="col-6">A</div>
    <div class="col-6">B</div>

</div>
```

Result:

```text
┌────────────────────┬────────────────────┐
│         A          │         B          │
└────────────────────┴────────────────────┘
```

---

# 🧱 14. Nested Rows

A row can contain another row inside a column.

```html
<div class="container">

    <div class="row">

        <div class="col-8">

            Main Content

            <div class="row">

                <div class="col-6">
                    Nested 1
                </div>

                <div class="col-6">
                    Nested 2
                </div>

            </div>

        </div>

        <div class="col-4">
            Sidebar
        </div>

    </div>

</div>
```

Concept:

```text
Container
   │
   └── Row
       │
       ├── col-8
       │    │
       │    └── Nested Row
       │         ├── col-6
       │         └── col-6
       │
       └── col-4
```

---

# 🎨 15. Complete Grid Example

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1">

    <title>Bootstrap Grid</title>

    <!-- Bootstrap CSS -->
    <link
        href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"
        rel="stylesheet">
</head>

<body>

    <div class="container mt-5">

        <h1 class="text-center text-primary mb-4">
            Bootstrap Grid System
        </h1>

        <div class="row g-3">

            <div class="col-12 col-md-6 col-lg-4">
                <div class="p-4 bg-light border">
                    Column 1
                </div>
            </div>

            <div class="col-12 col-md-6 col-lg-4">
                <div class="p-4 bg-light border">
                    Column 2
                </div>
            </div>

            <div class="col-12 col-md-6 col-lg-4">
                <div class="p-4 bg-light border">
                    Column 3
                </div>
            </div>

        </div>

    </div>

</body>

</html>
```

---

# 📐 16. Understanding `g-3`

In the previous example:

```html
<div class="row g-3">
```

`g-3` adds **gap/gutter spacing** between the grid items.

Other examples:

```html
<div class="row g-1">
<div class="row g-2">
<div class="row g-3">
<div class="row g-4">
<div class="row g-5">
```

---

# 🛒 17. Real-Life Example: Online Book Store

Suppose we have six books.

```html
<div class="container">

    <div class="row g-4">

        <div class="col-12 col-md-6 col-lg-4">
            Book 1
        </div>

        <div class="col-12 col-md-6 col-lg-4">
            Book 2
        </div>

        <div class="col-12 col-md-6 col-lg-4">
            Book 3
        </div>

        <div class="col-12 col-md-6 col-lg-4">
            Book 4
        </div>

        <div class="col-12 col-md-6 col-lg-4">
            Book 5
        </div>

        <div class="col-12 col-md-6 col-lg-4">
            Book 6
        </div>

    </div>

</div>
```

### Layout

```text
📱 Mobile

Book 1
Book 2
Book 3
Book 4
Book 5
Book 6


📱 Tablet

Book 1 | Book 2
Book 3 | Book 4
Book 5 | Book 6


💻 Large Screen

Book 1 | Book 2 | Book 3
Book 4 | Book 5 | Book 6
```

---

# 🧠 18. Important Rule

Always remember:

```text
One Row = 12 Grid Units
```

For example:

```text
col-3 + col-3 + col-3 + col-3
       = 12
```

```text
col-6 + col-6
       = 12
```

```text
col-8 + col-4
       = 12
```

```text
col-7 + col-5
       = 12
```

If the total exceeds 12, additional columns can wrap to the next line.

---

# ⚠️ 19. Common Mistakes

### ❌ Mistake 1: Using `.col` without `.row`

Prefer:

```html
<div class="row">
    <div class="col">Content</div>
</div>
```

### ❌ Mistake 2: Forgetting the container

A typical Bootstrap grid structure is:

```text
.container
    ↓
.row
    ↓
.col
```

### ❌ Mistake 3: Forgetting responsive classes

Instead of:

```html
<div class="col-4">
```

consider:

```html
<div class="col-12 col-md-6 col-lg-4">
```

when you want different layouts at different viewport widths.

---

# 🎯 20. Student Practice

Create a **Student Dashboard** using Bootstrap Grid.

Your webpage should contain:

```text
              Student Dashboard

┌───────────────────────────────────────┐
│               Header                  │
└───────────────────────────────────────┘

┌───────────────┬───────────────────────┐
│   Sidebar     │      Main Content      │
│               │                       │
│   Home        │   Profile             │
│   Courses     │   Courses             │
│   Results     │   Announcements       │
└───────────────┴───────────────────────┘
```

### Requirements

* Use `.container`
* Use `.row`
* Use `.col-*`
* Use at least **3 responsive columns**
* Use `g-3` or `g-4`
* Make the layout responsive

---

# ❓ 21. Important Questions

### Q1. How many columns are available in the Bootstrap Grid?

**12 columns.**

### Q2. What is the purpose of `.row`?

It creates a row for arranging Bootstrap columns.

### Q3. What does `.col-6` mean?

It occupies **6 out of 12 grid units**, approximately **50%** of the row.

### Q4. What does `.col-md-6` mean?

The element occupies 6 grid units at the **medium breakpoint and above**, subject to Bootstrap's responsive breakpoint rules.

### Q5. What is `.container`?

It provides a responsive content container with breakpoint-dependent maximum widths.

### Q6. What is `.container-fluid`?

It uses the full available width.

### Q7. What is the basic Bootstrap Grid structure?

```text
Container
    ↓
Row
    ↓
Columns
```

---

# ⚡ 22. Quick Revision

```text
📐 Bootstrap Grid
        ↓
     12 Units
        ↓
   ┌────┴────┐
   ↓         ↓
  Row      Columns
             ↓
      Responsive Layout
```

### Remember:

| Concept            | Meaning                        |
| ------------------ | ------------------------------ |
| `.container`       | Responsive container           |
| `.container-fluid` | Full-width container           |
| `.row`             | Grid row                       |
| `.col`             | Automatic column               |
| `.col-6`           | 6/12 grid units                |
| `.col-md-6`        | 6 units from medium breakpoint |
| `.col-lg-4`        | 4 units from large breakpoint  |
| `g-3`              | Grid gap/gutter spacing        |

### Golden Rule ⭐

> **Bootstrap Grid = Container + Row + Columns**

And:

> **One Bootstrap row = 12 grid units.**

---

<p align="center">
  <img src="https://img.shields.io/badge/Bootstrap-Grid%20System-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white">
</p>

<p align="center">
  <b>BCS353 • Web Designing Workshop</b>
</p>
