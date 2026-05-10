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


## 📦 What Are Non-Primitive Types?

Non-primitive data types এমন data type যেগুলো একাধিক value বা structured data store করে।

👉 উদাহরণ:

* array
* object
* tuple

---

## 🔢 Array

Array ব্যবহার করা হয় multiple value একসাথে store করার জন্য

```ts id="7c3hsl"
let numbers: number[] = [1, 2, 3, 4];
let names: string[] = ["Rahim", "Karim", "Jamal"];
```

👉 Explanation:
এখানে `numbers` array শুধু number store করতে পারবে এবং `names` array শুধু string store করবে।

👉 Alternative syntax:

```ts id="5hh6fc"
let marks: Array<number> = [80, 90, 100];
```

👉 Mixed array (avoid করা ভালো):

```ts id="5yk3km"
let mixed: (string | number)[] = ["Rahim", 25];
```

---

## 🧱 Object

Object ব্যবহার করা হয় structured data store করার জন্য (key-value pair)

```ts id="9fz0k9"
let user: {
  name: string;
  orge: "programming Hero"; //fix type  value jake literal bole
  age: number;
  isAdmin: boolean;
} = {
  name: "Rahim",
  age: 25,
  isAdmin: false
};
```

👉 Explanation:
Object-এর মধ্যে key (name, age, isAdmin) এবং তাদের type define করা থাকে।
ভুল type দিলে error দিবে।

👉 Optional property:

```ts id="p5y9k1"
let product: {
  name: string;
  price: number;
  discount?: number;
} = {
  name: "Mobile",
  price: 20000
};
```

👉 Explanation:
`discount?` মানে optional — থাকলেও হবে, না থাকলেও হবে।

---

## 🎯 Tuple

Tuple হলো fixed length array যেখানে প্রতিটি index-এর type নির্দিষ্ট থাকে

```ts id="3x8l2n"
let userInfo: [string, number] = ["Rahim", 25];
```

👉 Explanation:
এখানে প্রথম value অবশ্যই string এবং দ্বিতীয় value number হতে হবে।


## 📦 What Is a Function?

Function হলো এমন একটি block of code যেটা নির্দিষ্ট কাজ করে এবং reuse করা যায়।

👉 TypeScript-এ function এর input (parameter) এবং output (return value) type define করা যায়।

---

## 🔹 Basic Function

```ts id="n3k2js"
function add(a: number, b: number): number {
  return a + b;
}
```

👉 Explanation:
এখানে `a` এবং `b` number type এবং function number return করবে।


## 🔹 Optional Parameters

```ts id="m4l9x2"
function greetUser(name: string, age?: number) {
  console.log(name, age);
}
```

👉 Explanation:
`age?` মানে optional — দিলে হবে, না দিলেও হবে।

---

## 🔹 Default Parameters

```ts id="k2s8f1"
function welcome(name: string = "Guest") {
  console.log("Welcome " + name);
}
```

👉 Explanation:
value না দিলে default `"Guest"` ব্যবহার হবে।

---

## 🔹 Arrow Function

```ts id="p7x2q8"
const multiply = (a: number, b: number): number => {
  return a * b;
};
```

👉 Explanation:
এটা modern JavaScript/TypeScript function লেখার style।


## 🔹 Literal Type in Function

```ts id="u7w3r4"
function setRole(role: "admin" | "user") {
  console.log(role);
}
```

👉 Explanation:
Function শুধু নির্দিষ্ট value accept করবে।

---

## 🔹 Object as Parameter

```ts id="d5n2h7"
function createUser(user: { name: string; age: number }) {
  console.log(user.name, user.age);
}
```

👉 Explanation:
Object parameter হিসেবে pass করা যায় এবং তার type define করা যায়।

---

## 🔹 Array as Parameter

```ts id="x3c9m8"
function getTotal(numbers: number[]): number {
  return numbers.reduce((sum, num) => sum + num, 0);
}
```

👉 Explanation:
Array parameter হিসেবে নিয়ে calculation করা হয়েছে।

---



## 🔹 Callback Function

```ts id="y2n8p4"
function processUser(name: string, callback: (msg: string) => void) {
  callback("Hello " + name);
}
```

👉 Explanation:
Function-এর ভিতরে আরেকটা function pass করা যায়।

---


## 🔍 Difference Between Rest & Spread

| Operator | কাজ                                        |
| -------- | ------------------------------------------ |
| Rest     | multiple value → একটায় (collect করে)       |
| Spread   | একটার value → আলাদা আলাদা করে (expand করে) |

---

