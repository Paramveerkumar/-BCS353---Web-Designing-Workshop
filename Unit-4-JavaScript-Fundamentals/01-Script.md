# 🚀 01. JavaScript Script — Getting Started

> 🎯 **Learning Objectives**
> - Understand JavaScript and its role in web development.
> - Write and execute a JavaScript program.
> - Differentiate between inline, internal, and external JavaScript.
> - Understand comments and case sensitivity.
> - Create a simple interactive webpage.

---

## 🌟 1. What is JavaScript?

JavaScript (JS) is a programming language used to make websites **interactive and dynamic**.

Imagine you are building a college website. 🏫

| Technology | Role | Example |
|---|---|---|
| 🏗️ HTML | Structure | Creates a button |
| 🎨 CSS | Styling | Changes the button's colour |
| ⚡ JavaScript | Behaviour | Performs an action when clicked |

### 🧠 Remember This!

- 🏗️ **HTML** = What is on the page?
- 🎨 **CSS** = How does it look?
- ⚡ **JavaScript** = What happens when we interact with it?

---

## 💻 2. Your First JavaScript Program

Let's write our first program!

```javascript
console.log("Hello, Students!");
console.log("Welcome to JavaScript 🚀");
```

### 📤 Output

```text
Hello, Students!
Welcome to JavaScript 🚀
```

### 🔍 Explanation

- `console` provides access to the browser's developer console.
- `log()` displays information in the console.
- `"Hello, Students!"` is a string (text).
- `;` marks the end of a statement in this example.

💡 **Try It Yourself:** Change `"Hello, Students!"` to your name and run the program again.

---

## 📝 3. Three Ways to Write JavaScript

### 🟢 Method 1: Inline JavaScript

JavaScript is written directly inside an HTML element using an event attribute.

```html
<button onclick="alert('Hello Students!')">
    Click Me 🎯
</button>
```

**Expected result:** When the user clicks the button, a popup appears.

🔍 **Explanation:**
- `<button>` creates a button.
- `onclick` specifies what happens when the button is clicked.
- `alert()` displays a popup message.

> 💡 Inline JavaScript is useful for demonstrations. For larger projects, prefer using `addEventListener()`.

### 🟡 Method 2: Internal JavaScript

JavaScript is written inside the HTML `<script>` element.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Internal JavaScript</title>
</head>
<body>

    <h1>Welcome to JavaScript 🎉</h1>

    <script>
        console.log("Hello Students!");
        console.log("Let's learn JavaScript.");
    </script>

</body>
</html>
```

**📤 Output in the browser console:**

```text
Hello Students!
Let's learn JavaScript.
```

**💡 Key Point:** The `<script>` element tells the browser where JavaScript code is written.

### 🔵 Method 3: External JavaScript ⭐

JavaScript is stored in a separate `.js` file. This keeps HTML and JavaScript organised.

**📁 Project Structure**

```text
📂 MyJavaScriptProject
 ├── 📄 index.html
 └── 📄 script.js
```

**Step 1️⃣ — Create `index.html`**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>External JavaScript</title>
</head>
<body>

    <h1 id="heading">Welcome! 👋</h1>
    <button id="myButton">Click Me 🚀</button>

    <script src="script.js" defer></script>

</body>
</html>
```

**Step 2️⃣ — Create `script.js`**

```javascript
console.log("JavaScript Connected Successfully! ✅");

const button = document.querySelector("#myButton");
const heading = document.querySelector("#heading");

button.addEventListener("click", function () {
    heading.textContent = "JavaScript is Amazing! 🎉";
});
```

### 🎯 What Happens?

1. Open `index.html` in your browser.
2. The heading displays **Welcome! 👋**
3. Click the **Click Me 🚀** button.
4. The heading changes to **JavaScript is Amazing! 🎉**

### 🔍 Understanding the Code

| Code | Purpose |
|---|---|
| `src="script.js"` | Connects the external JavaScript file |
| `defer` | Executes the script after HTML parsing |
| `querySelector()` | Finds an HTML element |
| `addEventListener()` | Responds to an event |
| `textContent` | Changes the text displayed on the page |

---

## 💬 4. JavaScript Comments

Comments explain code to programmers. They are not executed as program instructions.

### 🟢 Single-Line Comment

Use `//`.

```javascript
// Display a welcome message
console.log("Welcome!");
```

### 🔵 Multi-Line Comment

Use `/* ... */`.

```javascript
/*
This is my first JavaScript program.
I am learning how to write comments.
*/

console.log("Happy Coding! 💻");
```

### 🤔 Why Are Comments Useful?

- 📖 Make code easier to understand.
- 👥 Help other programmers read your code.
- 🛠️ Explain complicated logic.
- 📝 Record important notes.

---

## ⚠️ 5. JavaScript Is Case-Sensitive

JavaScript treats uppercase and lowercase letters differently.

