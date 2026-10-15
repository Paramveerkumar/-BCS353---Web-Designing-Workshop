# ➕ JavaScript Operators

> 🎯 **Learning Objectives**
> - Understand what operators and operands are.
> - Use arithmetic, assignment, comparison, and logical operators.
> - Differentiate between `==` and `===`.
> - Use the ternary and `typeof` operators.
> - Understand operator precedence.

---

## 🌟 1. What is an Operator?

An **operator** is a symbol that performs an operation on values. The values it works on are called **operands**.

Think of a **calculator**. 🧮

```text
  10  +  5
  ↑   ↑  ↑
operand operator operand
```

| Term | Meaning | Example |
|---|---|---|
| **Operand** | The value being worked on | `10`, `5` |
| **Operator** | The symbol that does the work | `+` |
| **Expression** | Operands and operators together | `10 + 5` |

### 🗂️ Types of Operators

| Type | Purpose | Examples |
|---|---|---|
| ➕ Arithmetic | Mathematical calculations | `+  -  *  /  %  **` |
| ✏️ Assignment | Store values in variables | `=  +=  -=` |
| ⚖️ Comparison | Compare two values | `==  ===  >  <` |
| 🔀 Logical | Combine conditions | `&&  \|\|  !` |
| ❓ Ternary | Short if-else | `condition ? a : b` |
| 🔍 `typeof` | Find the data type | `typeof 42` |

---

## ➕ 2. Arithmetic Operators

```javascript
let a = 10;
let b = 3;

console.log(a + b);
console.log(a - b);
console.log(a * b);
console.log(a / b);
console.log(a % b);
console.log(a ** b);
```

### 📤 Output

```text
13
7
30
3.3333333333333335
1
1000
```

### 🔍 Explanation

| Operator | Name | Example | Result |
|---|---|---|---|
| `+` | Addition | `10 + 3` | `13` |
| `-` | Subtraction | `10 - 3` | `7` |
| `*` | Multiplication | `10 * 3` | `30` |
| `/` | Division | `10 / 3` | `3.3333333333333335` |
| `%` | Modulus (remainder) | `10 % 3` | `1` |
| `**` | Exponent (power) | `10 ** 3` | `1000` |

💡 **Modulus is very useful.** To check whether a number is even: `num % 2 === 0`.

### 🔼 Increment and Decrement

```javascript
let count = 5;

count++;                // increase by 1
console.log(count);

count--;                // decrease by 1
console.log(count);
```

### 📤 Output

```text
6
5
```

### 🆚 Prefix vs Postfix

```javascript
let x = 5;

console.log(x++);   // uses the value, THEN increases
console.log(x);
console.log(++x);   // increases FIRST, then uses the value
```

### 📤 Output

```text
5
6
7
```

### 🔤 The `+` Operator with Strings

When `+` is used with text, it **joins** (concatenates) the values.

```javascript
console.log("Hello, " + "Aman");
console.log("5" + 3);
console.log("5" - 3);
```

### 📤 Output

```text
Hello, Aman
53
2
```

> ⚠️ `+` joins when a string is involved, but `-`, `*`, and `/` convert strings to numbers. This is a very common source of bugs.

### 🪤 Floating-Point Surprise

```javascript
console.log(0.1 + 0.2);
```

### 📤 Output

```text
0.30000000000000004
```

Computers store decimals in binary, so some decimal values are not stored exactly. This happens in many programming languages, not just JavaScript.

---

## ✏️ 3. Assignment Operators

The `=` operator stores a value. Shortcut versions combine an operation with assignment.

```javascript
let x = 10;

x += 5;    console.log(x);
x -= 3;    console.log(x);
x *= 2;    console.log(x);
x /= 4;    console.log(x);
x %= 4;    console.log(x);
x **= 3;   console.log(x);
```

### 📤 Output

```text
15
12
24
6
2
8
```

| Operator | Same as | Meaning |
|---|---|---|
| `x += 5` | `x = x + 5` | Add and assign |
| `x -= 3` | `x = x - 3` | Subtract and assign |
| `x *= 2` | `x = x * 2` | Multiply and assign |
| `x /= 4` | `x = x / 4` | Divide and assign |
| `x %= 4` | `x = x % 4` | Remainder and assign |
| `x **= 3` | `x = x ** 3` | Power and assign |

---

## ⚖️ 4. Comparison Operators

Comparison operators compare two values and always give a **boolean** (`true` or `false`).

```javascript
console.log(5 > 3);
console.log(5 < 3);
console.log(5 >= 5);
console.log(5 <= 4);
```

### 📤 Output

```text
true
false
true
false
```

### 🆚 `==` vs `===` ⭐

