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

👉 Example with multiple types:

```ts id="j8p1c2"
let employee: [number, string, boolean] = [101, "Karim", true];
```

👉 Wrong example:

```ts id="9c2k1l"
let wrong: [string, number] = [25, "Rahim"]; // ❌ Error
```

👉 Explanation:
Tuple-এ order খুব গুরুত্বপূর্ণ — type mismatch হলে error দিবে।

---

## ⚠️ Important Notes

* Array → same type multiple value
* Object → structured data (key-value)
* Tuple → fixed structure + fixed order

---

## 📊 Summary Table

| Type   | Example                  | Description                |
| ------ | ------------------------ | -------------------------- |
| Array  | [1, 2, 3]                | একই type এর multiple value |
| Object | {name: "Rahim", age: 25} | structured data            |
| Tuple  | ["Rahim", 25]            | fixed order + fixed type   |

---

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

---

## 🔹 Function Without Return (void)

```ts id="a8c3k9"
function greet(name: string): void {
  console.log("Hello " + name);
}
```

👉 Explanation:
`void` মানে function কোনো value return করবে না।

---

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

---

## 🔹 Function Type

```ts id="t8v3n1"
let addNumbers: (x: number, y: number) => number;

addNumbers = (x, y) => x + y;
```

👉 Explanation:
এখানে variable-এ function type define করা হয়েছে।

---

## 🔹 Union Type in Function

```ts id="z1k9d2"
function printId(id: number | string) {
  console.log(id);
}
```

👉 Explanation:
এখানে `id` number অথবা string দুইটাই হতে পারে।

---

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

## 📦 Rest in Object Destructuring

```ts id="c3k9d2"
let user = { name: "Rahim", age: 25, city: "Dhaka" };

let { name, ...others } = user;
```

👉 Explanation:
`name = "Rahim"`
`others = { age: 25, city: "Dhaka" }`

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

---

## 📦 Override Value

```ts id="z5p1t6"
let user = { name: "Rahim", age: 25 };

let newUser = { ...user, age: 30 };
```

👉 Explanation:
শেষের value (`age: 30`) পুরানোটাকে override করবে।

---

## 📦 Copy Array / Object

```ts id="b6y3f2"
let numbers = [1, 2, 3];
let copyNumbers = [...numbers];
```

👉 Explanation:
এটা shallow copy তৈরি করে।

---

# ⚠️ Important Notes

* Rest → সবসময় **শেষ parameter** হতে হবে
* Spread → copy/merge/expand করার জন্য
* Spread shallow copy করে (deep copy না)

---

## 📊 Summary Table

| Feature | Rest               | Spread                  |
| ------- | ------------------ | ----------------------- |
| কাজ     | collect            | expand                  |
| ব্যবহার | function parameter | array/object copy/merge |
| result  | array              | individual values       |

---

## 📦 What Is Destructuring?

Destructuring হলো এমন একটি syntax যেটা ব্যবহার করে আমরা **array বা object থেকে value আলাদা করে variable-এ assign করতে পারি**।

👉 এতে code ছোট, clean এবং readable হয়।

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

---

## 🔸 Default Value

```ts id="q8k1z5"
let [x = 5, y = 10] = [1];
```

👉 Explanation:
`x = 1`, `y = 10` (কারণ y এর value দেওয়া হয়নি)

---

## 🔸 Rest with Array

```ts id="d2f7h9"
let [first, ...rest] = [1, 2, 3, 4];
```

👉 Explanation:
`first = 1`, `rest = [2, 3, 4]`

---

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

---

## 🔸 Rename Variable

```ts id="u4x8c2"
let { name: userName } = user;
```

👉 Explanation:
`name` property কে `userName` নামে ব্যবহার করা হয়েছে

---

## 🔸 Default Value

```ts id="y6p2r1"
let { city = "Dhaka" } = user;
```

👉 Explanation:
`city` না থাকলে default `"Dhaka"` হবে

---

## 🔸 Rest with Object

```ts id="k1m9z7"
let { name, ...others } = {
  name: "Rahim",
  age: 25,
  city: "Dhaka",
};
```

👉 Explanation:
`name = "Rahim"`
`others = { age: 25, city: "Dhaka" }`

---

# 🔹 Destructuring in Function Parameter

```ts id="n8q2v4"
function printUser({ name, age }: { name: string; age: number }) {
  console.log(name, age);
}
```

👉 Explanation:
Function parameter-এর মধ্যে destructuring করা হয়েছে এবং type define করা হয়েছে।

---

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

# ⚠️ Important Notes

* Array destructuring → order গুরুত্বপূর্ণ
* Object destructuring → key নাম গুরুত্বপূর্ণ
* Default value ব্যবহার করা যায়
* Rest operator (`...`) ব্যবহার করা যায়

---

## 📊 Summary Table

