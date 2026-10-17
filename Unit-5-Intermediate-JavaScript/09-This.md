# 🚀 The `this` Keyword in JavaScript

Welcome to **the `this` keyword in JavaScript!** 🎯

The `this` keyword is one of the most important concepts in JavaScript. It refers to a value determined by **how a function is called**.

Understanding `this` helps you work confidently with objects, methods, constructors, classes, and event handlers.

## 🎯 Learning Objectives

After completing this topic, students will be able to:

- ✅ Understand the meaning of `this`.
- ✅ Use `this` inside object methods.
- ✅ Understand `this` in regular functions and arrow functions.
- ✅ Use `this` in constructors and classes.
- ✅ Understand `this` in event handlers.
- ✅ Use `call()`, `apply()`, and `bind()`.
- ✅ Avoid common mistakes involving `this`.

---

## 🌟 1. What Is `this` in JavaScript?

The `this` keyword refers to a value associated with the current function execution.

Its value depends on the way the function is called, except in arrow functions, which inherit `this` from their surrounding lexical scope.

### 🏫 Real-World Example

Imagine two students, Rahul and Priya. Both have a method called `introduce()`.

When Rahul calls the method, it should display Rahul's details. When Priya calls it, it should display Priya's details.

The `this` keyword helps a method access the relevant object's properties.

### 💻 Example

```javascript
const student1 = {
    name: "Rahul",

    introduce: function () {
        console.log("My name is " + this.name);
    }
};

const student2 = {
    name: "Priya",

    introduce: function () {
        console.log("My name is " + this.name);
    }
};

student1.introduce();
student2.introduce();
```

**Output:**

```text
My name is Rahul
My name is Priya
```

### 🔍 Explanation

- `student1.introduce()` calls the method through `student1`.
- Inside that call, `this` refers to `student1`.
- `student2.introduce()` calls the method through `student2`.
- Inside that call, `this` refers to `student2`.

💡 **Remember:** In a regular method call such as `object.method()`, `this` normally refers to the object before the dot.

---

## 🧱 2. `this` Inside an Object Method

When a regular function is called as a method of an object, `this` refers to the object used for that call.

```javascript
const car = {
    brand: "Tata",
    model: "Nexon",
    color: "Black",

    displayDetails() {
        console.log("Brand: " + this.brand);
        console.log("Model: " + this.model);
        console.log("Color: " + this.color);
    }
};

car.displayDetails();
```

**Output:**

```text
Brand: Tata
Model: Nexon
Color: Black
```

### 🧠 Step-by-Step Dry Run

| Expression | Meaning |
|---|---|
| `car.displayDetails()` | Calls the method through `car` |
| `this.brand` | Reads `car.brand` |
| `this.model` | Reads `car.model` |
| `this.color` | Reads `car.color` |

### 🎯 Key Point

The same method can work with different objects if it is called with the appropriate receiver.

```javascript
const person1 = {
    name: "Amit",
    greet() {
        console.log("Hello, " + this.name);
    }
};

const person2 = {
    name: "Neha"
};

person2.greet = person1.greet;

person1.greet();
person2.greet();
```

**Output:**

```text
Hello, Amit
Hello, Neha
```

Although the function is the same, the call determines the value of `this`.

---

## ⚠️ 3. `this` in a Regular Function

A regular function's `this` depends on how it is called.

When a regular function is called without an object receiver:

- In **strict mode**, `this` is `undefined`.
- In a browser's non-strict global function call, `this` generally refers to the global object, `window`.

### 💻 Example: Strict Mode

```javascript
"use strict";

function showThis() {
    console.log(this);
}

showThis();
```

**Output:**

```text
undefined
```

### 🔍 Why?

The function is called directly as `showThis()`, not as an object method. Because strict mode is enabled, JavaScript does not substitute the global object for `this`.

📌 JavaScript class bodies and class methods always execute in strict mode.

---

## 🏹 4. `this` in Arrow Functions

Arrow functions do not have their own `this`. They **inherit `this` from the surrounding lexical scope**.

This is one of the most important differences between arrow functions and regular functions.

### ❌ Common Mistake: Arrow Function as an Object Method

```javascript
const student = {
    name: "Rahul",

    introduce: () => {
        console.log(this.name);
    }
};

student.introduce();
```

In a typical browser script, the result is often `undefined` because the arrow function inherits `this` from its surrounding scope rather than using `student` as its receiver.

### ✅ Correct Approach: Use a Regular Method

