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



```





# 3. Understanding `any`, `unknown`, and `never` in TypeScript

TypeScript introduces advanced types that improve code safety and clarity. Among them, `any`, `unknown`, and `never` are often misunderstood but serve distinct and important purposes. Here's a concise breakdown of how and when to use each.

---

##  `any`

- Represents **any value**.
- **No type checking** is enforced.
- You can assign and use the value however you like typeScript won't complain.

### Example:

```ts
let value: any = "Hello";
value = 10;
value = true;


```
#  Understanding `any`, `unknown`, and `never` in TypeScript

TypeScript provides powerful type checking features that help catch errors early and improve code quality. Among its advanced types are `any`, `unknown`, and `never`. Each serves a different purpose and should be used appropriately.

---

##  `any`

The `any` type disables all type checking. A variable declared with `any` can hold **any value**, and TypeScript won't check its type at all.

```ts
let value: any = "Hello";
value = 10;
value = true;
````

###  Use Case

* When you're working with legacy code or third pparty libraries where type information isn't available.


---

##  `unknown`

The `unknown` type is similar to `any` in that it can hold any value, **but** TypeScript **forces** you to do a type check before using it.

```ts
let data: unknown = "Hello";

if (typeof data === "string") {
  console.log(data.toUpperCase()); 
}
```

### Use Case

* When you want to accept any value but still enforce type safety before using it.

###  Benefit

Stronger and safer than `any`, since TypeScript ensures proper type checks.

---

##  `never`

The `never` type represents values that **never occur**. It's used in functions that:

* Always throw an error
* Never return (infinite loops, etc.)

```ts
function throwError(): never {
  throw new Error("Galti se error ho gaya");
}
```

###  Use Case

* Functions that are expected to never return a value.
* Exhaustiveness checks in `switch` statements.


