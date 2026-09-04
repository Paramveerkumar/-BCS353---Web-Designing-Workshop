# 🔤 HTML Headings

## 📚 Introduction

HTML headings are used to define **titles and headings** on a webpage.

HTML provides **six levels of headings**, from `<h1>` to `<h6>`.

* `<h1>` defines the **most important heading**.
* `<h6>` defines the **least important heading**.

---

# 📝 HTML Heading Tags

HTML provides the following heading tags:

```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
```

---

## 📊 Heading Hierarchy

| Tag    | Importance | Common Use              |
| ------ | ---------- | ----------------------- |
| `<h1>` | Highest    | Main page title         |
| `<h2>` | High       | Major section           |
| `<h3>` | Medium     | Sub-section             |
| `<h4>` | Lower      | Smaller section         |
| `<h5>` | Low        | Minor heading           |
| `<h6>` | Lowest     | Least important heading |

---

# 💻 Basic Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML Headings</title>
</head>

<body>

    <h1>Heading 1</h1>
    <h2>Heading 2</h2>
    <h3>Heading 3</h3>
    <h4>Heading 4</h4>
    <h5>Heading 5</h5>
    <h6>Heading 6</h6>

</body>

</html>
```

---

# 👀 Expected Output

The headings will generally appear in decreasing levels of importance:

```text
Heading 1  → Largest and most important
Heading 2
Heading 3
Heading 4
Heading 5
Heading 6  → Smallest and least important
```

> 💡 Browsers automatically apply default styling and spacing around heading elements.

---

# 🎯 Why Are Headings Important?

Headings help organize the content of a webpage.

They make a webpage:

* Easier to read
* Easier to understand
* Better organized
* Easier to navigate
* More meaningful for the structure of the document

Users often scan a webpage by looking at its headings first.

---

# 🏗️ Using Headings to Create Document Structure

HTML headings should follow a logical hierarchy.

For example:

```text
<h1> → Main Topic
│
├── <h2> → Main Section
│   │
│   ├── <h3> → Sub-section
│   └── <h3> → Sub-section
│
└── <h2> → Another Main Section
    │
    └── <h3> → Sub-section
```

---

# 📖 Example: College Website Structure

```html
<h1>ABC College of Engineering</h1>

<h2>About the College</h2>
<p>Information about the college.</p>

<h2>Departments</h2>

<h3>Computer Science and Engineering</h3>
<p>Information about the CSE department.</p>

<h3>Electronics and Communication Engineering</h3>
<p>Information about the ECE department.</p>

<h2>Contact Information</h2>
<p>College contact details.</p>
```

---

## 🔍 Understanding the Structure

```text
ABC College of Engineering
        │
        ├── About the College
        │
        ├── Departments
        │      │
        │      ├── Computer Science and Engineering
        │      │
        │      └── Electronics and Communication Engineering
        │
        └── Contact Information
```

This creates a clear hierarchy for the webpage.

---

# 🧠 Easy Way to Understand Heading Levels

Think about a book.

```text
Book Title
   │
   ├── Chapter
   │      │
   │      ├── Topic
   │      └── Topic
   │
   └── Chapter
          │
          └── Topic
```

Similarly, in HTML:

```text
<h1> → Book Title
<h2> → Chapter
<h3> → Topic
<h4> → Sub-topic
```

---

# ⭐ Recommended Use of Headings

A common structure is:

```html
<h1>Web Designing</h1>

<h2>HTML</h2>

<h3>HTML Elements</h3>
<h3>HTML Attributes</h3>
<h3>HTML Headings</h3>

<h2>CSS</h2>

<h3>CSS Colors</h3>
<h3>CSS Background</h3>

<h2>JavaScript</h2>

<h3>Variables</h3>
<h3>Functions</h3>
```

This structure clearly shows the relationship between topics.

---

# ⚠️ Do Not Use Headings Only to Make Text Big

Heading tags should be used to represent **headings and document structure**.

### ❌ Incorrect Idea

Using:

```html
<h1>This text should look big</h1>
```

only because you want large text.

### ✅ Better Approach

Use CSS when you want to change the appearance of normal text.

```html
<p style="font-size: 40px;">
    This text is large.
