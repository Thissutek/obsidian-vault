2026-06-09 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Design Patterns]]

# Pub/Sub Pattern

## What is it?
The Publish/Subscribe (Pub/Sub) pattern is a messaging pattern where senders (publishers) send messages without needing to know who will receive them (subscribers). Instead of a direct connection, a broker or message queue is often used to manage the communication, allowing for a decoupled architecture where components can evolve independently.

## Why does it matter?
The Pub/Sub pattern is crucial in modern software engineering because it enhances scalability and flexibility. By allowing components to communicate without tight coupling, developers can add or remove components easily without affecting the entire system. This is especially important in microservices architecture, where different services need to interact without being directly linked.

## Example
Imagine a weather service that publishes weather updates. Multiple applications can subscribe to receive these updates based on their needs:

```python
class WeatherService:
    def __init__(self):
        self.subscribers = []

    def subscribe(self, subscriber):
        self.subscribers.append(subscriber)

    def publish(self, update):
        for subscriber in self.subscribers:
            subscriber.receive(update)

class MobileApp:
    def receive(self, update):
        print(f"Mobile app received weather update: {update}")

# Usage
weather_service = WeatherService()
app = MobileApp()
weather_service.subscribe(app)
weather_service.publish("Sunny 75°F")
```

In this example, the `WeatherService` publishes updates, and the `MobileApp` subscribes to receive those updates without knowing the details of how the service works.