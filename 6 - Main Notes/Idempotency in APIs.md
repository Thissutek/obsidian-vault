2026-05-23 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[API & Networking]]

# Idempotency in APIs

## What is it?
Idempotency in APIs refers to the property of an operation that can be performed multiple times without changing the result beyond the initial application. In simpler terms, if you call the same API endpoint with the same data multiple times, the outcome should be the same as if you called it just once. This is crucial for operations like updating resources or making payments, where you want to avoid duplicate effects.

## Why does it matter?
Understanding idempotency is essential in software engineering because it ensures reliability and consistency in API interactions, especially in distributed systems. For instance, if a user resends a command due to a network issue, an idempotent API will prevent unintended duplications, thus protecting data integrity and providing a smoother user experience.

## Example
Consider a RESTful API for updating a user's email address. The endpoint `PUT /users/123/email` is designed to change the email address of the user with ID 123. If we send the request with the same new email, regardless of how many times we submit it, the email will only be updated once:

```python
import requests

# Example of an idempotent API call
response = requests.put('https://api.example.com/users/123/email', json={'email': 'new.email@example.com'})
print(response.status_code)  # Returns 200 OK on the first call, the same response on subsequent calls
```

In this example, calling the endpoint multiple times with the same email does not change the outcome after the first call, demonstrating idempotency.