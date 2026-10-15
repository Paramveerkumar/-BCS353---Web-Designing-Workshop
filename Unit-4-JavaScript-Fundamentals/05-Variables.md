# 📦 JavaScript Variables

> 🎯 **Learning Objectives**
> - Understand what a variable is and why we need it.
> - Declare variables using `let`, `const`, and `var`.
> - Follow the rules and conventions for naming variables.
> - Differentiate between `let`, `const`, and `var`.
> - Understand block scope and the danger of `var`.

---

## 🌟 1. What is a Variable?

A **variable** is a named container that stores a value in the computer's memory.

Imagine **labelled boxes** in a storeroom. 📦

| Storeroom | JavaScript |
|---|---|
| 📦 The box | The variable |
| 🏷️ The label on the box | The variable name |
| 🎁 The item inside | The value |

You can look inside the box (read the value), and sometimes replace what is inside (change the value).

### 🧠 Remember This!

- A variable has a **name** and a **value**.
- The value can be used again and again by writing the name.

---

## 💻 2. Your First Variables

```javascript
let studentName = "Aman";
let age = 20;

console.log(studentName);
console.log(age);
```

### 📤 Output

```text
Aman
20
```

### 🔍 Explanation

- `let` is the keyword that declares a variable.
- `studentName` and `age` are the variable names.
- `=` is the **assignment operator**. It stores the value on the right into the variable on the left.
- `"Aman"` is text (a string) and `20` is a number.

### 🧩 Syntax

```javascript
keyword variableName = value;
```

💡 **Try It Yourself:** Create variables for your name, branch, and college, then print each one.

---

## 🔑 3. Three Ways to Declare Variables

### 🟢 `let`: for values that can change

```javascript
let score = 50;
console.log(score);

score = 75;          // value changed
console.log(score);
```

### 📤 Output

```text
50
75
```

### 🔵 `const`: for values that must not change ⭐

```javascript
const pi = 3.14;
console.log(pi);

pi = 3.15;           // ❌ Error
```

### 📤 Output

```text
3.14
TypeError: Assignment to constant variable.
```

> 💡 A `const` variable **must be given a value when it is declared**, and it **cannot be reassigned** afterwards.

### 🔴 `var`: the old way

```javascript
var city = "Delhi";
console.log(city);
```

### 📤 Output

```text
Delhi
```

`var` is the original way to declare variables. It still works, but it has confusing behaviour (see section 6), so modern code uses `let` and `const`.

### 🎯 Which One Should I Use?

1. ✅ Use **`const`** by default.
2. 🔄 Use **`let`** only when the value will change.
3. ⚠️ Avoid **`var`** in new code.

---

## 📊 4. Quick Comparison

| Feature | `var` | `let` | `const` |
|---|---|---|---|
| Can be reassigned? | ✅ Yes | ✅ Yes | ❌ No |
| Can be redeclared in the same scope? | ✅ Yes | ❌ No | ❌ No |
| Scope | Function | Block | Block |
| Must be initialised at declaration? | ❌ No | ❌ No | ✅ Yes |
| Recommended? | ⚠️ No | ✅ Yes | ✅ Yes (default) |

---

## 🏷️ 5. Naming Variables

### ✅ Rules (must follow)

- Names can contain **letters, digits, underscore `_`, and dollar sign `$`**.
- A name **cannot start with a digit**.
- **No spaces** are allowed.
- **Reserved words** (like `let`, `if`, `class`) cannot be used as names.
- Names are **case-sensitive**: `age` and `Age` are different variables.

```javascript
let studentName = "Aman";   // ✅ valid
let _count = 5;             // ✅ valid
let $price = 99;            // ✅ valid
let student2 = "Priya";     // ✅ valid

let 2student = "Riya";      // ❌ starts with a digit
let student name = "Ravi";  // ❌ contains a space
let let = 10;               // ❌ reserved word
```

### 🐪 Convention (good practice)

Use **camelCase**: the first word is lowercase, and each next word starts with a capital letter.

| ❌ Poor | ✅ Good |
|---|---|
| `x` | `age` |
| `studentname` | `studentName` |
| `total_marks_of_student` | `totalMarks` |

💡 Choose **meaningful names**. `totalMarks` is far clearer than `tm`.

---

## 🔄 6. Scope and the Problem with `var`

**Scope** decides where a variable can be used.

```javascript
if (true) {
    let x = 10;
    var y = 20;
}

console.log(y);   // 20
console.log(x);   // ❌ ReferenceError
```

### 📤 Output

```text
20
ReferenceError: x is not defined
```

### 🔍 Explanation

- `let` and `const` are **block-scoped**. They exist only inside the `{ }` where they are declared.
- `var` is **function-scoped**. It ignores blocks, so `y` "leaks" outside the `if` block.

### 🪝 `var` is Hoisted with `undefined`

```javascript
console.log(a);
var a = 5;
```

### 📤 Output

```text
undefined
```

With `let` and `const`, using the variable before its declaration gives an error instead, which helps you catch mistakes earlier:

```javascript
console.log(b);
let b = 5;
```

### 📤 Output

```text
ReferenceError: Cannot access 'b' before initialization
```

