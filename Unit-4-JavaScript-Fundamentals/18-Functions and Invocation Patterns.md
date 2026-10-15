# 🎭 JavaScript Functions and Invocation Patterns

> 🎯 **Learning Objectives**
> - Understand what "invocation" means and why *how* a function is called matters.
> - Understand how the value of `this` is decided.
> - Use the four invocation patterns: function, method, constructor, and indirect (`call`, `apply`, `bind`).
> - Understand how arrow functions handle `this`.
> - Use IIFEs, callbacks, higher-order functions, closures, and recursion.
> - Avoid the classic "lost `this`" bug.

---

## 🌟 1. What is Invocation?

**Invoking** (or **calling**) a function means running it. The surprising part of JavaScript is this:

> 🔑 **The value of `this` inside a function is decided by *how the function is called*, not by where it is written.**

Think of the word **"I"** in English. 🗣️

| Situation | Who does "I" mean? |
|---|---|
| Aman says "I am hungry" | Aman |
| Priya says "I am hungry" | Priya |

The sentence is the same, but "I" changes with **who is speaking**. In JavaScript, `this` is like "I": it changes with **who is calling**.

### 🗂️ The Invocation Patterns at a Glance

| Pattern | How it looks | `this` is... |
|---|---|---|
| 1️⃣ **Function invocation** | `greet()` | `undefined` (strict mode) or the global object (sloppy mode) |
| 2️⃣ **Method invocation** | `student.greet()` | The object before the dot (`student`) |
| 3️⃣ **Constructor invocation** | `new Student()` | A brand-new object |
| 4️⃣ **Indirect invocation** | `greet.call(obj)` | Whatever you pass in |
| ➡️ **Arrow function** | `() => { ... }` | Inherited from the surrounding code (no own `this`) |

### 🧠 Remember This!

- Look at the **call site** (the place where the function is called) to find `this`.
- Arrow functions are the exception: they look at where they were **written**.

---

## 🔁 2. Quick Recap: Defining Functions

```javascript
function add(a, b) {            // declaration
    return a + b;
}

const multiply = function (a, b) {   // function expression
    return a * b;
};

const subtract = (a, b) => a - b;    // arrow function

console.log(add(5, 3));
console.log(multiply(5, 3));
console.log(subtract(5, 3));
```

### 📤 Output

```text
8
15
2
```

### ⚠️ Missing and Extra Arguments

```javascript
console.log(add(2));
console.log(add(2, 3, 99));
```

### 📤 Output

```text
NaN
5
```

- A missing argument becomes `undefined`, so `2 + undefined` is `NaN`.
- Extra arguments are simply ignored.

---

## 1️⃣ 3. Function Invocation Pattern

A plain call with nothing before it.

```javascript
function showThis() {
    console.log(this === globalThis);
}

showThis();
```

### 📤 Output

```text
true
```

In a normal (sloppy-mode) script, `this` inside a plain function is the **global object** (`window` in a browser).

### 🔒 Strict Mode Changes It

```javascript
function showThisStrict() {
    "use strict";
    console.log(this);
}

showThisStrict();
```

### 📤 Output

```text
undefined
```

In **strict mode**, `this` is `undefined` instead of the global object. Code inside **classes** and **ES modules** (`<script type="module">`) is always strict.

> 💡 Strict mode is safer because it stops you from accidentally reading or creating global variables through `this`.

---

## 2️⃣ 4. Method Invocation Pattern

A function stored as a property of an object, called with a dot.

```javascript
const student = {
    name: "Aman",
    greet() {
        console.log("Hi, I am " + this.name);
    }
};

student.greet();
```

### 📤 Output

```text
Hi, I am Aman
```

### 🔍 Explanation

- The call is `student.greet()`, so `this` is whatever is **before the dot**: `student`.
- `this.name` therefore means `student.name`.

### 🔁 Same Function, Different Owners

```javascript
function introduce() {
    console.log("I am " + this.name);
}

const a = { name: "Aman", introduce };
const b = { name: "Priya", introduce };

a.introduce();
b.introduce();
```

### 📤 Output

```text
I am Aman
I am Priya
```

One function, two different `this` values, just like the word "I".

