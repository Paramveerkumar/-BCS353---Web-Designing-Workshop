# ✅ JavaScript Form Validation

> 🎯 **Learning Objectives**
> - Understand what form validation is and why it is needed.
> - Differentiate between client-side and server-side validation.
> - Use built-in HTML5 validation attributes.
> - Validate forms with JavaScript on the `submit` event.
> - Check for empty fields, length, email, phone, and password rules using regular expressions.
> - Show helpful error messages next to each field.
> - Validate in real time and build a complete registration form.

---

## 🌟 1. What is Form Validation?

**Form validation** is the process of checking that the data a user enters is **correct, complete, and in the right format** before it is accepted.

Think of a **security guard at a gate**. 💂

| Guard | Form validation |
|---|---|
| Checks your ID before letting you in | Checks the data before submitting the form |
| Turns you away if the ID is missing or fake | Shows an error if a field is empty or invalid |
| Tells you **why** you were stopped | Shows a clear error message |

### 🤔 Why Do We Validate?

- ✅ **Correct data:** an email should look like an email.
- 😊 **Better experience:** users get instant feedback instead of waiting for the server.
- 🛡️ **Safer systems:** reduces bad or harmful input.
- 🧹 **Cleaner database:** no empty names or "abc" phone numbers.

### 🧠 Remember This!

- Validation checks the **format and rules** of the data.
- Good error messages tell the user **what went wrong** and **how to fix it**.

---

## 🖥️ 2. Client-Side vs Server-Side Validation

| | 🖥️ Client-side | 🗄️ Server-side |
|---|---|---|
| **Where it runs** | In the user's browser | On the server |
| **Written in** | HTML and JavaScript | Backend language (Node.js, PHP, Python...) |
| **Speed** | Instant feedback | Needs a network trip |
| **Purpose** | Convenience for the user | **Real security** |
| **Can be bypassed?** | ✅ Yes, using DevTools or by sending requests directly | ❌ No |

> ⚠️ **Very important:** Client-side validation is for **user convenience only**. A user can switch it off with a few clicks. **Always validate again on the server.** This lesson covers client-side validation.

---

## 🏗️ 3. Built-in HTML5 Validation

HTML can validate forms **without any JavaScript**.

```html
<form>
    <input type="text" name="username"
           required minlength="3" maxlength="20"
           placeholder="Username (3-20 characters)">

    <input type="email" name="email" required placeholder="Email">

    <input type="number" name="age" min="18" max="60" placeholder="Age (18-60)">

    <input type="text" name="phone"
           pattern="[6-9][0-9]{9}"
           title="Enter a 10-digit mobile number starting with 6-9"
           placeholder="Mobile number">

    <button type="submit">Submit</button>
</form>
```

**Expected result:** If the user submits with an invalid field, the browser blocks the submission and shows its own message, such as "Please fill out this field."

### 📋 Common Validation Attributes

| Attribute | Purpose | Example |
|---|---|---|
| `required` | Field cannot be empty | `<input required>` |
| `minlength` / `maxlength` | Minimum / maximum text length | `minlength="3"` |
| `min` / `max` | Minimum / maximum number or date | `min="18"` |
| `type="email"` | Must look like an email address | `<input type="email">` |
| `type="url"` | Must be a valid URL | `<input type="url">` |
| `type="number"` | Only numbers allowed | `<input type="number">` |
| `pattern` | Must match a regular expression | `pattern="[0-9]{6}"` |
| `title` | Hint text shown with a pattern error | `title="6 digits"` |

### 🎨 Styling with CSS

```css
input:valid   { border: 2px solid green; }
input:invalid { border: 2px solid red; }
```

### 🆚 HTML5 vs JavaScript Validation

| HTML5 validation | JavaScript validation |
|---|---|
| Quick to write | Full control |
| Browser-controlled messages and style | Custom messages and design |
| Simple rules | Complex rules (password match, custom logic) |

💡 In real projects, use **both**: HTML attributes for the basics, and JavaScript for custom rules and nicer messages.

---

## 🧰 4. The Constraint Validation API

JavaScript can read the browser's built-in validation results.

```javascript
const email = document.querySelector("#email");

console.log(email.checkValidity());
console.log(email.validity.valueMissing);
console.log(email.validity.typeMismatch);
console.log(email.validationMessage);
```

