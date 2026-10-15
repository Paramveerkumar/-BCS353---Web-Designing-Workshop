# 🔄 JavaScript for Loop

> 🎯 **Learning Objectives**
> - Understand why programs need loops.
> - Write a `for` loop using initialisation, condition, and update.
> - Trace how a `for` loop executes step by step.
> - Use `break` and `continue` to control a loop.
> - Loop through arrays and strings.
> - Write nested loops to create patterns.
> - Avoid common mistakes like infinite loops and off-by-one errors.

---

## 🌟 1. What is a Loop?

A **loop** repeats a block of code multiple times, so you don't have to write the same code again and again.

Imagine a **teacher taking attendance**. 📋

| Without a loop | With a loop |
|---|---|
| Call student 1, call student 2, call student 3 ... (60 times) | "For each student from 1 to 60, call the name" |

### 🤔 Why Do We Need Loops?

- ♻️ Avoid repeating code.
- 📈 Process large amounts of data (100 or 10,000 items).
- 🧮 Perform calculations such as sums and tables.
- 📚 Work through every item of an array.

### 🧠 Remember This!

- Use a **`for` loop** when you know **how many times** to repeat.
- One run of the loop body is called an **iteration**.

---

## 💻 2. Your First for Loop

```javascript
for (let i = 1; i <= 5; i++) {
    console.log(i);
}
```

### 📤 Output

```text
1
2
3
4
5
```

### 🧩 Syntax

```javascript
for (initialisation; condition; update) {
    // code to repeat
}
```

### 🔍 Explanation

| Part | Code | Purpose |
|---|---|---|
| 1️⃣ **Initialisation** | `let i = 1` | Creates the counter. Runs **once** at the start |
| 2️⃣ **Condition** | `i <= 5` | Checked **before every iteration**. The loop runs while it is `true` |
| 3️⃣ **Update** | `i++` | Runs **after every iteration** (increases `i` by 1) |
| 🔁 **Body** | `console.log(i);` | The code that repeats |

💡 **Try It Yourself:** Change `5` to `10`, then change `i = 1` to `i = 0`, and watch the output change.

---

## 🧭 3. How a for Loop Runs (Step by Step)

```javascript
for (let i = 1; i <= 3; i++) {
    console.log("Round " + i);
}
console.log("Done");
```

### 🔍 Execution Trace

| Step | What happens | `i` | Output |
|---|---|---|---|
| 1 | Initialisation: `let i = 1` (once) | 1 | |
| 2 | Check `1 <= 3` → true | 1 | |
| 3 | Run body | 1 | `Round 1` |
| 4 | Update `i++` | 2 | |
| 5 | Check `2 <= 3` → true | 2 | |
| 6 | Run body | 2 | `Round 2` |
| 7 | Update `i++` | 3 | |
| 8 | Check `3 <= 3` → true | 3 | |
| 9 | Run body | 3 | `Round 3` |
| 10 | Update `i++` | 4 | |
| 11 | Check `4 <= 3` → **false**, so the loop ends | 4 | |
| 12 | Continue after the loop | | `Done` |

### 📤 Output

```text
Round 1
Round 2
Round 3
Done
```

---

## 🎛️ 4. Variations of the for Loop

### ⬇️ Counting Down

```javascript
for (let i = 5; i >= 1; i--) {
    console.log(i);
}
console.log("Liftoff 🚀");
```

### 📤 Output

```text
5
4
3
2
1
Liftoff 🚀
```

### ⏭️ Counting in Steps

```javascript
for (let i = 0; i <= 10; i += 2) {
    console.log(i);
}
```

### 📤 Output

```text
0
2
4
6
8
10
```

### ➕ Sum of Numbers from 1 to 10

```javascript
let sum = 0;

for (let i = 1; i <= 10; i++) {
    sum += i;
}

console.log("Sum = " + sum);
```

### 📤 Output

```text
Sum = 55
```

### 🔍 How the Sum Builds Up

```text
Start:   sum = 0
i = 1:   sum = 0 + 1 = 1
i = 2:   sum = 1 + 2 = 3
i = 3:   sum = 3 + 3 = 6
...
i = 10:  sum = 45 + 10 = 55
```

### ✖️ Multiplication Table