### 🪤 The Classic Bug: Losing `this`

```javascript
"use strict";

const student = {
    name: "Aman",
    greet() {
        console.log("Hi, I am " + this.name);
    }
};

const saved = student.greet;   // copy the function out of the object
saved();                       // plain call, with nothing before the dot
```

### 📤 Output

```text
TypeError: Cannot read properties of undefined (reading 'name')
```

### 🔍 Explanation

- `saved()` has **no object before the dot**, so it is a **function invocation**, and `this` is `undefined`.
- (In sloppy mode there would be no crash. `this` would be the global object, and `this.name` would silently be the wrong value.)

The same thing happens when you **pass a method as a callback**:

```javascript
setTimeout(student.greet, 1000);   // ❌ this is lost
```

### 🛠️ Three Ways to Fix It

```javascript
saved = student.greet.bind(student);          // 1. bind
student.greet();                              // 2. call it with the object
setTimeout(() => student.greet(), 1000);      // 3. wrap it in an arrow function
```

---

## 3️⃣ 5. Constructor Invocation Pattern

Calling a function with the **`new`** keyword makes it a **constructor** that builds objects.

```javascript
function Student(name, age) {
    this.name = name;
    this.age = age;
}

const s1 = new Student("Aman", 20);
const s2 = new Student("Priya", 22);

console.log(s1);
console.log(s2.name);
```

### 📤 Output

```text
Student { name: 'Aman', age: 20 }
Priya
```

### 🔍 What `new` Does (4 Steps)

| Step | Action |
|---|---|
| 1️⃣ | Creates a new empty object |
| 2️⃣ | Links that object to the constructor's prototype |
| 3️⃣ | Runs the function with `this` set to the new object |
| 4️⃣ | Returns the new object (unless the function returns a different object) |

> 📝 **Convention:** Constructor names start with a **capital letter** (`Student`, not `student`).

### 🪤 Forgetting `new`

```javascript
"use strict";

function Student(name) {
    this.name = name;
}

const s = Student("Aman");   // ❌ no new
```

### 📤 Output

```text
TypeError: Cannot set properties of undefined (setting 'name')
```

Without `new`, it is a plain function call, so `this` is `undefined`. (In sloppy mode it would silently create a global variable `name`, which is even worse.)

### ✨ The Modern Way: `class`

A class is cleaner syntax for the same idea.

```javascript
class Student {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }

    greet() {
        return "Hi, I am " + this.name;
    }
}

const s = new Student("Riya", 21);
console.log(s.greet());
```

### 📤 Output

```text
Hi, I am Riya
```

```javascript
Student("Riya", 21);   // ❌ forgot new
```

### 📤 Output

```text
TypeError: Class constructor Student cannot be invoked without 'new'
```

Classes **refuse** to run without `new`, which prevents the mistake above.

---

## 4️⃣ 6. Indirect Invocation: `call`, `apply`, `bind`

These methods let **you** choose what `this` is.

```javascript
function intro(city, country) {
    console.log(`${this.name} from ${city}, ${country}`);
}

const person = { name: "Aman" };
```

### 📞 `call(thisArg, arg1, arg2, ...)`: Calls immediately, arguments listed one by one

```javascript
intro.call(person, "Delhi", "India");
```

### 📤 Output

```text
Aman from Delhi, India
```

### 📋 `apply(thisArg, [args])`: Calls immediately, arguments in an **array**

```javascript
intro.apply(person, ["Mumbai", "India"]);
```

### 📤 Output

```text
Aman from Mumbai, India
```

### 🔗 `bind(thisArg, ...)`: Does **not** call. Returns a **new function** with `this` fixed

```javascript
const boundIntro = intro.bind(person, "Pune");
boundIntro("India");
```

### 📤 Output

```text
Aman from Pune, India
```

### 📊 Comparison

| Method | Calls the function? | Arguments | Returns |
|---|---|---|---|
| `call` | ✅ Immediately | One by one: `f.call(obj, a, b)` | The function's result |
| `apply` | ✅ Immediately | As an array: `f.apply(obj, [a, b])` | The function's result |
| `bind` | ❌ Later | Can pre-fill some: `f.bind(obj, a)` | A **new function** |

