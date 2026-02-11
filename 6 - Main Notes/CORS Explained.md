2026-02-11 13:23

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[API & Networking]]

# CORS Explained

## What is it?
CORS, or Cross-Origin Resource Sharing, is a security feature implemented in web browsers that allows or restricts web pages from making requests to a different domain than the one that served the web page. This is important because it prevents malicious sites from accessing sensitive data from another site without permission.

## Why does it matter?
CORS matters in software engineering because it helps protect users from cross-site attacks, where an attacker might try to steal information by sending unauthorized requests to a different server. Properly configuring CORS ensures that legitimate applications can access necessary resources while keeping unauthorized access at bay, which is crucial for maintaining security and trust in web applications.

## Example
Let's say you have a web app hosted at `https://myapp.com` that wants to fetch data from an API at `https://api.example.com`. If the API server has the following CORS header:

```http
Access-Control-Allow-Origin: https://myapp.com
```

This header tells the browser it's okay for your app to access resources from that API. If the header were missing or set to a different domain, your app would be blocked from making that request, helping to protect users from potential threats.