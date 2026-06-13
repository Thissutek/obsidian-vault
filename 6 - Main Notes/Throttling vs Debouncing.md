2026-06-13 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Concurrency]]

# Throttling vs Debouncing

## What is it?
Throttling and debouncing are two techniques used to limit the number of times a function is executed in response to events like scrolling or resizing. Throttling ensures a function is executed at regular intervals—regardless of how often an event occurs—while debouncing delays the function execution until a specified time has passed since the last event.

## Why does it matter?
These techniques are important for optimizing performance in web applications. For instance, when users resize a window or scroll a page, an excessive number of function calls can slow down the application. By using throttling and debouncing, you can enhance user experience and reduce unnecessary resource consumption, ensuring that your application runs smoothly and efficiently.

## Example
Here’s a simple example in JavaScript to illustrate the difference:

```javascript
// Throttling example
let lastExecution = 0;
function throttle(callback, limit) {
    return function() {
        const now = new Date().getTime();
        if (now - lastExecution >= limit) {
            lastExecution = now;
            callback();
        }
    };
}

// Debouncing example
function debounce(callback, delay) {
    let timer;
    return function() {
        clearTimeout(timer);
        timer = setTimeout(callback, delay);
    };
}

// Usage
window.addEventListener('scroll', throttle(() => {
    console.log('Throttled scroll event');
}, 100));

window.addEventListener('resize', debounce(() => {
    console.log('Debounced resize event');
}, 300));
```

In this code, the `throttle` function limits how often the scroll event can trigger a callback, while the `debounce` function delays the execution of the resize event until after the user has stopped resizing for 300 milliseconds.