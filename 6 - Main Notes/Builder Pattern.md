2026-05-18 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Design Patterns]]

# Builder Pattern

## What is it?
The Builder Pattern is a design pattern that helps create complex objects step by step. Instead of constructing an object in one go, this pattern allows you to specify different parts of an object incrementally, making it easier to manage and understand how the object is built. It’s particularly useful when an object requires many parameters or when you want to create variations of the same object type.

## Why does it matter?
In real software engineering, using the Builder Pattern can improve the readability and maintainability of your code. When dealing with complex objects, having a clear, step-by-step construction process makes it easier for other developers (or your future self) to understand how to create and modify those objects. This approach can help reduce errors, especially when there are optional parameters or when an object has default values.

## Example
Here’s a simple example in Python that demonstrates the Builder Pattern for creating a `Pizza` object:

```python
class Pizza:
    def __init__(self):
        self.toppings = []

    def add_topping(self, topping):
        self.toppings.append(topping)

class PizzaBuilder:
    def __init__(self):
        self.pizza = Pizza()

    def add_pepperoni(self):
        self.pizza.add_topping('pepperoni')
        return self

    def add_mushrooms(self):
        self.pizza.add_topping('mushrooms')
        return self

    def build(self):
        return self.pizza

# Using the Builder
builder = PizzaBuilder()
my_pizza = builder.add_pepperoni().add_mushrooms().build()

print(my_pizza.toppings)  # Output: ['pepperoni', 'mushrooms']
```

In this example, the `PizzaBuilder` class allows you to create a `Pizza` step by step, making it clear what toppings you are adding before finalizing the object.