# Variable

Variable in javascript are use to store and manipulate data. They serve as containers that hold values, wich can be different types such as `string`, `number`, `array` and `objects` etc. You must declare it using the `var`, `let` or `const` keyword. 


## VAR, LET, CONST

| Name              | Description                       |
| ----------------- | --------------------------------- |
| var               | Use to declare variable that have function scope or global scope. Variable declared with `var` can be redeclare and resignned within their scope |
| let               | Introduced in ES6 and is used to declare variables that have block scope. Variables declared with let can be reassigned but cannot be redeclared within the same scope. | 
| const             | Also introduced in ES6 and is used to declare variables that have block scope. Variables declared with const cannot be reassigned or redeclared. |


## Scope

Scope in JavaScript refers to the visibility and accessibility of variables and functions within your code. It determines where these identifiers are accessible and where they are not. Understanding scope is crucial for writing maintainable and bug-free code.

There are two main types of scope in Javascript :

1. **Global Scope** : Variables declared outside of any function or block have global scope. They can be accessed from anywhere in the code, including inside functions and nested scopes.

```
var globalVar = "I'm a global variable";

function myFunction() {
    console.log(globalVar); // Output: I'm a global variable
}

console.log(globalVar); // Output: I'm a global variable
```

2. **Local Scope** : Variables declare inside of curly bracked are call `Local Scope`. We can separate two scope inside local scope. These are `function Scope` and `Block Scope`.

- **Function Scope**: Variables declared inside a function have function scope. They are accessible only within that function.

```
function myFunction() {
    var localVar = "I'm a local variable";
    console.log(localVar); // Output: I'm a local variable
}

myFunction();
console.log(localVar); // Error: localVar is not defined

```

-  **Block Scope (introduced in ES6)** : Variables declared with let and const inside a block (a set of opening and closing curly braces) have block scope. They are accessible only within that block. Block scope is particularly useful for variables declared within loops, conditionals, and other control flow structures.

```
if (true) {
    let blockVar = "I'm a block-scoped variable";
    console.log(blockVar); // Output: I'm a block-scoped variable
}

console.log(blockVar); // Error: blockVar is not defined

```



## Data Types

Javascript support various data types, which can be categorized into two main group: `Primitive` and `Reference` data types.

### Primitive Data Types

| Name              | Description                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| Number            | Represents numeric values, including integers and floating-point numbers |
| String            | Represents textual data enclosed within single (''), double ("") or backticks (``) quotes |
| Boolean           | Represents a logical value of true or false                              | 
| Null              | Represents the intentional absence of any value                          |
| Undefined         | Represents a variable that has been declared but has not been assigned a value |
| Symbol            | Represents a unique identifier introduced in ES6                         |

### Reference Data Types

| Name              | Description                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| Object            | Represents a collection of key-value pairs, where values can be of any data type, including other objects, functions, and arrays |
| Array             | Represents a collection of elements stored in sequential order, indexed by integers |
| Function          | Represents a reusable block of code that performs a specific task                   | 
| Date              | Represents a specific point in time, including the date and time components         | 
| RegExp            | Represents a regular expression, used for pattern matching within strings           |