---

## 🧩 7. More About Variables

### 📭 Declaring Without a Value

```javascript
let result;
console.log(result);

result = 100;
console.log(result);
```

### 📤 Output

```text
undefined
100
```

A variable declared without a value holds `undefined`.

### 📚 Declaring Several Variables Together

```javascript
let a = 1, b = 2, c = 3;
console.log(a + b + c);
```

### 📤 Output

```text
6
```

### 🔁 Variables Can Hold Different Types

```javascript
let data = "Hello";
console.log(typeof data);

data = 42;
console.log(typeof data);
```

### 📤 Output

```text
string
number
```

JavaScript is **dynamically typed**: the same variable can hold a different type of value later.

### 🗃️ `const` with Arrays and Objects

`const` stops you from **reassigning** the variable, but the contents of an array or object can still change.

```javascript
const colors = ["red", "green"];
colors.push("blue");
console.log(colors);

colors = ["pink"];   // ❌ TypeError
```

### 📤 Output

```text
[ 'red', 'green', 'blue' ]
TypeError: Assignment to constant variable.
```

---

## ⚠️ 8. Common Mistakes

| ❌ Mistake | ✅ Correct |
|---|---|
| `const x;` (no value) | `const x = 5;` |
| Reassigning a `const` | Use `let` if the value must change |
| Using `Student` when you declared `student` | Keep the exact spelling and case |
| Using a variable before declaring it | Declare first, then use |
| Redeclaring with `let` in the same scope | Declare once, then just assign |
| Vague names like `a1`, `temp2` | Meaningful names like `totalMarks` |

---

## 🧪 9. Practice Tasks

- [ ] 🟢 **Beginner:** Declare variables for your name, age, and city, and print them.
- [ ] 🟡 **Intermediate:** Create a `const` named `collegeName` and try to change it. Note the error.
- [ ] 🟡 **Intermediate:** Swap the values of two `let` variables using a third variable.
- [ ] 🔵 **Practice:** Which of these names are invalid and why? `1name`, `my_age`, `total marks`, `$cost`, `class`
- [ ] 🔴 **Challenge:** Store the length and width of a rectangle in variables and print its area and perimeter using template literals.

---

## 🎤 10. Viva Voce Questions and Answers

### 🟢 Basic Questions

**Q1. What is a variable?**

**Answer:** A variable is a named container used to store a value in memory.

**Q2. How do you declare a variable in JavaScript?**

**Answer:** Using the keywords `let`, `const`, or `var`, for example `let age = 20;`.

**Q3. What is the assignment operator?**

**Answer:** The `=` symbol. It stores the value on the right side into the variable on the left side.

**Q4. Is JavaScript case-sensitive for variable names?**

**Answer:** Yes. `age` and `Age` are different variables.

**Q5. What is the naming convention for variables in JavaScript?**

**Answer:** camelCase, for example `studentName`.

### 🟡 Intermediate Questions

**Q6. What is the difference between `let` and `const`?**

**Answer:** A `let` variable can be reassigned, while a `const` variable cannot be reassigned and must be initialised when declared.

**Q7. What is the difference between `let` and `var`?**

**Answer:** `let` is block-scoped and cannot be redeclared in the same scope. `var` is function-scoped and can be redeclared.

**Q8. Why is `var` discouraged in modern JavaScript?**

**Answer:** It ignores block scope and is hoisted with the value `undefined`, which can cause confusing bugs.

**Q9. What value does a declared but unassigned variable hold?**

**Answer:** `undefined`.

**Q10. What are the rules for naming variables?**

**Answer:** A name may contain letters, digits, `_`, and `$`; it cannot start with a digit, contain spaces, or be a reserved keyword.

**Q11. What is block scope?**

**Answer:** A variable declared with `let` or `const` inside `{ }` can be accessed only within that block.

### 🔵 Practical Questions

**Q12. What happens if you declare `const x;` without a value?**

**Answer:** It causes a `SyntaxError` because a `const` variable must be initialised when declared.

**Q13. Can you change the contents of an array declared with `const`?**

**Answer:** Yes. `const` prevents reassignment of the variable, but the array's elements can still be modified, for example with `push()`.

**Q14. What is the output of the following code?**

```javascript
console.log(a);
let a = 10;
```

**Answer:** A `ReferenceError`: `Cannot access 'a' before initialization`.

**Q15. What does it mean that JavaScript is dynamically typed?**

**Answer:** A variable is not tied to one data type, so it can hold a number now and a string later.

---

## 🏆 11. Key Takeaways

- 📦 A variable is a named container for a value.
- 🔵 Use `const` by default, and `let` when the value must change.
- ⚠️ Avoid `var` in modern code.
- 🧱 `let` and `const` are block-scoped; `var` is function-scoped.
- 🏷️ Use meaningful camelCase names and remember that names are case-sensitive.
- 📭 A variable with no value holds `undefined`.
- 🗃️ `const` stops reassignment, but arrays and objects can still be modified.

---

### 🚀 Keep Practising!

> 💡 **Remember:** Good variable names make your code easy to read, even months later.

**Happy Coding! 💻✨**
