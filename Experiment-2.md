# 🌸 Experiment-2: Design Login Page Using HTML

<p align="center">
<img src="https://img.shields.io/badge/HTML-Login%20Page-orange?style=for-the-badge&logo=html5">
<img src="https://img.shields.io/badge/Experiment-02-blue?style=for-the-badge">
<img src="https://img.shields.io/badge/Level-Beginner-success?style=for-the-badge">
</p>

---

# 🎯 Aim

Design a simple **Login Page** using HTML that contains:

- 👤 Login ID
- 🔒 Password
- ✅ Submit Button
- 🔄 Reset Button

---

# 🛠️ Program

```html
<!DOCTYPE html>
<html>

<head>
    <title>Login Page</title>
</head>

<body bgcolor="pink">

<center>

<h1>LOGIN PAGE</h1>

<font face="Brush Script MT" size="7" color="purple">
<b>Enter Login Details</b>
</font>

<br><br>

<form method="post" action="right.html">

<table>

<tr>
<td><b>Login ID</b></td>
<td><input type="text"></td>
</tr>

<tr>
<td><b>Password</b></td>
<td><input type="password"></td>
</tr>

<tr align="center">
<td><input type="submit" value="Submit"></td>
<td><input type="reset" value="Reset"></td>
</tr>

</table>

</form>

</center>

</body>
</html>
```

---

# 📖 Code Explanation

## 1️⃣ `<!DOCTYPE html>`

👉 Defines the document as an **HTML5** webpage.

---

## 2️⃣ `<html>`

Contains the complete HTML document.

---

## 3️⃣ `<head>`

Stores page information.

Example:

```html
<title>Login Page</title>
```

Browser Tab:

```
Login Page
```

---

## 4️⃣ `<body bgcolor="pink">`

Displays all webpage content.

`bgcolor="pink"` makes the page background pink.

---

## 5️⃣ `<center>`

Places all page content in the center.

---

## 6️⃣ `<font>`

Changes text style.

```html
<font face="Brush Script MT" size="7" color="purple">
```

- Font = Brush Script MT
- Size = 7
- Color = Purple

---

## 7️⃣ `<form>`

Creates the login form.

```html
<form method="post" action="right.html">
```

| Attribute | Meaning |
|-----------|---------|
| method="post" | Sends form data |
| action="right.html" | Opens another page after Submit |

---

## 8️⃣ Login ID

```html
<input type="text">
```

Creates a textbox.

Example

```
Login ID
[____________]
```

---

## 9️⃣ Password

```html
<input type="password">
```

Creates a password field.

Example

```
Password
[••••••••]
```

---

## 🔟 Submit Button

```html
<input type="submit">
```

Submits the form.

---

## 1️⃣1️⃣ Reset Button

```html
<input type="reset">
```

Clears all entered values.

---

# ⚙️ Working

```
Start
   │
   ▼
Open Login Page
   │
   ▼
Enter Login ID
   │
   ▼
Enter Password
   │
   ▼
Click Submit
   │
   ▼
Open right.html
```

If Reset is clicked:

```
Reset
   │
   ▼
Clear Login ID
Clear Password
```

---

# 📷 Output

```
              LOGIN PAGE

       Enter Login Details

Login ID    [____________]

Password    [••••••••••]

      [ Submit ]  [ Reset ]
```

---

# 💡 Key Points

✅ HTML Form is created using `<form>`

✅ Login ID uses `type="text"`

✅ Password uses `type="password"`

✅ Submit button sends data

✅ Reset button clears the form

---

# ❓ Viva Questions

### Q1. Which tag is used to create a form?

**Answer:** `<form>`

---

### Q2. Which input type hides the password?

**Answer:** `password`

---

### Q3. What is the use of the Submit button?

**Answer:** It submits the form data.

---

### Q4. What is the use of the Reset button?

**Answer:** It clears all entered values.

---

### Q5. Which tag changes the page title?

**Answer:** `<title>`

---

# 🎯 Result

The **Login Page** was successfully designed using HTML with Login ID, Password, Submit, and Reset buttons.