```javascript
const student = {
    name: "Rahul",

    introduce() {
        console.log("My name is " + this.name);
    }
};

student.introduce();
```

**Output:**

```text
My name is Rahul
```

### 📊 Regular Function vs Arrow Function

| Regular Function | Arrow Function |
|---|---|
| Has its own `this` based on how it is called | Inherits `this` from the surrounding scope |
| Can be used as a constructor with `new` | Cannot be used as a constructor |
| Useful for object methods that need their receiver | Useful for callbacks that should retain surrounding `this` |
| `this` can be changed using `call()` or `bind()` | `call()` and `bind()` cannot change its `this` |

---

## 🔁 5. Using `this` Inside a Callback

Arrow functions are useful when a callback needs to access the surrounding object's `this`.

### 💻 Example

```javascript
const counter = {
    count: 0,

    start() {
        const update = () => {
            this.count++;
            console.log(this.count);
        };

        update();
        update();
    }
};

counter.start();
```

**Output:**

```text
1
2
```

### 🔍 Explanation

- `start()` is called through `counter`.
- Therefore, `this` inside `start()` refers to `counter`.
- The arrow function `update` inherits that same `this`.
- Each call increments `counter.count`.

💡 Arrow functions are especially helpful for callbacks where you want to preserve the surrounding `this`.

---

## 🏗️ 6. `this` Inside a Constructor Function

A constructor function is commonly used with `new` to create and initialize objects.

When a constructor is called with `new`, `this` refers to the newly created object.

### 💻 Example

```javascript
function Student(name, rollNo) {
    this.name = name;
    this.rollNo = rollNo;
}

const s1 = new Student("Rahul", 101);
const s2 = new Student("Priya", 102);

console.log(s1.name);
console.log(s1.rollNo);

console.log(s2.name);
console.log(s2.rollNo);
```

**Output:**

```text
Rahul
101
Priya
102
```

### 🔍 Explanation

When JavaScript executes:

```javascript
const s1 = new Student("Rahul", 101);
```

It creates a new object and calls `Student` with `this` referring to that object.

The assignments:

```javascript
this.name = name;
this.rollNo = rollNo;
```

store the supplied values on the new object.

📌 Each object gets its own `name` and `rollNo` properties.

---

## 🧬 7. `this` Inside a JavaScript Class

In a class constructor, `this` refers to the newly created instance.

Inside a regular class method, `this` depends on how the method is called.

### 💻 Example

```javascript
class Employee {
    constructor(name, salary) {
        this.name = name;
        this.salary = salary;
    }

    displayDetails() {
        console.log("Employee: " + this.name);
        console.log("Salary: " + this.salary);
    }
}

const emp1 = new Employee("Amit", 45000);

emp1.displayDetails();
```

**Output:**

```text
Employee: Amit
Salary: 45000
```

### 🔍 Explanation

- `this.name` stores the employee's name.
- `this.salary` stores the employee's salary.
- `emp1.displayDetails()` calls the method through `emp1`, so `this` refers to `emp1`.

---

## 🎯 8. `this` in Inheritance

When a child class inherits from a parent class, `this` refers to the current instance, including when a method is inherited.

### 💻 Example

```javascript
class Person {
    constructor(name) {
        this.name = name;
    }

    introduce() {
        console.log("My name is " + this.name);
    }
}

class Teacher extends Person {
    constructor(name, subject) {
        super(name);
        this.subject = subject;
    }

    teach() {
        console.log(
            this.name + " teaches " + this.subject
        );
    }
}

const teacher = new Teacher("Anita", "JavaScript");

teacher.introduce();
teacher.teach();
```

**Output:**

```text
My name is Anita
Anita teaches JavaScript
```

### 🔍 Explanation

- `super(name)` initializes the inherited `name` property through the parent constructor.
- `this.subject` stores the subject on the current instance.
- Both methods access properties through the same teacher object.

---

## 🖱️ 9. `this` in Event Handlers

In a regular DOM event-handler function, `this` usually refers to the DOM element on which the handler is registered.

### 💻 Example: Button Click

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>This Keyword Example</title>
</head>
<body>

    <button id="myButton">Click Me</button>

    <script>
        const button = document.querySelector("#myButton");

        button.addEventListener("click", function () {
            console.log(this.textContent);
        });
    </script>

