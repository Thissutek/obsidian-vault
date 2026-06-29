2026-06-29 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[API & Networking]]

# TCP vs UDP

## What is it?
TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are communication protocols used for sending data over the internet. TCP is connection-oriented, meaning it establishes a reliable connection between sender and receiver before data transmission, ensuring that all packets are received in order. UDP, on the other hand, is connectionless and sends data without establishing a connection, which means it does not guarantee delivery or order.

## Why does it matter?
Understanding the difference between TCP and UDP is crucial in software engineering because it impacts how applications handle data. For instance, applications that require reliable data delivery, like web browsing or file transfers, use TCP. Conversely, applications that prioritize speed and can tolerate some data loss, like online gaming or video streaming, often use UDP. Choosing the right protocol can significantly affect performance and user experience.

## Example
Here's a simple analogy: think of TCP as sending a package through a postal service that ensures your package is delivered and signed for, while UDP is like sending a postcard without any tracking—there's no guarantee it will get to the recipient.

In code, here's how you would send a message using TCP and UDP in Python:

```python
# TCP Socket Example
import socket

tcp_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
tcp_socket.connect(('localhost', 8080))
tcp_socket.sendall(b'Hello via TCP')
tcp_socket.close()

# UDP Socket Example
udp_socket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
udp_socket.sendto(b'Hello via UDP', ('localhost', 8080))
udp_socket.close()
```

In this example, the TCP socket ensures a reliable connection, while the UDP socket sends data quickly without waiting for confirmation.