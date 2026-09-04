# 💬 HTML Comments

## 📚 Introduction

HTML comments are used to add **notes, explanations, reminders, or documentation** inside HTML source code.

Comments are written for developers and students to understand the code better.

> 💡 **HTML comments are not displayed in the browser.**

They are visible only when someone looks at the HTML source code.

---

# 📝 HTML Comment Syntax

HTML comments are written using:

```html
<!-- Write your comment here -->
```

### Structure

```text
<!--  Comment starts here  -->
 ↑                       ↑
Start                  End
```

Notice:

* The opening part is `<!--`
* The closing part is `-->`
* The exclamation mark (`!`) appears only at the beginning.

---

# 💻 Basic Example

```html
<!-- This is a comment -->

<p>This is a paragraph.</p>
```

### Browser Output

```text
This is a paragraph.
```

The comment:

```html
<!-- This is a comment -->
```

will **not appear in the browser**.

---

# 🎯 Why Do We Use Comments?

Comments are useful for:

* 📝 Explaining code
* 🔔 Adding reminders
* 📚 Documenting sections of a webpage
* 🛠️ Debugging HTML code
* 🚫 Temporarily hiding code

---

# 📝 Adding Comments to HTML Code

Comments can explain different parts of a program.

### Example

```html
<!-- Main heading of the webpage -->

<h1>Online Book Store</h1>

<!-- Introduction section -->

<p>
    Welcome to our online book store.
</p>

<!-- Navigation section -->

<a href="catalogue.html">
    View Books
</a>
```

These comments help students and developers understand the purpose of each section.

---

# 🏗️ Example: Comments in a Complete HTML Program

```html
<!DOCTYPE html>
<html>

<head>

    <!-- Title displayed in the browser tab -->

    <title>HTML Comments</title>

</head>

<body>

    <!-- Main heading -->

    <h1>Welcome Students</h1>

    <!-- Introduction paragraph -->

    <p>
        This webpage demonstrates HTML comments.
    </p>

</body>

</html>
```

---

# 🙈 Hiding Content Using Comments

Comments can be used to temporarily hide HTML content.

### Example

```html
<p>This paragraph will be displayed.</p>

<!--
<p>This paragraph will not be displayed.</p>
-->

<p>This paragraph will also be displayed.</p>
```

### Browser Output

```text
This paragraph will be displayed.

This paragraph will also be displayed.
```

The commented paragraph is ignored by the browser when rendering the page.

---

# 📦 Hiding Multiple Lines

Everything between:

```html
<!--
```

and:

```html
-->
```

is treated as a comment.

### Example

```html
<p>Welcome to our website.</p>

<!--

<h2>Special Offers</h2>

<p>
    This section is temporarily hidden.
</p>

<img src="offer.jpg" alt="Special Offer">

-->

<p>Thank you for visiting.</p>
```

The hidden section will not appear on the webpage.

---

# 🔧 Using Comments for Debugging

Comments can help during debugging.

Suppose a webpage contains several sections and you want to find which section is causing a problem.

You can temporarily comment out one section.

### Example

```html
<h1>My Website</h1>

<!--
<div>
    <h2>Problem Section</h2>
    <p>This section is temporarily disabled.</p>
</div>
-->

<p>This content is still displayed.</p>
```

This technique helps developers test different parts of their code.

---

# ✂️ Hiding Inline Content

Comments can also hide content inside a line or paragraph.

### Example

```html
<p>
    HTML is
    <!-- a very useful -->
    markup language.
</p>
```

### Browser Output

```text
HTML is markup language.
```

The text inside the comment is not displayed.

---

# 💡 Another Inline Example

```html
<p>
    Welcome to the
    <!-- Online -->
    Book Store.
</p>
```

### Output

```text
Welcome to the Book Store.
```

---

# 🧠 Important Concept

Consider this code:

```html
<!-- This is hidden -->
```

The browser does not display the comment.

But remember:

> ⚠️ Comments are part of the HTML source code and can be viewed by someone inspecting the page source.

Therefore, **never use HTML comments to store passwords, private information, or sensitive data**.

---

# 📊 HTML Comment Examples

| Purpose             | Example                           |
| ------------------- | --------------------------------- |
| Explain code        | `<!-- Main heading -->`           |
| Add reminder        | `<!-- Add image later -->`        |
| Hide one line       | `<!-- <p>Hidden</p> -->`          |
| Hide multiple lines | `<!-- Multiple lines -->`         |
| Debug code          | Temporarily comment out a section |

---

# 💻 Complete Practice Program

```html
<!DOCTYPE html>
<html>

<head>

    <!-- Browser tab title -->

    <title>HTML Comments Practice</title>

</head>

<body>

    <!-- Main heading -->

    <h1>Web Designing Workshop</h1>

    <!-- Introduction -->

    <p>
        Welcome to the Web Designing Workshop.
    </p>

    <!-- This paragraph is temporarily hidden -->

    <!--
    <p>
        This paragraph will not appear in the browser.
    </p>
    -->

    <!-- Course information -->

    <h2>Topics</h2>

    <p>
        HTML
        <!-- CSS -->
        and JavaScript
    </p>

</body>

</html>
```

---

# 🎯 Important Points

### 1️⃣ Comments Are Not Displayed

```html
<!-- This is a comment -->
```

This will not appear on the webpage.

---

### 2️⃣ Comments Can Explain Code

```html
<!-- Navigation Bar -->

<nav>
    Home | About | Contact
</nav>
```

---

### 3️⃣ Comments Can Hide Code

```html
<!--
<p>This content is hidden.</p>
-->
```

---

### 4️⃣ Comments Can Be Used for Debugging

You can temporarily disable sections of HTML code to test your webpage.

---

# 🧪 Practice Task

Create a webpage containing:

1. A main heading
2. A paragraph
3. A comment explaining the heading
4. A hidden paragraph
5. A comment reminding you to add more content later

### Expected Structure

```html
<!-- Main Heading -->

<h1>My College Website</h1>

<p>Welcome to our college website.</p>

<!--
<p>This paragraph is temporarily hidden.</p>
-->

<!-- Add more information about departments later -->
```

---

# 🎯 Chapter Summary

After completing this topic, students should understand:

* ✅ HTML comments are used to document source code.
* ✅ Comments are not displayed in the browser.
* ✅ Comments begin with `<!--`.
* ✅ Comments end with `-->`.
* ✅ Comments can explain HTML code.
* ✅ Comments can temporarily hide content.
* ✅ Comments can help during debugging.
* ⚠️ Comments should not contain sensitive information.

---

# 🧠 Quick Revision

```text
HTML COMMENTS
      │
      ▼

<!-- Your Comment -->

      │
      ├── Explain Code
      │
      ├── Add Notes
      │
      ├── Hide Content
      │
      └── Help Debug Code
```

---

# ❓ Viva Questions

1. What is an HTML comment?
2. Are HTML comments displayed in the browser?
3. What is the syntax of an HTML comment?
4. Why are comments used in HTML?
5. Can comments be used to hide HTML code?
6. Can multiple lines be included inside a comment?
7. How can comments help during debugging?
8. Can comments be used inside a paragraph?
9. Why should sensitive information not be stored in comments?
10. What is the difference between visible HTML content and an HTML comment?

---

# ⭐ Remember

> **HTML comments help developers understand and document their code.**

> **Comments are not displayed on the webpage.**

```html
<!-- This is an HTML Comment -->
```

