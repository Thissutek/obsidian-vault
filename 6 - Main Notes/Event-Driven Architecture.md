2026-06-05 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Architecture]]

# Event-Driven Architecture

## What is it?
Event-Driven Architecture (EDA) is a software design pattern that revolves around the production, detection, consumption, and reaction to events. An event is any significant change in state or an occurrence that can trigger a response, allowing different components of a system to communicate and respond independently.

## Why does it matter?
EDA is important because it promotes a decoupled and scalable system design. This means that components can evolve independently, making it easier to add features and improve performance without affecting the entire system. In real-world applications, such as online shopping platforms, EDA allows for real-time updates and a responsive user experience, enhancing customer satisfaction.

## Example
Here's a simple example in Python that demonstrates an event-driven approach using a basic event system:

```python
class Event:
    def __init__(self, name):
        self.name = name

class EventHandler:
    def handle(self, event):
        print(f"Handling event: {event.name}")

class EventEmitter:
    def __init__(self):
        self.handlers = []

    def subscribe(self, handler):
        self.handlers.append(handler)

    def emit(self, event):
        for handler in self.handlers:
            handler.handle(event)

# Usage
event_emitter = EventEmitter()
event_emitter.subscribe(EventHandler())
event_emitter.emit(Event("User Signed Up"))
```

In this example, when a "User Signed Up" event occurs, the system notifies the EventHandler, demonstrating how components can react to events without being tightly integrated.