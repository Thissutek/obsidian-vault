2026-07-01 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Design Patterns]]

# Command Pattern

## What is it?
The Command Pattern is a behavioral design pattern that encapsulates a request as an object, thereby allowing for parameterization of clients with queues, requests, and operations. This pattern separates the object that invokes the operation from the one that knows how to perform it. Essentially, it turns actions (commands) into first-class objects.

## Why does it matter?
This pattern is important in software engineering because it promotes decoupling, making your code more flexible and easier to manage. By using the Command Pattern, you can support undoable operations, queue requests, or log changes, which are often required in user interfaces and transactional systems. It also makes it easier to add new commands without modifying existing code.

## Example
Here’s a simple example in Python showcasing the Command Pattern:

```python
class Command:
    def execute(self):
        pass

class LightOnCommand(Command):
    def __init__(self, light):
        self.light = light
        
    def execute(self):
        self.light.turn_on()

class Light:
    def turn_on(self):
        print("The light is on!")

class RemoteControl:
    def submit(self, command):
        command.execute()

light = Light()
light_on = LightOnCommand(light)
remote = RemoteControl()

# Use the remote to turn on the light
remote.submit(light_on)
```

In this example, `LightOnCommand` encapsulates the command to turn on a light, while `RemoteControl` is the invoker that executes this command. This makes it easy to extend functionality by adding new commands later!