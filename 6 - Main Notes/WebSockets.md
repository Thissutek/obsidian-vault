2026-06-07 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[API & Networking]]

# WebSockets

## What is it?
WebSockets are a communication protocol that allows for full-duplex communication channels over a single, long-lived connection between a client and a server. Unlike traditional HTTP requests, which are one-way and require a new connection for each interaction, WebSockets enable real-time data transfer by keeping the connection open, allowing both parties to send and receive messages instantly.

## Why does it matter?
WebSockets are crucial for applications that require real-time updates, such as chat apps, online gaming, or live notifications. They enhance user experience by reducing latency, as data can be sent and received without the overhead of constantly opening and closing connections. This efficiency is essential for creating responsive, interactive web applications that users expect today.

## Example
Here’s a simple example of using WebSockets in JavaScript:

```javascript
// Create a websocket connection
const socket = new WebSocket('ws://example.com/socket');

// Listen for messages from the server
socket.onmessage = function(event) {
    console.log('Message from server:', event.data);
};

// Send a message to the server
socket.onopen = function() {
    socket.send('Hello Server!');
};
```

In this snippet, we create a WebSocket connection to a server and set up listeners for incoming messages. When the connection opens, we send a message to the server, demonstrating how easy it is to communicate in real-time!