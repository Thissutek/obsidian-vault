2026-06-16 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Software Principles]]

# Composition Over Inheritance

## What is it?
Composition over inheritance is a design principle in object-oriented programming that favors using composition—combining simple objects or functions—to build more complex ones, rather than relying on class inheritance. Inheritance creates a "is-a" relationship, while composition creates a "has-a" relationship, allowing for greater flexibility and reusability of code.

## Why does it matter?
This principle is important because it helps developers avoid the pitfalls of deep inheritance hierarchies, which can lead to tight coupling and make code harder to maintain and understand. By using composition, you can mix and match behaviors more easily, making your codebase more modular and adaptable to change as requirements evolve.

## Example
Here's a simple example in Python demonstrating composition:

```python
class Engine:
    def start(self):
        return "Engine started"

class Car:
    def __init__(self):
        self.engine = Engine()  # Composition: Car has an Engine

    def start(self):
        return self.engine.start()  # Delegating the start method to the Engine

my_car = Car()
print(my_car.start())  # Output: Engine started
```

In this example, instead of Car inheriting from Engine, it contains an instance of Engine, showcasing how composition allows for more flexibility without creating a rigid structure.