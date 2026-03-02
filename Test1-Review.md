# JavaScript Test Study Sheet

---

# 1️) The DOM (Document Object Model)

## What is the DOM?

* A tree structure built by the browser when HTML loads.
* Each HTML element becomes a node (object).
* The root node is `<html>`.
* The DOM is **live** — changes in JS update the page immediately.

---

## DOM Tree Relationships

Common properties:

* `parentNode`
* `childNodes`
* `children` (elements only)
* `firstChild`
* `lastChild`
* `previousElementSibling`
* `nextElementSibling`

---

## Selecting Elements

### By ID

```js
const el = document.getElementById('id');
```

### By Tag

```js
document.getElementsByTagName('div');
```

### By Class

```js
document.getElementsByClassName('box');
```

### CSS Selectors (Recommended)

```js
document.querySelector('.box');
document.querySelectorAll('.box');
```

---

## HTML Collections

* Array‑like but NOT true arrays.
* Convert using:

```js
Array.from(collection);
```

---

## Changing Content

### innerHTML

* Gets/sets HTML
* Parses HTML

### textContent

* Gets/sets raw text
* Does NOT parse HTML

### innerText

* Human‑visible text only (CSS aware)

---

## Creating & Modifying Elements

### Create

```js
const el = document.createElement('p');
const text = document.createTextNode('Hello');
el.appendChild(text);
```

### Insert / Move

```js
parent.appendChild(child);
parent.insertBefore(newNode, referenceNode);
parent.replaceChild(newNode, oldNode);
```

⚠ A DOM node can only exist in ONE place.

---

## Attributes

Access standard attributes directly:

```js
el.id
el.src
el.className
```

### classList

```js
el.classList.add('active');
el.classList.remove('active');
el.classList.toggle('active');
el.classList.contains('active');
```

### Custom Attributes

```js
el.setAttribute('data-info', 'value');
el.getAttribute('data-info');
```

---

## Styling with JavaScript

```js
el.style.backgroundColor = 'red';
el.style.width = '100px';
```

* Must use camelCase.
* Values must be strings.

---

## Element Size Properties

* `clientWidth` – no borders/scroll
* `offsetWidth` – includes borders
* `scrollHeight` – full scrollable height

---

# 2️) Core JavaScript (From Textbook)

## Variables

* `let` – changeable
* `const` – cannot reassign
* `var` – function scoped (avoid)

---

## Data Types

* Number
* String
* Boolean
* Null
* Undefined
* Object
* Array

---

## Functions

```js
function greet(name) {
  return `Hello ${name}`;
}
```

Arrow function:

```js
const greet = name => `Hello ${name}`;
```

---

## Arrays

```js
const arr = [1,2,3];
arr.push(4);
arr.map(x => x * 2);
```

---

## Objects

```js
const user = {
  name: 'Alice',
  age: 25
};
```

---

## Scope

* Global scope
* Function scope
* Block scope (`let`, `const`)

---

# 3️) TypeScript Basics

## What is TypeScript?

* Superset of JavaScript
* Adds static typing
* Compiles to JavaScript

---

## Basic Types

```ts
let age: number = 25;
let name: string = 'Alice';
let isActive: boolean = true;
```

---

## Arrays

```ts
let nums: number[] = [1,2,3];
```

---

## Functions

```ts
function add(a: number, b: number): number {
  return a + b;
}
```

---

## Interfaces

```ts
interface User {
  name: string;
  age: number;
}
```

---

# 4️) Events

## Common Events

* `click`
* `keydown`
* `submit`
* `mouseover`
* `load`

---

## Adding Event Listeners

```js
el.addEventListener('click', handler);
```

Multiple listeners allowed.

---

## Event Object

```js
el.addEventListener('click', event => {
  console.log(event.target);
  console.log(event.type);
});
```

Important properties:

* `event.target`
* `event.key`
* `event.type`

---

## Prevent Default

```js
event.preventDefault();
```

Stops browser default behavior.

---

## Stop Propagation

```js
event.stopPropagation();
```

Stops bubbling.

---

## Event Phases

1. Capturing (top → down)
2. Target
3. Bubbling (bottom → up, default)

Use capturing:

```js
el.addEventListener('click', fn, { capture: true });
```

---

## Event Delegation

Attach one listener to parent:

```js
list.addEventListener('click', e => {
  if (e.target.tagName === 'LI') {
    console.log(e.target.textContent);
  }
});
```

Efficient and works for dynamic elements.

---

## Timers

### setTimeout

```js
setTimeout(fn, 1000);
```

Runs once.

### setInterval

```js
setInterval(fn, 1000);
```

Runs repeatedly.

---

## Debounce vs Throttle

* Debounce → waits until activity stops
* Throttle → limits frequency

---

## Custom Events

```js
const ev = new CustomEvent('myEvent', {
  detail: { data: 123 },
  bubbles: true
});

element.dispatchEvent(ev);
```

---

# 5️) Promises & Async / Await

## Why Promises?

Avoid callback hell.

---

## Promise Basics

```js
const p = new Promise((resolve, reject) => {
  resolve('success');
});
```

States:

* Pending
* Fulfilled
* Rejected

---

## Using then / catch

```js
p.then(result => console.log(result))
 .catch(err => console.error(err));
```

---

## Async / Await

```js
async function getData() {
  const res = await fetch('/api');
  return res.json();
}
```

* `await` only works inside `async` functions.

---

## Error Handling

```js
try {
  const data = await getData();
} catch (err) {
  console.error(err);
}
```

---

## Promise.all

```js
await Promise.all([p1, p2]);
```

* Runs in parallel.
* Fails if ANY fail.

---

## Promise.allSettled

Returns status of all promises.

---

## Promise.race

Returns first settled promise.

---

## Promise.any

Returns first fulfilled promise.

---

# Quick Review Checklist

✔ Can explain DOM tree
✔ Can select & modify elements
✔ Understand event bubbling & capturing
✔ Know preventDefault vs stopPropagation
✔ Know difference between Promise.all & allSettled
✔ Can write async/await with try/catch
✔ Understand TypeScript basic typing

