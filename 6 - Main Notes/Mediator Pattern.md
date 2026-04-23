2026-04-23 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Design Patterns]]

# Mediator Pattern

## What is it?
The Mediator Pattern is a design pattern that allows various components of an application to communicate with each other indirectly through a central mediator object. Instead of components communicating directly, they send messages to the mediator, which then manages the interactions, promoting loose coupling between components.

## Why does it matter?
Using the Mediator Pattern can simplify complex communication between multiple objects, making your code easier to maintain and extend. It helps to reduce dependencies among components, which can lead to fewer bugs and better scalability as your application grows. This is especially important in large systems where direct communication can create tangled connections and tight coupling.

## Example
Imagine a chat room where users send messages. Instead of each user directly interacting with every other user, they send messages to a ChatRoom mediator. The ChatRoom then handles the distribution of messages to the correct users.

Here's a simple Python example:

```python
class ChatRoom:
    def show_message(self, user, message):
        print(f"{user}: {message}")

class User:
    def __init__(self, name, chat_room):
        self.name = name
        self.chat_room = chat_room

    def send_message(self, message):
        self.chat_room.show_message(self.name, message)

# Usage
chat_room = ChatRoom()
user1 = User("Alice", chat_room)
user2 = User("Bob", chat_room)

user1.send_message("Hi Bob!")
user2.send_message("Hello Alice!")
```

In this example, `User` objects communicate through the `ChatRoom`, demonstrating how the Mediator Pattern keeps their interactions organized and decoupled.