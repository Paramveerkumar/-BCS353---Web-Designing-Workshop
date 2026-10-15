# 🔀 JavaScript if-else Statements

> 🎯 **Learning Objectives**
> - Understand why programs need to make decisions.
> - Write `if`, `if-else`, and `else if` statements.
> - Use comparison and logical operators inside conditions.
> - Understand nested conditions and truthy/falsy values.
> - Use the ternary operator and a basic `switch` statement.
> - Avoid the most common mistakes in conditions.

---

## 🌟 1. What is a Conditional Statement?

A **conditional statement** lets a program **choose** what to do depending on whether a condition is `true` or `false`.

Think of a **traffic signal**. 🚦

| Condition | Action |
|---|---|
| 🔴 If the light is red | Stop |
| 🟡 Else if the light is yellow | Slow down |
| 🟢 Else (it must be green) | Go |

Your program makes decisions the same way.

### 🧠 Remember This!

- A **condition** is an expression that results in `true` or `false`.
- Only the code of the **first matching** branch runs.
- The condition is written inside **parentheses** `( )` and the code inside **curly braces** `{ }`.

---

## 💻 2. The `if` Statement

Runs a block of code **only if** the condition is true.

```javascript
let age = 20;

if (age >= 18) {
    console.log("You can vote ✅");
}

console.log("Program finished");
```

### 📤 Output

```text
You can vote ✅
Program finished
```

### 🔍 Explanation

- `age >= 18` is the condition. It is `true` here.
- Because it is true, the block runs.
- If `age` were `15`, the block would be skipped and only `Program finished` would print.

### 🧩 Syntax

```javascript
if (condition) {
    // runs when the condition is true
}
```

💡 **Try It Yourself:** Change `age` to `15` and run the code again.

---

## ↔️ 3. The `if-else` Statement

Runs one block if the condition is true, **otherwise** runs the other block.

```javascript
let marks = 35;

if (marks >= 40) {
    console.log("Pass 🎉");
} else {
    console.log("Fail 😔");
}
```

### 📤 Output

```text
Fail 😔
```

### 🧩 Syntax

```javascript
if (condition) {
    // runs when true
} else {
    // runs when false
}
```

> 💡 Exactly **one** of the two blocks always runs.

---

## 🪜 4. The `else if` Ladder

Use it when there are **more than two** possibilities.

```javascript
let marks = 82;

if (marks >= 90) {
    console.log("Grade A");
} else if (marks >= 75) {
    console.log("Grade B");
} else if (marks >= 60) {
    console.log("Grade C");
} else if (marks >= 40) {
    console.log("Grade D");
} else {
    console.log("Fail");
}
```

### 📤 Output

```text
Grade B
```

### 🔍 Explanation

1. `82 >= 90` is false, so JavaScript moves on.
2. `82 >= 75` is true, so it prints `Grade B`.
3. The remaining conditions are **skipped**, even though `82 >= 60` is also true.

### ⚠️ Order Matters!

```javascript
let marks = 95;

if (marks >= 40) {
    console.log("Grade D");      // ❌ matches first!
} else if (marks >= 90) {
    console.log("Grade A");
}
```

### 📤 Output

```text
Grade D
```

Put the **strictest (most specific) condition first**. Here `95 >= 40` is true, so the `Grade A` check is never reached.

---

## 🔗 5. Combining Conditions with Logical Operators

| Operator | Meaning | Example |
|---|---|---|
| `&&` | AND: **both** must be true | `age >= 18 && hasID` |
| `\|\|` | OR: **at least one** must be true | `isWeekend \|\| isHoliday` |
| `!` | NOT: reverses the result | `!isLoggedIn` |

```javascript
let age = 25;
let hasLicense = true;

if (age >= 18 && hasLicense) {
    console.log("You can drive 🚗");
} else {
    console.log("You cannot drive");
}
```

### 📤 Output

```text
You can drive 🚗
```

```javascript
let isWeekend = false;
let isHoliday = true;

if (isWeekend || isHoliday) {
    console.log("No classes today 🎉");
}
```

### 📤 Output

```text
No classes today 🎉
```

### 📅 Example: Leap Year

A year is a leap year if it is divisible by 4 **and** not by 100, **or** it is divisible by 400.

```javascript
let year = 2024;

if ((year % 4 === 0 && year % 100 !== 0) || year % 400 === 0) {
    console.log(year + " is a leap year");
} else {
    console.log(year + " is not a leap year");
}
```

### 📤 Output

```text
2024 is a leap year
```

| Year | Result |
|---|---|
| `2024` | Leap year |
| `1900` | Not a leap year (divisible by 100 but not 400) |
| `2000` | Leap year (divisible by 400) |

---

## 🪆 6. Nested `if`

An `if` inside another `if`.