```javascript
let number = 5;

for (let i = 1; i <= 5; i++) {
    console.log(`${number} x ${i} = ${number * i}`);
}
```

### 📤 Output

```text
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
```

### ❗ Factorial of 5

```javascript
let factorial = 1;

for (let i = 1; i <= 5; i++) {
    factorial *= i;
}

console.log(factorial);
```

### 📤 Output

```text
120
```

---

## 📚 5. Looping Through Arrays and Strings

### 📚 Array

```javascript
const fruits = ["Apple", "Banana", "Mango"];

for (let i = 0; i < fruits.length; i++) {
    console.log(i + ": " + fruits[i]);
}
```

### 📤 Output

```text
0: Apple
1: Banana
2: Mango
```

> 💡 Array indexes start at `0`, so the condition is `i < fruits.length` (**less than**, not less than or equal to).

### 🔤 String

```javascript
let word = "JavaScript";
let vowels = 0;

for (let i = 0; i < word.length; i++) {
    if ("aeiou".includes(word[i].toLowerCase())) {
        vowels++;
    }
}

console.log("Vowels: " + vowels);
```

### 📤 Output

```text
Vowels: 3
```

The vowels in `"JavaScript"` are `a`, `a`, and `i`.

---

## 🛑 6. `break` and `continue`

### 🛑 `break`: Stop the Loop Completely

```javascript
for (let i = 1; i <= 10; i++) {
    if (i === 5) {
        break;
    }
    console.log(i);
}
```

### 📤 Output

```text
1
2
3
4
```

### ⏭️ `continue`: Skip the Current Iteration

```javascript
for (let i = 1; i <= 5; i++) {
    if (i === 3) {
        continue;
    }
    console.log(i);
}
```

### 📤 Output

```text
1
2
4
5
```

### 🆚 Comparison

| Keyword | Effect |
|---|---|
| `break` | Exits the **whole loop** immediately |
| `continue` | Skips the rest of **this iteration** and moves to the next one |

---

## 🪆 7. Nested Loops

A loop **inside** another loop. The inner loop runs **completely** for every single iteration of the outer loop.

### ⭐ Star Pattern

```javascript
for (let i = 1; i <= 4; i++) {
    let row = "";

    for (let j = 1; j <= i; j++) {
        row += "*";
    }

    console.log(row);
}
```

### 📤 Output

```text
*
**
***
****
```

### 🔍 Explanation

| Outer `i` | Inner loop runs | Row printed |
|---|---|---|
| 1 | `j = 1` | `*` |
| 2 | `j = 1, 2` | `**` |
| 3 | `j = 1, 2, 3` | `***` |
| 4 | `j = 1, 2, 3, 4` | `****` |

💡 Think of a **clock**: the minute hand (inner loop) completes a full circle for every single step of the hour hand (outer loop).

### 🔢 Multiplication Grid

```javascript
for (let i = 1; i <= 3; i++) {
    let row = "";

    for (let j = 1; j <= 3; j++) {
        row += i * j + "\t";
    }

    console.log(row);
}
```

### 📤 Output

```text
1	2	3
2	4	6
3	6	9
```

---

## 🔭 8. Loop Variable Scope: `let` vs `var`

```javascript
for (let i = 0; i < 3; i++) {
    // loop body
}
console.log(i);   // ❌ ReferenceError
```

### 📤 Output

```text
ReferenceError: i is not defined
```

```javascript
for (var j = 0; j < 3; j++) {
    // loop body
}
console.log(j);   // 3
```

### 📤 Output

```text
3
```

- `let` keeps the counter **inside** the loop. ✅
- `var` lets the counter **leak** outside the loop. ⚠️

### 🎁 Bonus: Why `let` is Safer with Delays

```javascript
for (var a = 0; a < 3; a++) {
    setTimeout(() => console.log("var:", a), 0);
}

for (let b = 0; b < 3; b++) {
    setTimeout(() => console.log("let:", b), 0);
}
```

### 📤 Output

```text
var: 3
var: 3
var: 3
let: 0
let: 1
let: 2
```

With `let`, each iteration gets its **own copy** of the counter. With `var`, all iterations share one variable, which is already `3` by the time the delayed code runs.

---

