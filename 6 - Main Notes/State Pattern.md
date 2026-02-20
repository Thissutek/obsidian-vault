2026-02-20 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Design Patterns]]

# State Pattern

## What is it?
The State Pattern is a design pattern that allows an object to alter its behavior when its internal state changes. Instead of having many conditional statements to manage different states, this pattern encapsulates each state in a separate class, making the code more modular and easier to manage.

## Why does it matter?
In software engineering, managing complex state behaviors can become tedious and error-prone, especially as the application grows. By using the State Pattern, you can keep your code clean and organized, which improves maintainability and scalability. It also promotes adherence to the Single Responsibility Principle, as each state class has one job: to represent and manage its specific state.

## Example
Here's a simple example in Python that illustrates the State Pattern with a traffic light system:

```python
class TrafficLight:
    def __init__(self):
        self.state = Red(self)

    def change(self):
        self.state.change()

class Red:
    def __init__(self, light):
        self.light = light

    def change(self):
        print("Red light, stop.")
        self.light.state = Green(self.light)

class Green:
    def __init__(self, light):
        self.light = light

    def change(self):
        print("Green light, go.")
        self.light.state = Yellow(self.light)

class Yellow:
    def __init__(self, light):
        self.light = light

    def change(self):
        print("Yellow light, prepare to stop.")
        self.light.state = Red(self.light)

# Usage
traffic_light = TrafficLight()
traffic_light.change()  # Output: Red light, stop.
traffic_light.change()  # Output: Green light, go.
traffic_light.change()  # Output: Yellow light, prepare to stop.
```

In this example, each light color (state) manages its behavior, making it easier to extend or modify in the future!