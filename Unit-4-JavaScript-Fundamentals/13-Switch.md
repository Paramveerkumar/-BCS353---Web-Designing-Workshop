# 🔁 JavaScript switch Statement

> 🎯 **Learning Objectives**
> - Understand when and why we use `switch`.
> - Write a `switch` with `case`, `break`, and `default`.
> - Understand fall-through and use it to group cases.
> - Know that `switch` uses strict equality (`===`).
> - Use `switch(true)` for ranges and `return` inside functions.
> - Choose correctly between `switch` and `if-else`.

---

## 🌟 1. What is a switch Statement?

A **switch statement** compares **one value** against **many possible options** and runs the code of the matching one.

Think of a **lift (elevator) panel**. 🛗

| You press | The lift goes to |
|---|---|
| 1 | Ground floor |
| 2 | First floor |
| 3 | Second floor |
| Anything else | Shows an error |

One input, many fixed choices. That is exactly what `switch` is made for.

### 🧠 Remember This!

- `switch` checks **one value** against several `case` values.
- It uses **strict equality** (`===`) to compare.
- `break` stops the switch after a match.
- `default` runs when **no case matches**.

---

## 💻 2. Your First switch

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

- `switch (day)` evaluates `day` once.
- JavaScript compares it with `case 1`, `case 2`, `case 3` from top to bottom.
- `case 3` matches, so `"Wednesday"` prints.
- `break` exits the switch so the remaining cases are skipped.

### 🧩 Syntax

```javascript
switch (expression) {
    case value1:
        // code
        break;
    case value2:
        // code
        break;
    default:
        // code when nothing matches
}
```

💡 **Try It Yourself:** Change `day` to `7`. Which message appears and why?

---

## 🛑 3. The `default` Case

`default` works like the `else` of an `if-else` ladder.

```javascript
let color = "green";

switch (color) {
    case "red":
        console.log("Stop 🛑");
        break;
    case "yellow":
        console.log("Get ready ⚠️");
        break;
    case "green":
        console.log("Go ✅");
        break;
    default:
        console.log("Invalid colour ❌");
}
```

### 📤 Output

```text
Go ✅
```

- If `color` were `"blue"`, the output would be `Invalid colour ❌`.
- If there is **no** `default` and nothing matches, nothing happens.
- `default` is usually written **last**. If you put it elsewhere, add a `break` after it.

---

## 🌊 4. Fall-Through (What if `break` is Missing?)

Without `break`, execution **"falls through"** into the next case and keeps running until it reaches a `break` or the end of the switch.

```javascript
let n = 1;

switch (n) {
    case 1:
        console.log("A");
    case 2:
        console.log("B");
        break;
    case 3:
        console.log("C");
}
```

### 📤 Output

```text
A
B
```

### 🔍 Explanation

- `case 1` matches and prints `A`.
- There is no `break`, so JavaScript continues into `case 2` and prints `B`, even though `n` is not `2`.
- `break` in `case 2` finally stops it.

> ⚠️ Forgetting `break` is the **most common** switch bug.

### 🎯 Using Fall-Through on Purpose: Grouping Cases

When several cases should do the **same thing**, stack them together.

```javascript
let day = 6;

switch (day) {
    case 6:
    case 7:
        console.log("Weekend 🎉");
        break;
    case 1:
    case 2:
    case 3:
    case 4:
    case 5:
        console.log("Weekday 💼");
        break;
    default:
        console.log("Invalid day");
}
```

### 📤 Output

```text
Weekend 🎉
```

---

## ⚖️ 5. switch Uses Strict Equality

`switch` compares with `===`, so the **type must match** too.

```javascript
let x = "1";

switch (x) {
    case 1:
        console.log("number one");
        break;
    case "1":
        console.log("string one");
        break;
}
```

### 📤 Output

```text
string one
```

`"1"` (string) is **not** strictly equal to `1` (number), so only `case "1"` matches.

💡 This is a common problem when the value comes from an input box, because input values are **strings**. Convert first, for example `switch (Number(input))`.

---

## 🔙 6. switch Inside a Function with `return`

When a function returns from inside a `case`, you **don't need `break`**, because `return` already exits the function.

```javascript
function daysInMonth(month) {
    switch (month) {
        case 4:
        case 6:
        case 9:
        case 11:
            return 30;
        case 2:
            return "28 or 29";
        default:
            return 31;
    }
}

console.log(daysInMonth(4));
console.log(daysInMonth(2));
console.log(daysInMonth(12));
```

### 📤 Output