## 🔀 9. Other Ways to Write a for Loop

### 🔁 `for...of`: Loop Over Values

Works with arrays, strings, and other iterables. No counter needed.

```javascript
for (const fruit of ["Apple", "Banana"]) {
    console.log(fruit);
}

for (const ch of "Hi") {
    console.log(ch);
}
```

### 📤 Output

```text
Apple
Banana
H
i
```

### 🗝️ `for...in`: Loop Over Object Keys

```javascript
const student = { name: "Aman", age: 20 };

for (const key in student) {
    console.log(key + ": " + student[key]);
}
```

### 📤 Output

```text
name: Aman
age: 20
```

> ⚠️ Don't use `for...in` for arrays. Use `for...of` or a normal `for` loop.

### 📊 Which Loop to Use?

| Loop | Best for |
|---|---|
| `for` | When you need the **index** or a specific number of repetitions |
| `for...of` | Reading every **value** of an array or string |
| `for...in` | Going through the **keys** of an object |

---

## 🧮 10. Mini Examples

### 🔢 Sum of Even Numbers from 1 to 20

```javascript
let total = 0;

for (let i = 2; i <= 20; i += 2) {
    total += i;
}

console.log(total);
```

### 📤 Output

```text
110
```

### 🔍 Prime Number Checker

```javascript
function isPrime(n) {
    if (n < 2) {
        return false;
    }

    for (let i = 2; i * i <= n; i++) {
        if (n % i === 0) {
            return false;
        }
    }

    return true;
}

console.log(isPrime(7));
console.log(isPrime(10));
console.log(isPrime(1));
```

### 📤 Output

```text
true
false
false
```

### 🔍 What Happens?

- A prime number has no divisors other than `1` and itself.
- The loop tests divisors from `2` upward. It only needs to go until `i * i <= n`.
- The moment a divisor is found, `return false` ends both the loop and the function.

---

## ⚠️ 11. Common Mistakes

| ❌ Mistake | ✅ Correct |
|---|---|
| Forgetting `i++`, which causes an **infinite loop** | Always make sure the counter moves towards the end condition |
| `i <= arr.length` when looping an array | Use `i < arr.length` |
| `for (...);` with a semicolon at the end | `for (...) { ... }` |
| Using `=` in the condition: `i = 5` | Use a comparison: `i <= 5` |
| Changing the counter inside the body unexpectedly | Update the counter only in the update part |
| Using `for...in` on arrays | Use `for...of` or a normal `for` |
| Using `var` for the loop counter | Use `let` |

### 🪤 Off-by-One Error

```javascript
const arr = [10, 20, 30];

for (let i = 0; i <= arr.length; i++) {
    console.log(arr[i]);
}
```

### 📤 Output

```text
10
20
30
undefined
```

The array has indexes `0, 1, 2`, but the loop also tries `3`.

### 🪤 The Semicolon Trap

```javascript
for (let i = 0; i < 3; i++);
{
    console.log("Hi");
}
```

### 📤 Output

```text
Hi
```

The semicolon gives the loop an **empty body**, so the block below runs only **once**, after the loop finishes.

### 🪤 Infinite Loop (Do Not Run!)

```javascript
for (let i = 1; i <= 5; ) {
    console.log(i);     // i never changes, so the condition is always true
}
```

⚠️ This freezes the tab or program. If it happens, close the tab or stop the program.

---

## 🧪 12. Practice Tasks

- [ ] 🟢 **Beginner:** Print numbers from 1 to 10.
- [ ] 🟢 **Beginner:** Print your name 5 times using a loop.
- [ ] 🟡 **Intermediate:** Print the multiplication table of any number up to 10.
- [ ] 🟡 **Intermediate:** Print all even numbers between 1 and 50.
- [ ] 🔵 **Practice:** Find the sum and average of the numbers from 1 to 100.
- [ ] 🔵 **Practice:** Loop through an array of marks and print the highest one.
- [ ] 🔵 **Practice:** Count how many times the letter `a` appears in a sentence.
- [ ] 🔴 **Challenge:** Print the Fibonacci series for the first 10 numbers (0, 1, 1, 2, 3, 5, ...).
- [ ] 🔴 **Challenge:** Print a number triangle using nested loops:

