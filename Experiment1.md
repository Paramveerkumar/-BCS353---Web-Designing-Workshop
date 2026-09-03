# 🧪 Experiment 1: Online Book Store Website

## 🎯 Aim

Design the following static web pages required for an **Online Book Store Website**.

The website contains three main sections:

1. **Top Frame** – Displays the logo, website name, and navigation links.
2. **Left Frame** – Displays links to different engineering departments.
3. **Right Frame** – Displays the selected webpage or catalogue.

---

# 📂 Project Structure

```text
C
│
├── home.html
├── top.html
├── left.html
├── right.html
│
├── cse.html
├── ece.html
├── eee.html
├── mech.html
│
└── images/
    ├── logo1.png
    ├── cse.png
    └── Books.jpg
```

---

# 🏠 1. Home Page

The home page divides the browser window into different frames.

* **Top Frame** → Navigation and website information.
* **Left Frame** → Department links.
* **Right Frame** → Displays the selected page.

## 📄 File: `home.html`

```html
<!DOCTYPE html>
<html>

<head>
    <title>Online Book Store</title>
</head>

<frameset rows="40%,*">

    <!-- Top Frame -->
    <frame 
        src="top.html"
        name="topframe"
        noresize
        scrolling="no"
    >

    <frameset cols="15%,*">

        <!-- Left Navigation Frame -->
        <frame 
            src="left.html"
            name="leftframe"
            noresize
            scrolling="no"
        >

        <!-- Main Content Frame -->
        <frame 
            src="right.html"
            name="rightframe"
            noresize
            scrolling="auto"
        >

    </frameset>

</frameset>

</html>
```

---

## 🔍 Explanation of `home.html`

### Main Frameset

```html
<frameset rows="40%,*">
```

This divides the browser window into two rows:

* Top section → `40%`
* Remaining section → `*`

---

### Top Frame

```html
<frame src="top.html" name="topframe">
```

Loads `top.html` into the top section.

---

### Second Frameset

```html
<frameset cols="15%,*">
```

The remaining area is divided into two columns:

* Left column → `15%`
* Right column → Remaining space

---

### Right Frame

```html
<frame src="right.html" name="rightframe">
```

Initially, the `right.html` page is displayed here.

When students click department links such as **CSE**, **ECE**, **EEE**, or **MECH**, the corresponding pages are loaded into this frame.

---

# 🔝 2. Top Frame

The top frame contains:

* Website logo
* Website title
* Navigation links

## 📄 File: `top.html`

```html
<!DOCTYPE html>
<html>

<head>
    <title>Top Frame</title>
</head>

<body bgcolor="brown">

    <!-- Left Logo -->
    <img 
        src="images/logo1.png"
        width="125"
        height="115"
        align="left"
        alt="Website Logo"
    >

    <!-- Right Image -->
    <img 
        src="images/cse.png"
        width="125"
        height="115"
        align="right"
        alt="College Logo"
    >

    <center>

        <marquee 
            bgcolor="yellow"
            width="650"
            behavior="alternate"
        >
            <font face="Brush Script MT" size="8" color="green">
                <b><i>Online Book Store</i></b>
            </font>
        </marquee>

        <br>

        <font face="Brush Script MT" size="6" color="white">
            <b>Created & Maintained By College</b>
        </font>

    </center>

    <br>

    <!-- Navigation Links -->

    <table width="100%" cellspacing="10">

        <tr align="center">

            <td>
                <a href="home.html" target="_parent">
                    HOME
                </a>
            </td>

            <td>
                <a href="login.html" target="rightframe">
                    LOGIN
                </a>
            </td>

            <td>
                <a href="registration.html" target="rightframe">
                    REGISTER
                </a>
            </td>

            <td>
                <a href="catalogue.html" target="rightframe">
                    CATALOGUE
                </a>
            </td>

        </tr>

    </table>

</body>

</html>
```

---

## 🔍 Explanation

### Navigation Links

```html
<a href="login.html" target="rightframe">
    LOGIN
</a>
```

* `href` specifies which page should open.
* `target="rightframe"` specifies where the page should open.

Therefore:

```text
Click LOGIN
      ↓
login.html
      ↓
Loads inside rightframe
```

---

# 📚 3. Left Frame

The left frame contains links to different engineering departments.

## 📄 File: `left.html`

```html
<!DOCTYPE html>
<html>

<head>
    <title>Departments</title>
</head>

<body bgcolor="white">

    <br>

    <center>

        <a href="cse.html" target="rightframe">
            <font size="6">CSE</font>
        </a>

        <br><br>

        <a href="ece.html" target="rightframe">
            <font size="6">ECE</font>
        </a>

        <br><br>

        <a href="eee.html" target="rightframe">
            <font size="6">EEE</font>
        </a>

        <br><br>

        <a href="mech.html" target="rightframe">
            <font size="6">MECH</font>
        </a>

    </center>

</body>

</html>
```

---

## 🔍 Explanation

Each link uses:

```html
target="rightframe"
```

This means the selected page opens in the right frame.

### Navigation Flow

```text
CSE  ───→ cse.html
ECE  ───→ ece.html
EEE  ───→ eee.html
MECH ───→ mech.html

              ↓

        Displayed in
        RIGHT FRAME
```

---

# 🏪 4. Right Frame

Initially, the right frame displays information about the Online Book Store.

## 📄 File: `right.html`

