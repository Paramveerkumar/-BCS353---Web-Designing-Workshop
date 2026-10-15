# ⚙️ JavaScript Functions

> 🎯 **Learning Objectives**
> - Understand what a function is and why we use it.
> - Declare and call a function.
> - Use parameters, arguments, and default values.
> - Return a value from a function.
> - Differentiate between function declarations, function expressions, and arrow functions.
> - Understand scope, hoisting, and callback functions.
> - Build a small interactive webpage using functions.

---

## 🌟 1. What is a Function?

A **function** is a reusable block of code that performs a specific task. You write it once and use it as many times as you need.

Imagine a **vending machine**. 🥤

| Vending Machine | JavaScript Function |
|---|---|
| 🪙 You insert coins and select an item | 📥 You pass **arguments** (input) |
| ⚙️ The machine works internally | 🧠 The function **body** runs |
| 🥤 You receive a drink | 📤 The function **returns** a value (output) |

You don't need to know how the machine works inside. You only need to know how to use it.

### 🤔 Why Do We Use Functions?

- ♻️ **Reusability:** write once, use many times.
- 📦 **Organisation:** break large programs into small, manageable pieces.
- 🛠️ **Easy maintenance:** fix a problem in one place instead of many.
- 📖 **Readability:** a good function name explains what the code does.

### 🧠 Remember This!

- 📝 **Declare** a function = create it.
- 📞 **Call** a function = run it.
- A function does nothing until it is called.

---

## 💻 2. Your First Function

```javascript
function greet() {
    console.log("Hello, Students!");
    console.log("Welcome to JavaScript Functions 🚀");
}

greet();
greet();
```

### 📤 Output

```text
Hello, Students!
Welcome to JavaScript Functions 🚀
Hello, Students!
Welcome to JavaScript Functions 🚀
```

### 🔍 Explanation

- `function` is the keyword used to declare a function.
- `greet` is the **function name**.
- `()` holds the parameters (empty here).
- `{ ... }` is the **function body**, the code that runs.
- `greet();` **calls** the function. We called it twice, so the message appears twice.

### 🧩 Syntax

```javascript
function functionName(parameter1, parameter2) {
    // code to execute
    return result; // optional
}
```

💡 **Try It Yourself:** Create a function named `showCollege` that prints your college name, then call it three times.

---

## 📥 3. Parameters and Arguments

Functions become powerful when they accept **input**.

```javascript
function greetStudent(name) {
    console.log("Hello, " + name + "! 👋");
}

greetStudent("Aman");
greetStudent("Priya");
```

### 📤 Output

```text
Hello, Aman! 👋
Hello, Priya! 👋
```

### 🔍 Explanation

| Term | Meaning | In the example |
|---|---|---|
| **Parameter** | A variable listed in the function definition | `name` |
| **Argument** | The actual value passed when calling the function | `"Aman"`, `"Priya"` |

> 💡 **Easy way to remember:** Parameters are the *placeholders*. Arguments are the *real values*.

### 🔢 Multiple Parameters

```javascript
function introduce(name, branch) {
    console.log(name + " studies " + branch + ".");
}

introduce("Aman", "Computer Science");
```

### 📤 Output

```text
Aman studies Computer Science.
```

⚠️ **Order matters!** Arguments are matched to parameters by position.

### 🎁 Default Parameters

If no argument is passed, a **default value** is used.

```javascript
function welcome(name = "Student") {
    console.log(`Welcome, ${name}! 🎉`);
}

welcome("Riya");
welcome();
```

### 📤 Output

```text
Welcome, Riya! 🎉
Welcome, Student! 🎉
```

> 💡 The backticks `` ` `` and `${ }` create a **template literal**, a clean way to put variables inside text.

---

## 📤 4. Returning a Value

The `return` statement sends a result **back** to the place where the function was called.

```javascript
function add(a, b) {
    return a + b;
}

let result = add(5, 3);
console.log(result);
console.log(add(10, 20));
```

### 📤 Output

```text
8
30
```

### 🔍 Explanation

- `add(5, 3)` runs the function and **returns** `8`.
- The returned value can be stored in a variable or used directly.

### 🛑 `return` Ends the Function

```javascript
function test() {
    console.log("Before return");
    return;
    console.log("After return"); // never runs
}

