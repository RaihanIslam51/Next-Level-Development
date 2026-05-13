
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