### 🔍 Useful Members

| Member | Meaning |
|---|---|
| `input.checkValidity()` | Returns `true` if the field is valid |
| `form.checkValidity()` | Returns `true` if **all** fields are valid |
| `form.reportValidity()` | Checks the form and **shows** the browser's error messages |
| `input.validity.valueMissing` | `true` if a `required` field is empty |
| `input.validity.typeMismatch` | `true` if the value doesn't match the `type` (like email) |
| `input.validity.tooShort` / `tooLong` | `true` if the length rule fails |
| `input.validity.patternMismatch` | `true` if the `pattern` doesn't match |
| `input.validationMessage` | The browser's message text |
| `input.setCustomValidity("msg")` | Set your own error message (use `""` to clear it) |

```javascript
const password = document.querySelector("#password");

password.addEventListener("input", function () {
    if (password.value.length < 8) {
        password.setCustomValidity("Password must be at least 8 characters");
    } else {
        password.setCustomValidity("");   // empty string = valid
    }
});
```

> ⚠️ If you forget to clear the message with `setCustomValidity("")`, the field stays invalid forever.

---

## 💻 5. Your First JavaScript Validation

**📄 `index.html`**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Simple Validation</title>
</head>
<body>

    <form id="myForm" novalidate>
        <label for="username">Username:</label>
        <input type="text" id="username">
        <button type="submit">Submit</button>
    </form>

    <p id="message"></p>

    <script src="script.js" defer></script>

</body>
</html>
```

**📄 `script.js`**

```javascript
const form = document.querySelector("#myForm");
const message = document.querySelector("#message");

form.addEventListener("submit", function (event) {
    event.preventDefault();

    const username = document.querySelector("#username").value.trim();

    if (username === "") {
        message.textContent = "Username is required ❌";
    } else if (username.length < 3) {
        message.textContent = "Username must have at least 3 characters ❌";
    } else {
        message.textContent = "Welcome, " + username + "! ✅";
    }
});
```

### 🎯 What Happens?

| Input | Message |
|---|---|
| *(empty)* | Username is required ❌ |
| `Al` | Username must have at least 3 characters ❌ |
| `Aman` | Welcome, Aman! ✅ |

### 🔍 Understanding the Code

| Code | Purpose |
|---|---|
| `novalidate` | Turns off the browser's built-in messages so our own code handles validation |
| `submit` event | Fires when the form is submitted |
| `event.preventDefault()` | Stops the page from reloading |
| `.value` | Reads what the user typed |
| `.trim()` | Removes spaces at the start and end, so `"   "` counts as empty |

💡 **Try It Yourself:** Type only spaces and click Submit. Remove `.trim()` and see what changes.

---

## 🔢 6. Common Validation Checks

### 📭 Empty Check

```javascript
function isEmpty(value) {
    return value.trim() === "";
}

console.log(isEmpty(""));
console.log(isEmpty("   "));
console.log(isEmpty("Aman"));
```

### 📤 Output

```text
true
true
false
```

### 📏 Length Check

```javascript
const name = "Al";

if (name.length < 3) {
    console.log("Too short");
}
```

### 📤 Output

```text
Too short
```

### 🔢 Number Check

Input values are always **strings**, so convert them first.

```javascript
function validateAge(value) {
    const age = Number(value);

    if (value.trim() === "") return "Age is required";
    if (Number.isNaN(age)) return "Age must be a number";
    if (!Number.isInteger(age)) return "Age must be a whole number";
    if (age < 18 || age > 60) return "Age must be between 18 and 60";
    return "";
}