</body>
</html>
```

**Output after clicking the button:**

```text
Click Me
```

### 🔍 Explanation

- `addEventListener()` registers a click handler.
- The browser calls the regular handler with `this` referring to the element on which the listener was registered.
- `this.textContent` reads the button's text.

### ⚠️ What About an Arrow Function?

```javascript
button.addEventListener("click", () => {
    console.log(this);
});
```

Here, `this` is inherited from the surrounding scope. It does not automatically become the clicked button.

If you need the clicked element inside an arrow-function handler, use the event object:

```javascript
button.addEventListener("click", (event) => {
    console.log(event.currentTarget.textContent);
});
```

**Output after clicking the button:**

```text
Click Me
```

---

## 🛠️ 10. `call()`, `apply()`, and `bind()`

These methods let you control the `this` value for a regular function.

### A. `call()`

Calls a function immediately with a specified `this` value and individual arguments.

```javascript
function introduce(city) {
    console.log(
        this.name + " lives in " + city
    );
}

const person = {
    name: "Rahul"
};

introduce.call(person, "Delhi");
```

**Output:**

```text
Rahul lives in Delhi
```

### B. `apply()`

Works like `call()`, but supplies the function arguments as an array (or array-like object).

```javascript
function introduce(city, country) {
    console.log(
        this.name + " lives in " +
        city + ", " + country
    );
}

const person = {
    name: "Priya"
};

introduce.apply(person, ["Mumbai", "India"]);
```

**Output:**

```text
Priya lives in Mumbai, India
```

### C. `bind()`

Returns a new function with a specified `this` value. The function is not called immediately.

```javascript
function greet() {
    console.log("Hello, " + this.name);
}

const person = {
    name: "Amit"
};

const greetPerson = greet.bind(person);

greetPerson();
```

**Output:**

```text
Hello, Amit
```

### 📊 Comparison

| Method | What it does | Arguments |
|---|---|---|
| `call()` | Calls the function immediately | Passed individually |
| `apply()` | Calls the function immediately | Passed as an array or array-like object |
| `bind()` | Returns a new bound function | Passed individually when binding, with optional later arguments |

📌 These methods cannot override the lexical `this` of an arrow function.

---

## ⚠️ 11. Common Mistakes with `this`

### Mistake 1: Detaching an Object Method

```javascript
"use strict";

const student = {
    name: "Rahul",

    greet() {
        console.log(this.name);
    }
};

const greetFunction = student.greet;

greetFunction();
```

**Output:**

```text
TypeError
```

In strict mode, the detached method is called without an object receiver, so `this` is `undefined`. Accessing `this.name` throws a `TypeError`.

✅ **Solution:** Call the method through the object:

```javascript
student.greet();
```

### Mistake 2: Using an Arrow Function as a Method

```javascript
const user = {
    name: "Priya",

    greet: () => {
        console.log(this.name);
    }
};
```

The arrow function does not receive `user` as its `this`.

✅ **Solution:** Use method syntax:

```javascript
const user = {
    name: "Priya",

    greet() {
        console.log(this.name);
    }
};