| Feature              | Description                    |
| -------------------- | ------------------------------ |
| Array Destructuring  | index অনুযায়ী value বের করা    |
| Object Destructuring | key অনুযায়ী value বের করা      |
| Default Value        | fallback value দেওয়া যায়       |
| Rename               | variable নাম পরিবর্তন করা যায়  |
| Rest                 | remaining data collect করা যায় |

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

---


## 🔹 Function Type Alias

```ts id="f7g8h9"
type Add = (a: number, b: number) => number;

const addNumbers: Add = (a, b) => a + b;
```

👉 Explanation:
Function-এর type একবার define করে reuse করা যায়।

---

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

---

## 🔸 Union with Function

```ts id="u4n5i6"
function printId(id: number | string) {
  console.log(id);
}
```

👉 Explanation:
Function parameter-এ একাধিক type allow করা হয়েছে।

---

## 🔸 Union with Array

```ts id="u7n8i9"
let mixed: (number | string)[] = [1, "Rahim", 2, "Karim"];
```

👉 Explanation:
Array-এ multiple type allow করা হয়েছে।

---

## 🔸 Literal Union

```ts id="u0l1t2"
type Status = "success" | "error" | "loading";

let currentStatus: Status = "success";
```

👉 Explanation:
নির্দিষ্ট কিছু value limit করা হয়েছে।

---

## ⚠️ Narrowing (Important)

```ts id="u3n4a5"
function process(value: number | string) {
  if (typeof value === "string") {
    console.log(value.toUpperCase());
  } else {
    console.log(value.toFixed(2));
  }
}
```

👉 Explanation:
Type check করে specific type অনুযায়ী কাজ করা হয় — এটাকে narrowing বলে।

---

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

---

## 🔸 Conflict Example

```ts id="i7n8t9"
type A = { id: number };
type B = { id: string };

type C = A & B; // ❌ Problem
```

👉 Explanation:
একই property different type হলে conflict হয়।

---

# 🔍 Union vs Intersection

| Feature        | Union (`|`)                      | Intersection (`&`)              |
|----------------|----------------------------------|--------------------------------|
| কাজ            | একটার মধ্যে যেকোনো একটা          | সবগুলো একসাথে                  |
| Example        | string | number                 | A & B                          |
| Use Case       | flexible input                  | combine structure              |

---

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

---

## 📦 Optional Chaining with Function

```ts id="o7p8t9"
let user = {
  greet: () => "Hello",
};

let msg = user.greet?.();
```

👉 Explanation:
Function থাকলে call হবে, না থাকলে error হবে না।

---

# 🔍 Combined Example

```ts id="c1o2m3"
let user = {
  name: "Rahim",
};

let city = user.address?.city ?? "Unknown";
```

👉 Explanation:
`address` না থাকলে `city` undefined → তারপর `"Unknown"` use হবে।

---

# ⚠️ Important Notes

* Ternary → short condition
* `??` → null/undefined check করে
* `?.` → safe access দেয়
* `||` আর `??` এক না

---

## 📊 Summary Table

| Feature            | Operator | কাজ                   |
| ------------------ | -------- | --------------------- |
| Ternary            | ? :      | condition short করা   |
| Nullish Coalescing | ??       | default value set করা |
| Optional Chaining  | ?.       | safe property access  |

---

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

---

## 📦 Combined Nullable

```ts id="n7u8l9"
let user: string | null | undefined;
```

👉 Explanation:
এখানে তিনটা possible value আছে।

---

## ⚠️ Important

```ts id="n0u1l2"
let name: string | null = null;

console.log(name.length); // ❌ Error
```

👉 Explanation:
null হলে property access করা যাবে না — আগে check করতে হবে।

---

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

---

## ✅ With Type Checking

```ts id="u7n8k9"
let value: unknown = "Hello";

if (typeof value === "string") {
  console.log(value.toUpperCase());
}
```

👉 Explanation:
type check করার পরে safely ব্যবহার করা যায়।

---

## 🔍 unknown vs any

| Feature | any       | unknown   |
| ------- | --------- | --------- |
| Safety  | ❌ unsafe  | ✅ safe    |
| Check   | দরকার নাই | দরকার আছে |

---

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

---

## 📦 Exhaustive Check

```ts id="n9e0v1"
type Shape = "circle" | "square";

function getShape(shape: Shape) {
  if (shape === "circle") return "Circle";
  if (shape === "square") return "Square";

  let check: never = shape; // ensure সব case cover হয়েছে
}
```

👉 Explanation:
সব condition handle করা হয়েছে কিনা check করার জন্য `never` ব্যবহার হয়।

---

# ⚠️ Important Notes

* Nullable → null/undefined allow করে
* unknown → safe any
* never → never return / unreachable code

---

## 📊 Summary Table

| Type     | Description                      |
| -------- | -------------------------------- |
| Nullable | null / undefined allow           |
| unknown  | safe any (type check required)   |
| never    | never returns / impossible state |

---




































