# 🎯 Scope in JavaScript

JavaScript **scope** determines where a variable can be accessed or used in a program.

Think of scope like a room in a house 🏠. Some things are available throughout the house, while others are available only inside a particular room.

---

## 📌 Types of Scope in JavaScript

JavaScript has three main types of scope:

1. 🌍 Global Scope
2. 🏠 Function Scope
3. 📦 Block Scope

## 1. 🌍 Global Scope

A variable declared outside all functions and blocks has **global scope**. It can generally be accessed from anywhere in its accessible program scope.

```javascript
let username = "Paramveer";

function greet() {
    console.log(username);
}

greet();

console.log(username);
```

**Output:**
```text
Paramveer
Paramveer
```

💡 **Explanation:** The variable `username` is declared outside the function, so it can be accessed both inside and outside `greet()`.

---

## 2. 🏠 Function Scope

Variables declared with `var`, `let`, or `const` inside a function are accessible only within that function, subject to their declaration rules.

```javascript
function display() {
    let message = "Hello Students!";
    console.log(message);
}

display();

// console.log(message); // ReferenceError
```

**Output:**
```text
Hello Students!
```

💡 **Explanation:** The variable `message` exists within the function. Trying to access it outside the function causes a `ReferenceError`.

### 🔍 Important Difference

- `var` is function-scoped.
- `let` and `const` are block-scoped, and they are also limited to the function when declared inside one.

---

## 3. 📦 Block Scope

A block is a group of statements enclosed in curly braces `{ }`, such as an `if` statement or a loop.

Variables declared using `let` and `const` inside a block are accessible only within that block.

```javascript
if (true) {
    let age = 25;
    const city = "Greater Noida";

    console.log(age);
    console.log(city);
}

// console.log(age);  // ReferenceError
// console.log(city); // ReferenceError
```

**Output:**
```text
25
Greater Noida
```

💡 **Explanation:** Both variables are declared inside the `if` block, so they cannot be accessed outside it.

### ⚠️ What About `var`?

The `var` keyword does not follow block scope.

```javascript
if (true) {
    var course = "JavaScript";
}

console.log(course);
```

**Output:**
```text
JavaScript
```

💡 **Explanation:** The variable `course` is not restricted to the `if` block because `var` is function-scoped rather than block-scoped.

---

## 📊 Scope Comparison Table

| Feature | `var` | `let` | `const` |
|---|---|---|---|
| Global scope | Yes, depending on declaration location | Yes, depending on declaration location | Yes, depending on declaration location |
| Function scope | Yes | When declared inside a function | When declared inside a function |
| Block scope | ❌ No | ✅ Yes | ✅ Yes |
| Can be reassigned? | ✅ Yes | ✅ Yes | ❌ No |
| Can be redeclared in the same scope? | ✅ Yes | ❌ No | ❌ No |

---

## 🔗 Bonus: Lexical Scope

**Lexical scope** means an inner function can access variables from its outer function because of where the functions are written in the code.

```javascript
function outer() {
    let message = "Welcome to JavaScript!";

    function inner() {
        console.log(message);
    }

    inner();
}

outer();
```

**Output:**
```text
Welcome to JavaScript!
```

💡 **Explanation:** The `inner()` function can access `message` because it is defined inside `outer()`.

This concept is important for understanding **closures** in JavaScript.

---

## 🧠 Key Takeaways

- 🌍 Global scope allows access across the relevant program scope.
- 🏠 Function scope restricts variables to a function.
- 📦 Block scope restricts `let` and `const` to a block.
- ⚠️ `var` is function-scoped, not block-scoped.
- 🔗 Lexical scope allows inner functions to access variables in their outer scopes.
- ✅ Prefer `const` by default and use `let` when reassignment is needed.

---

## 🎤 Viva Questions

**Q1. What is scope in JavaScript?**

Scope defines where a variable can be accessed in a program.

**Q2. How many main types of scope are commonly discussed in JavaScript?**

Three: global scope, function scope, and block scope.

**Q3. What is the difference between `var` and `let`?**

`var` is function-scoped, whereas `let` is block-scoped.

**Q4. Can a function access a variable declared in its outer function?**

Yes, provided the variable is accessible through lexical scope.

**Q5. What happens if we access a block-scoped variable outside its block?**

A `ReferenceError` occurs.

**Q6. What is lexical scope?**

It is the rule that determines variable access based on where functions and blocks are written in the source code.

**Q7. Which keyword should we generally prefer for variables that do not need reassignment?**

`const`.

---

✨ **Remember:** Scope decides *where* you can access a variable, while closures explain how a function can retain access to variables from its surrounding lexical scope.
