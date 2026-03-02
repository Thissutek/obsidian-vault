2026-03-02 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Software Principles]]

# YAGNI Principle

## What is it?
YAGNI stands for "You Aren't Gonna Need It." It's a software development principle that suggests you should not add functionality until it is necessary. In other words, avoid building features that you think you might need in the future but aren't currently required.

## Why does it matter?
YAGNI is important because it helps keep your codebase simpler and more maintainable. By focusing only on the features that are needed right now, developers can reduce complexity, save time, and avoid over-engineering solutions that may never be used. This leads to faster development cycles and less technical debt over time.

## Example
Consider you’re creating a simple to-do list application. Instead of building an elaborate tagging system, complex user authentication, or notifications right away, you start with basic functionality: adding, editing, and deleting tasks. Once users request those advanced features based on their needs, you can then implement them. This approach keeps your initial development focused and efficient.

```python
class ToDoList:
    def __init__(self):
        self.tasks = []

    def add_task(self, task):
        self.tasks.append(task)

    def list_tasks(self):
        return self.tasks

# Example usage
todo = ToDoList()
todo.add_task("Finish homework")
print(todo.list_tasks())  # Output: ['Finish homework']
```