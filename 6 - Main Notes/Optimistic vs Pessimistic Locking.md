2026-05-13 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Concurrency]]

# Optimistic vs Pessimistic Locking

## What is it?
Optimistic and pessimistic locking are two strategies used in database management to handle concurrent data access. Optimistic locking assumes that multiple transactions can complete without interfering with each other and only checks for conflicts at the end. In contrast, pessimistic locking assumes conflicts will occur and locks the data for a transaction as soon as it starts, preventing others from accessing it until finished.

## Why does it matter?
Choosing the right locking strategy is crucial for ensuring data integrity and performance in applications where multiple users or processes access the same data simultaneously. Optimistic locking can lead to better performance in low-conflict scenarios, while pessimistic locking provides safety in high-conflict environments. Understanding these strategies helps developers design systems that balance efficiency with data consistency.

## Example
Imagine a library system:

- **Optimistic Locking:** A user checks out a book, assuming no one else will check it out at the same time. When they try to finalize the checkout, the system checks if the book is still available. If another user checked it out in the meantime, the checkout fails, and the user is informed.

- **Pessimistic Locking:** When a user starts the checkout process, the system immediately locks the book, preventing anyone else from checking it out until the user completes or cancels their action. This way, the system avoids any conflicts entirely but may cause delays for others trying to access the book. 

Here's a simple Python snippet showing optimistic locking:

```python
def checkout_book(book_id, user_id):
    book = get_book(book_id)
    if book.is_available():
        # Proceed to checkout
        book.checkout(user_id)
    else:
        raise Exception("Book is already checked out.")
``` 

In this example, the system checks availability before finalizing the action.