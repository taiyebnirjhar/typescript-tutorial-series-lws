# সহজ বাংলায় Type Script Tutorial Series ( lesson - 4 )

### Explicit Types

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

### Union Types

1. String: `let a: string | number ;`

➡️ Here value will be either string or number. pretty much self explainatory

2. Array: `let arr:(string | number)[] = []`

3. Object:

   type one:

   ```ts
   let c: object;
   c = {
     name: "taiyeb", // could be any type
   };
   ```

   type two:

   ```ts
   let c: {
     name: string;
     age: number;
     adult: boolean;
   };

   c = {
     name: "taiyeb",
     age: 24,
     adult: true,
   };
   ```

   type three:

   ```ts
   let c: object;

   c = [1, 2, 3];
   ```

   🔥 Also valid. becasue in javaScript `typeof arr === typeof obj` retruns `true`
   <br>
   ⚠️ But if our object has an explicit pattern, array will not be accepted

   ```ts
   let obj: {
     name: string;
     age: number;
   };
   obj = ["hi", 123];
   ~~~

   Error: Type '(string | number)[]' is missing the following properties from type '{ name: string; age: number; }': name, age
   ```

   🔥 HOW SMART! Aint it?
