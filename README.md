# 2. Understanding the `keyof` Keyword in TypeScript

The `keyof` keyword in TypeScript is a powerful utility that helps create safer, more predictable code when dealing with object properties.

---

##  What is `keyof`?

The `keyof` keyword is used to extract all the **property names (keys)** of a type or interface as a **union of string literal types**.

---

##  Why is it useful?

- It ensures you only access **valid properties** of an object.
- Prevents runtime errors by catching mistakes at compile time.
- Enhances **type safety** 

---

##  Example:

```ts
type User = {
  name: string;
  age: number;
};

function getValue(obj: User, key: keyof User): string | number {
  return obj[key];
}

const user: User = { name: "Monira", age: 21 };

console.log(getValue(user, "name")); // output: Monira
console.log(getValue(user, "age"));  // output: 21