console.log(validateAge(""));
console.log(validateAge("abc"));
console.log(validateAge("25.5"));
console.log(validateAge("70"));
console.log(validateAge("30") === "");
```

### 📤 Output

```text
Age is required
Age must be a number
Age must be a whole number
Age must be between 18 and 60
true
```

> 💡 A common pattern is a function that returns an **error message**, or an **empty string** `""` when the value is valid.

---

## 🔣 7. Validating with Regular Expressions

A **regular expression (regex)** describes a text pattern. Use `.test()` to check if text matches it. It returns `true` or `false`.

### 🧩 Regex Building Blocks

| Symbol | Meaning | Example |
|---|---|---|
| `^` | Start of the text | `^A` starts with A |
| `$` | End of the text | `z$` ends with z |
| `\d` | Any digit (0-9) | `\d\d` two digits |
| `[A-Z]` | Any uppercase letter | |
| `[a-z]` | Any lowercase letter | |
| `[6-9]` | Any digit from 6 to 9 | |
| `+` | One or more | `\d+` one or more digits |
| `{n}` | Exactly n times | `\d{10}` ten digits |
| `[^\s@]` | Any character except a space or `@` | |
| `\.` | A literal dot | |

### 📧 Email

```javascript
const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;

console.log(emailPattern.test("aman@example.com"));
console.log(emailPattern.test("aman@example"));
console.log(emailPattern.test("aman example@mail.com"));
```

### 📤 Output

```text
true
false
false
```

### 📱 Indian Mobile Number (10 digits, starts with 6 to 9)

```javascript
const phonePattern = /^[6-9]\d{9}$/;

console.log(phonePattern.test("9876543210"));
console.log(phonePattern.test("1234567890"));
console.log(phonePattern.test("98765"));
```

### 📤 Output

```text
true
false
false
```

### 🔐 Password Rules

```javascript
function validatePassword(password) {
    if (password.length < 8) return "At least 8 characters required";
    if (!/[A-Z]/.test(password)) return "Add at least one uppercase letter";
    if (!/[a-z]/.test(password)) return "Add at least one lowercase letter";
    if (!/\d/.test(password)) return "Add at least one digit";
    return "";
}

console.log(validatePassword("abc"));
console.log(validatePassword("abcdefgh"));
console.log(validatePassword("Abcdefgh"));
console.log(validatePassword("Abcdefg1") === "");
```

### 📤 Output

```text
At least 8 characters required
Add at least one uppercase letter
Add at least one digit
true
```

### 🔤 Name (letters and spaces only)

```javascript
const namePattern = /^[A-Za-z ]+$/;

console.log(namePattern.test("Aman Sharma"));
console.log(namePattern.test("Aman123"));
```

### 📤 Output

```text
true
false
```

> ⚠️ **Don't overdo email validation.** A simple pattern catches obvious typos. The only real proof an email works is **sending a verification email**.

---

## 🧪 8. Validating Other Input Types

### ☑️ Checkbox (Terms and Conditions)

```javascript
const terms = document.querySelector("#terms");

if (!terms.checked) {
    console.log("You must accept the terms");
}
```

### 🔘 Radio Buttons

```javascript
const selected = document.querySelector('input[name="gender"]:checked');

if (selected === null) {
    console.log("Please select an option");
} else {
    console.log("Selected: " + selected.value);
}
```

### 🔽 Dropdown (Select)

```html
<select id="city">
    <option value="">-- Select city --</option>
    <option value="delhi">Delhi</option>
    <option value="mumbai">Mumbai</option>
</select>
```

```javascript
const city = document.querySelector("#city").value;

if (city === "") {
    console.log("Please select a city");
}
```

### 🔁 Confirm Password

```javascript
const password = "Abcdefg1";
const confirm = "Abcdefg2";

if (password !== confirm) {
    console.log("Passwords do not match");
}
```

### 📤 Output

```text
Passwords do not match
```

---

## 🏆 9. Mini Project: Registration Form ⭐

A complete form that validates every field, shows an error beside each one, and checks fields in real time.

**📄 `index.html`**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Registration Form</title>
    <style>
        body { font-family: Arial, sans-serif; max-width: 420px; margin: 30px auto; }
        .field { margin-bottom: 14px; }
        label { display: block; margin-bottom: 4px; font-weight: bold; }
        input[type="text"], input[type="password"] {
            width: 100%; padding: 8px; box-sizing: border-box;
        }
        input.invalid { border: 2px solid crimson; }
        .error { color: crimson; font-size: 0.85rem; display: block; min-height: 1.1em; }
        #successMsg { color: green; font-weight: bold; }
    </style>
</head>
<body>

    <h2>Create Account 📝</h2>

    <form id="regForm" novalidate>

        <div class="field">
            <label for="name">Full Name</label>
            <input type="text" id="name">
            <span class="error" id="nameError"></span>
        </div>

        <div class="field">
            <label for="email">Email</label>
            <input type="text" id="email">
            <span class="error" id="emailError"></span>
        </div>

        <div class="field">
            <label for="phone">Mobile Number</label>
            <input type="text" id="phone">
            <span class="error" id="phoneError"></span>
        </div>

        <div class="field">
            <label for="password">Password</label>
            <input type="password" id="password">
            <span class="error" id="passwordError"></span>
        </div>

        <div class="field">
            <label for="confirm">Confirm Password</label>
            <input type="password" id="confirm">
            <span class="error" id="confirmError"></span>
        </div>

        <div class="field">
            <label>
                <input type="checkbox" id="terms"> I accept the terms and conditions
            </label>
            <span class="error" id="termsError"></span>
        </div>

        <button type="submit">Register</button>
    </form>

    <p id="successMsg"></p>

    <script src="script.js" defer></script>

</body>
</html>
```

