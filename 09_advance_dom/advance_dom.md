# Caching DOM Reference

Caching DOM references involves storing references to frequently accessed DOM elements in variables, rather than repeatedly querying the DOM for those elements. This practice improves performance by reducing the number of DOM queries, especially in situations where elements are accessed or manipulated frequently.

Here's a simple example demonstrating how to cache DOM references:

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cache DOM References</title>
    <style>
        .highlight {
            background-color: yellow;
        }
    </style>
</head>
<body>
    <div id="container">
        <button id="button">Click me</button>
    </div>

    <script>
        // Cache DOM references
        const container = document.getElementById('container');
        const button = document.getElementById('button');

        // Add event listener to button
        button.addEventListener('click', function() {
            // Toggle class on container
            container.classList.toggle('highlight');
        });
    </script>
</body>
</html>
```


**In this example:**

- We have a container `<div>` with an ID of "container" and a button element with an ID of `"button"`.

- We cache references to both the container and the button using document.getElementById() and store them in variables named - container and button, respectively.

- We then add an event listener to the button that toggles the "highlight" class on the container when the button is clicked.

By caching the DOM references outside of the event listener function, we avoid querying the DOM for those elements repeatedly every time the button is clicked. This improves performance, especially in more complex applications where multiple DOM queries may be involved.


# Event delegation

Event delegation is a technique in JavaScript where instead of attaching event handlers directly to individual elements, you attach a single event handler to a parent element that listens for events on its descendants. This is particularly useful when you have multiple elements of the same type that need the same event handling behavior.

Here's an example demonstrating how to use event delegation:

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Event Delegation</title>
</head>
<body>
    <ul id="todoList">
        <li>Task 1 <button class="deleteBtn">Delete</button></li>
        <li>Task 2 <button class="deleteBtn">Delete</button></li>
        <li>Task 3 <button class="deleteBtn">Delete</button></li>
    </ul>

    <script>
        // Get the parent element
        const todoList = document.getElementById('todoList');

        // Add event listener to the parent element
        todoList.addEventListener('click', function(event) {
            // Check if the clicked element is a delete button
            if (event.target.classList.contains('deleteBtn')) {
                // If yes, delete the parent <li> element
                event.target.parentNode.remove();
            }
        });
    </script>
</body>
</html>
```

**In this example:**

- We have an unordered list `<ul>` with several list items `<li>` each containing a task and a delete button.

- Instead of attaching event listeners to each delete button individually, we attach a single event listener to the `<ul>` element with the ID `"todoList"`.

- When a click event occurs within the `<ul>` element, the event bubbles up to the parent `<ul>` element.

- Inside the event listener, we check if the clicked element (event.target) has a class of "deleteBtn". If it does, we remove its parent `<li>` element from the DOM.

Using event delegation in this way makes the code more efficient and scalable, especially when dealing with a large number of dynamically created elements or elements that are added or removed frequently. It also reduces the amount of memory used since you only need one event listener instead of one for each individual element.



# Batch DOM Manipulation 

Batch DOM manipulation refers to the practice of grouping multiple DOM manipulation operations together and executing them as a single batch. This approach is aimed at reducing the number of times the DOM (Document Object Model) is updated, which can lead to improved performance and better user experience.

Here's a simple example to illustrate batch DOM manipulation:

```
function batchDOMManipulations() {
  const container = document.getElementById('container');
  const fragment = document.createDocumentFragment();

  for (let i = 0; i < 10; i++) {
    const newDiv = document.createElement('div');
    newDiv.textContent = 'Element ' + i;
    fragment.appendChild(newDiv);
  }

  container.appendChild(fragment);
}
```