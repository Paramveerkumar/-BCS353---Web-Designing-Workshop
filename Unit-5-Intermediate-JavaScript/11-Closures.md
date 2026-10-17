# 🔒 Closures in JavaScript

A **closure** is created when a function remembers and can access variables from its outer scope, even after the outer function has finished executing.

In simple words, 🧠 **a closure allows a function to remember its surroundings.**

---

## 📌 1. Understanding Closures with a Simple Example

```javascript
function outer() {
    let message = "Hello Students!";

    function inner() {
        console.log(message);
    }

    return inner;
}

const result = outer();
result();
```

**Output:**

```text
Hello Students!
```

### 🔍 How does it work?

<box border radius="lg" padding={3} gap={2}>
  <box background="surface-secondary" radius="md" padding={3} align="center">
    **Step 1: `outer()` runs**

    <text color="secondary" size="sm">Creates the variable `message`.</text>
  </box>
  <box align="center">
    <icon name="arrow-down" size="lg"/>
  </box>
  <box background="surface-secondary" radius="md" padding={3} align="center">
    **Step 2: `inner` is returned**

    <text color="secondary" size="sm">The function retains access to its lexical environment.</text>
  </box>
  <box align="center">
    <icon name="arrow-down" size="lg"/>
  </box>
  <box background="surface" border radius="md" padding={3} align="center">
    **Step 3: `result()` runs**

    <text color="secondary" size="sm">It can still access and print `message`.</text>
  </box>
</box>

💡 **Important:** Returning a function does not execute it. It returns the function itself, which we can call later.

---

## 🧪 2. Closure with a Counter

One of the most common uses of closures is to create a private variable.

```javascript
function counter() {
    let count = 0;

    return function () {
        count++;
        console.log(count);
    };
}

const increment = counter();

increment();
increment();
increment();
```

**Output:**

```text
1
2
3
```

### 🔎 Dry Run

| Function call | Value before | Operation | Value after |
|---|---:|---|---:|
| `increment()` | 0 | `count++` | 1 |
| `increment()` | 1 | `count++` | 2 |
| `increment()` | 2 | `count++` | 3 |

**Why does `count` not reset to zero?**

Because all three calls use the same returned function and its retained lexical environment. The variable `count` remains accessible between calls.

---

## 🔐 3. Closures for Data Privacy

Closures can help protect data by keeping variables inaccessible directly from outside a function.

```javascript
function bankAccount() {
    let balance = 1000;

    return {
        deposit(amount) {
            balance += amount;
            console.log("Balance:", balance);
        },

        checkBalance() {
            console.log("Balance:", balance);
        }
    };
}

const account = bankAccount();

account.checkBalance();
account.deposit(500);
account.checkBalance();
```

**Output:**

```text
Balance: 1000
Balance: 1500
Balance: 1500
```

You cannot directly access `balance` using `account.balance`, because it is a local variable, not a property of the returned object.

💡 This pattern is useful for creating private state and controlling how data is modified.

---

## 🌍 4. Real-Life Example: Remembering a User's Name

```javascript
function greetUser(name) {
    return function () {
        console.log("Welcome back, " + name + "!");
    };
}

const greetParamveer = greetUser("Paramveer");

greetParamveer();
greetParamveer();
```

**Output:**

```text
Welcome back, Paramveer!
Welcome back, Paramveer!
```

Even after `greetUser()` finishes, the returned function can still access the `name` value associated with that particular call.

---

## ⚠️ 5. Common Mistake: Shared Closures in a Loop

Consider this example using `var`:

```javascript
var functions = [];

for (var i = 0; i < 3; i++) {
    functions.push(function () {
        console.log(i);
    });
}

functions[0]();
functions[1]();
functions[2]();
```

**Output:**

```text
3
3
3
```

### Why?

All three functions refer to the same `i` variable. By the time they run, the loop has finished and `i` is `3`.

### ✅ Solution: Use `let`

```javascript
const functions = [];

for (let i = 0; i < 3; i++) {
    functions.push(function () {
        console.log(i);
    });
}

functions[0]();
functions[1]();
functions[2]();
```

**Output:**

```text
0
1
2
```

With `let` in a `for` loop, each iteration gets its own binding for `i`, so each function remembers the corresponding value.

---

## 📊 6. Closure vs Normal Function

| Feature | Normal function | Function using a closure |
|---|---|---|
| Executes code | ✅ Yes | ✅ Yes |
| Can access local variables | ✅ Yes | ✅ Yes |
| Can retain access to outer variables | Depending on lexical scope and lifetime | ✅ Yes, when it retains access to its outer environment |
| Can maintain private state between calls | Not necessarily | ✅ Yes |
| Common use | Calculations and reusable operations | Counters, private data, callbacks |

**Remember:** A closure is not a special syntax or separate type of function. It is a function together with its retained lexical environment.

---

## 🎯 7. Where Are Closures Used?

- 🔢 Counters and state management
- 🔐 Data privacy
- ⏰ Callbacks and event handlers
- ⚙️ Function factories
- 🌐 Maintaining state in asynchronous operations
- 🧩 Implementing modules and reusable utilities

---

## 🎤 8. Viva Questions

**Q1. What is a closure in JavaScript?**

A closure is a function that retains access to variables from its surrounding lexical scope.

**Q2. Does a closure work after the outer function finishes?**

Yes. The inner function can continue accessing the variables it needs from the outer function's lexical environment.

**Q3. What is the main advantage of closures?**

They allow functions to retain state and provide a way to encapsulate data.

**Q4. What is lexical scope?**

Lexical scope determines variable accessibility based on where code is defined.

**Q5. Can closures modify outer variables?**

Yes, if those variables are accessible and mutable. For example, a closure can increment a retained `count` variable.

**Q6. Are closures useful in event handlers?**

Yes. An event handler can retain access to variables that were in scope when the handler was created.

**Q7. What is a practical use of closures?**

A counter function that remembers its count between calls.

**Q8. What is the difference between a closure and a callback?**

A callback is a function passed to another function to be called later. A callback may also use a closure if it accesses variables from its surrounding scope.

---

## 🧠 Final Summary

- A closure lets a function retain access to its surrounding lexical environment.
- The outer function can finish executing while the returned inner function still accesses its variables.
- Closures can preserve state between function calls.
- They are useful for privacy, callbacks, counters, and function factories.
- `let` in loops helps avoid the shared-binding behavior of `var`.

✨ **One-line definition for exams:** A closure is a function bundled with its lexical environment, allowing it to access variables from its outer scope even after the outer function has completed execution.