```text
30
28 or 29
31
```

---

## 📏 7. Ranges with `switch (true)`

A normal `switch` is meant for exact values, not ranges. A common pattern for ranges is `switch (true)`, where each case is a condition.

```javascript
let marks = 82;

switch (true) {
    case marks >= 90:
        console.log("Grade A");
        break;
    case marks >= 75:
        console.log("Grade B");
        break;
    case marks >= 60:
        console.log("Grade C");
        break;
    default:
        console.log("Grade D or Fail");
}
```

### 📤 Output

```text
Grade B
```

### 🔍 Explanation

- Each `case` expression (like `marks >= 90`) evaluates to `true` or `false`.
- JavaScript compares each result with `true` using `===` and runs the first match.
- Order matters, just like in an `else if` ladder.

> 💡 For ranges, a plain `else if` ladder is usually clearer. Use `switch (true)` only if you like the style.

---

## 🧱 8. Variables Inside Cases: Use Braces

All cases share **one block scope**. Declaring the same `let` or `const` name in two cases causes an error.

```javascript
let option = 1;

switch (option) {
    case 1:
        let message = "First";
        console.log(message);
        break;
    case 2:
        let message = "Second";   // ❌ SyntaxError
        console.log(message);
        break;
}
```

### 📤 Output

```text
SyntaxError: Identifier 'message' has already been declared
```

### ✅ Fix: Wrap Each Case in `{ }`

```javascript
switch (option) {
    case 1: {
        let message = "First";
        console.log(message);
        break;
    }
    case 2: {
        let message = "Second";
        console.log(message);
        break;
    }
}
```

### 📤 Output

```text
First
```

---

## 🧮 9. Mini Example: Simple Calculator

```javascript
function calculate(a, op, b) {
    switch (op) {
        case "+":
            return a + b;
        case "-":
            return a - b;
        case "*":
            return a * b;
        case "/":
            if (b === 0) {
                return "Cannot divide by zero ❌";
            }
            return a / b;
        default:
            return "Invalid operator ❌";
    }
}

console.log(calculate(10, "+", 5));
console.log(calculate(10, "-", 5));
console.log(calculate(10, "*", 5));
console.log(calculate(10, "/", 5));
console.log(calculate(10, "/", 0));
console.log(calculate(10, "%", 5));
```

### 📤 Output

```text
15
5
50
2
Cannot divide by zero ❌
Invalid operator ❌
```

### 🔍 What Happens?

- One value (`op`) is checked against fixed options, which is the perfect use for `switch`.
- Each `case` returns a result, so no `break` is needed.
- `default` handles any unknown operator.

---

## 🗺️ 10. An Alternative: Object Lookup

For simple "value → value" mappings, an object can be shorter than a switch.

```javascript
const dayNames = {
    1: "Monday",
    2: "Tuesday",
    3: "Wednesday"
};

let day = 3;
console.log(dayNames[day] ?? "Another day");
```

### 📤 Output

```text
Wednesday
```

---

## 🆚 11. `switch` vs `if-else`

| Feature | `switch` | `if-else` |
|---|---|---|
| Best for | One value with many **exact** options | Ranges and complex conditions |
| Comparison | Strict equality (`===`) only | Any condition (`>`, `<`, `&&`, `\|\|`) |
| Readability with many options | ✅ Cleaner | ❌ Long ladders |
| Needs `break` | ✅ Yes (unless using `return`) | ❌ No |
| Example | Day number, menu choice, operator | Marks to grade, age checks |

### 🧠 Quick Rule

- ✅ Checking **one variable against fixed values** → `switch`
- ✅ Checking **ranges or multiple different conditions** → `if-else`

---

## ⚠️ 12. Common Mistakes

| ❌ Mistake | ✅ Correct |
|---|---|
| Forgetting `break` | Add `break` after every case (or `return`) |
| `case marks >= 90:` in a normal `switch (marks)` | Use `switch (true)` or an `if-else` ladder |
| Comparing `"1"` with `case 1` | Convert the type, or write `case "1"` |
| Declaring the same `let` in two cases | Wrap each case in `{ }` |
| Forgetting `default` | Add `default` to handle unexpected values |
| Writing `case 1, 2:` for grouping | Write `case 1:` and `case 2:` on separate lines |
| Using `switch` for long ranges | Use `if-else` instead |

---

## 🧪 13. Practice Tasks

