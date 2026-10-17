# 🚀 Object-Oriented Programming (OOP) in JavaScript

Welcome to **Object-Oriented Programming (OOP) in JavaScript!** 🎯

OOP is a programming approach that organizes code using **objects and classes**. It helps us write reusable, organized, and maintainable programs.

## 🎯 Learning Objectives

After completing this topic, students will be able to:

- ✅ Understand the concept of OOP.
- ✅ Explain classes and objects.
- ✅ Understand constructors and the `this` keyword.
- ✅ Apply the four pillars of OOP.
- ✅ Implement inheritance, encapsulation, polymorphism, and abstraction.
- ✅ Create real-world programs using JavaScript OOP.

---

## 🌟 1. What Is OOP?

**Object-Oriented Programming (OOP)** is a programming paradigm in which we organize data and functionality into objects.

### 🏫 Real-World Example: A Student

Think about a student in a college.

| Property (Data) | Behaviour (Functionality) |
|---|---|
| Name | Attend class |
| Roll Number | Study |
| Branch | Submit assignment |
| Marks | Display result |

In JavaScript, we can represent a student as an object containing properties and methods.

```javascript
const student = {
    name: "Rahul",
    rollNo: 101,
    branch: "CSE",

    introduce: function () {
        console.log("Hello, I am " + this.name);
    }
};

console.log(student.name);
student.introduce();
```

**Output:**

```text
Rahul
Hello, I am Rahul
```

💡 **Remember:** Properties represent data, while methods represent actions.

---

## 🧱 2. What Is a Class?

A **class** is a blueprint or template used to create objects.

🏠 Think of a class as a house design. Different houses can be built using the same design, just as multiple objects can be created from one class.

### Syntax

```javascript
class ClassName {
    // Properties and methods
}
```

### Example: Student Class

```javascript
class Student {
    display() {
        console.log("Welcome to JavaScript OOP!");
    }
}

const s1 = new Student();

s1.display();
```

**Output:**

```text
Welcome to JavaScript OOP!
```

### 🔍 Understanding the Code

- `class Student` defines a class.
- `display()` defines a method.
- `new Student()` creates an object.
- `s1.display()` calls the method.

---

## 🧑‍💻 3. What Is an Object?

An **object** is an instance of a class. It can have its own properties and access the methods defined by its class.

### Example: Creating Multiple Objects

```javascript
class Student {
    constructor(name, rollNo) {
        this.name = name;
        this.rollNo = rollNo;
    }

    display() {
        console.log(
            "Name: " + this.name +
            ", Roll No: " + this.rollNo
        );
    }
}

const s1 = new Student("Rahul", 101);
const s2 = new Student("Priya", 102);

s1.display();
s2.display();
```

**Output:**

```text
Name: Rahul, Roll No: 101
Name: Priya, Roll No: 102
```

📌 Here, `Student` is the class, while `s1` and `s2` are two different objects.

---

## ⚙️ 4. Constructor in JavaScript

A **constructor** is a special method that runs automatically when an object is created using `new`.

It is commonly used to initialize an object's properties.

```javascript
class Employee {
    constructor(name, salary) {
        this.name = name;
        this.salary = salary;
    }
}

const emp1 = new Employee("Amit", 40000);

console.log(emp1.name);
console.log(emp1.salary);
```

**Output:**

```text
Amit
40000
```

### 🧠 What Does `this` Mean?

The `this` keyword refers to the object associated with the current method call. In a class constructor, it refers to the newly created object.

```javascript
class Car {
    constructor(brand) {
        this.brand = brand;
    }
}

const car1 = new Car("Tata");
const car2 = new Car("Mahindra");

console.log(car1.brand);
console.log(car2.brand);
```

**Output:**

```text
Tata
Mahindra
```

💡 `this.brand` stores the value in the current object, so each car can have a different brand.

---

# 🏆 5. The Four Pillars of OOP

The four commonly taught pillars of OOP are:

| Pillar | Meaning | Example |
|---|---|---|
| 🔒 Encapsulation | Bundling data and methods together, with controlled access | Private fields |
| 🧬 Inheritance | Creating a class based on another class | `extends` |
| 🎭 Polymorphism | The same method name can have different behaviours | Method overriding |
| 🎯 Abstraction | Exposing essential operations while hiding implementation details | A public method that hides internal steps |

Let's understand each pillar with simple examples.

---

## 🔒 6. Encapsulation

**Encapsulation** means bundling data and methods together and controlling how the data is accessed or modified.

JavaScript supports private class fields using the `#` symbol.

### Example: Bank Account

