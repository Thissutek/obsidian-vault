2026-02-07 15:52

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Architecture]]

# Hexagonal Architecture

## What is it?
Hexagonal Architecture, also known as the Ports and Adapters pattern, is a software design approach that aims to separate the core logic of an application from external influences, such as databases, user interfaces, or third-party services. It organizes the system into a central core (the application’s business logic) surrounded by various "ports" (interfaces) and "adapters" (implementations) that enable communication with external systems.

## Why does it matter?
This architecture is important because it enhances the maintainability and testability of applications. By isolating the core logic from external dependencies, developers can change or replace these dependencies without affecting the core functionality. This leads to cleaner code, easier unit testing, and a more flexible system that can adapt to changes over time.

## Example
Here's a simple Python example demonstrating a hexagonal structure for a book management system:

```python
# Core business logic
class Book:
    def __init__(self, title):
        self.title = title

    def get_title(self):
        return self.title

# Port (interface)
class BookRepository:
    def save(self, book): pass
    def find(self, title): pass

# Adapter (implementation)
class InMemoryBookRepository(BookRepository):
    def __init__(self):
        self.books = []
        
    def save(self, book):
        self.books.append(book)
        
    def find(self, title):
        return next((book for book in self.books if book.get_title() == title), None)

# Using the adapter
repo = InMemoryBookRepository()
repo.save(Book("1984"))
print(repo.find("1984").get_title())  # Outputs: 1984
```

In this example, `Book` represents the core logic, while `BookRepository` serves as the port, and `InMemoryBookRepository` is the adapter that interacts with that logic.