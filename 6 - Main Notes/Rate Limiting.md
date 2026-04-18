2026-04-18 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[System Design]]

# Rate Limiting

## What is it?
Rate limiting is a technique used to control the amount of incoming requests to a server or service within a specified time frame. This helps ensure that a system can handle incoming traffic without being overwhelmed, thus maintaining performance and reliability.

## Why does it matter?
In real software engineering, rate limiting is crucial for protecting resources from abuse, such as preventing denial-of-service attacks where a service is flooded with too many requests. It also helps in ensuring fair usage among users, managing API call limits, and maintaining a smooth and responsive user experience.

## Example
Consider a web API that allows users to fetch data. You can implement rate limiting to allow a maximum of 5 requests per minute per user. Here's a simple example in Python using a dictionary to track requests:

```python
from time import time

rate_limit = {}
limit = 5  # max requests
time_frame = 60  # time frame in seconds

def is_request_allowed(user_id):
    current_time = time()
    if user_id not in rate_limit:
        rate_limit[user_id] = [current_time]
        return True
    else:
        rate_limit[user_id] = [t for t in rate_limit[user_id] if t > current_time - time_frame]
        if len(rate_limit[user_id]) < limit:
            rate_limit[user_id].append(current_time)
            return True
    return False

# Example usage
user_id = "user123"
if is_request_allowed(user_id):
    print("Request is allowed.")
else:
    print("Rate limit exceeded. Please try again later.")
```

In this example, the `is_request_allowed` function checks if a user can make a request based on their request history.