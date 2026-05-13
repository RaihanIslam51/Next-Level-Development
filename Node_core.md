
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

#### Node.js এর জন্য NPM এ লাখ লাখ package পাওয়া যায় যা development অনেক সহজ করে দেয়।
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

#### V8 হলো Google দ্বারা তৈরি একটি high-performance JavaScript engine, যা Node.js-এর ভিতরে JavaScript code execute করে।
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


## Process

Process হলো running program এর একটি instance।

যখন Node.js application run করা হয়, তখন operating system একটি আলাদা process তৈরি করে।

একটি process এর ভিতরে থাকে:

- Memory
- Variables
- Code
- Thread
- Event Loop

👉 সহজভাবে: Process হলো পুরো running application।

---

## Thread

Thread হলো process এর ভিতরে কাজ করার unit।

একটি process এর ভিতরে এক বা একাধিক thread থাকতে পারে।

Thread মূলত code execute করে।

---

# Single Thread in Node.js

Node.js মূল JavaScript execution এর জন্য single thread ব্যবহার করে।
মানে একই সময়ে একটি main thread এ JavaScript code execute হয়।

---

## সুবিধা

- Lightweight
- Fast
- কম memory ব্যবহার করে
- High concurrency handle করতে পারে

---

## সমস্যা
CPU heavy কাজ করলে পুরো application slow হয়ে যেতে পারে।

যেমন:

- Video processing
- Large calculation
- Image compression
- Encryption

---

# Multiple Threads (all backend langages)

যখন একাধিক thread ব্যবহার করা হয় তখন multiple task parallel ভাবে run করা যায়।
Node.js internally কিছু background কাজ multiple thread দিয়ে handle করে।

---

# Thread Pool

Node.js এর ভিতরে Libuv একটি thread pool ব্যবহার করে।

Default ভাবে:

```text
4 Threads
```

ব্যবহার হয়।

---

## Thread Pool যেসব কাজ handle করে

- File System
- DNS Lookup
- Crypto
- Compression

---

## Workflow

```text
Request
   ↓
Event Loop
   ↓
Thread Pool
   ↓
Background Work
   ↓
Callback Queue
   ↓
Response
```

---

# Vertical Scaling

Vertical scaling মানে server এর power বাড়ানো।

যেমন:

- বেশি RAM
- বেশি CPU
- Faster SSD

---

## Example

```text
4GB RAM → 16GB RAM
```

---

## সুবিধা

- সহজ setup
- কম configuration

---

## সমস্যা

- Hardware limitation আছে
- খুব expensive

---

# Horizontal Scaling

Horizontal scaling মানে multiple server add করা।

---

## Example

```text
1 Server → 10 Servers
```

---

## সুবিধা

- High scalability
- Better fault tolerance
- Large traffic handle করতে পারে

---

## Example Technologies

- Load Balancer
- Kubernetes
- Docker
- PM2 Cluster Mode

---

# Asynchronous Programming
Asynchronous মানে কাজ background এ চলবে এবং main thread block হবে না।

---

## Example

```js
setTimeout(() => {
  console.log("Done");
}, 2000);

console.log("Running");
```

---

## Output

```text
Running
Done
```

কারণ timeout asynchronous ভাবে execute হয়।

---


# Problem in Node.js

Node.js single thread হওয়ায় CPU heavy কাজ Event Loop block করে দিতে পারে।

ফলে অন্য request wait করতে থাকে।

---

# Multithreading in Node.js

এই সমস্যা সমাধানের জন্য Node.js Worker Threads ব্যবহার করে।

---

## Worker Thread

Worker Thread আলাদা thread এ heavy কাজ execute করে।

---

## Example

```js
const { Worker } = require('worker_threads');
```

---

## সুবিধা

- Main thread block হয় না
- Performance improve হয়
- Heavy task parallel run হয়

---

# Event Loop

Event Loop হলো Node.js এর heart।

এটি asynchronous কাজ manage করে।

---

# Event Loop Workflow

```text
Call Stack
    ↓
Web APIs / Libuv
    ↓
Callback Queue
    ↓
Event Loop
    ↓
Execute Callback
```

---

# Event Loop Phases

Node.js Event Loop বিভিন্ন phase এ কাজ করে।

---

## 1. Timers Phase

এই phase এ execute হয়:

```js
setTimeout()
setInterval()
```

---

## 2. Pending Callbacks Phase

System related callbacks execute হয়।

যেমন:

- TCP Errors
- Network callbacks

---

## 3. Idle / Prepare Phase

Internal Node.js operations execute হয়।

---

## 4. Poll Phase

সবচেয়ে গুরুত্বপূর্ণ phase।

এখানে:

- Incoming requests
- File system callbacks
- I/O operations

handle করা হয়।

---

## 5. Check Phase

এখানে execute হয়:

```js
setImmediate()
```

---

## 6. Close Callbacks Phase

Close events execute হয়।

যেমন:

```js
socket.on('close')
```

---

# Complete Event Loop Cycle

```text
Timers
   ↓
Pending Callbacks
   ↓
Idle / Prepare
   ↓
Poll
   ↓
Check
   ↓
Close Callbacks
   ↓
Repeat Again
```

---

# Microtask Queue

Microtask queue high priority queue।

এখানে থাকে:

