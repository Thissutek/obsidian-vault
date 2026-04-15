2026-04-15 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[API & Networking]]

# HTTP/2 vs HTTP/1.1

## What is it?
HTTP/2 is the second major version of the Hypertext Transfer Protocol, which is used for transferring data on the web. It introduces features like multiplexing, allowing multiple requests and responses to be sent at the same time over a single connection, reducing latency and improving performance compared to HTTP/1.1, where each connection can only handle one request at a time.

## Why does it matter?
Understanding the differences between HTTP/2 and HTTP/1.1 is crucial for web developers and engineers because it significantly impacts website performance and user experience. By leveraging the features of HTTP/2, developers can create faster-loading websites and applications, which can lead to better user retention and potentially higher conversion rates.

## Example
Here’s a simple example illustrating how HTTP/2 can reduce latency:

Imagine a café where customers (clients) place orders (requests) at a single counter (connection). In HTTP/1.1, each customer must wait until their order is completely fulfilled before the next can place theirs. In contrast, with HTTP/2, multiple customers can place their orders simultaneously without waiting, leading to faster service.

In code, a simple HTTP request using a library in Python could look like this:

```python
import http.client

conn = http.client.HTTPSConnection("www.example.com")
conn.request("GET", "/")
response = conn.getresponse()
print(response.status, response.reason)
```

With HTTP/2, you can optimize requests, reducing response time and improving overall performance!