```javascript
class BankAccount {
    #balance = 0;

    deposit(amount) {
        if (amount > 0) {
            this.#balance += amount;
        }
    }

    getBalance() {
        return this.#balance;
    }
}

const account = new BankAccount();

account.deposit(5000);

console.log(account.getBalance());
```

**Output:**

```text
5000
```

### 🔍 Explanation

- `#balance` is a private field.
- It cannot be accessed directly outside the class.
- `deposit()` controls how money is added.
- `getBalance()` provides access to the balance.

```javascript
console.log(account.#balance); // SyntaxError
```

⚠️ The last line causes a syntax error because private fields cannot be accessed directly outside their declaring class.

**Real-world example:** A bank account does not allow arbitrary changes to its balance; transactions must follow defined rules.

---

## 🧬 7. Inheritance

**Inheritance** allows one class to reuse properties and methods from another class.

- **Parent class:** The class whose features are inherited.
- **Child class:** The class that inherits those features.

JavaScript uses `extends` to establish class inheritance.

### Example: Animal and Dog

```javascript
class Animal {
    eat() {
        console.log("Animal is eating.");
    }
}

class Dog extends Animal {
    bark() {
        console.log("Dog is barking.");
    }
}

const dog = new Dog();

dog.eat();
dog.bark();
```

**Output:**

```text
Animal is eating.
Dog is barking.
```

### 🔍 Explanation

- `Animal` is the parent class.
- `Dog` is the child class.
- `Dog extends Animal` establishes inheritance.
- The `dog` object can use both `eat()` and `bark()`.

### Example with a Parent Constructor

```javascript
class Person {
    constructor(name) {
        this.name = name;
    }
}

class Teacher extends Person {
    constructor(name, subject) {
        super(name);
        this.subject = subject;
    }

    introduce() {
        console.log(
            this.name + " teaches " + this.subject
        );
    }
}

const t1 = new Teacher("Anita", "JavaScript");

t1.introduce();
```

**Output:**

```text
Anita teaches JavaScript
```

📌 `super(name)` calls the parent class constructor. In a derived class constructor, `super()` must be called before accessing `this`.

---

## 🎭 8. Polymorphism

**Polymorphism** means “many forms.” In OOP, the same method name can produce different behaviour depending on the object.

### Example: Method Overriding

```javascript
class Animal {
    sound() {
        console.log("Animal makes a sound.");
    }
}

class Dog extends Animal {
    sound() {
        console.log("Dog barks.");
    }
}

class Cat extends Animal {
    sound() {
        console.log("Cat meows.");
    }
}

const animals = [
    new Dog(),
    new Cat()
];

for (const animal of animals) {
    animal.sound();
}
```

**Output:**

```text
Dog barks.
Cat meows.
```

### 🔍 Explanation

Both `Dog` and `Cat` define a method named `sound()`, but each provides its own implementation.

This is an example of **method overriding**, a common way to demonstrate runtime polymorphism.

💡 JavaScript does not support traditional method overloading by defining multiple methods with the same name and different parameter lists in the same class. The later definition replaces the earlier one.

---

## 🎯 9. Abstraction

**Abstraction** means exposing essential operations while hiding unnecessary implementation details.

### 🚗 Real-World Example

When you drive a car, you use the steering wheel and pedals. You do not need to understand every internal engine operation.

Similarly, a method can provide a simple interface while hiding the steps required to complete a task.

### Example: Coffee Machine

```javascript
class CoffeeMachine {
    makeCoffee() {
        this.#boilWater();
        this.#brewCoffee();

        console.log("Coffee is ready!");
    }

    #boilWater() {
        console.log("Boiling water...");
    }

    #brewCoffee() {
        console.log("Brewing coffee...");
    }
}

const machine = new CoffeeMachine();

machine.makeCoffee();
```

**Output:**

```text
Boiling water...
Brewing coffee...
Coffee is ready!
```

### 🔍 Explanation

- `makeCoffee()` is the public operation.
- `#boilWater()` and `#brewCoffee()` are private implementation details.
- The user calls one method without needing to manage every internal step.

📌 JavaScript classes do not have a built-in `abstract class` keyword like some other OOP languages. Abstraction can be implemented through public interfaces, private methods, and other design techniques.

---

## 📊 10. Quick Comparison of the Four Pillars

| Pillar | Main Idea | JavaScript Feature |
|---|---|---|
| Encapsulation | Control access to data | `#privateField` |
| Inheritance | Reuse existing class features | `extends`, `super()` |
| Polymorphism | Different behaviour through a common interface | Method overriding |
| Abstraction | Hide internal complexity | Public methods and private implementation |

---

## 🔄 11. Class vs Object

