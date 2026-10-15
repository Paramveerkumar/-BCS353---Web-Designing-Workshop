# 📝 JavaScript Statements

> 🎯 **Learning Objectives**
> - Understand what a statement is.
> - Write multiple statements and understand the order of execution.
> - Use semicolons and code blocks correctly.
> - Differentiate between a statement and an expression.
> - Identify the common types of statements.

---

## 🌟 1. What is a Statement?

A **statement** is a single instruction that tells the computer to do something. A JavaScript program is simply a list of statements.

Imagine a **recipe**. 🍳

| Recipe | JavaScript Program |
|---|---|
| The whole recipe | The program |
| Each step ("Boil water", "Add salt") | Each statement |
| Steps followed in order | Statements run **top to bottom** |

### 🧠 Remember This!

- A statement is one instruction.
- A program is a collection of statements.
- The browser runs statements **one by one, in order**.

---

## 💻 2. Your First Statements

```javascript
let name = "Aman";
let age = 20;
console.log(name);
console.log(age);
```

### 📤 Output

```text
Aman
20
```

### 🔍 Explanation

- `let name = "Aman";` is a **declaration** statement. It creates a variable and stores a value.
- `let age = 20;` is another declaration statement.
- `console.log(name);` is a statement that **calls a function** to print a value.
- They run in order: line 1, then 2, 3, and 4.

💡 **Try It Yourself:** Swap the order of the last two lines and see how the output changes.

---

## ⏭️ 3. Order of Execution

JavaScript runs statements from **top to bottom**. The order matters!

```javascript
console.log(score);
let score = 90;
```

### 📤 Output

```text
ReferenceError: Cannot access 'score' before initialization
```

**Why?** The variable is used before it is declared. Write the declaration first:

```javascript
let score = 90;
console.log(score);
```

### 📤 Output

```text
90
```

---

## ✂️ 4. Semicolons and Line Breaks

A semicolon `;` marks the **end of a statement**.

```javascript
let a = 5;
let b = 10;
console.log(a + b);
```

### 📤 Output

```text
15
```

### 📌 Multiple Statements on One Line

You can place several statements on one line if you separate them with semicolons.

```javascript
let x = 1; let y = 2; console.log(x + y);
```

### 📤 Output

```text
3
```

> 💡 For readability, write **one statement per line**.

### ⚠️ Are Semicolons Required?

JavaScript can often insert semicolons automatically (called **Automatic Semicolon Insertion**), so code may work without them. But this can cause surprises:

```javascript
function getValue() {
    return
    42;
}

console.log(getValue());
```

### 📤 Output

```text
undefined
```

JavaScript inserts a semicolon right after `return`, so `42` is never returned. Keep the value on the same line as `return`.

✅ **Best practice:** Always end your statements with semicolons.

---

## 🧱 5. Code Blocks `{ }`

Curly braces group several statements into one **block**.

```javascript
let marks = 80;

if (marks >= 40) {
    console.log("You passed! 🎉");
    console.log("Congratulations!");
}
```

### 📤 Output

```text
You passed! 🎉
Congratulations!
```

### 🔍 Explanation

- The `{ }` block holds two statements.
- Both run together only when the condition is true.
- A block does **not** need a semicolon after the closing `}`.

---

## 🔍 6. Statement vs Expression

| Term | Meaning | Example |
|---|---|---|
| **Expression** | Code that **produces a value** | `5 + 3`, `"Hi"`, `age > 18` |
| **Statement** | A complete **instruction** that performs an action | `let total = 5 + 3;` |

```javascript
let total = 5 + 3;   // 5 + 3 is an expression; the whole line is a statement
console.log(total);
```

### 📤 Output

```text
8
```

> 💡 **Easy way to remember:** An expression is like a *phrase* ("five plus three"). A statement is like a *complete sentence* ("Store five plus three in total.").

---

## 🗂️ 7. Types of Statements

| Type | Purpose | Example |
|---|---|---|
| 📦 Declaration | Create variables | `let city = "Delhi";` |
| ✏️ Assignment | Give a variable a new value | `city = "Mumbai";` |
| 📞 Function call | Run a function | `console.log(city);` |
| 🔀 Conditional | Make decisions | `if (age >= 18) { ... }` |
| 🔁 Loop | Repeat code | `for (let i = 0; i < 3; i++) { ... }` |
| 📤 Return | Send a value out of a function | `return total;` |
| 🛑 Control | Stop or skip in loops | `break;` `continue;` |

### 🧪 All Together

```javascript
let city = "Delhi";                  // declaration
city = "Mumbai";                     // assignment
console.log(city);                   // function call

if (city === "Mumbai") {             // conditional
    console.log("Welcome to Mumbai!");
}

for (let i = 1; i <= 3; i++) {       // loop
    console.log("Round " + i);
}
```

### 📤 Output

```text
Mumbai
Welcome to Mumbai!
Round 1
Round 2
Round 3
```

---

## 🧪 8. Practice Tasks

- [ ] 🟢 **Beginner:** Write three statements that store your name, branch, and college in variables, then print them.
- [ ] 🟡 **Intermediate:** Write a program with two numbers and print their sum, difference, and product.
- [ ] 🔵 **Practice:** Find and fix the error: `console.log(city); let city = "Delhi";`
- [ ] 🔴 **Challenge:** Write a program that uses one declaration, one assignment, one `if` statement, and one loop.

---

## 🎤 9. Viva Voce Questions and Answers

**Q1. What is a statement in JavaScript?**

**Answer:** A statement is a single instruction that tells the computer to perform an action.

**Q2. In what order does JavaScript execute statements?**

**Answer:** From top to bottom, one after another.

**Q3. What is the use of a semicolon?**

**Answer:** It marks the end of a statement.

**Q4. Can we write multiple statements on one line?**

**Answer:** Yes, if they are separated by semicolons, but one statement per line is more readable.

**Q5. What is a code block?**

**Answer:** A group of statements enclosed in curly braces `{ }`, treated as a unit.

**Q6. What is the difference between a statement and an expression?**

**Answer:** An expression produces a value (like `5 + 3`), while a statement is a complete instruction that performs an action (like `let total = 5 + 3;`).

**Q7. Name some types of statements.**

**Answer:** Declaration, assignment, function call, conditional, loop, return, `break`, and `continue`.

**Q8. What is Automatic Semicolon Insertion (ASI)?**

**Answer:** A feature where JavaScript automatically adds semicolons in certain places. It can cause unexpected results, such as when a value is placed on a new line after `return`.

---

## 🏆 10. Key Takeaways

- 📝 A statement is one instruction; a program is a list of statements.
- ⏭️ Statements run from top to bottom.
- ✂️ Use `;` to end statements and write one statement per line.
- 🧱 `{ }` groups statements into a block.
- 🔍 An expression produces a value; a statement performs an action.
- ⚠️ Never put the returned value on a new line after `return`.

**Happy Coding! 💻✨**
