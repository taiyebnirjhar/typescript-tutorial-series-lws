# সহজ বাংলায় Type Script Tutorial Series ( lesson - 4 )

### Explicit & Union Types

---

#### String

Explicitly declaring variable type for string

```bash
let myName: string;

myName = "taiyeb nirjhor";

console.log(myName); // taiyeb nirjhor
```

If we try to assign anyother type of value rather than string, it will return an error, like:

```bash
let myName: string;

myName = 1999;
~~~~~~
console.log(myName);

terminal error: Type 'number' is not assignable to type 'string'.
```

---

#### Number

Explicitly declaring variable type for number

```bash
let myRole: number;

myName = 212902003;

console.log(myName); // 212902003
```

#### Array

Array of String

```ts
let a: string[] = [];
```

Here We have to assign a value (in this case empty array `[]`), otherwise it will give error. for example:

```ts
let a: string[];

a.push('hello');
~~~~~~

Error: Variable 'a' is used before being assigned.
```

➡️ `We Can't Use an Array Method (array.push()), Without an Array 😅`

➡️ Because a is declared as an `array of strings` but has not been initialized with a value (`atleast empty array [] `). When we try to push a value to an uninitialized array, TypeScript will throw an error `because the array does not exist yet. `.

⚠️➡️⚠️🔥