</p>
```

> 💡 **HTML defines the structure, while CSS controls the appearance.**

---

# 📏 Changing Heading Size

Every heading has a default size.

You can change the size using the CSS `font-size` property.

### Example

```html
<h1 style="font-size: 60px;">
    Welcome to My Website
</h1>
```

Another example:

```html
<h2 style="font-size: 30px;">
    Computer Science Department
</h2>
```

---

# 🎨 Styling Headings

You can also change other properties using the `style` attribute.

### Example

```html
<h1 style="color: blue; text-align: center;">
    Welcome Students
</h1>
```

This example changes:

* Text color
* Text alignment

---

# 💻 Complete Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>College Website</title>
</head>

<body>

    <h1 style="text-align: center;">
        ABC College of Engineering
    </h1>

    <h2>About Us</h2>

    <p>
        Welcome to our college website.
    </p>

    <h2>Departments</h2>

    <h3>Computer Science and Engineering</h3>

    <p>
        Information about the CSE department.
    </p>

    <h3>Electronics and Communication Engineering</h3>

    <p>
        Information about the ECE department.
    </p>

    <h2>Courses</h2>

    <h3>Undergraduate Courses</h3>

    <h3>Postgraduate Courses</h3>

    <h2>Contact Us</h2>

    <p>
        Contact the college for more information.
    </p>

</body>

</html>
```

---

# 📌 Important Points

### 1️⃣ `<h1>` is the Main Heading

```html
<h1>Online Book Store</h1>
```

Usually represents the main topic of the webpage.

---

### 2️⃣ `<h2>` Represents Major Sections

```html
<h2>Available Books</h2>
```

Used for important sections under the main topic.

---

### 3️⃣ `<h3>` Represents Sub-sections

```html
<h3>Computer Science Books</h3>
```

Used for smaller sections under an `<h2>`.

---

# 🧪 Practice Program

Create a webpage showing the structure of your college.

```html
<!DOCTYPE html>
<html>

<head>
    <title>My College</title>
</head>

<body>

    <h1>My College</h1>

    <h2>About College</h2>
    <p>This section contains information about the college.</p>

    <h2>Departments</h2>

    <h3>Computer Science Engineering</h3>
    <h3>Electronics Engineering</h3>
    <h3>Mechanical Engineering</h3>

    <h2>Facilities</h2>

    <h3>Library</h3>
    <h3>Computer Laboratory</h3>
    <h3>Sports Facility</h3>

</body>

</html>
```

---

# 🎯 Chapter Summary

After completing this topic, students should understand:

* ✅ HTML provides six heading levels.
* ✅ `<h1>` is the most important heading.
* ✅ `<h6>` is the least important heading.
* ✅ Headings help organize webpage content.
* ✅ Headings should follow a logical hierarchy.
* ✅ Use headings for structure, not only for making text large.
* ✅ CSS can be used to change heading size and appearance.

---

# 🧠 Quick Revision

```text
HTML HEADINGS
│
├── <h1> → Main Title
│
├── <h2> → Main Section
│
├── <h3> → Sub-section
│
├── <h4> → Smaller Section
│
├── <h5> → Minor Heading
│
└── <h6> → Least Important Heading
```

---

# ❓ Viva Questions

1. How many heading levels are available in HTML?
2. Which HTML tag defines the most important heading?
3. Which HTML tag defines the least important heading?
4. What is the difference between `<h1>` and `<h2>`?
5. Why are headings important in a webpage?
6. Can heading tags be used only to make text bigger?
7. How can you change the size of a heading?
8. What CSS property is used to change text size?
9. Give an example of a logical heading hierarchy.
10. What is the purpose of `<h3>` in a webpage?

---

# ⭐ Remember

> **`<h1>` to `<h6>` are used to create a structured hierarchy of headings in an HTML webpage.**

> 🧱 **HTML provides the structure, and CSS controls the appearance.**

