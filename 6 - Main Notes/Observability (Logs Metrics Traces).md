2026-02-18 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[DevOps]]

# Observability (Logs Metrics Traces)

## What is it?
Observability is a measure of how well you can understand what's happening in a system by looking at its output. It is typically broken down into three key components: logs (records of events), metrics (numerical data points that measure performance), and traces (records of the flow of requests through various services). Together, these elements help you monitor, diagnose, and optimize your software applications.

## Why does it matter?
In real software engineering, observability is crucial because it enables developers and operations teams to identify and resolve issues quickly, ensuring that applications run smoothly. Without effective observability, it can be challenging to detect performance bottlenecks, understand user behavior, and maintain system reliability, leading to poor user experiences and potential revenue loss.

## Example
Imagine you have a web application that users can access to order products online. If performance slows down, logs can show error messages, metrics can reveal the time taken for various operations (like database queries), and traces can help you visualize how requests move through the system. Here's a simple Python example illustrating logging:

```python
import logging

# Configure logging
logging.basicConfig(level=logging.INFO)

def process_order(order_id):
    logging.info(f"Processing order: {order_id}")
    # Simulate processing logic
    if order_id < 0:
        logging.error("Invalid order ID!")
        return "Error"
    return "Order processed"

print(process_order(1))
print(process_order(-1))
```

In this snippet, logs help track the order processing flow and capture errors, illustrating the importance of observability in maintaining application health.