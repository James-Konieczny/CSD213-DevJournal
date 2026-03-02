# Web Development Final Study Sheet

This study sheet summarizes and highlights the **core concepts** that repeatedly appeared across all question sets.

---

# 🌐 DOM & Events

## ✅ Event Propagation Phases

**Three phases:**

1. Capturing
2. Target
3. Bubbling

* `addEventListener('click', handler, true)` → runs in the **capturing phase**.
* By default, most events run in the **bubbling phase**.
* `event.stopPropagation()` prevents the event from reaching ancestor elements.

### ⭐ Core Concept: Event Delegation

Attach one listener to a **parent element** to handle events from its children.

```js
document.body.addEventListener('click', (e) => {
  if (e.target.matches('button')) {
    console.log('Button clicked');
  }
});
```

---

## ✅ DOM Selection & Collections

* `document.querySelectorAll()` → returns a **static NodeList** (NOT live).
* `appendChild()` → returns the appended node.
* `element.getAttribute('href')` → returns the attribute value as a **string**.

---

## ✅ Removing DOM Nodes

Correct classic method:

```js
element.parentNode.removeChild(element);
```

Modern alternative (good to know):

```js
element.remove();
```

---

# 🧠 JavaScript Core Concepts

## ✅ Hoisting

* Function **declarations** are fully hoisted.
* Function **expressions & arrow functions** are NOT initialized until execution.

---

## ✅ Variable Scope

| Keyword | Scope    | Reassignable | Hoisted  |
| ------- | -------- | ------------ | -------- |
| var     | Function | Yes          | Yes      |
| let     | Block    | Yes          | No (TDZ) |
| const   | Block    | No           | No (TDZ) |

⭐ Use `const` by default.

---

## ✅ Equality

* `2 == '2'` → **true** (type coercion)
* `2 === '2'` → false (strict equality)

⭐ Prefer `===`

---

## ✅ Template Literals

* Use backticks: `` ` ``
* Support interpolation: `${value}`
* Can span multiple lines

```js
const name = "Alice";
console.log(`Hello, ${name}!`);
```

---

## ✅ Destructuring

```js
const [a, b, c] = [1, 2, 3, 4];
// a = 1, c = 3
```

Default values are allowed:

```js
const [x = 10] = [];
```

---

## ✅ Spread Operator

Creates a shallow copy of arrays:

```js
let newArr = [...oldArr];
```

---

# 📦 Arrays & Methods

## ✅ Methods That MODIFY the Original Array

* `splice()`

## ✅ Methods That Return NEW Arrays

* `slice()`
* `map()`
* `filter()`

## ✅ Accumulation

* `reduce()` accumulates values.

---

# 🏹 Arrow Functions

### ⭐ Core Properties

* Do NOT have their own `this`
* Cannot be used as constructors
* Can have default parameters
* Do NOT automatically return a Promise

`this` inside arrow functions refers to the **lexical (surrounding) scope**.

---

# 🧮 Numbers & Special Values

* `Number.isNaN(NaN)` → true

---

# 📚 JSON

* `JSON.stringify(obj)` → converts object to JSON string
* `JSON.parse(string)` → converts JSON string to JavaScript object

---

# 📦 ES6 Modules

* `export default` → allows exporting a single default value

---

# 🔷 TypeScript Core Concepts

## ✅ Compilation

TypeScript can compile to multiple targets (ES3, ES5, ES6, etc.)

---

## ✅ Interfaces

Interfaces can be extended:

```ts
interface A { x: number }
interface B extends A { y: number }
```

---

## ✅ Union Types

Valid unions:

```ts
type ID = number | string;
type ID = number | undefined;
```

---

## ✅ Enums

Correct numeric enum:

```ts
enum Direction { Up = 1, Down, Left, Right }
```

---

## ✅ Type Guards

Correct type guard for `string[]`:

```ts
function isStringArray(arr: any): arr is string[] {
  return Array.isArray(arr) && arr.every(item => typeof item === 'string');
}
```

⭐ Core idea: A type guard must:

1. Return a boolean
2. Use `arr is Type`
3. Actually check the runtime type

---

# 📌 High-Frequency Exam Traps

1. `querySelectorAll()` is NOT live
2. `==` vs `===`
3. Arrow function `this`
4. `splice()` mutates, `slice()` does not
5. Capturing vs Bubbling phase
6. Type guards must actually validate the type

---

# 🎯 If You Remember Only These Things

* Use `const` by default
* Prefer `===`
* Understand event propagation
* Know which array methods mutate
* Understand lexical `this` in arrow functions
* Know how JSON works
* Understand TypeScript unions, enums, and type guards

---

End of Final Study Sheet