# 🔹 Rest Operator (`...`)

Rest operator ব্যবহার করা হয় **multiple value এক জায়গায় collect করার জন্য**।

---

## 📦 Rest in Function Parameter

```ts id="r1x9k3"
function sum(...numbers: number[]): number {
  return numbers.reduce((total, num) => total + num, 0);
}
```

👉 Explanation:
এখানে যতগুলো argument দিবা, সবগুলো `numbers` array এর মধ্যে collect হবে।

👉 Example:

```ts id="x8d2m5"
sum(1, 2, 3, 4); // output: 10
```

---

## 📦 Rest in Array Destructuring

```ts id="p4n7s1"
let [first, second, ...rest] = [10, 20, 30, 40];
```

👉 Explanation:
`first = 10`, `second = 20`
`rest = [30, 40]`

---

# 🔹 Spread Operator (`...`)

Spread operator ব্যবহার করা হয় **existing data কে expand করার জন্য**।

---

## 📦 Spread in Array

```ts id="v7m2q8"
let arr1 = [1, 2, 3];
let arr2 = [...arr1, 4, 5];
```

👉 Explanation:
`arr1` এর সব value copy হয়ে `arr2` তে যোগ হয়েছে।

---

## 📦 Merge Arrays

```ts id="k9x3l1"
let a = [1, 2];
let b = [3, 4];

let result = [...a, ...b];
```

👉 Explanation:
দুইটা array একসাথে merge করা হয়েছে।

---

## 📦 Spread in Object

```ts id="m2c8z4"
let user = { name: "Rahim", age: 25 };

let updatedUser = { ...user, city: "Dhaka" };
```

👉 Explanation:
পুরানো object copy করে নতুন property add করা হয়েছে।


## 📦 Copy Array / Object

```ts id="b6y3f2"
let numbers = [1, 2, 3];
let copyNumbers = [...numbers];
```

👉 Explanation:
এটা shallow copy তৈরি করে।

---


## 📦 What Is Destructuring?

Destructuring হলো এমন একটি syntax যেটা ব্যবহার করে আমরা **array বা object থেকে value আলাদা করে variable-এ assign করতে পারি**।


---

# 🔹 Array Destructuring

Array থেকে value বের করার জন্য index অনুযায়ী destructuring করা হয়।

```ts id="x7p2k4"
let numbers: number[] = [10, 20, 30];

let [a, b, c] = numbers;
```

👉 Explanation:
`a = 10`, `b = 20`, `c = 30`

---

## 🔸 Skip Value

```ts id="m3n9t1"
let [first, , third] = [10, 20, 30];
```

👉 Explanation:
`first = 10`, `third = 30` (মাঝের value skip করা হয়েছে)



# 🔹 Object Destructuring

Object থেকে key অনুযায়ী value বের করা হয়।

```ts id="j9k3p6"
let user = {
  name: "Rahim",
  age: 25,
};

let { name, age } = user;
```

👉 Explanation:
`name = "Rahim"`, `age = 25`


## 🔸 Default Value

```ts id="y6p2r1"
let { city = "Dhaka" } = user;
```

👉 Explanation:
`city` না থাকলে default `"Dhaka"` হবে


# 🔹 Nested Destructuring

```ts id="p3c7x1"
let user = {
  name: "Rahim",
  address: {
    city: "Dhaka",
    zip: 1200,
  },
};

let {
  address: { city },
} = user;
```

👉 Explanation:
Nested object থেকে সরাসরি `city` বের করা হয়েছে।

---


## 📦 What Is Type Alias?

Type Alias হলো এমন একটি উপায় যেটা দিয়ে তুমি **custom type name** তৈরি করতে পারো।

👉 মানে, complex type বারবার না লিখে একটা নাম দিয়ে reuse করা যায়।

---

## 🔹 Basic Type Alias

```ts id="t1a2b3"
type UserName = string;

let name: UserName = "Rahim";
```

👉 Explanation:
এখানে `UserName` আসলে string এর alias (অন্য নাম)।

---

## 🔹 Object Type Alias

```ts id="o4b5c6"
type User = {
  name: string;
  age: number;
  isAdmin: boolean;
};

let user1: User = {
  name: "Rahim",
  age: 25,
  isAdmin: false,
};
```

👉 Explanation:
একটা object-এর structure একবার define করে অনেক জায়গায় ব্যবহার করা যায়।

---

## 🔹 Optional Property

```ts id="p7q8r9"
type Product = {
  name: string;
  price: number;
  discount?: number;
};
```