**📄 `script.js`**

```javascript
const form = document.querySelector("#regForm");
const successMsg = document.querySelector("#successMsg");

// ---------- helper: show or clear an error ----------
function setError(id, message) {
    document.querySelector("#" + id + "Error").textContent = message;
    document.querySelector("#" + id).classList.toggle("invalid", message !== "");
}

// ---------- validators: return an error message, or "" if valid ----------
function validateName() {
    const value = document.querySelector("#name").value.trim();
    if (value === "") return "Name is required";
    if (value.length < 3) return "Name must be at least 3 characters";
    if (!/^[A-Za-z ]+$/.test(value)) return "Name can contain only letters and spaces";
    return "";
}

function validateEmail() {
    const value = document.querySelector("#email").value.trim();
    if (value === "") return "Email is required";
    if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(value)) return "Enter a valid email address";
    return "";
}

function validatePhone() {
    const value = document.querySelector("#phone").value.trim();
    if (value === "") return "Mobile number is required";
    if (!/^[6-9]\d{9}$/.test(value)) return "Enter a valid 10-digit mobile number";
    return "";
}

function validatePassword() {
    const value = document.querySelector("#password").value;
    if (value === "") return "Password is required";
    if (value.length < 8) return "Password must be at least 8 characters";
    if (!/[A-Z]/.test(value)) return "Add at least one uppercase letter";
    if (!/[a-z]/.test(value)) return "Add at least one lowercase letter";
    if (!/\d/.test(value)) return "Add at least one digit";
    return "";
}

function validateConfirm() {
    const password = document.querySelector("#password").value;
    const confirm = document.querySelector("#confirm").value;
    if (confirm === "") return "Please confirm your password";
    if (confirm !== password) return "Passwords do not match";
    return "";
}

function validateTerms() {
    return document.querySelector("#terms").checked
        ? ""
        : "You must accept the terms and conditions";
}

// ---------- list of fields and their validators ----------
const fields = [
    { id: "name", validate: validateName },
    { id: "email", validate: validateEmail },
    { id: "phone", validate: validatePhone },
    { id: "password", validate: validatePassword },
    { id: "confirm", validate: validateConfirm },
    { id: "terms", validate: validateTerms }
];

// ---------- real-time validation ----------
fields.forEach(({ id, validate }) => {
    const element = document.querySelector("#" + id);
    const eventName = element.type === "checkbox" ? "change" : "blur";

    // check when the user leaves the field
    element.addEventListener(eventName, () => setError(id, validate()));

    // once a field is marked invalid, re-check while the user types
    element.addEventListener("input", () => {
        if (element.classList.contains("invalid")) {
            setError(id, validate());
        }
    });
});

// ---------- validate everything on submit ----------
form.addEventListener("submit", function (event) {
    event.preventDefault();

    let firstInvalid = null;

    fields.forEach(({ id, validate }) => {
        const message = validate();
        setError(id, message);

        if (message !== "" && firstInvalid === null) {
            firstInvalid = document.querySelector("#" + id);
        }
    });

    if (firstInvalid !== null) {
        successMsg.textContent = "";
        firstInvalid.focus();
        return;
    }

    successMsg.textContent = "Registration successful ✅";
    form.reset();
});
```

### 🎯 What Happens?

