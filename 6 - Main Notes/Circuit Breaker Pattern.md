2026-04-20 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Design Patterns]]

# Circuit Breaker Pattern

## What is it?
The Circuit Breaker Pattern is a software design pattern used to manage faults in a distributed system. It acts like an electrical circuit breaker, which stops the flow of electricity when there's a fault, preventing further damage. In software, it monitors requests to a service and, if the failure rate exceeds a certain threshold, it "trips" the circuit to stop sending requests, allowing the service to recover.

## Why does it matter?
This pattern is crucial for building resilient applications, especially in microservices architectures where services communicate over a network. By preventing repeated requests to a failing service, the Circuit Breaker Pattern helps improve overall system stability and user experience, minimizing downtime and reducing the risk of cascading failures.

## Example
Here's a simple example in Python using a pseudo-implementation of the Circuit Breaker Pattern:

```python
class CircuitBreaker:
    def __init__(self, failure_threshold):
        self.failure_threshold = failure_threshold
        self.failure_count = 0
        self.is_open = False

    def call_service(self):
        if self.is_open:
            print("Circuit is open. Service call denied.")
            return

        try:
            # Simulate a service call that may fail
            result = self.service_call()
            self.reset()
            return result
        except Exception:
            self.failure_count += 1
            if self.failure_count >= self.failure_threshold:
                self.is_open = True
                print("Circuit is now open due to failures.")

    def service_call(self):
        # Simulated service logic
        raise Exception("Service failed")  # Simulating a failure

    def reset(self):
        self.failure_count = 0
        self.is_open = False

# Using the Circuit Breaker
cb = CircuitBreaker(failure_threshold=3)
for _ in range(5):
    cb.call_service()
```

In this example, if the service fails three times, the circuit breaks, and subsequent calls are denied until the circuit is reset.