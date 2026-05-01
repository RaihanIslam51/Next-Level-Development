TypeScript is a strongly typed superset of JavaScript that helps developers write safer and more maintainable code.
This guide covers all **primitive data types** in TypeScript with practical examples.

---

## 📦 What Are Primitive Data Types?

Primitive data types are the most basic data types that store **single values**.

✔ Immutable
✔ Lightweight
✔ Directly stored in memory

---

## 🔢 1. number

Represents all numeric values (integers, floats, etc.)

```ts
let age: number = 25;
let price: number = 99.99;
let temperature: number = -10;
```

---

## 🔤 2. string

Represents textual data

```ts
let firstName: string = "Rahim";
let lastName: string = 'Karim';
let fullName: string = `Hello ${firstName} ${lastName}`;
```

---

## 🔘 3. boolean

Represents logical values: `true` or `false`

```ts
let isLoggedIn: boolean = true;
let isAdmin: boolean = false;
```

---

## ⚪ 4. null

Represents an intentional absence of value

```ts
let emptyValue: null = null;
```

---

## ⚫ 5. undefined

Represents a variable that has been declared but not assigned

```ts
let data: undefined = undefined;
```

---

## 🔢 6. bigint

Used for very large integers beyond the safe limit of number

```ts
let bigNumber: bigint = 123456789012345678901234567890n;
```

---

## 🔷 7. symbol

Used to create unique identifiers

```ts
let id: symbol = Symbol("id");
let anotherId: symbol = Symbol("id");

console.log(id === anotherId); // false
```

---

## ⚠️ Type Safety Example

TypeScript prevents incorrect assignments:

```ts
let num: number = "hello"; // ❌ Error
```

---

## 📊 Summary Table

| Type      | Example      | Description        |
| --------- | ------------ | ------------------ |
| number    | 10, 3.14     | Numeric values     |
| string    | "Hello"      | Text data          |
| boolean   | true / false | Logical values     |
| null      | null         | Empty value        |
| undefined | undefined    | Not assigned       |
| bigint    | 123n         | Large integers     |
| symbol    | Symbol()     | Unique identifiers |

---

## 💡 Best Practices

* ✅ Always define types explicitly
* ✅ Avoid using `any` unless necessary
* ✅ Use `bigint` for very large numbers
* ✅ Use `symbol` for unique keys (advanced use cases)

---

## 🛠️ How to Run TypeScript

### 1. Install TypeScript

```bash
npm install -g typescript
```

### 2. Initialize Config

```bash
tsc --init
```

### 3. Compile TypeScript

```bash
tsc index.ts
```

---

## 📁 Project Structure (Example)

```
typescript-primitive-types/
│
├── src/
│   └── index.ts
│
├── tsconfig.json
└── README.md
```

---

## 🌍 Use Cases

* Form validation
* API response typing
* Large-scale applications
* Backend development with Node.js

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create a new branch
3. Make your changes
4. Submit a Pull Request

---

## 📜 License

This project is licensed under the **MIT License**

---

## 👨‍💻 Author

**MD. Raihan Islam**
Full Stack Web Developer (MERN)

* 🌐 Portfolio: Coming Soon
* 💼 Open for freelance & remote jobs

---

## ⭐ Support

If you like this project, give it a ⭐ on GitHub!

---