💡 **Memory trick:** **A**pply takes an **A**rray. **C**all takes **c**omma-separated values. **B**ind **b**uilds a new function for **b**ackup use later.

### 🧰 A Handy Use: Borrowing a Method

```javascript
console.log(Math.max.apply(null, [4, 9, 2]));
console.log(Math.max(...[4, 9, 2]));   // modern alternative using spread
```

### 📤 Output

```text
9
9
```

---

## ➡️ 7. Arrow Functions and `this`

Arrow functions do **not** have their own `this`. They use the `this` of the code **around** them (called **lexical `this`**).

### ✅ Where Arrow Functions Help

```javascript
const team = {
    name: "Dev Team",
    members: ["Aman", "Priya"],

    showMembers() {
        this.members.forEach((member) => {
            console.log(`${member} is in ${this.name}`);
        });
    }
};

team.showMembers();
```

### 📤 Output

```text
Aman is in Dev Team
Priya is in Dev Team
```

The arrow function inherits `this` from `showMembers()`, where `this` is `team`.

### ❌ The Same Code with a Regular Function Callback

```javascript
"use strict";

const team = {
    name: "Dev Team",
    members: ["Aman", "Priya"],

    showMembers() {
        this.members.forEach(function (member) {
            console.log(`${member} is in ${this.name}`);
        });
    }
};

team.showMembers();
```

### 📤 Output

```text
TypeError: Cannot read properties of undefined (reading 'name')
```

The callback is called as a **plain function** by `forEach`, so its own `this` is `undefined`.

### ❌ Where Arrow Functions Hurt

**1. As object methods:**

```javascript
const person = {
    name: "Aman",
    sayHi: () => {
        console.log(this.name);    // ❌ this is NOT person
    }
};

person.sayHi();   // does not print "Aman"
```

The arrow function takes `this` from the surrounding code (not the object), so it does not print `"Aman"`.

**2. As constructors:**

```javascript
const Point = (x, y) => {
    this.x = x;
    this.y = y;
};

new Point(1, 2);
```

### 📤 Output

```text
TypeError: Point is not a constructor
```

### 🧭 Regular vs Arrow Functions

| Feature | Regular function | Arrow function |
|---|---|---|
| Own `this` | ✅ Yes (depends on the call) | ❌ No (inherits from outside) |
| Can use `new` | ✅ Yes | ❌ No |
| Has `arguments` object | ✅ Yes | ❌ No |
| Good as an object method | ✅ Yes | ❌ No |
| Good as a callback | OK | ✅ Great |

### 🖱️ Event Handlers

```javascript
button.addEventListener("click", function () {
    console.log(this === button);     // true: this is the element
});

button.addEventListener("click", () => {
    console.log(this === button);     // false: arrow keeps the outer this
});
```

---

## 🧩 8. Putting It Together: How is `this` Decided?

Check these in order and use the **first one that applies**:

| Order | Question | `this` is... |
|---|---|---|
| 1️⃣ | Is it an **arrow function**? | The `this` of the surrounding code (stop here) |
| 2️⃣ | Called with **`new`**? | The newly created object |
| 3️⃣ | Called with **`call` / `apply` / `bind`**? | The object you passed |
| 4️⃣ | Called as a **method** `obj.fn()`? | `obj` |
| 5️⃣ | Plain call `fn()`? | `undefined` (strict) or the global object (sloppy) |

---

## ⚡ 9. IIFE: Immediately Invoked Function Expression

A function that is **defined and called at the same moment**.

```javascript
(function () {
    const secret = "I am private";
    console.log("This runs immediately ✅");
    console.log(secret);
})();

// Arrow version
(() => {
    console.log("Arrow IIFE ✅");
})();

console.log(typeof secret);
```

### 📤 Output

```text
This runs immediately ✅
I am private
Arrow IIFE ✅
undefined
```

### 🔍 Explanation

- The parentheses around the function turn it into an **expression**.
- The final `()` **calls** it right away.
- Variables inside are **private**, because the function creates its own scope. `secret` is not visible outside.

### 🎯 Why Use an IIFE?