user.greet();
```

### Mistake 3: Assuming `this` Always Means the Same Thing

The value of `this` is not always the object in which the function was originally written.

Always ask: **How is this function being called?**

---

## 📊 12. Quick Revision Table

| Situation | Meaning of `this` |
|---|---|
| `object.method()` | Usually the object before the dot |
| Regular function call in strict mode | `undefined` |
| Regular function call in a non-strict browser global context | Generally `window` |
| Constructor called with `new` | Newly created instance |
| Class constructor | Newly created instance |
| Arrow function | Inherited from surrounding lexical scope |
| Regular DOM event handler | Usually the element receiving the event listener call |
| `call()` or `apply()` on a regular function | Specified `this` value |
| `bind()` on a regular function | Specified `this` value in the returned function |

---

## 🧪 13. Practice Tasks

Try these programs yourself. 🚀

- [ ] **Task 1:** Create a `Student` object with a method that displays the student's name using `this`.
- [ ] **Task 2:** Create two objects that use the same method and display different names.
- [ ] **Task 3:** Write a regular function and observe `this` in strict mode.
- [ ] **Task 4:** Compare a regular function and an arrow function inside an object.
- [ ] **Task 5:** Create an `Employee` constructor using `this`.
- [ ] **Task 6:** Create a `Car` class with a method that displays its brand and model.
- [ ] **Task 7:** Create a button and display its text using a regular event handler.
- [ ] **Task 8:** Call a function using `call()` and `apply()`.
- [ ] **Task 9:** Use `bind()` to create a function that always greets a particular person.
- [ ] **Task 10:** Detach an object method and investigate how binding changes its behaviour.

---

# 🎤 14. Viva Voce Questions and Answers

## 🟢 Basic Questions

**Q1. What is the `this` keyword in JavaScript?**

It refers to a value determined by the function's calling context, except in arrow functions, which inherit `this` from their surrounding scope.

**Q2. What is the value of `this` inside an object method?**

In a regular method call such as `student.greet()`, `this` usually refers to `student`.

**Q3. What is the value of `this` inside a constructor called with `new`?**

It refers to the newly created instance.

**Q4. Do arrow functions have their own `this`?**

No. Arrow functions inherit `this` from the surrounding lexical scope.

**Q5. What is the difference between `this` and a normal variable?**

A normal variable is resolved through lexical scope rules, while `this` is determined by the function's calling context or inherited lexical context for arrow functions.

## 🟡 Intermediate Questions

**Q6. What is the value of `this` in a strict-mode regular function called directly?**

It is `undefined`.

**Q7. What is the difference between a regular function and an arrow function regarding `this`?**

A regular function's `this` depends on how it is called; an arrow function inherits `this` from the surrounding scope.

**Q8. Why should arrow functions generally not be used as ordinary object methods when accessing `this`?**

They do not receive the object as their `this`, so they may not access the object's properties as expected.

**Q9. What is the purpose of `call()`?**

It invokes a regular function immediately with a specified `this` value and individually supplied arguments.

**Q10. What is the difference between `call()` and `apply()`?**

Both invoke a function immediately, but `call()` accepts individual arguments and `apply()` accepts an array or array-like collection of arguments.

**Q11. What is the purpose of `bind()`?**

It returns a new function with a specified `this` value.

**Q12. Does `bind()` immediately execute a function?**

No. It returns a new bound function that can be called later.

**Q13. Can `call()` change the `this` value of an arrow function?**

No. An arrow function's lexical `this` cannot be changed by `call()`, `apply()`, or `bind()`.

**Q14. What is the value of `this` inside a class method?**

It depends on how the method is called. For `employee.display()`, `this` normally refers to `employee`.

**Q15. What does `this` refer to in a regular DOM event handler?**

It usually refers to the element on which the handler was registered.

## 🔵 Practical Questions

**Q16. Why can a detached method lose its expected `this` value?**

Because calling the function without its original object receiver changes how `this` is determined.

**Q17. How can you preserve an object's method context?**

Call the method through the object or use `bind()` to create a bound regular function.

**Q18. Can an arrow function be used as a constructor with `new`?**

No. Arrow functions are not constructible.

**Q19. What is lexical `this`?**

It is the `this` value inherited by an arrow function from its surrounding lexical scope.

**Q20. Why is understanding `this` important?**

It helps prevent bugs when using objects, callbacks, constructors, classes, and event handlers.

**Q21. Does `this` always refer to the object in which a function is defined?**

No. For regular functions, it generally depends on how the function is called.

**Q22. What is the difference between `this` and `event.currentTarget` in a DOM event handler?**

In a regular event handler, `this` typically equals `event.currentTarget`. The explicit `event.currentTarget` property is also available in arrow handlers.

**Q23. What happens when a class method is extracted and called without its instance?**

The method loses its object receiver. In strict mode, `this` is `undefined`, which can cause errors when the method accesses instance properties.

**Q24. How can an arrow function access the surrounding object's `this`?**

Define the arrow function inside a method or another function whose `this` already refers to the desired object.

**Q25. What is the main rule for understanding `this` in JavaScript?**

For regular functions, examine how the function is called. For arrow functions, examine the surrounding lexical scope.

---

## 🏆 15. Key Takeaways

- ✅ `this` depends on the calling context for regular functions.
- ✅ In a regular object method call, `this` usually refers to the calling object.
- ✅ Arrow functions inherit `this` from their surrounding scope.
- ✅ Constructors called with `new` initialize the newly created instance through `this`.
- ✅ Class methods follow strict-mode rules.
- ✅ `call()`, `apply()`, and `bind()` help manage `this` for regular functions.
- ✅ Regular DOM event handlers typically receive the element as `this`.
- ✅ Always check how a function is called before deciding what `this` means.

> 💡 **Remember:** For regular functions, look at the call. For arrow functions, look at the surrounding scope.

🎉 **Happy Coding! Keep Practicing JavaScript!** 🚀
