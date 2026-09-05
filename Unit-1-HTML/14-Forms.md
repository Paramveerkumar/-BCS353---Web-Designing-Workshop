# 📝 HTML Forms

## 📌 Introduction

An **HTML form** is used to collect information from users.

For example, a form can collect:

* 👤 Name
* 📧 Email address
* 🔒 Password
* 📱 Phone number
* 🎓 Course selection
* 🚻 Gender
* ☑️ User preferences

The information entered by the user can be sent to a **server** for processing.

---

# 🎯 Real-Life Example

You use forms every day!

Examples include:

* Login forms
* Registration forms
* College admission forms
* Contact forms
* Online shopping forms
* Google search forms

For example:

```text
First Name: [____________]

Last Name:  [____________]

            [ Submit ]
```

---

# 1️⃣ The `<form>` Element

The HTML `<form>` element is used to create a form.

### Basic Syntax

```html
<form>

    <!-- Form elements go here -->

</form>
```

The `<form>` element acts as a **container** for different form elements.

Some commonly used form elements are:

* `<input>`
* `<label>`
* `<select>`
* `<textarea>`
* `<button>`
* `<fieldset>`
* `<legend>`

---

# 2️⃣ The `<input>` Element

The `<input>` element is one of the most commonly used form elements.

The appearance of an `<input>` element depends on its `type` attribute.

## Common Input Types

| Input Type | Purpose                                 |
| ---------- | --------------------------------------- |
| `text`     | Single-line text input                  |
| `radio`    | Select one option from multiple choices |
| `checkbox` | Select zero, one, or multiple options   |
| `submit`   | Submit form data                        |
| `button`   | Creates a clickable button              |

### Examples

```html
<input type="text">
```

Creates a text field.

```html
<input type="radio">
```

Creates a radio button.

```html
<input type="checkbox">
```

Creates a checkbox.

```html
<input type="submit">
```

Creates a submit button.

---

# 3️⃣ Text Fields

The following input type:

```html
<input type="text">
```

creates a **single-line text input field**.

## Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>Text Field Example</title>
</head>

<body>

    <form>

        <label for="fname">First Name:</label><br>

        <input type="text" id="fname" name="fname"><br><br>

        <label for="lname">Last Name:</label><br>

        <input type="text" id="lname" name="lname">

    </form>

</body>

</html>
```

### 📝 Output

```text
First Name:
[____________]

Last Name:
[____________]
```

---

# 4️⃣ The `<label>` Element

The `<label>` element defines a **label or description** for an input element.

### Example

```html
<label for="fname">First Name:</label>

<input type="text" id="fname" name="fname">
```

---

## 🔗 Connection Between `<label>` and `<input>`

The value of the `for` attribute should match the `id` of the input element.

```html
<label for="fname">First Name:</label>

<input type="text" id="fname">
```

### Remember

```text
label → for="fname"

input → id="fname"
```

Both values should be the same.

This connects the label with its input field.

---

# 🧠 Easy Way to Remember

Think of a label as the **question** and the input as the **answer box**.

```text
First Name: [____________]
     ↑              ↑
   Label          Input
```

---

# 5️⃣ Radio Buttons

The following:

```html
<input type="radio">
```

creates a **radio button**.

Radio buttons allow the user to select **only ONE option** from a group.

## Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>Radio Button Example</title>
</head>

<body>

    <p>Choose your favorite Web Language:</p>

    <form>

        <input type="radio"
               id="html"
               name="fav_language"
               value="HTML">

        <label for="html">HTML</label>

        <br>

        <input type="radio"
               id="css"
               name="fav_language"
               value="CSS">

        <label for="css">CSS</label>

        <br>

        <input type="radio"
               id="javascript"
               name="fav_language"
               value="JavaScript">

        <label for="javascript">JavaScript</label>

    </form>

</body>

</html>
```

### 📝 Important Point

All radio buttons have the same:

```html
name="fav_language"
```

Therefore, the user can select **only one option**.

### Example

```text
Choose your favorite Web Language:

◉ HTML

○ CSS

○ JavaScript
```

---

# ⚠️ Important: Why is `name` Important for Radio Buttons?

To create a group of radio buttons, they must have the same `name`.

✅ Correct:

```html
<input type="radio" name="gender"> Male

<input type="radio" name="gender"> Female
```