- 🔒 Avoid polluting the global scope.
- 🧪 Run one-time setup code.
- 🧱 Create private variables (an older pattern; modules and closures now cover most uses).

---

## 🔁 10. Callbacks and Higher-Order Functions

In JavaScript, **functions are values**. You can pass them to other functions and return them from functions.

### 📞 Callback: A Function Passed to Another Function

```javascript
function processList(items, callback) {
    for (const item of items) {
        callback(item);
    }
}

processList(["Aman", "Priya"], (name) => console.log("Hello, " + name));
```

### 📤 Output

```text
Hello, Aman
Hello, Priya
```

### 🔝 Higher-Order Function: Takes or Returns a Function

```javascript
function multiplier(factor) {
    return function (n) {
        return n * factor;
    };
}

const double = multiplier(2);
const triple = multiplier(3);

console.log(double(5));
console.log(triple(5));
```

### 📤 Output

```text
10
15
```

### 🔍 Explanation

- `multiplier` is a higher-order function because it **returns** a function.
- Each returned function **remembers** its own `factor`. That is a **closure**, explained next.

### 🔄 Sync vs Async Callbacks

```javascript
console.log("1: start");

[1, 2].forEach((n) => console.log("2: forEach " + n));   // runs immediately

setTimeout(() => console.log("3: timeout"), 0);          // runs later

console.log("4: end");
```

### 📤 Output

```text
1: start
2: forEach 1
2: forEach 2
4: end
3: timeout
```

A callback given to `setTimeout` always runs **after** the current code finishes, even with a delay of `0`.

---

## 🔒 11. Closures

A **closure** is a function that **remembers the variables from the place where it was created**, even after that outer function has finished.

Think of a **backpack**. 🎒 When a function is created, it packs the variables it needs into its backpack and carries them everywhere.

```javascript
function makeCounter() {
    let count = 0;

    return function () {
        count++;
        return count;
    };
}

const counter1 = makeCounter();
const counter2 = makeCounter();

console.log(counter1());
console.log(counter1());
console.log(counter1());
console.log(counter2());
```

### 📤 Output

```text
1
2
3
1
```

### 🔍 Explanation

- `makeCounter()` finished running, but the returned function **still remembers `count`**.
- Each call to `makeCounter()` creates a **separate** `count`, so `counter2` starts again from 1.
- Nothing outside can touch `count` directly. It is **private**.

### 🏦 Mini Example: Private Bank Account

```javascript
function createAccount(initial) {
    let balance = initial;     // private variable

    return {
        deposit(amount) {
            balance += amount;
            return balance;
        },
        withdraw(amount) {
            if (amount > balance) {
                return "Insufficient funds ❌";
            }
            balance -= amount;
            return balance;
        },
        getBalance() {
            return balance;
        }
    };
}

const account = createAccount(1000);

console.log(account.deposit(500));
console.log(account.withdraw(200));
console.log(account.withdraw(5000));
console.log(account.getBalance());
console.log(account.balance);
```

### 📤 Output

```text
1500
1300
Insufficient funds ❌
1300
undefined
```

`balance` can only be changed through the provided methods. `account.balance` is `undefined` because the variable is hidden inside the closure.

---

## 🔂 12. Recursion: A Function That Calls Itself

```javascript
function factorial(n) {
    if (n <= 1) {            // base case: stops the recursion
        return 1;
    }
    return n * factorial(n - 1);   // recursive case
}

console.log(factorial(5));
```

### 📤 Output

```text
120
```

### 🔍 How It Unfolds

```text
factorial(5)
= 5 * factorial(4)
= 5 * (4 * factorial(3))
= 5 * (4 * (3 * factorial(2)))
= 5 * (4 * (3 * (2 * factorial(1))))
= 5 * 4 * 3 * 2 * 1
= 120
```

### ⚠️ Every Recursive Function Needs a Base Case

```javascript
function forever() {
    forever();
}

forever();
```

### 📤 Output

```text
RangeError: Maximum call stack size exceeded
```

Without a base case, the function calls itself until the browser runs out of memory for calls (the **call stack**).

---

## 📦 13. The `arguments` Object and Rest Parameters

Regular functions have a built-in, array-like `arguments` object.