| User action | Result |
|---|---|
| Clicks **Register** with everything empty | Every field shows its "is required" error; focus moves to the first field |
| Types `Al` in Name and leaves the field | "Name must be at least 3 characters" |
| Types `aman@mail` in Email | "Enter a valid email address" |
| Types `12345` in Mobile | "Enter a valid 10-digit mobile number" |
| Password `abcdefgh` | "Add at least one uppercase letter" |
| Confirm password differs | "Passwords do not match" |
| Does not tick the checkbox | "You must accept the terms and conditions" |
| Fixes everything and submits | **Registration successful ✅** and the form is cleared |

### 🔍 Understanding the Design

- **One validator per field.** Each function returns an error message, or `""` when the value is valid.
- **The `fields` array** links each field to its validator, so adding a new field takes one line.
- **`setError()`** shows or clears the message and toggles the red border, so the display logic lives in one place.
- **Real-time validation:** errors appear when the user leaves a field (`blur`), and clear **while typing** as soon as the user fixes them.
- **On submit**, all fields are checked, so the user sees every problem at once, and focus jumps to the first invalid field.

> 💡 If the user changes **Password** after filling **Confirm Password**, the confirm field is only re-checked when the user visits it again. As an improvement, try also calling `setError("confirm", validateConfirm())` inside the password's `input` handler.

---

## ♿ 10. User-Friendly and Accessible Validation

- 🏷️ Always connect every input to a `<label>` using `for` and `id`.
- 💬 Write **specific** messages: "Password must be at least 8 characters" is better than "Invalid input".
- 🎯 Don't show errors **before** the user has had a chance to type. Wait for `blur` or `submit`.
- 🎨 Don't rely on **colour alone** (red border). Always include text too.
- ⌨️ Move focus to the first invalid field after a failed submit.
- 🔊 For screen readers, add `aria-live="polite"` to the area where error messages appear, so they are announced.
- 🧑‍🤝‍🧑 Don't force unnecessary rules. Overly strict validation (for example rejecting valid names or phone formats) frustrates real users.

```html
<span class="error" id="nameError" aria-live="polite"></span>
```

---

## ⚠️ 11. Common Mistakes

| ❌ Mistake | ✅ Correct |
|---|---|
| Relying **only** on client-side validation | Always validate again on the server |
| Forgetting `event.preventDefault()` | Call it so an invalid form is not submitted and the page doesn't reload |
| Not using `.trim()`, so `"   "` passes as a valid name | `value.trim()` before checking |
| Treating number input values as numbers | `.value` is a string; use `Number()` |
| Forgetting `setCustomValidity("")` to clear a custom message | Reset it when the field becomes valid |
| Showing only the first error and hiding the rest | Validate all fields and show every error |
| Using `==` to compare passwords | Use `===` |
| Never clearing old error messages | Clear (or update) the message on every check |
| Vague messages like "Error!" | Say what is wrong and how to fix it |
| A giant, unreadable regex for email | Use a simple pattern and send a verification email |
| Checking validity on the `click` of the submit button | Use the form's `submit` event so pressing Enter is also handled |
| Putting `novalidate` on the form but writing no JavaScript | `novalidate` turns off the browser checks, so you must validate yourself |

---

## 🧪 12. Practice Tasks

- [ ] 🟢 **Beginner:** Create a form with a name field that shows an alert if it is empty on submit.
- [ ] 🟢 **Beginner:** Add HTML5 attributes (`required`, `minlength`, `type="email"`) to a simple contact form and test it.
- [ ] 🟡 **Intermediate:** Validate that an age field accepts only whole numbers between 18 and 60, with a clear message for each failure.
- [ ] 🟡 **Intermediate:** Validate an Indian PIN code (exactly 6 digits, not starting with 0) using a regex.
- [ ] 🔵 **Practice:** Build a login form that shows error messages below the email and password fields instead of using `alert()`.
- [ ] 🔵 **Practice:** Add a live **password strength meter** that shows "Weak", "Medium", or "Strong" while the user types.
- [ ] 🔴 **Challenge:** Add a "Date of Birth" field to the registration form and reject users who are under 18.
- [ ] 🔴 **Challenge:** Add a "Show/Hide password" button and make the confirm password field re-validate whenever the password changes.