```javascript
let age = 25;
let hasLicense = false;

if (age >= 18) {
    if (hasLicense) {
        console.log("You can drive 🚗");
    } else {
        console.log("Get a licence first 📝");
    }
} else {
    console.log("You are too young");
}
```

### 📤 Output

```text
Get a licence first 📝
```

> 💡 Too much nesting is hard to read. Often `&&` or an `else if` ladder is cleaner.

---

## ⚖️ 7. Truthy and Falsy Values in Conditions

A condition does not have to be a true boolean. JavaScript converts any value to `true` or `false`.

**Falsy values:** `false`, `0`, `""`, `null`, `undefined`, `NaN` (and `-0`, `0n`). **Everything else is truthy.**

```javascript
let userName = "";

if (userName) {
    console.log("Welcome, " + userName);
} else {
    console.log("Welcome, Guest");
}
```

### 📤 Output

```text
Welcome, Guest
```

```javascript
let items = [];

if (items.length) {
    console.log("Cart has items");
} else {
    console.log("Cart is empty 🛒");
}
```

### 📤 Output

```text
Cart is empty 🛒
```

> ⚠️ An empty array `[]` is **truthy**, so check `items.length` instead of `items`.

---

## ❓ 8. Ternary Operator: A Short if-else

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

💡 Use the ternary for **simple** choices that produce a value. For longer logic, use a normal `if-else`.

---

## 🔁 9. A Quick Look at `switch`

When you compare **one value against many exact options**, `switch` can be neater than a long `else if` ladder.

```javascript
let day = 3;

switch (day) {
    case 1:
        console.log("Monday");
        break;
    case 2:
        console.log("Tuesday");
        break;
    case 3:
        console.log("Wednesday");
        break;
    default:
        console.log("Another day");
}
```

### 📤 Output

```text
Wednesday
```

### 🔍 Explanation

- `switch` compares `day` with each `case` using strict equality (`===`).
- `break` stops the switch. Without it, execution **falls through** into the next case.
- `default` runs when no case matches.

### 🆚 `if-else` vs `switch`

| Use `if-else` for | Use `switch` for |
|---|---|
| Ranges (`marks >= 75`) | Exact matches (`day === 3`) |
| Complex conditions with `&&` and `\|\|` | One value with many fixed options |

---

## 🛡️ 10. Guard Clauses (Cleaner Code)

Inside a function, handle the **invalid cases first** and return early. It avoids deep nesting.

```javascript
function checkAge(age) {
    if (age < 0) {
        return "Invalid age";
    }
    if (age >= 18) {
        return "Adult";
    }
    return "Minor";
}

console.log(checkAge(-5));
console.log(checkAge(25));
console.log(checkAge(10));
```

### 📤 Output

```text
Invalid age
Adult
Minor
```

---

## 🖱️ 11. Mini Project: Age Checker Page

**📄 `index.html`**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Age Checker</title>
</head>
<body>

    <h1>Voting Eligibility 🗳️</h1>
    <input type="number" id="age" placeholder="Enter your age">
    <button id="checkBtn">Check</button>
    <p id="message"></p>

    <script src="script.js" defer></script>

</body>
</html>
```

**📄 `script.js`**

```javascript
document.querySelector("#checkBtn").addEventListener("click", function () {
    const input = document.querySelector("#age").value;
    const message = document.querySelector("#message");

    if (input === "") {
        message.textContent = "Please enter your age ⚠️";
        return;
    }

    const age = Number(input);

    if (age < 0) {
        message.textContent = "Age cannot be negative ❌";
    } else if (age >= 18) {
        message.textContent = "You are eligible to vote ✅";
    } else {
        const years = 18 - age;
        message.textContent = "Not eligible yet. Wait " + years + " more year(s) ⏳";
    }
});
```

### 🎯 What Happens?

| Input | Message |
|---|---|
| *(empty)* | Please enter your age ⚠️ |
| `-3` | Age cannot be negative ❌ |
| `20` | You are eligible to vote ✅ |
| `15` | Not eligible yet. Wait 3 more year(s) ⏳ |

---

## ⚠️ 12. Common Mistakes

| ❌ Mistake | ✅ Correct |
|---|---|
| `if (x = 5)` (assignment) | `if (x === 5)` (comparison) |
| `if (x > 5);` (semicolon after the condition) | `if (x > 5) { ... }` |
| Omitting braces for multiple statements | Always use `{ }` |
| Using `==` and getting surprising matches | Use `===` |
| Wrong order in an `else if` ladder | Put the most specific condition first |
| Checking `if (items)` for an empty array | Check `items.length` |
| Writing `if (18 <= age <= 60)` | Write `age >= 18 && age <= 60` |
| Forgetting `break` in `switch` | Add `break` after each case |

### 🪤 The Semicolon Trap

```javascript
let x = 1;

if (x > 5);
{
    console.log("This always runs!");
}
```

### 📤 Output

```text
This always runs!
```

The semicolon ends the `if` statement with an **empty body**, so the block below it is a separate block that always runs.

### 🪤 The Missing Braces Trap

```javascript
let x = 1;