```javascript
function showArgs() {
    console.log(arguments.length);
    console.log(arguments[0]);
}

showArgs("a", "b", "c");
```

### 📤 Output

```text
3
a
```

### ✅ Prefer Rest Parameters

```javascript
function sum(...numbers) {
    return numbers.reduce((total, n) => total + n, 0);
}

console.log(sum(1, 2, 3, 4));
```

### 📤 Output

```text
10
```

| `arguments` | Rest parameters `...args` |
|---|---|
| Array-like (no `map`, `filter`) | A real array |
| Not available in arrow functions | Works everywhere |
| Older style | Modern style ✅ |

---

## 📋 14. Master Comparison Table

| Pattern | Example | `this` | Typical use |
|---|---|---|---|
| Function | `fn()` | `undefined` / global | Utility and helper functions |
| Method | `obj.fn()` | `obj` | Behaviour attached to an object |
| Constructor | `new Fn()` | New object | Creating many similar objects |
| Indirect | `fn.call(obj)` | `obj` | Borrowing methods, fixing `this` |
| Arrow | `() => {}` | Outer `this` | Callbacks and short functions |
| IIFE | `(function(){})()` | Per call type | One-time code with private scope |

---

## ⚠️ 15. Common Mistakes

| ❌ Mistake | ✅ Correct |
|---|---|
| Passing `obj.method` as a callback and losing `this` | `obj.method.bind(obj)` or an arrow wrapper |
| Forgetting `new` with a constructor | Use `new`, or use a `class` |
| Using an arrow function as an object method | Use method syntax: `greet() { ... }` |
| Using an arrow function as a constructor | Use a regular function or a class |
| Writing `button.addEventListener("click", sayHi())` | Pass the function, not its result: `sayHi` |
| Recursive function with no base case | Always add a stopping condition |
| Using `arguments` inside an arrow function | Use rest parameters `...args` |
| Confusing `call` and `apply` | `call` = comma-separated args, `apply` = array |
| Assuming `this` depends on where the function is written | `this` depends on **how it is called** (except in arrow functions) |
| Not using strict mode, so a lost `this` fails silently | Use `"use strict"`, modules, or classes |

---

## 🧪 16. Practice Tasks

- [ ] 🟢 **Beginner:** Create an object `car` with a method `describe()` that prints the car's brand using `this`.
- [ ] 🟢 **Beginner:** Write a constructor function `Book(title, author)` and create two books with `new`.
- [ ] 🟡 **Intermediate:** Copy a method out of an object into a variable, call it, and observe the error. Then fix it using `bind()`.
- [ ] 🟡 **Intermediate:** Write a function that uses `this.name` and call it for two different objects using `call()`.
- [ ] 🔵 **Practice:** Convert the `Student` constructor function into a `class` with a `greet()` method.
- [ ] 🔵 **Practice:** Write an IIFE that prints "Welcome" immediately and keeps a private variable.
- [ ] 🔵 **Practice:** Write a higher-order function `power(exponent)` that returns a function raising a number to that power.
- [ ] 🔴 **Challenge:** Write `makeCounter()` with `increment()`, `decrement()`, and `getValue()` methods that share a private count.
- [ ] 🔴 **Challenge:** Write a recursive function that returns the sum of the digits of a number (for example `1234` gives `10`).

---

## 🎤 17. Viva Voce Questions and Answers

### 🟢 Basic Questions

**Q1. What is function invocation?**

**Answer:** Invocation means calling a function so that its code runs.

**Q2. What does `this` refer to in JavaScript?**

**Answer:** `this` refers to the object that the function is being called on. Its value is decided by how the function is invoked, not where it is defined.

**Q3. Name the invocation patterns in JavaScript.**

**Answer:** Function invocation, method invocation, constructor invocation, and indirect invocation (using `call`, `apply`, and `bind`).

**Q4. What is a method?**

**Answer:** A function stored as a property of an object and called using that object.

**Q5. What is a constructor function?**

**Answer:** A function designed to be called with `new` to create objects. By convention its name starts with a capital letter.

### 🟡 Intermediate Questions

**Q6. What is `this` in a plain function call?**

**Answer:** In sloppy mode it is the global object (`window` in browsers). In strict mode it is `undefined`.