👉 Explanation:
`discount?` মানে optional — থাকলেও হবে, না থাকলেও হবে।

---

## 🔹 Readonly Property

```ts id="r1s2t3"
type Account = {
  readonly id: number;
  name: string;
};

let acc: Account = {
  id: 1,
  name: "Rahim",
};

// acc.id = 2 ❌ Error
```

👉 Explanation:
`readonly` দিলে ওই property change করা যাবে না।


## 🔹 Array Type Alias

```ts id="a1b2c3"
type Numbers = number[];

let nums: Numbers = [1, 2, 3, 4];
```

👉 Explanation:
Array type short করে লেখা যায়।

---

## 📦 What Are Union & Intersection Types?

👉 **Union (`|`)** → একাধিক type এর মধ্যে যেকোনো একটা হতে পারে
👉 **Intersection (`&`)** → একাধিক type একসাথে combine করে

---

# 🔹 Union Type (`|`)

Union type ব্যবহার করা হয় যখন একটি variable একাধিক type/value নিতে পারে।

---

## 🔸 Basic Union

```ts id="u1n2i3"
let id: number | string;

id = 101;      // ✅
id = "A101";   // ✅
id = true;     // ❌ Error
```

👉 Explanation:
`id` number অথবা string হতে পারবে, অন্য type হলে error দিবে।


## 🔸 Literal Union

```ts id="u0l1t2"
type Status = "success" | "error" | "loading";

let currentStatus: Status = "success";
```

👉 Explanation:
নির্দিষ্ট কিছু value limit করা হয়েছে।


# 🔹 Intersection Type (`&`)

Intersection type ব্যবহার করা হয় multiple type combine করার জন্য।

---

## 🔸 Basic Intersection

```ts id="i1n2t3"
type Person = {
  name: string;
};

type Employee = {
  salary: number;
};

type Staff = Person & Employee;

let staff: Staff = {
  name: "Rahim",
  salary: 50000,
};
```

👉 Explanation:
`Staff` type-এ Person + Employee দুইটার property থাকবে।

---

## 🔸 Intersection with More Types

```ts id="i4n5t6"
type A = { a: number };
type B = { b: string };
type C = { c: boolean };

type Combined = A & B & C;
```

👉 Explanation:
একাধিক type combine করা যায়।



# 📘 Ternary, Nullish Coalescing & Optional Chaining in TypeScript

এই section-এ আমরা TypeScript (JavaScript)-এর খুব গুরুত্বপূর্ণ তিনটি concept নিয়ে আলোচনা করবো:

* Ternary Operator (`? :`)
* Nullish Coalescing (`??`)
* Optional Chaining (`?.`)

---

# 🔹 Ternary Operator (`? :`)

Ternary operator ব্যবহার করা হয় **short condition লিখার জন্য**।

👉 Syntax:

```ts id="t1e2r3"
condition ? valueIfTrue : valueIfFalse
```

---

## 📦 Example

```ts id="t4e5r6"
let age = 20;

let result = age >= 18 ? "Adult" : "Minor";
```

👉 Explanation:
যদি `age >= 18` true হয় তাহলে `"Adult"` return করবে, না হলে `"Minor"`।

---

## 📦 Nested Ternary

```ts id="t7e8r9"
let marks = 80;

let grade =
  marks >= 80 ? "A" :
  marks >= 60 ? "B" :
  "C";
```

👉 Explanation:
একাধিক condition check করার জন্য nested ternary ব্যবহার করা হয় (তবে বেশি ব্যবহার করলে code unreadable হয়ে যায়)।

---

# 🔹 Nullish Coalescing (`??`)

Nullish coalescing ব্যবহার করা হয় **default value সেট করার জন্য**, যখন value `null` বা `undefined` হয়।

👉 Syntax:

```ts id="n1u2l3"
value ?? defaultValue
```

---

## 📦 Example

```ts id="n4u5l6"
let name: string | null = null;

let userName = name ?? "Guest";
```

👉 Explanation:
`name` null হওয়ায় `"Guest"` assign হবে।

---

## 📦 Difference with `||`

```ts id="n7u8l9"
let count = 0;

let result1 = count || 10; // 10 ❌
let result2 = count ?? 10; // 0 ✅
```

👉 Explanation:
`||` false, 0, "" এগুলোকেও false ধরে
কিন্তু `??` শুধু null/undefined check করে — তাই বেশি safe।

---

# 🔹 Optional Chaining (`?.`)

Optional chaining ব্যবহার করা হয় **safe ভাবে property access করার জন্য**।