```html
<!DOCTYPE html>
<html>

<head>
    <title>Online Book Store</title>
</head>

<body bgcolor="orange">

    <center>

        <img 
            src="images/Books.jpg"
            height="170"
            alt="Books"
        >

        <br>

        <font face="Brush Script MT" size="5" color="blue">

            <h1>
                Welcome to the Online Book Store!
            </h1>

        </font>

        <font face="Brush Script MT" size="5" color="red">

            <h2>
                "A Huge Collection of Engineering Books"
            </h2>

        </font>

    </center>

</body>

</html>
```

---

# 💻 5. CSE Book Page

This page displays books related to **Computer Science and Engineering**.

## 📄 File: `cse.html`

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSE Books</title>
</head>

<body bgcolor="cyan">

    <center>

        <h1>
            <font color="blue">
                Computer Science and Engineering
            </font>
        </h1>

    </center>

    <br>

    <table align="center">

        <tr>

            <td>Text Books</td>

            <td>

                <select>

                    <option selected>
                        Select the Book
                    </option>

                    <option>C and Data Structures</option>
                    <option>Advanced Data Structures</option>
                    <option>Java Programming</option>
                    <option>Oracle</option>
                    <option>MS SQL Server</option>
                    <option>MySQL</option>

                </select>

            </td>

        </tr>

        <tr>

            <td>Quantity</td>

            <td>
                <input type="text" id="q">
            </td>

        </tr>

        <tr>

            <td></td>

            <td>

                <form method="post" action="order.html">

                    <input type="submit" value="OK">

                </form>

            </td>

        </tr>

    </table>

    <center>

        <pre>
Cost of one book: ₹500
Shipping charge: ₹100
        </pre>

    </center>

</body>

</html>
```

---

## 🔍 Explanation

### `<select>`

The `<select>` element creates a dropdown list.

```html
<select>
    <option>Java Programming</option>
    <option>MySQL</option>
</select>
```

---

### `<input>`

```html
<input type="text">
```

Creates a text input field where the user can enter the quantity.

---

# 📡 6. ECE Book Page

## 📄 File: `ece.html`

```html
<!DOCTYPE html>
<html>

<head>
    <title>ECE Books</title>
</head>

<body bgcolor="plum">

    <h1>
        <font color="blue">
            Electronics and Communication Engineering
        </font>
    </h1>

    <h2>Available Books</h2>

    <ul>

        <li>Digital Circuits</li>

        <li>Signals and Systems</li>

        <li>Digital Communication</li>

    </ul>

</body>

</html>
```

---

## 🔍 Explanation

The `<ul>` element creates an **unordered list**.

```html
<ul>
    <li>Digital Circuits</li>
    <li>Signals and Systems</li>
</ul>
```

---

# ⚡ 7. EEE Book Page

## 📄 File: `eee.html`

```html
<!DOCTYPE html>
<html>

<head>
    <title>EEE Books</title>
</head>

<body bgcolor="plum">

    <h1>
        <font color="blue">
            Electrical and Electronics Engineering
        </font>
    </h1>

    <h2>Available Books</h2>

    <ul type="square">

        <li>Concepts in Electric Circuits</li>

        <li>Introduction to Electronic Engineering</li>

        <li>Electrical Power</li>

    </ul>

</body>

</html>
```

---

# ⚙️ 8. Mechanical Engineering Book Page

## 📄 File: `mech.html`

```html
<!DOCTYPE html>
<html>
<head>
    <title>EEE Books</title>
</head>
<body bgcolor="plum">

    <!-- Header Title -->
    <h1>
        <font color="blue">Electrical and Electronics Engineering</font>
    </h1>

    <!-- Subheading -->
    <h2>Available Books</h2>

    <!-- Book List -->
    <ul type="square">
        <li>Concepts in Electric Circuits</li>
        <li>Introduction to Electronic Engineering</li>
        <li>Electrical Power</li>
    </ul>

</body>
</html>
```

---

# 🧠 How the Complete Website Works

```text
                    ONLINE BOOK STORE
                           │
                           ▼
                      home.html
                           │
             ┌─────────────┴─────────────┐
             │                           │
             ▼                           ▼
          top.html                  Main Area
                                        │
                              ┌─────────┴─────────┐
                              │                   │
                              ▼                   ▼
                         left.html            right.html
                              │
              ┌───────────────┼───────────────┐
              │               │               │
              ▼               ▼               ▼
           cse.html        ece.html        eee.html
              │
              └──────→ Displayed in rightframe
```

---

# 🎯 Concepts Used in This Experiment

This experiment demonstrates:

* HTML Documents
* Frames
* Framesets
* Hyperlinks
* Images
* Tables
* Lists
* Forms
* Text Fields
* Dropdown Lists
* Navigation
* Target Frames

---

# 📝 Viva Questions

### 1. What is the purpose of HTML frames?

### 2. What is the difference between `<frameset>` and `<frame>`?

### 3. What is the purpose of the `src` attribute in a frame?

### 4. What is the purpose of the `target` attribute in hyperlinks?

### 5. What is the difference between an ordered list and an unordered list?

### 6. What is the purpose of the `<select>` element?

### 7. What is the purpose of the `<option>` element?

### 8. Which frame displays the selected department page?

### 9. What is the role of `home.html` in this experiment?

### 10. Which HTML concepts are demonstrated in this experiment?

---

# ✅ Result

A static **Online Book Store Website** was successfully designed using HTML frames, hyperlinks, images, tables, forms, lists, and navigation links.
