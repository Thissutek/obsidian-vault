2026-04-02 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Design Patterns]]

# Observer Pattern

## What is it?
The Observer Pattern is a design pattern that allows one object, known as the "subject," to notify multiple other objects, called "observers," about changes in its state. This is useful for implementing a subscription mechanism where observers can register to receive updates whenever the subject changes.

## Why does it matter?
In software engineering, the Observer Pattern helps to create a flexible and decoupled system where components can interact without being tightly bound to each other. This makes your code easier to maintain, test, and extend because you can add or remove observers without changing the subject, promoting a cleaner architecture.

## Example
Here’s a simple example in Python demonstrating the Observer Pattern:

```python
class Subject:
    def __init__(self):
        self.observers = []
    
    def attach(self, observer):
        self.observers.append(observer)
    
    def notify(self, message):
        for observer in self.observers:
            observer.update(message)

class Observer:
    def update(self, message):
        print(f"Received message: {message}")

# Usage
subject = Subject()
observer1 = Observer()
observer2 = Observer()

subject.attach(observer1)
subject.attach(observer2)

subject.notify("Hello, Observers!")
```

In this example, when the `subject` notifies its observers with a message, both `observer1` and `observer2` receive it, demonstrating how multiple parts of your system can react to changes in state without direct dependencies.