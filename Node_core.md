
## Client and server core concept
<p align="center">
  <img src="https://i.ibb.co.com/WNPQm3Mr/Screenshot-2026-05-13-135116.png" width="100%" />
</p>

<p align="center">
  <img src="https://i.ibb.co.com/nNny4LRJ/Screenshot-2026-05-13-135325.png" width="100%" />
</p>

<p align="center">
  <img src="https://i.ibb.co.com/prjTcRjr/Screenshot-2026-05-13-135553.png" width="100%" />
</p>

# 🚀 What is Node.js?

Node.js হলো একটি powerful JavaScript runtime environment যেটা browser এর বাইরে JavaScript run করতে সাহায্য করে।  
এটি Chrome এর V8 Engine ব্যবহার করে খুব দ্রুত code execute করতে পারে।

সহজ ভাষায় বলতে গেলে, Node.js ব্যবহার করে JavaScript দিয়ে backend/server তৈরি করা যায়।

---

# 📌 Why Node.js is Important

বর্তমান সময়ে Node.js অনেক জনপ্রিয় কারণ এটি খুব fast, scalable এবং lightweight।
- REST API
- Real-time Chat Application
- Dashboard
- SaaS Product
- E-commerce Website
- Streaming Platform
- Automation Tool
বিশ্বের বড় বড় কোম্পানি যেমন Netflix, Uber, LinkedIn, PayPal Node.js ব্যবহার করে।
---

# ⚡ Main Features of Node.js
## 1. Fast Performance
Node.js Chrome এর V8 Engine ব্যবহার করে যার কারণে code খুব দ্রুত run হয়।
---

## 2. Non-Blocking System
একটি কাজ চলাকালীন অন্য কাজ বন্ধ হয়ে থাকে না।  
একসাথে অনেক request handle করতে পারে।

---

## 3. Single Language Development
Frontend এবং Backend দুই জায়গাতেই JavaScript ব্যবহার করা যায়।
---

## 4. Scalable
একসাথে হাজার হাজার user handle করতে পারে।
---

## 5. Huge NPM Ecosystem
Node.js এর জন্য NPM এ লাখ লাখ package পাওয়া যায় যা development অনেক সহজ করে দেয়।
---

# 🚀 Basic Node.js Example

```js
const http = require('http');

const server = http.createServer((req, res) => {
  res.write('Hello Node.js');
  res.end();
});

server.listen(3000, () => {
  console.log('Server Running');
});
```

এই code একটি simple server তৈরি করে।

---

# 📁 Popular Node.js Frameworks
- Express.js
- NestJS
- Fastify
- Koa.js

---

# ❌ Disadvantages of Node.js

❌ Heavy CPU task এর জন্য perfect না  
❌ Single-thread limitation আছে  
❌ পুরাতন code এ callback complexity হতে পারে  

---

# 🚀 Complete Node.js Architecture

```text
Client Request
       ↓
Node.js Server
       ↓
Event Loop
       ↓
Libuv
       ↓
OS / Thread Pool
       ↓
Response Back
```

## V8 JavaScript Engine

V8 হলো Google দ্বারা তৈরি একটি high-performance JavaScript engine, যা Node.js-এর ভিতরে JavaScript code execute করে।
V8 engine JavaScript code কে সরাসরি machine code এ convert করে, যার ফলে execution খুব দ্রুত হয়। এটি C++ দিয়ে লেখা এবং মূলত Google Chrome browser এও ব্যবহার করা হয়।
👉 সহজভাবে বলতে গেলে: V8 হলো এমন একটি engine যা JavaScript কে computer বুঝতে পারে এমন ভাষায় পরিবর্তন করে দেয়।
---
## 🔥 How V8 Works

```text
JavaScript Code
       ↓
Parsing
       ↓
Compilation
       ↓
Machine Code
       ↓
Execution
```

---

## ⚡ Advantages of V8
- Very Fast Execution
- High Performance
- Memory Optimization
- JIT (Just In Time) Compilation
---

---

## Event-Driven Architecture

Node.js একটি event-driven architecture অনুসরণ করে, যেখানে সব কাজ event এর মাধ্যমে পরিচালিত হয়।
যখন কোনো request আসে, Node.js সেটাকে event হিসেবে ধরে নেয় এবং সেই event অনুযায়ী callback function execute করে।
👉 এর মানে হলো: কাজগুলো একটার পর একটা blocking না হয়ে event অনুযায়ী handle হয়।
## 📌 What is Event Driven?

Node.js works using events.
Example:

 Click Event
- Request Event
- Response Event
- Database Event
---

## 🧠 Example

```js
button.click(() => {
  console.log("Button clicked");
});
```
When the event happens → callback function executes.
---

## Event Loop

Event Loop হলো Node.js এর core mechanism যা asynchronous কাজগুলো manage করে।
Node.js একটাই thread ব্যবহার করে, কিন্তু Event Loop এর মাধ্যমে একসাথে অনেক কাজ handle করতে পারে।
Event Loop continuously check করে:
- Call Stack খালি কিনা
- Callback Queue তে কোনো কাজ আছে কিনা
👉 সহজভাবে: Event Loop হলো এমন একটি system যা background এ সব কাজ manage করে এবং একে একে execute করে।

The Event Loop is the heart of Node.js.
It continuously checks:
- Call Stack
- Callback Queue
And manages asynchronous operations.
---

## 🧠 Why Event Loop is Important?
Node.js is:
- Single Threaded
But still handles:
- Multiple Requests
- APIs
- Database Queries
- File System Operations
Because of the Event Loop.
---
## 🔥 Event Loop Flow
```text
Call Stack Empty?
       ↓
Yes
       ↓
Take Task From Queue
       ↓
Execute Callback
       ↓
Repeat Again
```

---

## Libuv Library

Libuv হলো একটি C library যা Node.js এর ভিতরে async operations handle করে।
এটি file system, networking, timers, DNS ইত্যাদি কাজগুলো background এ execute করতে সাহায্য করে।
👉 মানে: Node.js যেসব heavy কাজ করে না সরাসরি, সেগুলো Libuv background এ করে দেয়।
Libuv is a C library used internally by Node.js.
It provides:
- Event Loop
- Thread Pool
- Async I/O Operations
---

## 🔥 Libuv Handles
- File System
- Networking
- Timers
- DNS
- Async Tasks
---

## Non-Blocking I/O

Node.js non-blocking I/O system ব্যবহার করে, যার মানে হলো কোনো কাজ শেষ না হওয়া পর্যন্ত অন্য কাজ বন্ধ থাকে না।
যেমন file read বা database query চলার সময় অন্য request আটকে থাকে না।
👉 সহজভাবে: Node.js এক কাজ শেষ না হওয়া পর্যন্ত অন্য কাজ আটকে রাখে না।

---

## Single Thread Model

Node.js একটি single thread এ কাজ করে, কিন্তু asynchronous system ব্যবহার করে অনেক request handle করতে পারে।
👉 মানে হলো: একটাই worker আছে, কিন্তু সে smartভাবে অনেক কাজ একসাথে manage করতে পারে।

---

## Summary

Node.js এর শক্তির মূল কারণগুলো হলো:

- V8 Engine → JavaScript run করে দ্রুত
- Event Loop → async কাজ manage করে
- Libuv → background operations handle করে
- Event Driven System → events অনুযায়ী কাজ করে
- Non-blocking I/O → কাজ আটকে রাখে না
- Single Thread → lightweight execution model