👉 যদি value `null` বা `undefined` হয়, তাহলে error দিবে না — undefined return করবে।

---

## 📦 Example

```ts id="o1p2t3"
let user = {
  name: "Rahim",
  address: {
    city: "Dhaka",
  },
};

let city = user.address?.city;
```

👉 Explanation:
`address` থাকলে city return করবে, না থাকলে error না দিয়ে undefined দিবে।

---

## 📦 Without Optional Chaining (Problem)

```ts id="o4p5t6"
let city = user.address.city; // ❌ error if address undefined
```

👉 Explanation:
এখানে error হতে পারে যদি address না থাকে।


# 📘 Nullable, Unknown & Never Types in TypeScript

এই section-এ আমরা TypeScript-এর তিনটি গুরুত্বপূর্ণ type নিয়ে আলোচনা করবো:

* Nullable Types
* Unknown Type
* Never Type

---

# 🔹 Nullable Types

Nullable type মানে হলো একটি variable `null` বা `undefined` হতে পারবে।

👉 সাধারণভাবে TypeScript-এ strict mode-এ null/undefined আলাদা type হিসেবে থাকে।

---

## 📦 Example

```ts id="n1u2l3"
let name: string | null = null;
```

👉 Explanation:
`name` variable string অথবা null — দুইটাই হতে পারে।

---

## 📦 With undefined

```ts id="n4u5l6"
let age: number | undefined;

age = 25;       // ✅
age = undefined; // ✅
```

👉 Explanation:
value assign না করলে undefined হতে পারে।


# 🔹 Unknown Type

`unknown` হলো safer version of `any`।

👉 যেকোনো type value assign করা যায়, কিন্তু use করার আগে type check করতে হবে।

---

## 📦 Example

```ts id="u1n2k3"
let value: unknown;

value = 10;
value = "Hello";
value = true;
```

👉 Explanation:
সব ধরনের value assign করা যাচ্ছে।

---

## ⚠️ Without Checking (Error)

```ts id="u4n5k6"
let value: unknown = "Hello";

value.toUpperCase(); // ❌ Error
```

👉 Explanation:
unknown type directly use করা যায় না।


# 🔹 Never Type

`never` type এমন value represent করে যেটা **কখনো return হয় না**।

---

## 📦 Example (Error Throw)

```ts id="n3e4v5"
function throwError(msg: string): never {
  throw new Error(msg);
}
```

👉 Explanation:
function error throw করে — তাই কোনো value return করে না।

---

## 📦 Infinite Loop

```ts id="n6e7v8"
function infiniteLoop(): never {
  while (true) {}
}
```

👉 Explanation:
function কখনো শেষ হয় না।

# TypeScript Type Assertion

## What is Type Assertion?

Type Assertion হলো TypeScript-এর একটি feature যেটা ব্যবহার করে আমরা TypeScript-কে manually বলে দেই কোনো value-এর type কী।

সহজ ভাষায়:

> “এই value-এর type আমি জানি।”

এটি শুধু TypeScript-এর জন্য কাজ করে।  
Runtime-এ actual value change হয় না।

---

# Syntax

Type Assertion করার সবচেয়ে popular syntax হলো `as`

```ts
value as Type
```

---

# Basic Example

```ts
let data: any = "Hello TypeScript";

let length = (data as string).length;

console.log(length);
```

---

## Explanation

এখানে:

- `data` এর type হলো `any`
- TypeScript জানে না এটি string
- তাই `as string` ব্যবহার করে manually string বলা হয়েছে

---

# Why We Use Type Assertion

Type Assertion ব্যবহার করা হয় যখন TypeScript exact type বুঝতে পারে না।

বিশেষ করে:

- DOM Elements
- API Response
- `unknown` type
- Dynamic Data

---

# Type Assertion with `unknown`

```ts
let value: unknown = "TypeScript";

console.log((value as string).toUpperCase());
```

---

## Explanation

`unknown` type directly ব্যবহার করা যায় না।

তাই আগে type assert করতে হয়।

---

# Important Thing

Type Assertion runtime value change করে না।

```ts
let value: any = 100;

let text = value as string;

console.log(typeof text);
```

---

## Output

```ts
number
```

কারণ actual value এখনো number।

---

# TypeScript Interface

Interface হলো TypeScript-এর একটি feature যেটা object-এর structure define করতে ব্যবহার করা হয়।

সহজ ভাষায়:

> Interface বলে দেয় একটি object-এর মধ্যে কোন কোন property থাকবে এবং তাদের type কী হবে।

---

# Basic Syntax

```ts
interface User {
  name: string;
  age: number;
}
```

