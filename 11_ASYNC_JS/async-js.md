# Asynchronous Javascript 

Asynchronous JavaScript allows code execution to continue while waiting for certain tasks, such as fetching data from a server, reading files, or handling user interactions. This non-blocking behavior ensures that the user interface remains responsive and smooth, even when dealing with time-consuming operations.


## Key concepts in Asynchronous Javascript

### Callbacks

Callback functions are a fundamental building block of asynchronous JavaScript. They allow developers to define what should happen after an asynchronous operation completes. However, nested callbacks can lead to callback hell, making code difficult to read and maintain.

```
// Function that takes two numbers and a callback function
function add(x, y, callback) {
    const result = x + y;
    // Call the callback function with the result
    callback(result);
}

// Callback function to handle the result
function displayResult(result) {
    console.log("The result is:", result);
}

// Calling the add function and passing the displayResult function as a callback
add(5, 3, displayResult); // Output: The result is: 8
```


### Promise 

Promises provide a more elegant solution for handling asynchronous operations. A promise represents the eventual completion or failure of an asynchronous task and allows chaining of multiple asynchronous operations. Promises simplify error handling and make asynchronous code more readable.

You can refer to the step-by-step breakdown of how a Promise works in the subsequent section.

#### Creation 

To create a Promise, you typically instantiate it with the `new Promise constructor`, passing a function (often referred to as the "executor") as an argument. This function, in turn, takes two arguments, `resolve` and `reject`, which are functions provided by the Promise implementation.

```
const myPromise = new Promise((resolve, reject) => {
    // Asynchronous operation, e.g., fetching data
    // If successful, call resolve with the result
    // If there's an error, call reject with an error object
});
```


#### State

A Promise can be in one of three states:

- **Pending**: Initial state, neither fulfilled nor rejected.

- **Fulfilled (resolved)**: The operation completed successfully.

- **Rejected**: The operation failed.


#### Consumption

You can consume the value of a Promise using its `then()` method. This method takes two optional callback functions: one to handle the `fulfillment (resolve)` and another to handle `rejection (reject)`.

```
myPromise.then(
    result => {
        // Handle successful completion (resolve)
        console.log('Success:', result);
    },
    error => {
        // Handle error (reject)
        console.error('Error:', error);
    }
);
```


#### Chaining 

Promises allow you to chain multiple asynchronous operations together using `then()`.

```
myPromise
    .then(result => {
        // First operation successful, do something with result
        return someOtherAsyncOperation(result);
    })
    .then(newResult => {
        // Handle the result of the second operation
        console.log('Second operation result:', newResult);
    })
```


#### Error Handling

You can handle errors using the `catch()` method, which is similar to providing a rejection handler to `then()`.


```
myPromise
    .then(result => {
        // First operation successful, do something with result
        return someOtherAsyncOperation(result);
    })
    .then(newResult => {
        // Handle the result of the second operation
        console.log('Second operation result:', newResult);
    })
    .catch(error => {
        // Handle errors from any of the previous operations
        console.error('An error occurred:', error);
    });
```


## Complete Example

```
// Function simulating an asynchronous operation (e.g., fetching data from a server)
function fetchData() {
    // Simulating an asynchronous operation with setTimeout
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            // Simulating successful completion with resolve
            // const data = { name: "John", age: 30 };
            // resolve(data);
            // Simulating failure with reject
            reject(new Error("Failed to fetch data"));
        }, 2000); // Simulating a delay of 2 seconds
    });
}

// Consuming the Promise
fetchData()
    .then(data => {
        // Handling successful completion
        console.log("Data received:", data);
        // Returning a value to chain promises
        return data.age * 2;
    })
    .then(doubledAge => {
        // Chaining another asynchronous operation
        console.log("Doubled age:", doubledAge);
        // Simulating an asynchronous operation with setTimeout
        return new Promise(resolve => {
            setTimeout(() => {
                resolve("Additional data");
            }, 1000); // Simulating a delay of 1 second
        });
    })
    .then(additionalData => {
        // Handling the result of the chained operation
        console.log("Additional data:", additionalData);
    })
    .catch(error => {
        // Handling errors
        console.error("An error occurred:", error.message);
    })
    .finally(() => {
        // Executed regardless of the Promise's outcome
        console.log("Promise finally block executed");
    });
```