- Promise callbacks
- process.nextTick()

---

## Example

```js
Promise.resolve().then(() => {
  console.log("Promise");
});
```

---

# Node.js Architecture Summary

| Concept | Description |
|----------|-------------|
| Process | Running application |
| Thread | Execution unit |
| Single Thread | One main JS thread |
| Thread Pool | Background worker threads |
| Async | Non-blocking execution |
| Event Loop | Async task manager |
| Worker Threads | CPU heavy task handling |
| Vertical Scaling | Server power increase |
| Horizontal Scaling | Multiple servers add |

---

## Buffer কী?

Buffer হলো Node.js এর temporary memory storage system যেখানে binary data store করা হয়।
কারণ JavaScript সাধারণভাবে binary data handle করতে পারে না, তাই Node.js Buffer ব্যবহার করে।

---

## কোথায় ব্যবহার হয়?
- File System
- Video Streaming
- Audio Processing
- TCP Streams
- Image Upload
- Network Packets

---

# Buffer Example

```js
const buffer = Buffer.from("Hello World");

console.log(buffer);
console.log(buffer.toString());
```

---

## Output

```text
<Buffer 48 65 6c 6c 6f 20 57 6f 72 6c 64>

Hello World
```

---

# Buffer Memory Flow

```text
Data
 ↓
Buffer Memory
 ↓
Process
 ↓
Output
```

---

## Stream কী?

Stream হলো data continuous way তে process করার system।
পুরো data memory তে load না করে ছোট ছোট chunk আকারে process করা হয়।

---

# Stream Types

| Type | Description |
|------|-------------|
| Readable Stream | Data read করে |
| Writable Stream | Data write করে |
| Duplex Stream | Read + Write |
| Transform Stream | Data modify করে |

---

# Writable Stream Example

```js
const fs = require("fs");

const writeStream = fs.createWriteStream("output.txt");

writeStream.write("Hello Node.js");
```

---

# Why Streams Important?

কারণ large file memory তে পুরো load করলে RAM usage অনেক বেড়ে যায়।

Stream chunk আকারে data process করে memory efficient করে।

---

# Stream Workflow

```text
Large File
    ↓
Chunks
    ↓
Stream
    ↓
Process
    ↓
Output
```

---

## Module কী?

Module হলো reusable code file।
একটি file এর functionality অন্য file এ use করা যায়।

---
# Why Modules?
- Clean Code
- Reusability
- Maintainability
- Scalability
- Separation of Concerns

---

# CommonJS Module System
Node.js এর traditional module system হলো CommonJS।

---
# Export Example (CommonJS)

## math.js

```js
const add = (a, b) => a + b;

module.exports = add;
```

---

# Import Example

## app.js

```js
const add = require("./math");

console.log(add(5, 10));
```

---

# Multiple Export Example

## user.js

```js
const name = "Rahim";
const age = 25;

module.exports = {
  name,
  age,
};
```

---

# Import Multiple Data

```js
const user = require("./user");

console.log(user.name);
console.log(user.age);
```

---

# Name Alias in CommonJS
Alias মানে import করার সময় নতুন নাম দেওয়া।

---

## Example

```js
const mathFunction = require("./math");

console.log(mathFunction(10, 20));
```

এখানে:

```js
mathFunction
```

হলো alias name।

---

# ESM (ECMAScript Module)
Modern JavaScript module system হলো ESM।

এটি browser এবং modern Node.js এ use হয়।

---

# Export Example (ESM)

## math.js

```js
export const add = (a, b) => a + b;
```

---

# Import Example

## app.js

```js
import { add } from "./math.js";

console.log(add(5, 10));
```

---

# Default Export

## user.js

```js
const user = {
  name: "Rahim",
};

export default user;
```

---

# Default Import

```js
import user from "./user.js";

console.log(user.name);
```

---

# Name Alias in ESM

Alias use করা হয়:

```js
as
```

keyword দিয়ে।

---

# Example

```js
import { add as sum } from "./math.js";

console.log(sum(5, 5));
```

এখানে:

```js
sum
```

হলো alias name।

---

# CommonJS vs ESM

| Feature | CommonJS | ESM |
|---------|----------|-----|
| Import | require() | import |
| Export | module.exports | export |
| Synchronous | Yes | No |
| Browser Support | No | Yes |
| Modern Standard | No | Yes |

---
## IIFE কী?

IIFE হলো এমন function যা define করার সাথে সাথে execute হয়।

---

# Syntax

```js
(function () {
  console.log("Hello");
})();
```

---

# Arrow Function IIFE

```js
(() => {
  console.log("IIFE Running");
})();
```

---

# Why Use IIFE?

- Private Scope তৈরি করতে
- Global scope pollution কমাতে
- Immediate execution এর জন্য

---

# Example with Private Variable

```js
(function () {
  let secret = "Hidden Data";

  console.log(secret);
})();
```

---

# Output

```text
Hidden Data
```

বাইরে থেকে:

```js
console.log(secret);
```

access করা যাবে না।

---

# Streams + Buffers Relationship
Buffer temporary memory তে data store করে।
Stream সেই data chunk আকারে process করে।

---

# Real Workflow

```text
File
 ↓
Buffer
 ↓
Chunks
 ↓
Stream
 ↓
Processing
 ↓
Response
```

---