Only one option can be selected.

---

# 6️⃣ Checkboxes

The following:

```html
<input type="checkbox">
```

creates a **checkbox**.

Checkboxes allow users to select **zero, one, or multiple options**.

## Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>Checkbox Example</title>
</head>

<body>

    <form>

        <input type="checkbox"
               id="vehicle1"
               name="vehicle1"
               value="Bike">

        <label for="vehicle1">
            I have a Bike
        </label>

        <br>

        <input type="checkbox"
               id="vehicle2"
               name="vehicle2"
               value="Car">

        <label for="vehicle2">
            I have a Car
        </label>

        <br>

        <input type="checkbox"
               id="vehicle3"
               name="vehicle3"
               value="Boat">

        <label for="vehicle3">
            I have a Boat
        </label>

    </form>

</body>

</html>
```

### 📝 Output

```text
☐ I have a Bike

☐ I have a Car

☐ I have a Boat
```

The user can select:

* None
* One option
* Multiple options

---

# 🆚 Radio Button vs Checkbox

| Feature   | Radio Button | Checkbox           |
| --------- | ------------ | ------------------ |
| Selection | One option   | Multiple options   |
| Used for  | Choose one   | Choose one or more |
| Example   | Gender       | Hobbies            |

### Example

### Radio Button

```text
Choose Gender:

○ Male

○ Female
```

Select only **one**.

### Checkbox

```text
Select Hobbies:

☐ Cricket

☐ Music

☐ Reading
```

Select **multiple options**.

---

# 7️⃣ The Submit Button

The following:

```html
<input type="submit">
```

creates a **Submit button**.

The Submit button sends the form data for processing.

## Example

```html
<form>

    <label for="fname">First Name:</label><br>

    <input type="text"
           id="fname"
           name="fname">

    <br><br>

    <label for="lname">Last Name:</label><br>

    <input type="text"
           id="lname"
           name="lname">

    <br><br>

    <input type="submit" value="Submit">

</form>
```

The text displayed on the button is controlled using:

```html
value="Submit"
```

---

# 8️⃣ Complete Student Registration Form

Let's combine what we have learned.

```html
<!DOCTYPE html>
<html>

<head>
    <title>Student Registration Form</title>
</head>

<body>

    <h1>Student Registration Form</h1>

    <form>

        <!-- Name -->

        <label for="name">Student Name:</label><br>

        <input type="text"
               id="name"
               name="name">

        <br><br>


        <!-- Email -->

        <label for="email">Email:</label><br>

        <input type="text"
               id="email"
               name="email">

        <br><br>


        <!-- Gender -->

        <p>Select Gender:</p>

        <input type="radio"
               id="male"
               name="gender"
               value="Male">

        <label for="male">Male</label>


        <input type="radio"
               id="female"
               name="gender"
               value="Female">

        <label for="female">Female</label>

        <br><br>


        <!-- Hobbies -->

        <p>Select Hobbies:</p>

        <input type="checkbox"
               id="sports"
               name="sports"
               value="Sports">

        <label for="sports">Sports</label>


        <input type="checkbox"
               id="music"
               name="music"
               value="Music">

        <label for="music">Music</label>


        <input type="checkbox"
               id="reading"
               name="reading"
               value="Reading">

        <label for="reading">Reading</label>

        <br><br>


        <!-- Submit -->

        <input type="submit" value="Register">

    </form>

</body>

</html>
```

---

# 9️⃣ The `name` Attribute

The `name` attribute is very important when submitting form data.

### Example

```html
<input type="text"
       id="fname"
       name="fname">
```

When the form is submitted, the data is usually sent using the `name`.

For example:

```text
fname = Rahul
```

---

## ⚠️ Important Rule

If an input does not have a `name` attribute, its value is generally **not included in the submitted form data**.

❌ Example:

```html
<input type="text"
       id="fname"
       value="Rahul">
```

There is no `name` attribute.

✅ Correct:

```html
<input type="text"
       id="fname"
       name="fname"
       value="Rahul">
