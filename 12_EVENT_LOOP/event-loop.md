# Event Loop

The event loop is a fundamental concept in JavaScript and other languages like Python and Ruby that use asynchronous programming models. It's essentially what allows JavaScript to perform non-blocking I/O operations, such as making AJAX requests, reading files, or waiting for events to occur, without stopping the execution of the rest of your code.

Here's a breakdown of how the event loop works:


## Call Stack

- When you execute JavaScript code, it's processed in a single-threaded manner through a call stack.

- Each function call creates a new frame that's added to the top of the call stack.

- The call stack follows the Last In, First Out (LIFO) principle, meaning that the last function added to the stack is the first one to be executed.


## Web APIs and Callback Queue:

- When you execute asynchronous code, such as making an AJAX request or setting a timer, JavaScript doesn't wait for these operations to complete. Instead, it delegates them to the browser's Web APIs (or Node.js APIs in the case of server-side JavaScript).

- Once the asynchronous operation is complete, a callback function associated with that operation is pushed to the Callback Queue.


## Event Loop

- The event loop constantly checks two things: the call stack and the Callback Queue.

- If the call stack is empty, the event loop takes the first function from the Callback Queue and pushes it onto the call stack to be executed.

- This process repeats indefinitely, allowing JavaScript to execute asynchronous operations while still handling synchronous code and keeping the UI responsive.


### Here's a simplified example of how the event loop works:

```
console.log('Start');

setTimeout(() => {
  console.log('Timer callback');
}, 0);

console.log('End');

// output
// 1. Start
// 2. End
// 3. Timer callback
```