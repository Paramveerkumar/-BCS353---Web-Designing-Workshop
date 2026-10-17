# ♻️ Refactoring in JavaScript

## 📌 What is Refactoring?

**Refactoring** is the process of improving the internal structure of existing code without changing its external behavior.

In simple words, refactoring means **making code cleaner, simpler, and easier to maintain without changing what it does.**

💡 Imagine cleaning and organizing your classroom. The classroom still serves the same purpose, but everything becomes easier to find and use!

---

## 🎯 1. Why Do We Need Refactoring?

Refactoring helps us:

- 🧹 Remove unnecessary or duplicate code.
- 📖 Improve code readability.
- 🔧 Make debugging and maintenance easier.
- ♻️ Reuse code efficiently.
- 🚀 Make future modifications easier.
- 🐛 Reduce the risk of bugs caused by confusing code.

---

## 🧪 2. Example: Before and After Refactoring

### ❌ Before Refactoring

```javascript
function calculate(a, b) {
    let result = a + b;
    console.log(result);
}

calculate(10, 20);
```

This code works, but the variable `result` is unnecessary because we can directly print the sum.

### ✅ After Refactoring

```javascript
function calculate(a, b) {
    console.log(a + b);
}

calculate(10, 20);
```

**Output in both cases:**

```text
30
```

🎯 The code is shorter, and its behavior remains the same for this example.

---

## 🧹 3. Refactoring Duplicate Code

Suppose we want to calculate the squares of two numbers.

### ❌ Before Refactoring

```javascript
let a = 5;
let squareA = a * a;
console.log(squareA);

let b = 8;
let squareB = b * b;
console.log(squareB);
```

The calculation logic is repeated.

### ✅ After Refactoring

```javascript
function square(number) {
    return number * number;
}

console.log(square(5));
console.log(square(8));
```

**Output:**

```text
25
64
```

💡 We created a reusable function and removed duplicated logic.

---

## ✨ 4. Refactoring Conditional Statements

### ❌ Before Refactoring

```javascript
function checkAge(age) {
    if (age >= 18) {
        return true;
    } else {
        return false;
    }
}

console.log(checkAge(20));
```

### ✅ After Refactoring

```javascript
function checkAge(age) {
    return age >= 18;
}

console.log(checkAge(20));
```

**Output:**

```text
true
```

💡 Since `age >= 18` already evaluates to a Boolean value, we can return it directly.

---

## 🏷️ 5. Refactoring Variable Names

Good variable names make programs easier to understand.

### ❌ Before Refactoring

```javascript
let x = 500;
let y = 10;

let z = x * y;

console.log(z);
```

### ✅ After Refactoring

```javascript
let productPrice = 500;
let quantity = 10;

let totalPrice = productPrice * quantity;

console.log(totalPrice);
```

**Output:**

```text
5000
```

💡 Meaningful names explain what the variables represent without requiring extra comments.

---

## 🔄 6. Refactoring with Arrow Functions

### ❌ Before Refactoring

```javascript
function double(number) {
    return number * 2;
}

console.log(double(5));
```

### ✅ After Refactoring

```javascript
const double = number => number * 2;

console.log(double(5));
```

**Output:**

```text
10
```

💡 An arrow function can make a short function more concise. However, traditional functions should still be used where their behavior is needed, such as when using a dynamic `this` value or a constructor.

---

## 🛠️ 7. Common Refactoring Techniques

| Technique | Purpose |
|---|---|
| Extract Function | Move repeated or complex logic into a separate function |
| Rename Variable | Give variables clearer names |
| Remove Duplicate Code | Avoid repeating the same logic |
| Simplify Conditional | Make decision-making logic easier to understand |
| Extract Variable | Store a complex expression in a meaningful variable |
| Replace Magic Numbers | Use named constants instead of unexplained numbers |
| Simplify Function | Reduce unnecessary steps and complexity |

### Example: Replace Magic Numbers

❌ Before:

```javascript
let total = 1000 * 0.18;
console.log(total);
```

✅ After:

