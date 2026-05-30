2026-05-30 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Programming Fundamentals]]

# Closures and Lexical Scope

## What is it?
A closure is a function that "remembers" the environment in which it was created, even when it’s executed outside of that environment. This means it can access variables from its surrounding lexical scope, which is the space where it was defined. Lexical scope refers to how variable scope is determined by the physical structure of the code.

## Why does it matter?
Understanding closures and lexical scope is crucial because they allow for powerful programming patterns such as data encapsulation, function factories, and managing private state. In real software engineering, closures enable you to create functions that maintain their own state without polluting the global scope, making your code more modular and easier to maintain.

## Example
Here’s a simple example in JavaScript:

```javascript
function makeCounter() {
    let count = 0;  // count is in the lexical scope of makeCounter
    return function() {
        count += 1;  // closure: this function can access count
        return count;
    };
}

const counter = makeCounter();
console.log(counter()); // Output: 1
console.log(counter()); // Output: 2
```

In this example, `count` is a private variable that the inner function can access and modify, demonstrating how closures work effectively within their lexical scope.