# DOM CHEETSHEET 

Accessing DOM elements is a fundamental aspect of web development, as it allows developers to interact with and manipulate the structure and content of web pages dynamically. Here's a comprehensive overview of various methods for accessing DOM elements:

## Accessing Methods

| Method                               | Description                                     |
| ------------------------------------ | ----------------------------------------------- |
| getElementById(`id`)                 | retrieves an element by its unique id attribute |
| getElementsByClassName(`class_name`) | returns a collection of elements that have a specified class name |
| getElementsByTagName(`tag`)          | returns a collection of elements with a specified tag name        |
| querySelector(`css_selector`)        | the first element that matches a specified CSS selector           |
| querySelectorAll(`css_selector`)     | returns a static (non-live) NodeList representing a list of elements that match a specified group of CSS selectors |


## Traversal Methods

| Method                               | Description                                     |
| ------------------------------------ | ----------------------------------------------- |
| parentNode()                         | returns the parent node of an element           | 
| childNodes()                         | returns a NodeList of child nodes of an element | 
| firstChild()                         | returns the first child node of an element      | 
| lastChild()                          | returns the last child node of an element       | 
| nextSibling()                        | returns the next sibling of an element          | 
| previousSibling()                    | returns the previous sibling of an element      | 


## Create or Remove Methods 

| Method                               | Description                                     |
| ------------------------------------ | ----------------------------------------------- |
| createElement(`tagName`)             | create new element with specified tag           |
| createTextNode(`text`)               | create new text node                            | 
| appendChild(`node`)                  | insert child into selected node                 | 
| removeChild(`childName`)             | remove selected node from the parent node       |
| replaceChild(`newNode`, `oldNode`)   | replace old node with new one                   |
| insertBefore(`node`, `beforeNode`)   | insert new element befored specified child node |


## Special Property
 
| Property                  | Description                         |
| ------------------------- | ----------------------------------- | 
| body                      | represents the `body` element of the current document |
| head                      | represents the `head` element of the current document |
| id                        | return `id` of current element                        |
| className                 | returns or sets the class attribute of the element    | 
| classList                 | returns a DOMTokenList representing the class attribute of the element |
| attributes                | returns a NamedNodeMap representing the attributes of the element |
| style                     | returns an object representing the inline style of the element    |
| textContent               | returns the text content of the element and its descendants       | 
| innerHTML                 | returns or sets the HTML content of the element                   | 
| value                     | returns or sets value of HTML form element                        | 
| nodeName                  | returns the name of the node, typically the tag name for element nodes   |
| nodeType                  | returns the type of node as a numeric value                       | 
| parentNode                | returns the parent node of the element                            | 
| childNodes                | returns the child node of the element                             | 
| firstChild                | returns the first child node of the element                       | 
| lastChild                 | returns the last child node of the element                        | 
| nextSibling               | returns the next node at the same tree level                      | 
| previousSibling           | returns the previous node at the same tree level                  | 
| offsetWidth               | returns the width of the element, including padding, border, and scrollbar, if any |
| offsetHeight              | returns the height of the element, including padding, border, and scrollbar, if any | 
| offsetParent              | returns the nearest positioned ancestor element                   |
| clientWidth               | returns the width of the element, including padding but excluding scrollbar and border |
| clientHeight              | returns the height of the element, including padding but excluding scrollbar and border |
| scrollWidth               | returns the total width of the element's content, including overflow content not visible on the screen |
| scrollHeight              | returns the total height of the element's content, including overflow content not visible on the screen |
| scrollTop                 | returns or sets the number of pixels the content of an element is scrolled vertically |
| scrollLeft                | returns or sets the number of pixels the content of an element is scrolled horizontally |