---

# Example

```ts
interface User {
  name: string;
  age: number;
}

const user: User = {
  name: "Raihan",
  age: 22,
};

console.log(user);
```

---

## Explanation

এখানে:

- `User` নামে একটি interface তৈরি করা হয়েছে
- এতে `name` string হবে
- `age` number হবে
- object অবশ্যই এই structure follow করবে

---

# Why We Use Interface


- Object structure define করতে
- Code reusable করতে
- Type safety বাড়াতে
- Large project manage করতে

---

# Optional Property

সব property required না করলেও হয়।

`?` ব্যবহার করে optional করা যায়।

---

# Example

```ts
interface User {
  name: string;
  age?: number;
}

const user: User = {
  name: "Raihan",
};
```

---

## Explanation

এখানে `age` optional।

তাই না দিলেও error হবে না।

---

# Interface with Function

Function-এর structure-ও define করা যায়।

---

# Example

```ts
interface Add {
  (a: number, b: number): number;
}

const sum: Add = (a, b) => {
  return a + b;
};

console.log(sum(5, 5));
```

---

## Explanation

এখানে function কী parameter নেবে এবং কী return করবে তা define করা হয়েছে।

---

# Interface with Array

```ts
interface StringArray {
  [index: number]: string;
}

const names: StringArray = [
  "Raihan",
  "Hasan",
];
```

---

# Interface Extending

একটি interface আরেকটি interface inherit করতে পারে।

---

# Example

```ts
interface Person {
  name: string;
}

interface Student extends Person {
  roll: number;
}

const student: Student = {
  name: "Raihan",
  roll: 101,
};
```

---

## Explanation

`Student` interface এখন `Person` এর property-ও পাবে।

---

# Interface vs Type

অনেক সময় Interface এবং Type একইরকম মনে হয়।

কিন্তু কিছু পার্থক্য আছে।

---

# Interface

```ts
interface User {
  name: string;
}
```

---

# Type

```ts
type User = {
  name: string;
};
```

---

## Main Difference

| Interface | Type |
|---|---|
| Object-এর জন্য বেশি ব্যবহার হয় | সব ধরনের type define করা যায় |
| Extend করা সহজ | Union type support করে |
| Large project-এ বেশি popular | Flexible |

---

# TypeScript Generics

Generics হলো TypeScript-এর একটি powerful feature যেটা reusable এবং flexible code লিখতে সাহায্য করে।

সহজ ভাষায়:

> Generics ব্যবহার করে আমরা এমন function, interface বা class তৈরি করতে পারি যেটা different type-এর data নিয়ে কাজ করতে পারে type safety বজায় রেখে।

---

# Why We Use Generics

- Reusable code লেখার জন্য
- Type safety বজায় রাখার জন্য
- Duplicate code কমানোর জন্য
- Flexible function তৈরি করার জন্য

---

# Problem Without Generics

ধরি আমরা string return করার function লিখলাম।

```ts
function getData(data: string): string {
  return data;
}
```

এখন number পাঠালে error হবে।

```ts
getData(10);
```

তাই different type support করার জন্য Generics ব্যবহার করা হয়।

---

# Basic Generic Syntax

```ts
function functionName<T>(value: T): T {
  return value;
}
```

---

## Explanation

এখানে:

- `T` হলো generic type
- এটি যেকোনো type represent করতে পারে
- Call করার সময় TypeScript automatically type detect করে

---

# Basic Example

```ts
function getData<T>(data: T): T {
  return data;
}

console.log(getData<string>("Hello"));
console.log(getData<number>(100));
```

---

## Explanation

এখানে একই function:

- string handle করছে
- number handle করছে

কোনো extra function ছাড়াই।

---




---

## Explanation

এখানে generic array ব্যবহার করা হয়েছে।

---

# Generics with Interface

```ts
interface ApiResponse<T> {
  success: boolean;
  data: T;
}
```

---

# Example

```ts
interface ApiResponse<T> {
  success: boolean;
  data: T;
}

const response: ApiResponse<string> = {
  success: true,
  data: "Data Loaded",
};
```

---

## Explanation

এখানে `data` different type হতে পারবে।

---

# Generics with Multiple Types

একাধিক generic type ব্যবহার করা যায়।

---

# Example

```ts
function getInfo<T, U>(
  name: T,
  age: U
): void {
  console.log(name, age);
}

getInfo<string, number>("Raihan", 22);
```

---

# Explanation

এখানে:

- `T` = string
- `U` = number

---

# Real Life Example

