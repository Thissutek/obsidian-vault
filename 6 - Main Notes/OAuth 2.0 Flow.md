2026-04-28 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[API & Networking]]

# OAuth 2.0 Flow

## What is it?
OAuth 2.0 is an open standard for authorization that allows third-party applications to access user data without sharing passwords. Instead of giving your credentials to an application, OAuth 2.0 uses tokens to grant limited access, ensuring that your sensitive information remains secure.

## Why does it matter?
OAuth 2.0 is crucial in modern software engineering because it enables developers to create applications that interact with services like Google or Facebook, without compromising user security. It simplifies user experiences by allowing one-click logins and integration, increasing trust and usability for both users and developers.

## Example
Here’s a simple flow using OAuth 2.0 in a web application:

```javascript
// Step 1: Redirect user to authorization URL
const clientId = 'YOUR_CLIENT_ID';
const redirectUri = 'YOUR_REDIRECT_URI';
const authUrl = `https://authorization-server.com/auth?response_type=code&client_id=${clientId}&redirect_uri=${redirectUri}`;
window.location.href = authUrl;

// Step 2: After user authorizes, they are redirected back with a code
// Step 3: Exchange the code for an access token
fetch('https://authorization-server.com/token', {
    method: 'POST',
    body: JSON.stringify({
        code: 'AUTHORIZATION_CODE',
        redirect_uri: redirectUri,
        client_id: clientId,
        grant_type: 'authorization_code'
    }),
    headers: { 'Content-Type': 'application/json' }
})
.then(response => response.json())
.then(data => console.log('Access Token:', data.access_token));
```

In this flow, the user first authorizes the application, and then the app exchanges an authorization code for an access token that can be used to access user data securely.