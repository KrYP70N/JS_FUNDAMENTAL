# Basic Error Handling

Error handling is a critical aspect of writing robust and reliable JavaScript code. It involves identifying, managing, and responding to errors that may occur during the execution of your program. Effective error handling helps prevent unexpected crashes, provides meaningful feedback to users, and facilitates debugging and troubleshooting. Here's an explanation of error handling in JavaScript:


## Types of Errors

JavaScript errors can be broadly categorized into two types: syntax errors and runtime errors.

### syntax errors

Syntax errors occur when there are mistakes in the code structure, such as missing parentheses or semicolons. These errors are detected by the JavaScript engine during parsing and prevent the code from executing.

### Runtime errors

Runtime errors, also known as exceptions, occur during the execution of the code. Common examples include accessing undefined variables, calling undefined functions, or attempting to perform operations on incompatible data types.



## Try-Catch Statement

- JavaScript provides the try-catch statement for handling `runtime errors`.

- The `try` block contains the code that you want to monitor for errors.

- If an error occurs within the `try` block, control is transferred to the corresponding `catch` block.

- The `catch` block allows you to specify how to handle the error, such as logging an error message, displaying a user-friendly error notification, or gracefully recovering from the error.

```
try {
  // Code that may throw an error
} catch (error) {
  // Handle the error
  console.error('An error occurred:', error.message);
}
```


## Throwing Error

- You can explicitly throw errors using the `throw` statement.

- Throwing an error allows you to indicate that a certain condition or situation is exceptional and requires special handling.

- You can throw built-in error objects like `Error`, `SyntaxError`, `TypeError`, or create custom error objects to provide more specific information about the error.

```
function divide(x, y) {
  if (y === 0) {
    throw new Error('Division by zero');
  }
  return x / y;
}

try {
  console.log(divide(10, 0));
} catch (error) {
  console.error('Error:', error.message);
}
```


## Error Object

- When an error occurs, JavaScript creates an error object that contains information about the error, such as the error message, stack trace, and error name.

- Error objects can be customized by providing a descriptive error message and extending the `Error` class to create custom error types.

```
// with named params
try {
  throw new CustomError({
    name: 'Custom Error'
    message: 'Custom error message'
  });
} catch (error) {
  console.error('Error:', error.name, error.message);
}

// with extend Error class
class CustomError extends Error {
  constructor(message) {
    super(message);
    this.name = 'CustomError';
  }
}

try {
  throw new CustomError('Custom error message');
} catch (error) {
  console.error('Error:', error.name, error.message);
}
```


## Finally Block

- The `try-catch` statement can be augmented with a `finally` block, which is executed regardless of whether an error occurs.

- The `finally` block is useful for performing cleanup tasks, such as releasing resources or closing connections, that need to be executed regardless of the outcome of the `try` block.

```
try {
  // Code that may throw an error
} catch (error) {
  // Handle the error
} finally {
  // Cleanup code
}
```


## Global Error handling 

You can use global error handling mechanisms, such as `window.onerror` or `window.addEventListener('error')`, to capture unhandled errors that occur anywhere in your application.

```
window.onerror = function(message, source, lineno, colno, error) {
  console.error('Unhandled error:', message, source, lineno, colno, error);
};
```


By implementing proper error handling techniques in your JavaScript code, you can ensure that your applications are more robust, resilient, and user-friendly, ultimately providing a better experience for both developers and end-users.