- [ ] 🟢 **Beginner:** Print the day name for numbers 1 to 7 using `switch`, with `default` for invalid numbers.
- [ ] 🟢 **Beginner:** Print "Vowel" or "Consonant" for a given letter. Use grouped cases for `a`, `e`, `i`, `o`, `u`.
- [ ] 🟡 **Intermediate:** Print the number of days in a month using grouped cases.
- [ ] 🟡 **Intermediate:** Remove the `break` from a case and explain the new output.
- [ ] 🔵 **Practice:** Write a function that takes a traffic light colour and returns the action to take.
- [ ] 🔵 **Practice:** Convert marks to a grade using `switch (true)`.
- [ ] 🔴 **Challenge:** Build a webpage with a dropdown of fruits that shows the price of the selected fruit using `switch`.
- [ ] 🔴 **Challenge:** Create a calculator webpage with two inputs and an operator dropdown, using `switch` to calculate the result.

---

## 🎤 14. Viva Voce Questions and Answers

### 🟢 Basic Questions

**Q1. What is a `switch` statement?**

**Answer:** A control statement that compares one value against multiple `case` values and executes the code of the matching case.

**Q2. What is the syntax of `switch`?**

**Answer:** `switch (expression) { case value: // code; break; default: // code }`

**Q3. What is the use of `break` in a `switch`?**

**Answer:** It stops execution of the switch after a case runs, preventing fall-through into the next cases.

**Q4. What is the use of `default`?**

**Answer:** It runs when none of the cases match, similar to `else` in an `if-else` ladder.

**Q5. Is `default` mandatory?**

**Answer:** No, it is optional. If it is missing and nothing matches, nothing happens.

### 🟡 Intermediate Questions

**Q6. What is fall-through?**

**Answer:** When a case has no `break`, execution continues into the next case, running its code too, until a `break` or the end of the switch is reached.

**Q7. How can you run the same code for multiple cases?**

**Answer:** Stack the cases together without `break` between them, for example `case 6: case 7: console.log("Weekend"); break;`.

**Q8. Which type of comparison does `switch` use?**

**Answer:** Strict equality (`===`), so both value and type must match.

**Q9. What is the output of the following code?**

```javascript
let x = "5";
switch (x) {
    case 5:
        console.log("number");
        break;
    default:
        console.log("no match");
}
```

**Answer:** `no match`, because `"5"` is not strictly equal to `5`.

**Q10. When would you choose `switch` over `if-else`?**

**Answer:** When comparing one value against many exact, fixed options, since `switch` is cleaner and easier to read than a long `else if` ladder.

**Q11. Can a `switch` be used for ranges like `marks >= 90`?**

**Answer:** Not directly. You can use the `switch (true)` pattern, but an `if-else` ladder is usually clearer for ranges.

### 🔵 Practical Questions

**Q12. What is the output of the following code?**

```javascript
let n = 1;
switch (n) {
    case 1:
        console.log("A");
    case 2:
        console.log("B");
        break;
    case 3:
        console.log("C");
}
```

**Answer:** `A` followed by `B`, because `case 1` has no `break` and falls through into `case 2`.

**Q13. Do you need `break` when you use `return` inside a case?**

**Answer:** No. `return` exits the function immediately, so `break` is not needed.

**Q14. Why does declaring the same `let` variable in two cases cause an error?**

**Answer:** All cases share a single block scope. Wrapping each case in curly braces `{ }` gives each its own scope.

**Q15. Does the order of cases matter?**

**Answer:** Yes for fall-through and for the `switch (true)` pattern, because the first match wins. For exact-value cases, order does not change which one matches.

**Q16. Can `default` appear in the middle of a switch?**

**Answer:** Yes, but it is conventionally placed last. If it is not last, it needs a `break` to prevent falling through into the following cases.

**Q17. What is an alternative to a `switch` that maps values to results?**

**Answer:** An object lookup, for example `const names = { 1: "Monday" }; names[day]`.

---

## 🏆 15. Key Takeaways

- 🔁 `switch` compares one value against many exact options.
- ⚖️ It uses strict equality (`===`), so types must match.
- 🛑 Use `break` after each case to stop fall-through.
- 🌊 Fall-through is useful for grouping cases that share the same code.
- 🧱 `default` handles unmatched values.
- 🔙 Inside functions, `return` replaces `break`.
- 📏 For ranges, prefer `if-else` (or `switch (true)` if you like).
- 🧩 Wrap cases in `{ }` when declaring variables inside them.

---

### 🚀 Keep Practising!

> 💡 **Remember:** When you see a long chain of `else if` checking the same variable against fixed values, think `switch`.

**Happy Coding! 💻✨**