```ts
interface User {
  name: string;
  age: number;
}

function showUser<T>(user: T): T {
  return user;
}

const user = showUser<User>({
  name: "Raihan",
  age: 22,
});

console.log(user);
```

---

---

# Using Any

```ts
function getData(data: any): any {
  return data;
}
```

এখানে type safety নেই।

---

# Using Generics

```ts
function getData<T>(data: T): T {
  return data;
}
```

এখানে type safe থাকে।

---
# TypeScript Generic Constraints & `keyof`

Constraint হলো TypeScript Generics-এর একটি feature যেটা generic type-এর উপর rule বা restriction দেয়।

সহজ ভাষায়:

> কোন type allow হবে আর কোন type allow হবে না সেটা control করার জন্য Constraint ব্যবহার করা হয়।

Constraint দিতে `extends` keyword ব্যবহার করা হয়।

---

# Basic Constraint Syntax

```ts
function example<T extends Type>(
  value: T
) {}
```

---

# Basic Example

```ts
function printLength<T extends string>(
  value: T
): number {
  return value.length;
}

console.log(printLength("TypeScript"));
```

---

## Explanation

এখানে শুধুমাত্র string allow করা হয়েছে।

কারণ:

```ts
T extends string
```

---

# Constraint with Object

```ts
interface User {
  name: string;
}

function showUser<T extends User>(
  user: T
): void {
  console.log(user.name);
}

showUser({
  name: "Raihan",
});
```

---

## Explanation

এখানে object-এর মধ্যে অবশ্যই `name` property থাকতে হবে।

---

# What is `keyof`?

`keyof` হলো TypeScript-এর একটি keyword যেটা কোনো object type-এর সব key-এর union type তৈরি করে।

সহজ ভাষায়:

> Object-এর property name গুলো বের করার জন্য `keyof` ব্যবহার করা হয়।

---

# Basic Example of `keyof`

```ts
interface User {
  name: string;
  age: number;
}
```

---

```ts
type UserKeys = keyof User;
```

---

## Result

```ts
"name" | "age"
```

---

## Explanation

`keyof User` object-এর সব key return করেছে।

---

# `keyof` with Generic Constraint

এটি সবচেয়ে important use case।

---

# Example

```ts
function getProperty<
  T,
  K extends keyof T
>(obj: T, key: K) {
  return obj[key];
}
```

---

## Explanation

এখানে:

- `T` = object type
- `K` = object-এর key
- `K extends keyof T`

মানে:

> key অবশ্যই object-এর valid property হতে হবে।

---

# Full Example

```ts
function getProperty<
  T,
  K extends keyof T
>(obj: T, key: K) {
  return obj[key];
}

const user = {
  name: "Raihan",
  age: 22,
};

console.log(
  getProperty(user, "name")
);
```

---

## Output

```ts
Raihan
```

---

# Invalid Example

```ts
getProperty(user, "email");
```

---

## Problem

এখানে error হবে।

কারণ:

```ts
"email"
```

`user` object-এর valid key না।

---

# Why `keyof` is Useful

`keyof` ব্যবহার করলে:

- Invalid property access prevent হয়
- Type safety বাড়ে
- Better autocomplete পাওয়া যায়
- Dynamic object access safe হয়

---

# Real Life Example

```ts
interface Product {
  name: string;
  price: number;
}

function getValue<
  T,
  K extends keyof T
>(obj: T, key: K) {
  return obj[key];
}

const product: Product = {
  name: "Laptop",
  price: 50000,
};

console.log(
  getValue(product, "price")
);
```

---

# Constraint + `keyof`

```ts
K extends keyof T
```

এটি TypeScript-এর সবচেয়ে common generic patternগুলোর একটি।

এটি নিশ্চিত করে:

- key valid কিনা
- object-এর মধ্যে property আছে কিনা

---

# TypeScript Enum


Enum হলো TypeScript-এর একটি feature যেটা related constant values একসাথে group করে রাখার জন্য ব্যবহার করা হয়।

সহজ ভাষায়:

> একাধিক fixed value কে একটি নামের ভিতরে organize করার জন্য Enum ব্যবহার করা হয়।

---

# Why We Use Enum

- Fixed values manage করতে
- Readable code লিখতে
- Magic value avoid করতে
- Code clean করতে

---

# Basic Enum Syntax

```ts
enum EnumName {
  VALUE1,
  VALUE2,
  VALUE3,
}
```

---

# Custom Numeric Enum

আমরা চাইলে নিজেরাও number assign করতে পারি।

---

# Example

