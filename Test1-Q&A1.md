# Web Development Study Sheet – Answers

---

## Question 1

**addEventListener can accept a third argument for options**
**Answer:** True
The third parameter can be a boolean (capture) or an options object.

---

## Question 2

**document.body.appendChild() returns the appended node**
**Answer:** True

---

## Question 3

**document.querySelectorAll('.foo') returns a live collection**
**Answer:** False
It returns a static NodeList, not a live collection.

---

## Question 5

**Best description of event delegation**
**Answer:**
Attaching a single event listener to a parent element to manage events for its children

---

## Question 6

**The expression 2 == '2' evaluates to true in JavaScript**
**Answer:** True
Loose equality performs type coercion.

---

## Question 7

**Correct use of spread operator**
**Answer:**

```js
let newArr = [...oldArr];
```

---

## Question 8

**Template literals cannot span multiple lines**
**Answer:** False
Template literals can span multiple lines using backticks.

---

## Question 9

**Output of:**

```js
const [a, b, c] = [1, 2, 3, 4];
console.log(a, c);
```

**Answer:**
1 3

---

## Question 10

**Variables declared with `var` are function scoped**
**Answer:** True

---

## Question 11

**Method that converts an object into a JSON string**
**Answer:** JSON.stringify

---

## Question 12

**TypeScript compiles to ES6 JavaScript only**
**Answer:** False
TypeScript can compile to multiple JavaScript target versions (ES3, ES5, ES6, etc.).

---

## Question 13

**True statements about arrow functions:**

✔ Arrow functions do not have their own `this`
✔ Arrow functions cannot be used as constructors

False statements:

* Arrow functions always return a Promise
* Arrow functions cannot have default parameters

---

## Question 14

**JSON.parse returns a JavaScript object**
**Answer:** True

---

## Question 15

**Number.isNaN(NaN) returns true**
**Answer:** True

---

## Question 16

**Correct numeric enum in TypeScript:**

```ts
enum Direction { Up = 1, Down, Left, Right }
```

---

## Question 17

**Phase for `addEventListener('click', handler, true)`**
**Answer:** Capturing

---

## Question 18

**Array method that returns a new array of the same elements**
**Answer:** Array.prototype.slice()

---

## Question 19

**The `this` keyword inside an arrow function refers to the global object**
**Answer:** False
It refers to the surrounding lexical scope.

---

## Question 20

**Destructuring arrays can assign default values**
**Answer:** True

Example:

```js
const [a = 10, b = 20] = [1];
```

---

# Web Development Study Sheet – Answers (Set 5, No Repeats)

---

## Question 1

**Which array method modifies the original array?**
**Answer:** `Array.prototype.splice()`
`splice()` mutates the original array.

---

## Question 2

**Calling `event.stopPropagation()` stops the event from reaching ancestor elements**
**Answer:** True

---

## Question 5

**All event listeners in the DOM bubble by default**
**Answer:** True
Most events bubble, but not all events bubble.

---

## Question 6  (Type Guard – Reviewed Carefully)

**Which function correctly implements a type guard for `Array<string>`?**
**Correct Answer:**

```ts
function isStringArray(arr: any): arr is string[] {
  return arr.every(item => typeof item === 'string');
}
```

This is the only option that actually checks that every element is a string.
(Although in real-world TypeScript, you would typically also include `Array.isArray(arr)`.)

---

## Question 7

**TypeScript interfaces can be extended**
**Answer:** True

---

## Question 10

**Which methods can test if a string contains a substring?**
**Correct Answers:**

* `String.prototype.includes()`
* `String.prototype.indexOf()`

---

## Question 12

**Valid use of a template literal:**
**Answer:**

```js
const name = "Alice";
console.log(`Hello, ${name}!`);
```

---

## Question 13

**Array.prototype.reduce() can be used to accumulate a value**
**Answer:** True

---

## Question 15

**What will this log?**

```js
const s = new Set([1,2,3]);
s.add(4);
console.log(s.size);
```

**Answer:**
4

---

## Question 16

**ES6 modules can use `export default` to export a single value**
**Answer:** True

---

## Question 17

**What does `element.getAttribute('href')` return?**
**Answer:**
The value of the href attribute as a string
(It returns `null` only if the attribute does not exist.)

---

## Question 18

**Valid union type declarations in TypeScript:**
**Correct Answers:**

* `type ID = number | string;`
* `type ID = number | undefined;`

---

End of Study Sheet – Set 5 (No Repeats)
# Web Development Study Sheet – Answers (Set 6, No Repeats)

---

## Question 2

**Which of the following is NOT a valid DOM event?**
Options: click, mousemove, render
**Answer:** `render`
`click` and `mousemove` are valid DOM events. `render` is not a standard DOM event.

---

## Question 3

**Function declarations are hoisted but function expressions and arrow functions are not**
**Answer:** True
Function declarations are fully hoisted. Function expressions and arrow functions are not initialized until execution reaches them.

---

## Question 4

**Which keyword declares a variable that cannot be reassigned and is block-scoped?**
**Answer:** `const`
`const` is block-scoped and prevents reassignment.

---

## Question 7

**Select all statements that correctly remove a node from the DOM.**

**Correct Answer:**

```js
element.parentNode.removeChild(element)
```

This is the valid classic way to remove a node from the DOM.

Other options are incorrect because:

* `element.removeChild()` requires a child parameter.
* `element.parent.removeChild(element)` → `parent` is not a standard property.
* `document.remove(element)` is not a valid DOM method.

---

End of Study Sheet – Set 6 (No Repeats)

