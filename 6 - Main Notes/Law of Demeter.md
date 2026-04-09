2026-04-09 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Software Principles]]

# Law of Demeter

## What is it?
The Law of Demeter, often referred to as the "principle of least knowledge," is a design guideline for developing software, particularly in object-oriented programming. It suggests that a module or object should only interact with its immediate neighbors, not with the internal details of other modules or objects. This means an object should only call methods of itself, its direct properties, or objects created within its own methods.

## Why does it matter?
The Law of Demeter promotes loose coupling between components, making your code easier to maintain and less prone to errors. By reducing dependencies, changes to one part of the codebase are less likely to ripple through and break others, which significantly enhances code modularity and readability—key aspects of good software engineering practices.

## Example
Here's a simple example in Python:

```python
class Engine:
    def start(self):
        return "Engine started"

class Car:
    def __init__(self):
        self.engine = Engine()

    def start_car(self):
        return self.engine.start()

# Usage
my_car = Car()
print(my_car.start_car())  # Output: Engine started
```

In this example, the `Car` class interacts directly with its `Engine` object to start the car. It doesn't reach into an `Engine` object to access nested components or methods, adhering to the Law of Demeter.