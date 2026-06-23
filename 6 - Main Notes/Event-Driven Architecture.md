2026-06-23 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Architecture]]

# Event-Driven Architecture

## What is it?
Event-Driven Architecture (EDA) is a software design pattern that focuses on the production, detection, consumption, and reaction to events. An event is a significant change in state or an action that occurs, like a user clicking a button or data being updated. In this architecture, components communicate through events rather than direct calls, allowing for a more decoupled and scalable system.

## Why does it matter?
Event-Driven Architecture is important because it enhances system responsiveness and scalability. By allowing components to work independently and react to events as they happen, applications can handle high volumes of transactions and user interactions efficiently. This is particularly valuable in distributed systems where different services need to respond to changes without tightly coupling their functionalities.

## Example
Here’s a simple example in Python using a basic event system:

```python
class Event:
    def __init__(self, message):
        self.message = message

class EventListener:
    def handle_event(self, event):
        print(f"Event received: {event.message}")

def main():
    listener = EventListener()
    event = Event("User signed up")
    listener.handle_event(event)

main()
```

In this example, we create an `Event` representing a user sign-up and an `EventListener` that reacts to the event by printing a message. This simple pattern can be expanded to more complex systems, where multiple listeners react to various events in real-time.