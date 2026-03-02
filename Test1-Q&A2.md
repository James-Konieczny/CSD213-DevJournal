# Promise Practice Questions – Answers

---

## Question 1

**The Promise constructor takes two arguments: resolve and reject functions.**
**Answer:** True

---

## Question 2

**`Promise.all()` can take a Map or Set instead of an array.**
**Answer:** False

---

## Question 3

**Each `then()` returns the same Promise instance.**
**Answer:** False
Each `then()` returns a NEW Promise.

---

## Question 4

**What happens if you throw an error inside the Promise constructor?**
**Answer:** The promise is rejected with that error.

---

## Question 5

**Which of the following properties is NOT present in the objects returned by `Promise.allSettled()`?**
**Answer:** callback
The result objects contain:

* `status`
* `value` (if fulfilled)
* `reason` (if rejected)

---

## Question 6

**In the chain `p.then(f1).then(f2)`, which function runs first?**
**Answer:** f1

---

## Question 7

**`Promise.allSettled()` always resolves, never rejects.**
**Answer:** True

---

## Question 8

**Which function is equivalent to `Promise.resolve(value)`?**
**Answer:** `async () => value`
An async function automatically wraps returned values in a resolved promise.

---

## Question 9

**The `catch()` method only handles rejections, not fulfillment.**
**Answer:** True

---

## Question 10

**Which of the following is NOT a reason for `Promise.any()` to reject?**
**Answer:** All input promises never settle
`Promise.any()` rejects only if ALL promises reject OR if no promises are provided.

---

## Question 11

**What does `Promise.allSettled()` return?**
**Answer:** a promise that resolves with an array of result objects

---

## Question 12

**If a `then()` callback returns a value `x`, the next `then()` receives `x`.**
**Answer:** true

---

## Question 13

**Which of the following is a correct way to handle a promise rejection?**
**Answer:**

* `promise.catch(errorHandler)`


---

## Question 14

**Is the following chain valid? `p.finally(f).then(g)`?**
**Answer:** Yes
`finally()` returns a promise, so chaining is valid.

---

## Question 15

**When using `Promise.allSettled()`, which of the following statements is true?**
**Answer:** The returned promise never rejects.

---

## Question 16

**`Promise.any()` rejects if all promises reject.**
**Answer:** True

---

## Question 17

**The result of `Promise.allSettled()` includes a `value` field only for fulfilled promises.**
**Answer:** True

---

## Question 18

**Which of the following can be passed to `finally()`?**
**Answer:** a function

---

## Question 19

**If two promises reject and one fulfills, what is the outcome of `Promise.any()`?**
**Answer:** It resolves with the value of the fulfilled promise.

---

## Question 20

**`Promise.reject(error)` creates a rejected promise.**
**Answer:** True

---

# Promise Practice Questions – Answers (Set 2)

---

## Question 1

**When is the callback passed to `finally()` executed?**
**Answer:** After the promise is settled, regardless of fulfillment or rejection.

---

## Question 2

**What type of value can be passed to `reject()`?**
**Answer:** Any value (error object, string, number, etc.).

---

## Question 3

**If all promises passed to `Promise.any()` reject, what is the type of the rejection?**
**Answer:** AggregateError

---

## Question 4

**`Promise.resolve(value)` creates a fulfilled promise immediately.**
**Answer:** True
(It is fulfilled immediately, though handlers still run asynchronously.)

---

## Question 5

**Which statement correctly describes the outcome of `Promise.any()`?**
**Answer:** It resolves with the first fulfilled promise.

---

## Question 6

**Which of the following is a valid way to create a new Promise?**
**Answer:** `new Promise((resolve, reject) => { /* ... */ })`

---

## Question 7

**Uncaught rejections are automatically propagated to the nearest `catch()`.**
**Answer:** True
Rejections bubble down the promise chain until handled.

---

## Question 8

**`Promise.race()` settles with the value or reason of the first promise that settles.**
**Answer:** True

---

## Question 9

**If one element of `Promise.all()` array is not a promise, what happens?**
**Answer:** It is treated as a resolved promise with that value.

---

## Question 10

**The result array of `Promise.allSettled()` contains objects with status `fulfilled` or `rejected`.**
**Answer:** True

---

## Question 11

**What does the callback passed to `then()` receive?**
**Answer:** The resolved value of the promise.

---

## Question 12

**The callback passed to `finally()` runs before the promise is settled.**
**Answer:** False

---

## Question 13

**The rejection reason is accessible via the `reason` property in the result of `Promise.allSettled()`.**
**Answer:** True

---

## Question 14

**What happens when `Promise.all([p1, p2, p3])` is called?**
**Answer:**

* The resulting promise resolves when all input promises resolve. (this one worked as correct answer)
* The resulting promise rejects when any input promise rejects.

---

## Question 15

**Which of the following is equivalent to `Promise.reject(error)`?**
**Answer:** `async () => { throw error; }`
An async function that throws returns a rejected promise.

---

## Question 16

**What is the main use case for `Promise.race()`?**
**Answer:** To get the result of the first promise that settles.

---

## Question 17

**How can you await the resolution of multiple promises concurrently?**
**Answer:** `await Promise.all([p1, p2]);`

---

## Question 18

**When a Promise is resolved, its onFulfilled callback is called asynchronously (after the current call stack).**
**Answer:** True

---

## Question 19

**If one promise in `Promise.any()` resolves, the returned promise resolves immediately.**
**Answer:** True

---

## Question 20

**If an array passed to `Promise.all()` contains a non-Promise value, it is treated as a resolved promise.**
**Answer:** True

---

# Promise Practice Questions – Answers (Set 3 – New Questions Only)

(Repeated questions from previous sets have been omitted.)

---

## Question 2

**Which of the following properties is present in each result object returned by `Promise.allSettled()`?**
Options: status, reason, value, error
**Answer:** status
Every result object always contains a `status` property (`"fulfilled"` or `"rejected"`).

* `value` exists only if fulfilled
* `reason` exists only if rejected

---

## Question 3

**If any promise in `Promise.all()` resolves to another promise, `Promise.all()` flattens it automatically.**
**Answer:** True
If a promise resolves to another promise (a "thenable"), `Promise.all()` waits for that inner promise to resolve before continuing. This behavior is part of promise resolution and is sometimes referred to as promise flattening.

---

End of Answers (Set 3 – New Material Only)
