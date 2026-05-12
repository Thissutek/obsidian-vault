2026-05-12 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Software Principles]]

# Dependency Injection

## What is it?
Dependency Injection (DI) is a design pattern that allows a class to receive its dependencies from an external source rather than creating them internally. By doing so, the class becomes more flexible and easier to test, since you can easily swap out dependencies without modifying the class itself.

## Why does it matter?
Dependency Injection is important because it promotes loose coupling between components, making your codebase more maintainable and scalable. When components are decoupled, you can easily change or update individual parts of your application without affecting others. This is especially crucial in large software projects where different teams may work on distinct modules.

## Example
Here’s a simple example in Python using DI:

```python
class Database:
    def connect(self):
        return "Database connection established."

class UserService:
    def __init__(self, database: Database):
        self.database = database

    def get_user_data(self):
        return self.database.connect()

# Dependency is injected here
db = Database()
user_service = UserService(db)
print(user_service.get_user_data())  # Outputs: Database connection established.
```

In this example, `UserService` relies on `Database` but doesn’t create it itself. This allows you to easily change `Database` to another implementation without modifying `UserService`.