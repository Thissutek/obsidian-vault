2026-06-20 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Software Principles]]

# Law of Demeter

## What is it?
The Law of Demeter, also known as the Principle of Least Knowledge, is a design guideline for developing software, particularly in object-oriented programming. It suggests that an object should only communicate with its immediate friends and not with strangers, meaning it should only call methods on objects that it directly interacts with, avoiding interactions with objects that are several layers away. This helps in reducing dependencies between components.

## Why does it matter?
The Law of Demeter promotes loose coupling, making your code more modular and easier to maintain. When objects are less dependent on one another, changes can be made to one part of the system without impacting others, which is crucial in software engineering for scalability and reducing bugs. By adhering to this principle, developers can create cleaner, more understandable codebases that are simpler to test and refactor.

## Example
Here's a simple Python example demonstrating the Law of Demeter:

```python
class Engine:
    def start(self):
        return "Engine started"

class Car:
    def __init__(self):
        self.engine = Engine()

    def start(self):
        return self.engine.start()  # Directly calls the engine's start method

class Driver:
    def drive(self, car):
        return car.start()  # Calls the car's start method, not the engine's directly

driver = Driver()
my_car = Car()
print(driver.drive(my_car))  # Output: Engine started
```

In this example, the `Driver` interacts only with the `Car` object and not directly with the `Engine`, adhering to the Law of Demeter.