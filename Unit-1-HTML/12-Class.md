# 🎨 HTML `class` Attribute

## 📌 Introduction

The HTML `class` attribute is used to give a **name (class name)** to one or more HTML elements.

Multiple HTML elements can have the **same class name**.

The `class` attribute is mainly used with:

* 🎨 **CSS** — to apply the same style to multiple elements.
* ⚙️ **JavaScript** — to select and manipulate multiple elements.

---

# 1️⃣ What is the `class` Attribute?

Think of a class as a **group name**.

For example, suppose we have three students belonging to the same class:

* Student 1 → Class A
* Student 2 → Class A
* Student 3 → Class A

Similarly, in HTML, multiple elements can belong to the same class.

### Syntax

```html
<tagname class="classname">
    Content
</tagname>
```

For example:

```html
<h2 class="city">London</h2>
```

Here:

* `class` → Attribute name
* `"city"` → Class name

---

# 2️⃣ Using `class` with CSS

The `class` attribute is commonly used to apply the **same CSS style** to multiple HTML elements.

### Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML Class Example</title>

    <style>
        .city {
            background-color: tomato;
            color: white;
            border: 2px solid black;
            margin: 20px;
            padding: 20px;
        }
    </style>

</head>

<body>

    <div class="city">
        <h2>London</h2>
        <p>London is the capital of England.</p>
    </div>

    <div class="city">
        <h2>Paris</h2>
        <p>Paris is the capital of France.</p>
    </div>

    <div class="city">
        <h2>Tokyo</h2>
        <p>Tokyo is the capital of Japan.</p>
    </div>

</body>

</html>
```

### 📝 Explanation

All three `<div>` elements have:

```html
class="city"
```

Therefore, all of them receive the same CSS styling.

In CSS, a class selector starts with a **dot (`.`)**:

```css
.city {
    background-color: tomato;
}
```

The dot (`.`) tells CSS that `city` is a **class name**.

---

# 3️⃣ Using `class` with the `<span>` Element

The `class` attribute can also be used with inline elements such as `<span>`.

### Example

```html
<!DOCTYPE html>
<html>

<head>

    <style>
        .note {
            font-size: 120%;
            color: red;
        }
    </style>

</head>

<body>

    <h1>My <span class="note">Important</span> Heading</h1>

    <p>
        This is some <span class="note">important</span> text.
    </p>

</body>

</html>
```

### 📝 Explanation

Both `<span>` elements have:

```html
class="note"
```

Therefore, both words will:

* Appear in **red color**
* Have a larger font size

---

# 💡 Important Point

The `class` attribute can be used with **almost any HTML element**.

For example:

```html
<h1 class="heading">Welcome</h1>

<p class="text">This is a paragraph.</p>

<div class="box">Hello</div>

<button class="btn">Click Me</button>
```

---

# 4️⃣ How to Create a Class in CSS

To create a class in CSS:

1. Write a **dot (`.`)**
2. Write the **class name**
3. Add CSS properties inside `{ }`

### Syntax

```css
.classname {
    property: value;
}
```

### Example

```css
.city {
    background-color: tomato;
    color: white;
    padding: 10px;
}
```

Now we can use this class in HTML:

```html
<h2 class="city">London</h2>

<h2 class="city">Paris</h2>

<h2 class="city">Tokyo</h2>
```

All three headings will receive the same style.

---

# 5️⃣ Complete Example

```html
<!DOCTYPE html>
<html>

<head>

    <title>Class Attribute Example</title>

    <style>

        .city {
            background-color: tomato;
            color: white;
            padding: 10px;
        }

    </style>

</head>

<body>

    <h2 class="city">London</h2>
    <p>London is the capital of England.</p>

    <h2 class="city">Paris</h2>
    <p>Paris is the capital of France.</p>

    <h2 class="city">Tokyo</h2>
    <p>Tokyo is the capital of Japan.</p>

</body>

</html>
```

---

# 6️⃣ Multiple Classes

An HTML element can belong to **more than one class**.

Separate multiple class names using a **space**.

### Syntax

```html
<tag class="class1 class2">
```

### Example

```html
<h2 class="city main">London</h2>

<h2 class="city">Paris</h2>

<h2 class="city">Tokyo</h2>
```

The first heading belongs to **two classes**:

* `city`
* `main`

Therefore, it will receive styles from **both classes**.

---

## Example with CSS

```html
<!DOCTYPE html>
<html>