```ts
enum StatusCode {
  Success = 200,
  NotFound = 404,
  ServerError = 500,
}

console.log(StatusCode.Success);
```

---

## Output

```ts
200
```

---

# String Enum

Enum-এর value string-ও হতে পারে।

---

# Example

```ts
enum Role {
  Admin = "ADMIN",
  User = "USER",
  Guest = "GUEST",
}

console.log(Role.Admin);
```

---

## Output

```ts
ADMIN
```


# Using Enum in Function

```ts
enum Role {
  Admin = "ADMIN",
  User = "USER",
}

function checkRole(role: Role) {
  console.log(role);
}

checkRole(Role.Admin);
```

---

# TypeScript `as const`

`as const` হলো TypeScript-এর একটি feature যেটা ব্যবহার করে value-কে fully readonly এবং exact literal type বানানো হয়।

সহজ ভাষায়:

> কোনো value যেন change না হয় এবং exact value type হিসেবে থাকে, তার জন্য `as const` ব্যবহার করা হয়।

---

# Why We Use `as const`

সাধারণভাবে TypeScript value-কে broad type বানিয়ে ফেলে।

যেমন:

```ts
let role = "ADMIN";
```

এখানে type হবে:

```ts
string
```

কিন্তু অনেক সময় আমরা exact value রাখতে চাই:

```ts
"ADMIN"
```

তখন `as const` ব্যবহার করা হয়।

---

# Basic Syntax

```ts
value as const
```

---

# Basic Example

```ts
const role = "ADMIN" as const;
```

---

## Explanation

এখানে type হবে:

```ts
"ADMIN"
```

string না।

---

# Without `as const`

```ts
const status = "SUCCESS";
```

---

## Type

```ts
string
```

---

# With `as const`

```ts
const status = "SUCCESS" as const;
```

---

## Type

```ts
"SUCCESS"
```

---

# `as const` with Object

```ts
const user = {
  name: "Raihan",
  age: 22,
} as const;
```

---

## Explanation

এখন:

- সব property readonly হয়ে যাবে
- exact value type হবে

---

## Result Type

```ts
{
  readonly name: "Raihan";
  readonly age: 22;
}
```

---

# Invalid Update Example

```ts
const user = {
  name: "Raihan",
} as const;

user.name = "Hasan";
```

---

## Problem

এখানে error হবে।

কারণ property readonly।

---

# `as const` with Array

```ts
const colors = [
  "red",
  "green",
  "blue",
] as const;
```

---

## Result Type

```ts
readonly ["red", "green", "blue"]
```

---

## Explanation

এখন array:

- readonly
- exact literal values ধরে রাখবে

---

# Real Life Example

```ts
const Roles = {
  ADMIN: "ADMIN",
  USER: "USER",
  GUEST: "GUEST",
} as const;
```

---

# Access Example

```ts
console.log(Roles.ADMIN);
```

---

## Output

```ts
ADMIN
```

---

# Why `as const` Better Than Enum Sometimes

অনেক project-এ `as const` Enum-এর alternative হিসেবে ব্যবহার করা হয়।

কারণ:

- Extra JavaScript code generate করে না
- Lightweight
- Better performance
- Modern TypeScript pattern

---

# Enum Example

```ts
enum Role {
  Admin = "ADMIN",
}
```

---

# `as const` Alternative

```ts
const Role = {
  Admin: "ADMIN",
} as const;
```

---

# Extract Type from `as const`

```ts
const Roles = {
  ADMIN: "ADMIN",
  USER: "USER",
} as const;

type Role =
  (typeof Roles)[keyof typeof Roles];
```

---

## Result

```ts
"ADMIN" | "USER"
```

---

# Explanation

এখানে object values থেকে union type তৈরি হয়েছে।

---
# TypeScript Conditional Type

Conditional Type হলো TypeScript-এর একটি feature যেটা condition অনুযায়ী different type return করে।

সহজ ভাষায়:

> Type-এর উপর condition চালিয়ে নতুন type তৈরি করার জন্য Conditional Type ব্যবহার করা হয়।

---

# Syntax

```ts
T extends U ? X : Y
```

---

## Explanation

মানে:

```ts
যদি T, U কে follow করে
তাহলে X
না হলে Y
```

---

# Basic Example

```ts
type CheckString<T> =
  T extends string ? string : number;
```

---

# Example Usage

```ts
type A = CheckString<string>;
type B = CheckString<boolean>;
```

---

## Result

```ts
A = string
B = number
```

---

# Real Example

```ts
type IsNumber<T> =
  T extends number ? "Yes" : "No";

type Result1 = IsNumber<number>;
type Result2 = IsNumber<string>;
```