```javascript
let student = "Aman";

console.log(student);  // ✅ Aman
console.log(Student);  // ❌ ReferenceError
```

**Why?** `student` and `Student` are different variable names.

💡 **Remember:** Always use consistent spelling and capitalisation.

---

## 🛠️ 6. How to Run JavaScript

### 🌐 Option 1: Browser Console

1. Open Google Chrome.
2. Right-click a webpage and select **Inspect**.
3. Open the **Console** tab.
4. Type this code:

```javascript
console.log("Hello World! 🌍");
```

5. Press Enter to see the output.

### 💻 Option 2: Using VS Code

1. Open VS Code.
2. Create an `index.html` file.
3. Write HTML and JavaScript.
4. Save the file.
5. Open it in your browser.
6. Open the developer console to view the output.

---

## 🧪 7. Practice Tasks

Try these exercises yourself!

- [ ] 🟢 **Beginner:** Print your name, branch, and college using `console.log()`.
- [ ] 🟡 **Intermediate:** Create a button that displays a welcome popup.
- [ ] 🔵 **Practice:** Connect an external JavaScript file to an HTML page.
- [ ] 🔴 **Challenge:** Change a webpage heading when a button is clicked.

---

## 🎤 8. Viva Voce Questions and Answers

Prepare these questions for your practical examination and classroom viva.

### 🟢 Basic Questions

**Q1. What is JavaScript?**

**Answer:** JavaScript is a programming language used to make websites interactive and dynamic.

**Q2. What is the full form of JS?**

**Answer:** JS stands for JavaScript.

**Q3. Why do we use JavaScript in web development?**

**Answer:** We use JavaScript to handle user interactions, validate forms, perform calculations, and dynamically update webpage content.

**Q4. What is the difference between HTML, CSS, and JavaScript?**

**Answer:** HTML creates the structure, CSS styles the webpage, and JavaScript adds behaviour and interactivity.

**Q5. Is JavaScript the same as Java?**

**Answer:** No. Java and JavaScript are different programming languages with different designs and uses.

### 🟡 Intermediate Questions

**Q6. What is a JavaScript script?**

**Answer:** A JavaScript script is a set of JavaScript instructions written to perform a particular task.

**Q7. What are the three ways to include JavaScript in HTML?**

**Answer:** Inline JavaScript, internal JavaScript, and external JavaScript.

**Q8. What is the difference between internal and external JavaScript?**

**Answer:** Internal JavaScript is written inside the HTML document's `<script>` element. External JavaScript is stored in a separate `.js` file and linked to the HTML document.

**Q9. What is the purpose of the `<script>` tag?**

**Answer:** It is used to include or embed JavaScript in an HTML document.

**Q10. What is the purpose of `console.log()`?**

**Answer:** It displays messages and values in the browser's developer console.

**Q11. What is the purpose of `alert()`?**

**Answer:** It displays a popup dialog containing a message.

**Q12. What are comments in JavaScript?**

**Answer:** Comments are notes in the source code that JavaScript does not execute as program instructions.

**Q13. Is JavaScript case-sensitive?**

**Answer:** Yes. For example, `student` and `Student` are treated as different identifiers.

### 🔵 Practical Questions

**Q14. How do you connect an external JavaScript file to HTML?**

**Answer:**

```html
<script src="script.js" defer></script>
```

**Q15. What is the purpose of the `defer` attribute?**

**Answer:** It tells the browser to execute the external script after the HTML document has been parsed.

**Q16. How can you display your name in the browser console?**

**Answer:**

```javascript
console.log("My name is Aman");
```

**Q17. How do you display a popup message when a button is clicked?**

**Answer:**

```html
<button onclick="alert('Hello!')">Click Me</button>
```

**Q18. What happens if you write `Console.log()` instead of `console.log()`?**

**Answer:** It normally produces a `ReferenceError` because JavaScript is case-sensitive and `Console` is not the same identifier as `console`.

**Q19. How can JavaScript change the text of an HTML element?**

**Answer:** By selecting the element and updating its `textContent` property.

```javascript
document.querySelector("#heading").textContent = "Hello Students!";
```

**Q20. Why is external JavaScript preferred in larger projects?**

**Answer:** It separates JavaScript from HTML, improves code organisation, and makes scripts easier to maintain and reuse.

---

## 🏆 9. Key Takeaways

- ⚡ JavaScript makes webpages interactive.
- 🏗️ HTML defines structure; CSS controls styling; JavaScript adds behaviour.
- 💻 JavaScript can be written inline, internally, or externally.
- 📤 `console.log()` displays information in the console.
- 💬 Comments make code easier to understand.
- 🔠 JavaScript is case-sensitive.
- ⭐ External JavaScript files help organise projects.

---

### 🚀 Keep Practising!

> 💡 **Remember:** The best way to learn programming is to write code, make mistakes, debug, and try again.

**Happy Coding! 💻✨**
