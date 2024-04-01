# OOP 

Object-Oriented Programming (OOP) in JavaScript allows developers to create modular, reusable, and maintainable code by organizing functionality into objects and classes. In this comprehensive guide, we'll cover the fundamental principles of OOP in JavaScript, including objects, classes, inheritance, encapsulation, and polymorphism.


```
// Creating an object using object literal syntax
const person = {
  name: 'John Doe',
  age: 30,
  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
};

// Accessing object properties
console.log(person.name); // Output: John Doe

// Calling object methods
person.greet(); // Output: Hello, my name is John Doe
```


## Classes

ES6 introduced class syntax, allowing developers to define classes and create objects based on those classes. Classes provide a more structured and familiar way to implement OOP concepts in JavaScript.


```
// Defining a class
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  // Defining a method
  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
}

// Creating an object based on the class
const person = new Person('John Doe', 30);

// Accessing object properties
console.log(person.name); // Output: John Doe

// Calling object methods
person.greet(); // Output: Hello, my name is John Doe
```


## Inheritance

JavaScript supports prototypal inheritance, where objects can inherit properties and methods from other objects. Classes can also extend other classes to inherit their functionality.

```
// Extending a class
class Student extends Person {
  constructor(name, age, grade) {
    super(name, age);
    this.grade = grade;
  }

  // Overriding a method
  greet() {
    console.log(`Hello, my name is ${this.name} and I'm in grade ${this.grade}`);
  }
}

// Creating an object based on the subclass
const student = new Student('Alice', 15, 10);

// Accessing inherited properties
console.log(student.name); // Output: Alice

// Calling overridden method
student.greet(); // Output: Hello, my name is Alice and I'm in grade 10
```


## Encapsulation

Encapsulation is the practice of bundling data and methods that operate on the data within a single unit (object or class), and controlling access to that unit. In JavaScript, encapsulation can be achieved using closures, private variables, and accessors (getters and setters).

```
// Encapsulation using closures
function createCounter() {
  let count = 0;

  return {
    increment() {
      count++;
    },
    decrement() {
      count--;
    },
    getCount() {
      return count;
    }
  };
}

const counter = createCounter();
counter.increment();
console.log(counter.getCount()); // Output: 1
```


## Polymorphism

Polymorphism allows objects of different classes to be treated as objects of a common superclass. JavaScript supports polymorphism through method overriding and dynamic binding.

```
// Polymorphism through method overriding
class Animal {
  speak() {
    console.log('The animal makes a sound');
  }
}

class Dog extends Animal {
  speak() {
    console.log('The dog barks');
  }
}

class Cat extends Animal {
  speak() {
    console.log('The cat meows');
  }
}

const dog = new Dog();
const cat = new Cat();

dog.speak(); // Output: The dog barks
cat.speak(); // Output: The cat meows
```