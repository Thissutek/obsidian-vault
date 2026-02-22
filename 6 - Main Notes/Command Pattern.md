2026-02-22 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Design Patterns]]

# Command Pattern

## What is it?
The Command Pattern is a behavioral design pattern that turns a request into a stand-alone object. This means that instead of calling a method directly, you create an object that encapsulates all the information needed to perform that action, including method name, parameters, and the object that owns the method. This allows for greater flexibility in your code, such as queueing requests or logging actions.

## Why does it matter?
In real software engineering, the Command Pattern helps in decoupling the sender of a request from the object that executes it. This separation of concerns makes your code more modular and easier to maintain. It also enables features like undo functionality, where you can store commands and later reverse them if needed.

## Example
Here’s a simple example in Python:

```python
class Light:
    def turn_on(self):
        print("The light is on")

    def turn_off(self):
        print("The light is off")

class Command:
    def __init__(self, light, action):
        self.light = light
        self.action = action

    def execute(self):
        if self.action == "on":
            self.light.turn_on()
        elif self.action == "off":
            self.light.turn_off()

# Usage
light = Light()
command_on = Command(light, "on")
command_off = Command(light, "off")

command_on.execute()  # Output: The light is on
command_off.execute()  # Output: The light is off
```

In this example, the `Command` class encapsulates the action to be performed (`turn_on` or `turn_off`) on the `Light` object, showcasing the flexibility of the Command Pattern.