| Class | Object |
|---|---|
| A blueprint or template | An instance created from a class |
| Defines methods and initialization | Uses methods and stores instance data |
| Example: `Student` | Example: `new Student("Rahul")` |
| One class can create many objects | Each object can hold different data |

---

## 🧪 12. Practice Tasks

Try these programs yourself. 🚀

- [ ] **Task 1:** Create a `Book` class with `title`, `author`, and `price`.
- [ ] **Task 2:** Create three objects from a `Student` class.
- [ ] **Task 3:** Create an `Employee` class with a constructor and a method to display employee details.
- [ ] **Task 4:** Create a private `#balance` field and implement deposit and withdrawal methods.
- [ ] **Task 5:** Create a `Vehicle` parent class and `Bike` child class.
- [ ] **Task 6:** Create `Circle` and `Rectangle` classes with a common `area()` method.
- [ ] **Task 7:** Design a `Payment` class with different payment methods that override a common `pay()` method.
- [ ] **Task 8:** Create a `CoffeeMachine` class with public and private methods.

---

# 🎤 13. Viva Voce Questions and Answers

## 🟢 Basic Questions

**Q1. What is OOP?**

OOP stands for Object-Oriented Programming. It organizes programs using objects that combine data and functionality.

**Q2. What is a class?**

A class is a blueprint used to create objects.

**Q3. What is an object?**

An object is an instance of a class containing data and providing access to its methods.

**Q4. What is a constructor?**

A constructor is a special method that initializes an object when it is created.

**Q5. What is the purpose of the `new` keyword?**

The `new` keyword creates an instance of a class and initializes it.

**Q6. What is the `this` keyword?**

`this` refers to the object associated with the current method call. In a constructor, it refers to the newly created instance.

## 🟡 Intermediate Questions

**Q7. What are the four pillars of OOP?**

Encapsulation, inheritance, polymorphism, and abstraction.

**Q8. What is encapsulation?**

Encapsulation bundles data and methods together and provides controlled access to data.

**Q9. How are private fields declared in JavaScript?**

Private fields are declared using the `#` prefix, for example, `#balance`.

**Q10. What is inheritance?**

Inheritance allows a child class to reuse and extend the features of a parent class.

**Q11. What is the purpose of `extends`?**

`extends` establishes inheritance between classes.

**Q12. What is the purpose of `super()`?**

`super()` calls the parent class constructor in a derived class.

**Q13. What is polymorphism?**

Polymorphism allows a common method name or interface to produce different behaviours for different objects.

**Q14. What is method overriding?**

Method overriding occurs when a child class provides its own implementation of a method inherited from its parent class.

**Q15. What is abstraction?**

Abstraction exposes essential operations while hiding unnecessary implementation details.

## 🔵 Practical Questions

**Q16. Can one class create multiple objects?**

Yes. A class can be used to create multiple objects, each with its own instance data.

**Q17. Can a child class access a private field declared in its parent class?**

No. JavaScript private fields are accessible only within the class body that declares them. A parent class can provide methods to access or modify the field when appropriate.

**Q18. Does JavaScript support multiple inheritance through classes?**

No. A JavaScript class can extend only one class directly. Other composition techniques can be used to combine behaviours.

**Q19. What happens if a derived class defines a method with the same name as a parent method?**

The child class method overrides the inherited method for calls on instances of the child class.

**Q20. What is the difference between a class and an object?**

A class defines the structure and behaviour; an object is an instance created from that class.

**Q21. Does JavaScript support OOP?**

Yes. JavaScript supports objects, classes, encapsulation, inheritance, and polymorphism. Its class syntax is built on JavaScript's prototype-based object model.

**Q22. Why is OOP useful?**

OOP can improve code organization, reuse, maintainability, and the representation of real-world entities.

**Q23. What is the difference between a property and a method?**

A property stores data, while a method is a function associated with an object or class.

**Q24. What is the difference between `this.name` and `name` in a constructor?**

`this.name` refers to a property of the current object. `name` may refer to a parameter or local variable.

**Q25. Can we create an object without using a class?**

Yes. JavaScript supports object literals, such as `const student = { name: "Rahul" };`.

---

## 🏆 14. Key Takeaways

- ✅ OOP organizes code around objects and their behaviour.
- ✅ A class is a blueprint; an object is an instance.
- ✅ Constructors initialize objects.
- ✅ `this` refers to the object associated with a method call.
- ✅ Encapsulation controls access to data.
- ✅ Inheritance enables reuse through `extends`.
- ✅ Polymorphism allows different implementations of a common method.
- ✅ Abstraction hides implementation details behind a simpler interface.

> 💡 **Remember:** Practice each concept with a small program before combining all four pillars in a larger project.

🎉 **Happy Coding! Keep Learning JavaScript!** 🚀