```

---

# 🔟 The `action` Attribute

The `action` attribute specifies **where the form data should be sent** after the user submits the form.

### Example

```html
<form action="/action_page.php">
```

When the user clicks Submit, the form data is sent to:

```text
/action_page.php
```

That server-side program processes the submitted data.

---

## Example

```html
<form action="/action_page.php">

    <label for="fname">First Name:</label><br>

    <input type="text"
           id="fname"
           name="fname"
           value="John">

    <br>

    <label for="lname">Last Name:</label><br>

    <input type="text"
           id="lname"
           name="lname"
           value="Doe">

    <br><br>

    <input type="submit" value="Submit">

</form>
```

---

# 1️⃣1️⃣ The `target` Attribute

The `target` attribute specifies **where the response will be displayed** after submitting the form.

### Example

```html
<form action="/action_page.php" target="_blank">
```

This opens the response in a **new browser tab**.

## Common Values

| Value       | Description                               |
| ----------- | ----------------------------------------- |
| `_blank`    | Opens response in a new tab/window        |
| `_self`     | Opens response in the current window      |
| `_parent`   | Opens response in the parent frame        |
| `_top`      | Opens response in the full window         |
| `framename` | Opens response in a named frame or iframe |

### Default Value

The default value is:

```text
_self
```

This means the response opens in the **current window**.

---

# 1️⃣2️⃣ The `method` Attribute

The `method` attribute specifies **how the form data is sent to the server**.

There are two commonly used methods:

* `GET`
* `POST`

---

## GET Method

```html
<form action="/action_page.php" method="get">
```

With GET, form data is added to the URL.

### Example

```text
website.com/page?name=Rahul&course=BTech
```

### Characteristics of GET

* Form data appears in the URL.
* Useful for search forms and non-sensitive data.
* URLs can be bookmarked or shared.
* ❌ Do not use GET for passwords or sensitive information.

---

## POST Method

```html
<form action="/action_page.php" method="post">
```

With POST, form data is sent in the **HTTP request body**.

### Characteristics of POST

* Form data is not displayed in the URL.
* Commonly used for registration and login forms.
* Better suited for sending larger amounts of data.

⚠️ **Important:** `POST` does not automatically make data secure. Sensitive data should also be protected using HTTPS and proper server-side security.

---

# 🆚 GET vs POST

| Feature        | GET               | POST                        |
| -------------- | ----------------- | --------------------------- |
| Data location  | URL               | Request body                |
| Visible in URL | ✅ Yes             | ❌ No                        |
| Good for       | Search/query data | Form submissions            |
| Bookmarkable   | ✅ Yes             | Usually no                  |
| Sensitive data | ❌ Avoid           | More appropriate with HTTPS |

---

# 1️⃣3️⃣ HTML Form Elements

The `<form>` element can contain different form elements.

Common form elements include:

```html
<input>

<label>

<select>

<textarea>

<button>

<fieldset>

<legend>

<datalist>

<output>
```

Let's understand some important ones.

---

# 1️⃣4️⃣ The `<select>` Element

The `<select>` element creates a **drop-down list**.

### Example

```html
<label for="cars">Choose a Car:</label>

<select id="cars" name="cars">

    <option value="volvo">Volvo</option>

    <option value="saab">Saab</option>

    <option value="fiat">Fiat</option>

    <option value="audi">Audi</option>

</select>
```

### 📝 Output

```text
Choose a Car:

[ Volvo ▼ ]
```

---

# 1️⃣5️⃣ The `<option>` Element

The `<option>` element defines an item inside a `<select>` list.

### Example

```html
<select>

    <option>HTML</option>

    <option>CSS</option>

    <option>JavaScript</option>

</select>
```

---

# 1️⃣6️⃣ Pre-selected Option

To select an option by default, use the `selected` attribute.

### Example

```html
<option value="fiat" selected>
    Fiat
</option>
```

Now `Fiat` will be selected automatically.

---

# 1️⃣7️⃣ Visible Options Using `size`

The `size` attribute specifies how many options are visible at one time.

### Example

```html
<label for="cars">Choose a Car:</label>

<select id="cars" name="cars" size="3">

    <option value="volvo">Volvo</option>

    <option value="saab">Saab</option>

    <option value="fiat">Fiat</option>

    <option value="audi">Audi</option>

</select>
```

Here, approximately **3 options** are visible at a time.

---

# 1️⃣8️⃣ Allow Multiple Selections

Use the `multiple` attribute to allow users to select more than one option.

### Example

```html
<label for="cars">Choose Cars:</label>