---

## Result

```ts
"Yes"
"No"
```

---

# Why Conditional Type Useful?

- Dynamic type তৈরি করা যায়
- Reusable type লেখা যায়
- Advanced type logic তৈরি করা যায়

---

---

# TypeScript Mapped Type


Mapped Type ব্যবহার করে existing type-এর সব property modify করে নতুন type তৈরি করা হয়।

সহজ ভাষায়:

> এক type-এর property গুলো loop করে নতুন type তৈরি করার জন্য Mapped Type ব্যবহার করা হয়।

---

# Basic Syntax

```ts
type NewType = {
  [Key in keyof OldType]: Type;
};
```

---

# Basic Example

```ts
type User = {
  name: string;
  age: number;
};
```

---

```ts
type ReadOnlyUser = {
  readonly [K in keyof User]: User[K];
};
```

---

## Result

```ts
{
  readonly name: string;
  readonly age: number;
}
```

---

# Explanation

এখানে:

- `keyof User` সব key নিয়েছে
- loop করে readonly করেছে

---

# Another Example

```ts
type BooleanUser = {
  [K in keyof User]: boolean;
};
```

---

## Result

```ts
{
  name: boolean;
  age: boolean;
}
```

---

# Why Mapped Type Useful?

- Reusable type তৈরি করা যায়
- Duplicate code কমে
- Dynamic type manipulation করা যায়

---

---

# TypeScript Utility Types

## What are Utility Types?

Utility Types হলো TypeScript-এর built-in helper types যেগুলো existing type modify করতে সাহায্য করে।

---

# Common Utility Types

- `Partial`
- `Required`
- `Readonly`
- `Pick`
- `Omit`
- `Record`

---

# 1. Partial

সব property optional করে দেয়।

---

# Example

```ts
type User = {
  name: string;
  age: number;
};
```

---

```ts
type PartialUser = Partial<User>;
```

---

## Result

```ts
{
  name?: string;
  age?: number;
}
```

---

# 2. Required

সব property required করে দেয়।

---

# Example

```ts
type User = {
  name?: string;
  age?: number;
};

type RequiredUser = Required<User>;
```

---

## Result

```ts
{
  name: string;
  age: number;
}
```

---

# 3. Readonly

সব property readonly করে দেয়।

---

# Example

```ts
type User = {
  name: string;
};

type ReadonlyUser = Readonly<User>;
```

---

# Result

```ts
{
  readonly name: string;
}
```

---

# 4. Pick

Specific property select করে।

---

# Example

```ts
type User = {
  name: string;
  age: number;
  email: string;
};

type UserInfo = Pick<
  User,
  "name" | "email"
>;
```

---

## Result

```ts
{
  name: string;
  email: string;
}
```

---

# 5. Omit

Specific property remove করে।

---

# Example

```ts
type User = {
  name: string;
  age: number;
  password: string;
};

type SafeUser = Omit<
  User,
  "password"
>;
```

---

## Result

```ts
{
  name: string;
  age: number;
}
```

---

# 6. Record

Specific key এবং value type দিয়ে object তৈরি করে।

---

# Example

```ts
type Roles = Record<
  string,
  string
>;
```

---

## Result

```ts
{
  [key: string]: string;
}
```

---

# Why Utility Types Useful?

- Code reusable হয়
- Duplicate code কমে
- Type manipulation সহজ হয়
- Cleaner code পাওয়া যায়

---

# Best Practices

## ✅ Built-in Utility Types ব্যবহার করুন

নিজে manually type না লিখে utility type ব্যবহার করুন।

---

## ✅ Mapped Type ব্যবহার করুন dynamic type তৈরির জন্য

---

## ✅ Conditional Type ব্যবহার করুন advanced logic-এর জন্য

---

# Quick Recap

| Topic | Purpose |
|---|---|
| Conditional Type | Condition অনুযায়ী type return |
| Mapped Type | Existing type modify |
| Utility Type | Built-in helper type |

---

# Final Example

```ts
type User = {
  name: string;
  age: number;
  password: string;
};

type PublicUser = Omit<
  User,
  "password"
>;

type OptionalUser =
  Partial<User>;
```

---

# Conclusion

Conditional Type, Mapped Type এবং Utility Types হলো TypeScript-এর advanced এবং powerful feature।

এগুলো ব্যবহার করে:

- reusable
- dynamic
- clean
- type safe

code লেখা যায়।

বিশেষ করে large TypeScript project-এ এগুলো অনেক important।






