```javascript
console.log(5 == "5");
console.log(5 === "5");
console.log(5 != "5");
console.log(5 !== "5");
```

### 📤 Output

```text
true
false
false
true
```

### 🔍 Explanation

| Operator | Name | What it checks |
|---|---|---|
| `==` | Loose equality | Value only (converts types first) |
| `===` | Strict equality | Value **and** type |
| `!=` | Loose inequality | Value is different (after conversion) |
| `!==` | Strict inequality | Value **or** type is different |

### 🎭 Why Loose Equality is Risky

```javascript
console.log(0 == false);
console.log("" == 0);
console.log(null == undefined);
console.log(null === undefined);
```

### 📤 Output

```text
true
true
true
false
```

✅ **Best practice:** Always use `===` and `!==`.

---

## 🔀 5. Logical Operators

Logical operators combine conditions.

| Operator | Name | Result |
|---|---|---|
| `&&` | AND | `true` only if **both** sides are true |
| `\|\|` | OR | `true` if **at least one** side is true |
| `!` | NOT | Reverses the value |

```javascript
let age = 20;
let hasID = true;

console.log(age >= 18 && hasID);
console.log(age < 18 || hasID);
console.log(!hasID);
```

### 📤 Output

```text
true
true
false
```

### 📋 Truth Tables

| A | B | `A && B` | `A \|\| B` |
|---|---|---|---|
| true | true | true | true |
| true | false | false | true |
| false | true | false | true |
| false | false | false | false |

### ⚡ Short-Circuit Behaviour

`&&` and `||` stop as soon as the answer is known, and they return one of the **actual values**, not always `true` or `false`.

```javascript
console.log("Aman" || "Guest");
console.log("" || "Guest");
console.log(0 && 5);
console.log(1 && 5);
```

### 📤 Output

```text
Aman
Guest
0
5
```

A common use is providing a default value:

```javascript
let userName = "" || "Guest";
console.log(userName);
```

### 📤 Output

```text
Guest
```

### ❔ Nullish Coalescing `??`

`??` gives the right side **only if the left side is `null` or `undefined`**. Unlike `||`, it keeps `0` and `""`.

```javascript
console.log(0 || 10);
console.log(0 ?? 10);
console.log(null ?? 10);
```

### 📤 Output

```text
10
0
10
```

---

## ❓ 6. Ternary Operator

A short way to write a simple if-else.

```javascript
let age = 17;
let status = age >= 18 ? "Adult" : "Minor";
console.log(status);
```

### 📤 Output

```text
Minor
```

### 🧩 Syntax

```javascript
condition ? valueIfTrue : valueIfFalse;
```

---

## 🔍 7. `typeof` Operator

Tells you the data type of a value.

```javascript
console.log(typeof 42);
console.log(typeof "Hello");
console.log(typeof true);
console.log(typeof undefined);
```

### 📤 Output

```text
number
string
boolean
undefined
```

---

## 🥇 8. Operator Precedence

When an expression has several operators, JavaScript follows an order, like BODMAS in maths.

```javascript
console.log(2 + 3 * 4);
console.log((2 + 3) * 4);
console.log(10 - 2 - 3);
```

### 📤 Output

```text
14
20
5
```

### 🔍 Explanation

- `*` runs before `+`, so `2 + 3 * 4` is `2 + 12`.
- **Parentheses `( )`** have the highest priority and let you control the order.
- Operators of equal priority usually run left to right: `(10 - 2) - 3`.

### 📊 Rough Order (high to low)

| Priority | Operators |
|---|---|
| 1️⃣ Highest | `( )` |
| 2️⃣ | `++  --  !  typeof` |
| 3️⃣ | `**` |
| 4️⃣ | `*  /  %` |
| 5️⃣ | `+  -` |
| 6️⃣ | `<  >  <=  >=` |
| 7️⃣ | `==  ===  !=  !==` |
| 8️⃣ | `&&` |
| 9️⃣ | `\|\|`  `??` |
| 🔟 | `? :` |
| 1️⃣1️⃣ Lowest | `=  +=  -=` |

💡 When in doubt, use parentheses. They make your code clearer too.

---

## 🛒 9. Mini Example: Bill Calculator

```javascript
const price = 250;
const quantity = 3;
const discountLimit = 500;

let total = price * quantity;
let discount = total > discountLimit ? total * 0.1 : 0;
let finalAmount = total - discount;

console.log(`Total: ${total}`);
console.log(`Discount: ${discount}`);
console.log(`Final Amount: ${finalAmount}`);
```

### 📤 Output

```text
Total: 750
Discount: 75
Final Amount: 675
```

### 🔍 Operators Used

