2026-03-11 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Design Patterns]]

# Decorator Pattern

## What is it?
The Decorator Pattern is a structural design pattern that allows you to add new behavior or responsibilities to objects dynamically. This is done by "wrapping" them in a new class, which implements the same interface but adds additional functionalities without altering the original object.

## Why does it matter?
This pattern is essential in software engineering because it promotes the Single Responsibility Principle, where classes should have one reason to change. It allows developers to extend functionality in a flexible way, making the code easier to maintain and adapt without requiring changes to existing code.

## Example
Here's a simple example in Python where we use the Decorator Pattern to add extra features to a basic coffee order:

```python
class Coffee:
    def cost(self):
        return 5

class MilkDecorator:
    def __init__(self, coffee):
        self._coffee = coffee
        
    def cost(self):
        return self._coffee.cost() + 2  # adding the cost of milk

class SugarDecorator:
    def __init__(self, coffee):
        self._coffee = coffee
        
    def cost(self):
        return self._coffee.cost() + 1  # adding the cost of sugar

# Usage
basic_coffee = Coffee()
milk_coffee = MilkDecorator(basic_coffee)
sugar_milk_coffee = SugarDecorator(milk_coffee)

print(sugar_milk_coffee.cost())  # Outputs: 8
```

In this example, we start with a basic coffee and progressively add milk and sugar using decorators, showcasing how we can enhance the coffee object without modifying its original code.