test();
```

### 📤 Output

```text
Before return
```

### ❓ What If There Is No `return`?

```javascript
function sayHi() {
    console.log("Hi!");
}

let value = sayHi();
console.log(value);
```

### 📤 Output

```text
Hi!
undefined
```

A function without a `return` statement returns `undefined`.

### 🆚 `console.log()` vs `return`

| `console.log()` | `return` |
|---|---|
| Displays a value in the console | Sends a value back to the caller |
| Used for viewing/debugging | Used for reusing the result |
| The value cannot be stored | The value can be stored in a variable |

---

## 🧾 5. Three Ways to Create Functions

### 🟢 Method 1: Function Declaration

```javascript
function square(num) {
    return num * num;
}

console.log(square(4));
```

### 📤 Output

```text
16
```

### 🟡 Method 2: Function Expression

A function is stored inside a variable.

```javascript
const square = function (num) {
    return num * num;
};

console.log(square(5));
```

### 📤 Output

```text
25
```

💡 In JavaScript, functions are **values**. You can store them in variables, pass them to other functions, and return them from functions.

### 🔵 Method 3: Arrow Function ⭐

A shorter, modern syntax introduced in ES6.

```javascript
const square = (num) => {
    return num * num;
};

// Shorter version (implicit return)
const squareShort = (num) => num * num;

console.log(squareShort(6));
```

### 📤 Output

```text
36
```

### 🎯 Arrow Function Shortcuts

| Situation | Syntax |
|---|---|
| No parameters | `() => console.log("Hi")` |
| One parameter | `num => num * 2` (parentheses optional) |
| Multiple parameters | `(a, b) => a + b` |
| One-line body | The result is returned automatically (no `return` needed) |
| Multi-line body | Use `{ }` and write `return` yourself |

### 📊 Quick Comparison

| Feature | Declaration | Expression | Arrow |
|---|---|---|---|
| Syntax | `function name() {}` | `const name = function() {}` | `const name = () => {}` |
| Hoisted (usable before it is defined)? | ✅ Yes | ❌ No | ❌ No |
| Has its own `this` | ✅ Yes | ✅ Yes | ❌ No (uses surrounding `this`) |
| Best for | General use | Storing/passing functions | Short functions and callbacks |

---

## 🔭 6. Scope: Where Can a Variable Be Used?

**Scope** decides where a variable can be accessed.

```javascript
let college = "ABC College"; // global variable

function showInfo() {
    let student = "Aman"; // local variable
    console.log(college);
    console.log(student);
}

showInfo();
console.log(college);
console.log(student); // ❌ ReferenceError
```

### 📤 Output

```text
ABC College
Aman
ABC College
ReferenceError: student is not defined
```

### 🔍 Explanation

| Type | Where it is declared | Where it can be used |
|---|---|---|
| 🌍 **Global scope** | Outside all functions | Everywhere |
| 🏠 **Local (function) scope** | Inside a function | Only inside that function |

> 🏠 Think of a function as a **room**. Things inside the room (local variables) are invisible from outside, but the room can see the **hall** (global variables).

💡 **Best practice:** Prefer local variables. Too many globals make bugs hard to find.

---

## 🪝 7. Hoisting

JavaScript lets you **call a function declaration before it is written** in the code.

```javascript
sayHello(); // works ✅

function sayHello() {
    console.log("Hello from a hoisted function!");
}
```

### 📤 Output

```text
Hello from a hoisted function!
```

But function expressions and arrow functions stored with `const` or `let` **cannot** be used before they are defined.

```javascript
sayBye(); // ❌ ReferenceError

const sayBye = function () {
    console.log("Bye!");
};
```

### 📤 Output

```text
ReferenceError: Cannot access 'sayBye' before initialization
```

---

## 🔁 8. Callback Functions

A **callback** is a function passed as an argument to another function, to be called later.

```javascript
function processStudent(name, callback) {
    console.log("Processing " + name + "...");
    callback();
}

