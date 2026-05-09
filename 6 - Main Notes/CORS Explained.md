2026-05-09 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[API & Networking]]

# CORS Explained

## What is it?
CORS, or Cross-Origin Resource Sharing, is a security feature implemented in web browsers that allows or restricts web applications from making requests to a different domain than the one that served the original web page. Essentially, it’s a way for a website to ask a browser for permission to access resources from another domain while ensuring that this access is safe and controlled.

## Why does it matter?
CORS is crucial in preventing malicious websites from accessing sensitive data from another domain without permission. In software engineering, understanding CORS is important for building secure web applications, especially when your frontend (like a web app) interacts with different backends (like APIs) hosted on different domains. Without proper CORS configurations, your application could expose itself to security vulnerabilities.

## Example
Imagine you have a frontend application hosted at `https://myapp.com` which wants to fetch user data from an API at `https://api.myapp.com`. If the API server does not allow requests from your frontend's origin, the browser will block that request due to CORS policy.

Here’s a simple example of how CORS is handled in an Express.js server:

```javascript
const express = require('express');
const cors = require('cors');
const app = express();

app.use(cors()); // This allows all domains to access this server

app.get('/data', (req, res) => {
    res.json({ message: 'Hello from CORS-enabled API!' });
});

app.listen(3000, () => console.log('Server running on port 3000'));
```

In this code snippet, the `cors()` middleware allows any domain to access the `/data` endpoint, making it a CORS-enabled API.