<select id="cars"
        name="cars"
        size="4"
        multiple>

    <option value="volvo">Volvo</option>

    <option value="saab">Saab</option>

    <option value="fiat">Fiat</option>

    <option value="audi">Audi</option>

</select>
```

The user can select multiple options.

💡 On many computers, users can select multiple options using:

* `Ctrl` + Click on Windows/Linux
* `Command` + Click on macOS

---

# 🧠 Important Form Attributes

| Attribute | Purpose                             |
| --------- | ----------------------------------- |
| `action`  | Specifies where form data is sent   |
| `method`  | Specifies how form data is sent     |
| `target`  | Specifies where the response opens  |
| `id`      | Uniquely identifies an element      |
| `name`    | Name used when submitting form data |
| `value`   | Specifies the value of an input     |

---

# 🎯 Complete Example: Student Admission Form

```html
<!DOCTYPE html>
<html>

<head>
    <title>Student Admission Form</title>
</head>

<body>

    <h1>Student Admission Form</h1>

    <form action="/submit.php" method="post">

        <!-- Student Name -->

        <label for="name">Student Name:</label><br>

        <input type="text"
               id="name"
               name="student_name">

        <br><br>


        <!-- Email -->

        <label for="email">Email:</label><br>

        <input type="text"
               id="email"
               name="email">

        <br><br>


        <!-- Course -->

        <label for="course">Choose Course:</label><br>

        <select id="course" name="course">

            <option value="btech">B.Tech</option>

            <option value="mtech">M.Tech</option>

            <option value="phd">Ph.D.</option>

        </select>

        <br><br>


        <!-- Gender -->

        <p>Select Gender:</p>

        <input type="radio"
               id="male"
               name="gender"
               value="male">

        <label for="male">Male</label>


        <input type="radio"
               id="female"
               name="gender"
               value="female">

        <label for="female">Female</label>

        <br><br>


        <!-- Skills -->

        <p>Select Skills:</p>

        <input type="checkbox"
               id="html"
               name="html"
               value="HTML">

        <label for="html">HTML</label>


        <input type="checkbox"
               id="css"
               name="css"
               value="CSS">

        <label for="css">CSS</label>


        <input type="checkbox"
               id="javascript"
               name="javascript"
               value="JavaScript">

        <label for="javascript">JavaScript</label>

        <br><br>


        <!-- Submit Button -->

        <input type="submit" value="Submit Application">

    </form>

</body>

</html>
```

---

# 🧠 Easy Concept Map

```text
                    HTML FORM
                        │
        ┌───────────────┼───────────────┐
        │               │               │
      INPUT           SELECT          BUTTON
        │               │
   ┌────┼────┐          │
   │    │    │       OPTIONS
 Text Radio Checkbox
   │    │    │
   │    │    │
 User  One  Multiple
 Input Choice Choices
```

---

# 🎯 Chapter Summary

* The `<form>` element is used to collect user input.
* `<input>` is one of the most commonly used form elements.
* `<input type="text">` creates a text field.
* `<input type="radio">` allows one choice from a group.
* `<input type="checkbox">` allows multiple choices.
* `<input type="submit">` submits the form.
* `<label>` provides a description for form elements.
* The `for` attribute of `<label>` should match the `id` of the related input.
* The `name` attribute is important for submitting form data.
* The `action` attribute specifies where form data is sent.
* The `method` attribute specifies how form data is sent.
* GET sends data in the URL.
* POST sends data in the request body.
* `<select>` creates a drop-down list.
* `<option>` defines items inside a drop-down list.

---

# ❓ Practice Questions

### Question 1

What is the purpose of the `<form>` element?

### Question 2

Which HTML element is commonly used to collect user input?

### Question 3

What is the difference between a radio button and a checkbox?

### Question 4

Why is the `name` attribute important?

### Question 5

What is the purpose of the `action` attribute?

### Question 6

What is the difference between GET and POST?

### Question 7

Which element is used to create a drop-down list?

### Question 8

Which element defines an option inside a `<select>` element?

### Question 9

How do you connect a `<label>` with an `<input>` element?

---

# 💻 Practice Task

Create a **Student Registration Form** containing:

* Student Name
* Email Address
* Password
* Gender (Radio Buttons)
* Hobbies (Checkboxes)
* Course (Drop-down List)
* Submit Button

🎯 **Goal:** Practice using different HTML form elements together.