- `*` to find the total.
- `>` to compare with the limit.
- `? :` to decide the discount.
- `-` to find the final amount.

---

## ⚠️ 10. Common Mistakes

| ❌ Mistake | ✅ Correct |
|---|---|
| Using `=` to compare: `if (a = 5)` | Use `===`: `if (a === 5)` |
| Using `==` and getting surprising results | Use `===` |
| Expecting `"5" + 3` to equal `8` | Convert first: `Number("5") + 3` |
| Forgetting parentheses in a long expression | Add `( )` to show the intended order |
| Expecting `0.1 + 0.2` to equal `0.3` exactly | Round the result when needed |

---

## 🧪 11. Practice Tasks

- [ ] 🟢 **Beginner:** Store two numbers and print their sum, difference, product, quotient, and remainder.
- [ ] 🟢 **Beginner:** Predict the output: `console.log(10 + 5 * 2);`
- [ ] 🟡 **Intermediate:** Check whether a number is even or odd using `%` and the ternary operator.
- [ ] 🟡 **Intermediate:** Print the results of `5 == "5"` and `5 === "5"` and explain the difference.
- [ ] 🔵 **Practice:** Check whether a person can vote: age is 18 or more **and** has a voter ID.
- [ ] 🔴 **Challenge:** Write a program that takes marks in three subjects, calculates the average, and uses the ternary operator to print "Pass" if the average is 40 or more, otherwise "Fail".

---

## 🎤 12. Viva Voce Questions and Answers

### 🟢 Basic Questions

**Q1. What is an operator?**

**Answer:** An operator is a symbol that performs an operation on one or more values.

**Q2. What is an operand?**

**Answer:** An operand is a value on which an operator works. In `10 + 5`, the numbers `10` and `5` are operands.

**Q3. Name the types of operators in JavaScript.**

**Answer:** Arithmetic, assignment, comparison, logical, ternary, and `typeof` (among others).

**Q4. What does the `%` operator do?**

**Answer:** It returns the remainder of a division. For example, `10 % 3` gives `1`.

**Q5. What is the difference between `=` and `==`?**

**Answer:** `=` assigns a value to a variable, while `==` compares two values.

### 🟡 Intermediate Questions

**Q6. What is the difference between `==` and `===`?**

**Answer:** `==` compares only values after converting types, while `===` compares both value and type without conversion.

**Q7. Which one is recommended, `==` or `===`?**

**Answer:** `===`, because it avoids unexpected results caused by type conversion.

**Q8. What is the difference between `x++` and `++x`?**

**Answer:** `x++` returns the current value and then increases it. `++x` increases the value first and then returns it.

**Q9. What is the output of `"5" + 3` and `"5" - 3`?**

**Answer:** `"53"` and `2`. The `+` operator concatenates when a string is involved, but `-` converts the string to a number.

**Q10. What are logical operators?**

**Answer:** `&&` (AND), `||` (OR), and `!` (NOT). They are used to combine or reverse conditions.

**Q11. What is short-circuit evaluation?**

**Answer:** `&&` and `||` stop evaluating as soon as the result is known, and they return one of the operand values. For example, `"" || "Guest"` returns `"Guest"`.

**Q12. What is the ternary operator?**

**Answer:** A short form of if-else with the syntax `condition ? valueIfTrue : valueIfFalse`.

### 🔵 Practical Questions

**Q13. What is the output of `console.log(2 + 3 * 4);`?**

**Answer:** `14`, because multiplication has higher precedence than addition.

**Q14. How do you check whether a number is even?**

**Answer:** `num % 2 === 0`

**Q15. What is the difference between `||` and `??`?**

**Answer:** `||` returns the right side when the left side is any falsy value (like `0` or `""`). `??` returns the right side only when the left side is `null` or `undefined`.

**Q16. Why does `0.1 + 0.2` not equal `0.3` exactly?**

**Answer:** Decimal numbers are stored in binary, and some values cannot be represented exactly, so the result is `0.30000000000000004`.

---

## 🏆 13. Key Takeaways

- ➕ Operators perform operations on operands.
- 🧮 `%` gives the remainder, and `**` gives the power.
- ✏️ Shortcut operators like `+=` combine calculation and assignment.
- ⚖️ Always prefer `===` and `!==` over `==` and `!=`.
- 🔀 `&&`, `||`, and `!` combine conditions, and `&&`/`||` short-circuit.
- ❓ The ternary operator is a compact if-else.
- 🥇 Use parentheses to control the order of operations.

---

### 🚀 Keep Practising!

> 💡 **Remember:** Operators are the verbs of programming. They make your data do something.

**Happy Coding! 💻✨**