<head>

    <style>

        .city {
            background-color: tomato;
            color: white;
            padding: 10px;
        }

        .main {
            text-align: center;
            border: 3px solid black;
        }

    </style>

</head>

<body>

    <h2 class="city main">London</h2>

    <h2 class="city">Paris</h2>

    <h2 class="city">Tokyo</h2>

</body>

</html>
```

### 📝 Explanation

The London heading gets styles from:

```css
.city
```

AND

```css
.main
```

---

# 7️⃣ Different HTML Elements Can Share the Same Class

Different types of HTML elements can use the same class.

### Example

```html
<h2 class="city">Paris</h2>

<p class="city">
    Paris is the capital of France.
</p>
```

Both the `<h2>` and `<p>` elements belong to the `city` class.

Therefore, both can receive the same CSS styling.

---

# 8️⃣ `class` Attribute is Case Sensitive

Class names are **case sensitive**.

For example:

```html
class="city"
```

and

```html
class="City"
```

are considered different class names.

### Example

```css
.city {
    color: red;
}

.City {
    color: blue;
}
```

These are two different classes.

⚠️ **Best Practice:** Use lowercase letters for class names.

```html
class="city"
class="main-container"
class="student-details"
```

---

# 9️⃣ Using the `class` Attribute in JavaScript

JavaScript can also access elements using their class name.

The method used is:

```javascript
document.getElementsByClassName()
```

### Example

The following example hides all elements having the class name `city`.

```html
<!DOCTYPE html>
<html>

<body>

    <div class="city">
        <h2>London</h2>
    </div>

    <div class="city">
        <h2>Paris</h2>
    </div>

    <div class="city">
        <h2>Tokyo</h2>
    </div>

    <button onclick="myFunction()">
        Hide Cities
    </button>

    <script>

        function myFunction() {

            var x = document.getElementsByClassName("city");

            for (var i = 0; i < x.length; i++) {
                x[i].style.display = "none";
            }

        }

    </script>

</body>

</html>
```

### 📝 What happens here?

When the user clicks the button:

```html
Hide Cities
```

JavaScript finds all elements with:

```html
class="city"
```

Then:

```javascript
x[i].style.display = "none";
```

hides each element.

---

# 🧠 Easy Way to Remember

### `class` = Group Name

Imagine you have:

```text
Class: Red Team

👨 Student 1
👩 Student 2
👨 Student 3
```

All students belong to the same group.

Similarly:

```html
<div class="city">London</div>

<div class="city">Paris</div>

<div class="city">Tokyo</div>
```

All three elements belong to the same group called:

```text
city
```

So, we can apply the same style to all of them at once.

---

# 📌 Difference Between HTML and CSS Class Syntax

### In HTML

We assign the class name:

```html
<h1 class="title">Welcome</h1>
```

### In CSS

We select the class using a dot (`.`):

```css
.title {
    color: blue;
}
```

### Remember

```text
HTML → class="title"

CSS  → .title
```

---

# 🎯 Chapter Summary

* The HTML `class` attribute specifies one or more class names for an element.
* Multiple HTML elements can share the same class.
* Classes are mainly used with **CSS** and **JavaScript**.
* In CSS, a class selector starts with a **dot (`.`)**.
* An element can have multiple classes.
* Different HTML elements can use the same class name.
* Class names are case sensitive.
* JavaScript can access elements using:

```javascript
document.getElementsByClassName()
```

---

# ❓ Practice Questions

### Question 1

What is the purpose of the HTML `class` attribute?

### Question 2

How do you select a class named `student` in CSS?

### Question 3

Can multiple HTML elements have the same class name?

### Question 4

Can one HTML element have multiple classes?

### Question 5

What is the difference between:

```html
class="city"
```

and:

```html
class="City"
```

### Question 6

Which JavaScript method is used to access elements by class name?

---

# 💻 Practice Task

Create a webpage containing three student cards:

* Student 1
* Student 2
* Student 3

Use the same class for all three cards and apply:

* Background color
* Border
* Padding
* Margin

### Expected Concept

```html
<div class="student">
    <h2>Student Name</h2>
    <p>Course Name</p>
</div>
```

🎯 **Goal:** Understand how one CSS class can style multiple HTML elements.