**Q7. What is `this` in a method call like `obj.fn()`?**

**Answer:** The object before the dot, which is `obj`.

**Q8. What happens when you call a function with `new`?**

**Answer:** JavaScript creates a new object, links it to the constructor's prototype, runs the function with `this` set to that object, and returns the object.

**Q9. What happens if you forget `new` when calling a constructor?**

**Answer:** It becomes a plain function call, so `this` is the global object (sloppy mode) or `undefined` (strict mode), which can create global variables or throw a `TypeError`. A `class` throws an error if called without `new`.

**Q10. What is the difference between `call`, `apply`, and `bind`?**

**Answer:** `call` and `apply` invoke the function immediately with a chosen `this`; `call` takes arguments separately and `apply` takes them as an array. `bind` does not invoke the function but returns a new function with `this` permanently set.

**Q11. How do arrow functions handle `this`?**

**Answer:** They have no `this` of their own and use the `this` of the surrounding code where they were written (lexical `this`).

**Q12. Why should arrow functions not be used as object methods or constructors?**

**Answer:** As methods, `this` will not refer to the object. As constructors, they cannot be used with `new` and throw a `TypeError`.

### 🔵 Practical Questions

**Q13. Why does this code fail, and how would you fix it?**

```javascript
const student = { name: "Aman", greet() { console.log(this.name); } };
const saved = student.greet;
saved();
```

**Answer:** `saved()` is a plain function call with no object before it, so `this` is not `student` (it is `undefined` in strict mode or the global object in sloppy mode). Fix it with `student.greet.bind(student)`, or by calling `student.greet()`.

**Q14. What is an IIFE and why is it used?**

**Answer:** An Immediately Invoked Function Expression is a function that is defined and called right away, for example `(function () { ... })();`. It creates a private scope and avoids polluting the global scope.

**Q15. What is a callback function?**

**Answer:** A function passed as an argument to another function, to be called later by that function.

**Q16. What is a higher-order function?**

**Answer:** A function that takes another function as an argument or returns a function, such as `map`, `filter`, or a function that returns a function.

**Q17. What is a closure?**

**Answer:** A closure is a function that remembers and can access the variables from the scope where it was created, even after that outer function has finished running.

**Q18. What is the output of the following code?**

```javascript
function makeCounter() {
    let count = 0;
    return () => ++count;
}
const c = makeCounter();
c();
console.log(c());
```

**Answer:** `2`, because the returned function remembers `count` between calls.

**Q19. What is recursion, and why does it need a base case?**

**Answer:** Recursion is when a function calls itself. A base case is the condition that stops the recursion; without it the function calls itself endlessly and causes a `RangeError: Maximum call stack size exceeded`.

**Q20. Why are rest parameters preferred over the `arguments` object?**

**Answer:** Rest parameters create a real array with methods like `map` and `reduce`, and they work in arrow functions, while `arguments` is array-like only and is not available in arrow functions.

---

## 🏆 18. Key Takeaways

- 🎭 `this` is decided by **how a function is called**, like the word "I" changes with who is speaking.
- 1️⃣ **Function call** `fn()`: `this` is `undefined` (strict) or global (sloppy).
- 2️⃣ **Method call** `obj.fn()`: `this` is `obj`.
- 3️⃣ **Constructor call** `new Fn()`: `this` is a brand-new object. Prefer `class`.
- 4️⃣ **Indirect call**: `call` and `apply` run now; `bind` returns a new function with `this` fixed.
- ➡️ **Arrow functions** inherit `this`, so they are perfect for callbacks but not for methods or constructors.
- 🪤 Passing `obj.method` as a callback **loses `this`**. Use `bind` or an arrow wrapper.
- ⚡ An **IIFE** runs immediately and gives a private scope.
- 🔒 A **closure** remembers its outer variables, enabling private data and function factories.
- 🔂 Recursion needs a **base case**.
- ✅ Use strict mode, modules, or classes so mistakes with `this` fail loudly instead of silently.

---

### 🚀 Keep Practising!

> 💡 **Remember:** When `this` surprises you, ask one question: **"How was this function called?"** The answer is almost always there.

**Happy Coding! 💻✨**
