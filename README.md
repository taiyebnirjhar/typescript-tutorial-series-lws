# সহজ বাংলায় Type Script Tutorial Series ( lesson - 3 )

### Basic of type checking

---

#### String & Number

Lets check a simple variable assignment and declaration on vanila js style

```bash
let playerName = "sakib";
console.log(playerName);

playerName = 50;

console.log(playerName);

```

If we try to compile this code, it will return this error:

```bash
error TS2322: Type 'number' is not assignable to type 'string'.

line 4: playerName = 50;
        ~~~~~~~~~~
```

➡️ Beacuse typescript infere ( অনুমান করা) the value of `playerName` will be always string.

⚠️ How!!!!!

🔥 ` TypeScript infers the value type of a variable based on the type of value that is assigned to it.`

---

Hmmm.. WHAT IF, we just declare a variable without assigning any value, Like:

```bash
let playerName;

playerName = "Sakib";

playerName = 35;

console.log(playerName); // 35
```

Now its giving expected value.

➡️ Because initial value was `player === undifined`

🚨 ` SO TYPESCRIPT SHOW'S THIS KIND OF BEHAVIOUR ONLY IF WE DECLARE A VARIABLE AND ASSIGN A VALUE AT THE SAME TIME.`

---

#### Function

what about functions and its params!

lets see a simple function with a human error

```bash
function multiply(a, b) {
  return a * b;
}

console.log(multiply('hello', 5)); // NaN
```

⚠️ We have added a typo knowingly. but typescript helps us to get better developer experince.

My editor IntelliSense is giving me two warnings:

1.

```bash
Parameter 'a' implicitly has an 'any' type.
```

2.

```bash
Parameter 'b' implicitly has an 'any' type.
```

➡️ Because its not the recommended way to define a function in typescript.

➡️ we have to explicitely define type of arguments which can prevent our typo, like this:

```bash
function multiply(a: number, b: number) {
  return a * b;
}
```

now if we pass any arguments rather than number it will give us error

```bash
console.log(multiply('hello',5))
```

```bash
error TS2345: Argument of type 'string' is not assignable to parameter of type 'number'.

line 22: console.log(multiply("hello", 5));
                              ~~~~~~~
```

#### Array

For This array:

```bash
const mixed = [5, "mango", true];
```

➡️ only number, string and boolean are acceptable to push

#### Object

For This Object:

```bash
let person = {
  name: "masrafi",
  age: 34,
  isCaptain: true,
}
```

➡️ name can only hold string
➡️ age can only hold number
➡️ isCaptain can only hold boolean

if we try this

```bash
person.name = 10;
```

It will return error