---

## 🎤 13. Viva Voce Questions and Answers

### 🟢 Basic Questions

**Q1. What is form validation?**

**Answer:** Form validation is the process of checking that user input is correct, complete, and in the required format before the form is accepted.

**Q2. Why is form validation needed?**

**Answer:** It ensures correct data, gives users quick feedback, reduces errors, and keeps bad data out of the system.

**Q3. What is the difference between client-side and server-side validation?**

**Answer:** Client-side validation runs in the browser using HTML and JavaScript and gives instant feedback. Server-side validation runs on the server and provides real security.

**Q4. Which HTML attributes can be used for validation?**

**Answer:** `required`, `minlength`, `maxlength`, `min`, `max`, `pattern`, and input types such as `email`, `url`, and `number`.

**Q5. Which event is used to validate a form on submission?**

**Answer:** The `submit` event of the form.

### 🟡 Intermediate Questions

**Q6. Is client-side validation enough? Why or why not?**

**Answer:** No. A user can bypass client-side validation with developer tools or by sending requests directly to the server, so the server must always validate the data again.

**Q7. What is the purpose of `event.preventDefault()` in form validation?**

**Answer:** It stops the browser's default form submission (and page reload), so we can validate first and submit only if the data is valid.

**Q8. What does the `novalidate` attribute do?**

**Answer:** It turns off the browser's built-in validation messages so that custom JavaScript validation can control the process.

**Q9. Why do we use `trim()` when validating text?**

**Answer:** It removes leading and trailing spaces, so a value containing only spaces is treated as empty.

**Q10. What is a regular expression and how do you test a value against it?**

**Answer:** A regular expression is a pattern that describes text. We test with `pattern.test(value)`, which returns `true` if the value matches.

**Q11. What is the difference between the `input` and `blur` events for validation?**

**Answer:** `input` fires on every change while typing, while `blur` fires when the field loses focus. `blur` avoids showing errors while the user is still typing.

**Q12. Why is `input.value` converted with `Number()` before validating numbers?**

**Answer:** The value of an input is always a string, so it must be converted before numeric comparisons or checks like `Number.isNaN()`.

### 🔵 Practical Questions

**Q13. Write a regular expression for a 10-digit mobile number starting with 6 to 9.**

**Answer:** `/^[6-9]\d{9}$/`

**Q14. How do you check that password and confirm password match?**

**Answer:** Compare the two values with strict equality, for example `if (password !== confirm) { /* show error */ }`.

**Q15. What does `setCustomValidity()` do and how do you clear it?**

**Answer:** It sets a custom error message on a field and marks it invalid. Calling `setCustomValidity("")` with an empty string clears the error and makes the field valid again.

**Q16. What is the difference between `checkValidity()` and `reportValidity()`?**

**Answer:** `checkValidity()` only returns `true` or `false`. `reportValidity()` also shows the browser's validation messages to the user.

**Q17. How would you validate that the user has checked a Terms checkbox?**

**Answer:** Check the `checked` property, for example `if (!terms.checked) { /* show error */ }`.

**Q18. Why is it better to show all errors at once on submit instead of stopping at the first one?**

**Answer:** The user can see and fix every problem in one go, instead of fixing one error, resubmitting, and discovering the next.

---

## 🏆 14. Key Takeaways

- ✅ Form validation checks that user input is correct, complete, and properly formatted.
- 🖥️ Client-side validation gives instant feedback, but **server-side validation is essential** for security.
- 🏗️ HTML5 attributes (`required`, `minlength`, `pattern`, `type="email"`) handle the basics with no JavaScript.
- 🛑 For custom validation, listen to the `submit` event and call `event.preventDefault()`.
- ✂️ Use `.trim()` on text, and convert number input with `Number()`.
- 🔣 Regular expressions with `.test()` check formats like email, phone, and password rules.
- 🧱 Write small validator functions that return an error message, or `""` when valid.
- 💬 Show clear, specific messages next to each field, and validate in real time.
- ♿ Keep forms accessible: use labels, text messages (not just colour), and focus the first error.

---

### 🚀 Keep Practising!

> 💡 **Remember:** Good validation is invisible when the user does everything right, and helpful when they make a mistake.

**Happy Coding! 💻✨**