```text
1
12
123
1234
```

---

## 🎤 13. Viva Voce Questions and Answers

### 🟢 Basic Questions

**Q1. What is a loop?**

**Answer:** A loop is a control structure that repeats a block of code multiple times.

**Q2. What is the syntax of a `for` loop?**

**Answer:** `for (initialisation; condition; update) { // code }`

**Q3. What are the three parts of a `for` loop?**

**Answer:** Initialisation (runs once at the start), condition (checked before each iteration), and update (runs after each iteration).

**Q4. What is an iteration?**

**Answer:** One complete execution of the loop body.

**Q5. When should you use a `for` loop?**

**Answer:** When you know in advance how many times the code should repeat, or when you need to work through a range or an array by index.

### 🟡 Intermediate Questions

**Q6. In what order do the parts of a `for` loop execute?**

**Answer:** Initialisation (once), then condition check, then body, then update, then condition check again, and so on until the condition is false.

**Q7. What is the difference between `break` and `continue`?**

**Answer:** `break` exits the loop completely, while `continue` skips the remaining code of the current iteration and moves on to the next one.

**Q8. What is an infinite loop?**

**Answer:** A loop whose condition never becomes false, so it never stops, for example when the update step is missing.

**Q9. Why do we use `i < arr.length` and not `i <= arr.length`?**

**Answer:** Array indexes go from `0` to `length - 1`. Using `<=` would access an index that does not exist and give `undefined`.

**Q10. What is a nested loop?**

**Answer:** A loop placed inside another loop. The inner loop completes all its iterations for each iteration of the outer loop.

**Q11. What is the difference between `for`, `for...of`, and `for...in`?**

**Answer:** `for` uses a counter, `for...of` iterates over the values of an iterable (arrays, strings), and `for...in` iterates over the keys of an object.

**Q12. Why is `let` preferred over `var` in a `for` loop?**

**Answer:** `let` is block-scoped, so the counter does not leak outside the loop, and each iteration gets its own copy of the variable.

### 🔵 Practical Questions

**Q13. What is the output of the following code?**

```javascript
for (let i = 1; i <= 5; i++) {
    if (i === 3) continue;
    console.log(i);
}
```

**Answer:** `1 2 4 5`, each on a new line. The value `3` is skipped.

**Q14. How many times will this loop run?**

```javascript
for (let i = 0; i < 10; i += 2) {
    console.log(i);
}
```

**Answer:** 5 times (for `i` = 0, 2, 4, 6, 8).

**Q15. Write a loop to find the sum of numbers from 1 to 100.**

**Answer:**

```javascript
let sum = 0;
for (let i = 1; i <= 100; i++) {
    sum += i;
}
console.log(sum);
```

The result is `5050`.

**Q16. What is wrong with `for (let i = 0; i < 3; i++);`?**

**Answer:** The semicolon at the end gives the loop an empty body, so the block that follows is not part of the loop and runs only once.

**Q17. Can any part of a `for` loop be omitted?**

**Answer:** Yes. For example, `for (;;) { ... }` is an infinite loop that must be stopped with `break`. However, omitting parts reduces readability.

**Q18. What is the output of the following code?**

```javascript
for (let i = 1; i <= 3; i++) {
    let row = "";
    for (let j = 1; j <= i; j++) {
        row += "*";
    }
    console.log(row);
}
```

**Answer:**

```text
*
**
***
```

---

## 🏆 14. Key Takeaways

- 🔄 A loop repeats code, so you don't have to write it many times.
- 🧩 A `for` loop has three parts: initialisation, condition, and update.
- 🧭 The condition is checked **before** every iteration, and the update runs **after** it.
- 🛑 `break` exits the loop; `continue` skips to the next iteration.
- 📚 Use `i < array.length` to loop through arrays.
- 🪆 In nested loops, the inner loop runs fully for each outer iteration.
- ✅ Use `let` for the counter, and use `for...of` when you only need the values.
- ⚠️ Beware of infinite loops, off-by-one errors, and a stray semicolon after `for (...)`.

---

### 🚀 Keep Practising!

> 💡 **Remember:** Loops turn a few lines of code into thousands of operations, which is where a computer's real power shows.

**Happy Coding! 💻✨**