if (x > 5)
    console.log("A");
    console.log("B");
```

### 📤 Output

```text
B
```

Without braces, **only the first statement** belongs to the `if`. The second line always runs, despite the indentation.

---

## 🧪 13. Practice Tasks

- [ ] 🟢 **Beginner:** Check whether a number is positive and print a message.
- [ ] 🟢 **Beginner:** Check whether a number is even or odd using `if-else`.
- [ ] 🟡 **Intermediate:** Print "Positive", "Negative", or "Zero" for a given number.
- [ ] 🟡 **Intermediate:** Find the largest of three numbers using `if-else`.
- [ ] 🔵 **Practice:** Convert marks into a grade (A, B, C, D, Fail) using an `else if` ladder.
- [ ] 🔵 **Practice:** Check whether a year is a leap year.
- [ ] 🔴 **Challenge:** Build a simple login check: print "Login successful" only if both username and password match, and tell the user which one is wrong otherwise.
- [ ] 🔴 **Challenge:** Create a webpage with an input for temperature and show "Cold", "Pleasant", or "Hot" using `else if`.

---

## 🎤 14. Viva Voce Questions and Answers

### 🟢 Basic Questions

**Q1. What is a conditional statement?**

**Answer:** A statement that lets a program execute different code depending on whether a condition is true or false.

**Q2. What is the syntax of an `if` statement?**

**Answer:** `if (condition) { // code }`

**Q3. What is the use of `else`?**

**Answer:** The `else` block runs when the `if` condition is false.

**Q4. When do we use `else if`?**

**Answer:** When there are more than two possible outcomes and we need to test multiple conditions in order.

**Q5. Can an `if` statement exist without an `else`?**

**Answer:** Yes. `else` is optional.

### 🟡 Intermediate Questions

**Q6. How many blocks of an `if-else if-else` ladder run?**

**Answer:** Only one: the first block whose condition is true. If none match, the `else` block runs.

**Q7. Why does the order of conditions matter in an `else if` ladder?**

**Answer:** Conditions are checked from top to bottom and the first true one wins, so a broad condition placed first can hide more specific ones.

**Q8. What are logical operators used for in conditions?**

**Answer:** `&&`, `||`, and `!` combine or reverse conditions, for example `age >= 18 && hasID`.

**Q9. What is a nested `if`?**

**Answer:** An `if` statement placed inside another `if` or `else` block.

**Q10. What are falsy values?**

**Answer:** Values treated as false in a condition: `false`, `0`, `""`, `null`, `undefined`, `NaN` (plus `-0` and `0n`).

**Q11. Is an empty array `[]` truthy or falsy?**

**Answer:** Truthy. To check whether an array is empty, use `arr.length`.

**Q12. What is the ternary operator?**

**Answer:** A short form of if-else: `condition ? valueIfTrue : valueIfFalse`.

### 🔵 Practical Questions

**Q13. What is the difference between `=`, `==`, and `===` in a condition?**

**Answer:** `=` assigns a value, `==` compares values with type conversion, and `===` compares value and type strictly. Use `===` in conditions.

**Q14. What is the output of the following code?**

```javascript
let x = 1;
if (x > 5);
{
    console.log("Hello");
}
```

**Answer:** `Hello`. The semicolon after the condition gives the `if` an empty body, so the block is a separate block that always runs.

**Q15. When should you use `switch` instead of `if-else`?**

**Answer:** When comparing a single value against many exact options. `if-else` is better for ranges and complex conditions.

**Q16. What happens if you forget `break` in a `switch`?**

**Answer:** Execution falls through into the next case and continues until a `break` or the end of the switch.

**Q17. How do you check that a number is between 18 and 60?**

**Answer:** `age >= 18 && age <= 60`. Writing `18 <= age <= 60` does not work as intended.

**Q18. What is a guard clause?**

**Answer:** An early `return` at the start of a function that handles invalid or special cases first, avoiding deep nesting.

---

## 🏆 15. Key Takeaways

- 🔀 Conditional statements let a program make decisions.
- ✅ `if` runs code when true, `else` when false, and `else if` handles extra cases.
- 🥇 In an `else if` ladder, the first true condition wins, so order matters.
- 🔗 Combine conditions with `&&`, `||`, and `!`.
- ⚖️ Use `===` for comparisons, never `=` inside a condition.
- ❓ The ternary operator is a compact if-else for simple values.
- 🔁 Use `switch` for one value with many exact options, and remember `break`.
- 🛡️ Guard clauses keep code flat and readable.
- 🧱 Always use curly braces `{ }` and never put a semicolon after the `if` condition.

---

### 🚀 Keep Practising!

> 💡 **Remember:** Every smart program, from a login page to a game, is built on simple yes-or-no decisions.

**Happy Coding! 💻✨**