```javascript
const GST_RATE = 0.18;
const amount = 1000;

let gstAmount = amount * GST_RATE;

console.log(gstAmount);
```

**Output:**

```text
180
```

💡 A named constant makes the purpose of `0.18` clearer. In a real application, tax rates should reflect the applicable rules.

---

## 🧭 8. The Refactoring Process

<box border radius="lg" padding={3} gap={3}>
  <row align="center" gap={3}>
    <box background="surface-secondary" radius="lg" size="44px" align="center" justify="center">
      <icon name="search" size="xl"/>
    </box>
    <box flex="1" gap={1}>
      **Step 1: Identify**

      <text color="secondary" size="sm">Find duplicated, complex, or difficult-to-read code.</text>
    </box>
  </row>
  <divider color="subtle"/>
  <row align="center" gap={3}>
    <box background="surface-secondary" radius="lg" size="44px" align="center" justify="center">
      <icon name="git-branch" size="xl"/>
    </box>
    <box flex="1" gap={1}>
      **Step 2: Improve**

      <text color="secondary" size="sm">Make small, focused changes to the code structure.</text>
    </box>
  </row>
  <divider color="subtle"/>
  <row align="center" gap={3}>
    <box background="surface-secondary" radius="lg" size="44px" align="center" justify="center">
      <icon name="check-circle" size="xl"/>
    </box>
    <box flex="1" gap={1}>
      **Step 3: Test**

      <text color="secondary" size="sm">Run tests to verify that the behavior remains unchanged.</text>
    </box>
  </row>
  <divider color="subtle"/>
  <row align="center" gap={3}>
    <box background="surface-secondary" radius="lg" size="44px" align="center" justify="center">
      <icon name="git-commit" size="xl"/>
    </box>
    <box flex="1" gap={1}>
      **Step 4: Review**

      <text color="secondary" size="sm">Check readability, correctness, and version-control changes.</text>
    </box>
  </row>
</box>

---

## ⚠️ 9. Important Rules of Refactoring

- ✅ Preserve the program's intended behavior.
- ✅ Make small changes rather than rewriting everything at once.
- ✅ Run tests before and after refactoring.
- ✅ Use meaningful variable and function names.
- ❌ Do not add unrelated features during refactoring.
- ❌ Do not assume shorter code is always better.
- ❌ Do not remove validation or error handling just to simplify code.

**Remember:** Refactoring improves the structure of code; adding a new feature changes what the program does.

---

## 🎤 10. Viva Questions

**Q1. What is refactoring?**

Refactoring is improving the internal structure of code without changing its external behavior.

**Q2. Why is refactoring important?**

It improves readability, maintainability, and code reuse while reducing unnecessary complexity.

**Q3. Does refactoring change program output?**

The intended observable behavior should remain the same for the relevant inputs and conditions.

**Q4. What is duplicate code?**

Duplicate code is the repetition of the same or very similar logic in multiple places.

**Q5. What is the Extract Function technique?**

It involves moving a section of code into a separate, appropriately named function.

**Q6. What is a magic number?**

A magic number is a numeric literal used without a clear explanation of its meaning.

**Q7. What is the role of testing in refactoring?**

Testing helps detect unintended behavioral changes introduced during code restructuring.

**Q8. What is the difference between refactoring and debugging?**

Refactoring improves code structure, whereas debugging identifies and fixes defects.

**Q9. What is the difference between refactoring and adding a feature?**

Refactoring preserves intended behavior; adding a feature introduces new functionality.

**Q10. Can refactoring improve performance?**

Sometimes, but its primary goal is better code structure rather than performance improvement.

---

## 🧠 Quick Revision

- ♻️ Refactoring = improving code structure.
- 🎯 Main goal = maintainability and readability.
- 🔁 Duplicate code can often be replaced with reusable functions.
- 🧪 Testing helps preserve existing behavior.
- 🚫 Refactoring is not the same as adding features or fixing bugs.

✨ **Exam definition:** Refactoring is the systematic process of restructuring existing source code to improve its design, readability, and maintainability without changing its intended external behavior.
