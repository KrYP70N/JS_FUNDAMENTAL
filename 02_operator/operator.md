# Operators

Operators are the backbone of expression evaluation and manipulation. They empower developers to perform various operations, ranging from basic arithmetic calculations to complex logical comparisons. Understanding JavaScript operators is fundamental to mastering the language and harnessing its full potential. In this section, we will delve into the diverse landscape of JavaScript operators, exploring their types, functionalities, and best practices.


## Arithmetic Operators

JavaScript provides a set of arithmetic operators for performing mathematical calculations. These include `addition +`, `subtraction -`, `multiplication *`, `division /`, `modulus %`, `increment ++`, and `decrement --`. These operators work as expected in most scenarios, but there are certain nuances to be aware of, such as the treatment of non-numeric operands and the behavior of division with zero.

```
let x = 10;
let y = 5;
console.log(x + y); // Output: 15
console.log(x - y); // Output: 5
console.log(x * y); // Output: 50
console.log(x / y); // Output: 2
console.log(x % y); // Output: 0
```


## Comparison Operators

Comparison operators in JavaScript are used to compare values and return Boolean results. These include `equal to ==`, `not equal to !=`, `strictly equal to ===`, `strictly not equal to !==`, `greater than >`, `less than <`, `greater than or equal to >=`, and `less than or equal to <=`. It's essential to understand the difference between equality operators (== and ===) and how they handle type coercion.

```
let a = 5;
let b = "5";
console.log(a == b); // Output: true (Equality with type coercion)
console.log(a === b); // Output: false (Strict equality without type coercion)
console.log(a != b); // Output: false
console.log(a !== b); // Output: true
```


## Logical Operators

Logical operators are used to combine or manipulate Boolean values. JavaScript supports logical `AND &&`, `logical OR ||`, and `logical NOT !`. These operators are commonly used in conditional statements and control flow structures to make decisions based on multiple conditions.

```
let condition1 = true;
let condition2 = false;

console.log(condition1 && condition2); // Output: false
console.log(condition1 || condition2); // Output: true
console.log(!condition1); // Output: false
```


## Assignment Operators

Assignment operators are used to assign values to variables. In addition to the basic `assignment operator =`, JavaScript provides compound assignment operators such as `+=`, `-=`, `*=`, `/=`, and `%=`. These operators combine assignment with arithmetic operations, providing a concise way to update variable values.

```
let num = 10;
num += 5; // Equivalent to num = num + 5
console.log(num); // Output: 15
```


## Bitwise Operators

Bitwise operators perform operations on binary representations of numbers. These include `bitwise AND &`, `bitwise OR |`, `bitwise XOR ^`, `bitwise NOT ~`, `left shift <<`, and `right shift >>`. While bitwise operators are less commonly used in everyday programming, they find applications in scenarios involving low-level operations or optimizations.