function done() {
    console.log("Processing complete ✅");
}

processStudent("Aman", done);
```

### 📤 Output

```text
Processing Aman...
Processing complete ✅
```

⚠️ Pass `done` (the function itself), not `done()`. Writing `done()` would run it immediately.

### 🌍 Callbacks in Real Life

```javascript
// Runs after 2 seconds
setTimeout(function () {
    console.log("2 seconds have passed ⏰");
}, 2000);

// Runs once for every item in an array
const names = ["Aman", "Priya", "Riya"];
names.forEach((name) => console.log("Hello, " + name));
```

### 📤 Output

```text
Hello, Aman
Hello, Priya
Hello, Riya
2 seconds have passed ⏰
```

---

## 📦 9. Rest Parameters (Unlimited Arguments)

What if you don't know how many values will be passed? Use `...` (the rest operator).

```javascript
function sum(...numbers) {
    let total = 0;
    for (const n of numbers) {
        total += n;
    }
    return total;
}

console.log(sum(1, 2, 3));
console.log(sum(10, 20, 30, 40));
```

### 📤 Output

```text
6
100
```

`numbers` becomes an **array** containing all the arguments.

---

## 🖱️ 10. Mini Project: Functions in a Webpage

Let's use functions to build a simple **marks checker**.

**📄 `index.html`**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Marks Checker</title>
</head>
<body>

    <h1>Marks Checker 📝</h1>
    <input type="number" id="marks" placeholder="Enter marks (0-100)">
    <button id="checkBtn">Check Result</button>
    <p id="result"></p>

    <script src="script.js" defer></script>

</body>
</html>
```

**📄 `script.js`**

```javascript
function getGrade(marks) {
    if (marks >= 90) return "A";
    if (marks >= 75) return "B";
    if (marks >= 60) return "C";
    if (marks >= 40) return "D";
    return "Fail";
}

function showResult() {
    const marks = Number(document.querySelector("#marks").value);
    const grade = getGrade(marks);
    document.querySelector("#result").textContent =
        "Marks: " + marks + " | Grade: " + grade;
}

document.querySelector("#checkBtn").addEventListener("click", showResult);
```

### 🎯 What Happens?

1. The user types marks, for example `82`.
2. The user clicks **Check Result**.
3. `showResult()` runs and calls `getGrade(82)`.
4. The page displays: **Marks: 82 | Grade: B**

### 🔍 Understanding the Code

| Code | Purpose |
|---|---|
| `getGrade(marks)` | Takes marks and **returns** a grade |
| `showResult()` | Reads the input, calls `getGrade()`, shows the output |
| `Number(...)` | Converts the input text into a number |
| `addEventListener("click", showResult)` | Uses `showResult` as a **callback** |

💡 Notice how each function does **one job**. That is good function design.

---

## ⚠️ 11. Common Mistakes

| ❌ Mistake | ✅ Correct |
|---|---|
| Forgetting to call the function: `greet;` | `greet();` |
| Using `console.log` when you need a value back | Use `return` |
| Writing code after `return` and expecting it to run | Put the code before `return` |
| Passing `done()` as a callback | Pass `done` |
| Using a local variable outside its function | Return the value, or declare it in a wider scope |
| Wrong argument order | Match the order of parameters |

---

## 🧪 12. Practice Tasks

Try these exercises yourself!

- [ ] 🟢 **Beginner:** Write a function `sayHello()` that prints "Hello, JavaScript!" and call it 3 times.
- [ ] 🟢 **Beginner:** Write a function `greetUser(name)` that prints a greeting using the given name.
- [ ] 🟡 **Intermediate:** Write a function `multiply(a, b)` that returns the product of two numbers.
- [ ] 🟡 **Intermediate:** Write a function `isEven(num)` that returns `true` if the number is even, otherwise `false`.
- [ ] 🔵 **Practice:** Convert `function cube(n) { return n * n * n; }` into an arrow function.
- [ ] 🔵 **Practice:** Write a function `findMax(a, b, c)` that returns the largest of three numbers.
- [ ] 🔴 **Challenge:** Write a function `average(...numbers)` that returns the average of any number of values.
- [ ] 🔴 **Challenge:** Build a webpage with two inputs and four buttons (Add, Subtract, Multiply, Divide), using a separate function for each operation.

---

## 🎤 13. Viva Voce Questions and Answers

Prepare these questions for your practical examination and classroom viva.

### 🟢 Basic Questions

**Q1. What is a function?**

**Answer:** A function is a reusable block of code that performs a specific task and runs when it is called.

**Q2. Why do we use functions?**

**Answer:** Functions provide reusability, better organisation, easier maintenance, and improved readability.

**Q3. Which keyword is used to declare a function?**

**Answer:** The `function` keyword.

**Q4. How do you call a function?**

**Answer:** By writing its name followed by parentheses, for example `greet();`.

**Q5. What is the difference between a parameter and an argument?**

**Answer:** A parameter is a variable listed in the function definition. An argument is the actual value passed to the function when it is called.

### 🟡 Intermediate Questions

**Q6. What does the `return` statement do?**

**Answer:** It sends a value back to the caller and immediately stops the execution of the function.

**Q7. What does a function return if there is no `return` statement?**

**Answer:** It returns `undefined`.

**Q8. What is the difference between `console.log()` and `return`?**

**Answer:** `console.log()` only displays a value in the console. `return` sends the value back to the caller so it can be stored or reused.

**Q9. What are default parameters?**

**Answer:** Default parameters give a parameter a fallback value that is used when no argument (or `undefined`) is passed.

**Q10. What is a function expression?**

**Answer:** A function expression is a function stored in a variable, for example `const add = function (a, b) { return a + b; };`.

**Q11. What is an arrow function?**

**Answer:** An arrow function is a shorter syntax for writing functions using `=>`, introduced in ES6.

**Q12. What is scope?**

**Answer:** Scope determines where in the program a variable can be accessed. Variables are mainly global (accessible everywhere) or local (accessible only inside their function or block).

**Q13. What is hoisting with respect to functions?**

**Answer:** Function declarations can be called before the line where they are written. Function expressions and arrow functions stored in `const` or `let` cannot.

**Q14. What is a callback function?**

**Answer:** A callback is a function passed as an argument to another function, to be executed later.

### 🔵 Practical Questions

**Q15. Write a function that returns the sum of two numbers.**

**Answer:**

```javascript
function add(a, b) {
    return a + b;
}
```

**Q16. Rewrite the above function as an arrow function.**

**Answer:**

```javascript
const add = (a, b) => a + b;
```

**Q17. What is the output of the following code?**

```javascript
function show() {
    return "Hello";
    console.log("World");
}
console.log(show());
```

**Answer:** `Hello`. The line after `return` never runs.

**Q18. What happens if you call a function with fewer arguments than parameters?**

**Answer:** The missing parameters become `undefined` (unless they have default values).

**Q19. What is the rest parameter?**

**Answer:** The rest parameter (`...args`) collects any number of arguments into an array.

```javascript
function total(...nums) {
    return nums.length;
}
```

**Q20. What is the difference between `done` and `done()` when passing a callback?**

**Answer:** `done` passes the function itself so it can be called later. `done()` runs the function immediately and passes its return value instead.

---

## 🏆 14. Key Takeaways

- ⚙️ A function is a reusable block of code that performs one task.
- 📝 **Declare** a function once, then **call** it as many times as needed.
- 📥 Parameters are placeholders; arguments are the real values.
- 📤 `return` sends a result back and ends the function.
- 🎁 Default parameters provide fallback values.
- 🧾 Functions can be written as declarations, expressions, or arrow functions.
- 🔭 Variables declared inside a function are local to that function.
- 🪝 Function declarations are hoisted; expressions and arrow functions are not.
- 🔁 A callback is a function passed to another function.
- 📦 Rest parameters (`...args`) accept any number of arguments.

---

### 🚀 Keep Practising!

> 💡 **Remember:** Small functions that do one job well are the building blocks of every great program.

**Happy Coding! 💻✨**
