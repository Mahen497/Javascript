## ⚡ JavaScript Quick Memory Sheet

---

### ➕➖ Operators

**🧠 Trick:**

> **“Plus makes friends, Minus does maths”**

* `+`

  * If any operand is a string → does **string concatenation**
  * Else → does **numeric addition**

* `-` `*` `/` `%`

  * Always try **numeric conversion** first

**Example:**

```js
10 + "20"   // "1020" (string)
10 - "20"   // -10    (number)
```

---

### ‼️ Double NOT (`!!`)

**🧠 Meaning:**

> `!!` acts like a **Truth Scanner** 🔍

* Converts any value to **boolean**
* `!!value → true` if value is **truthy**
* `!!value → false` if value is **falsy**

**Falsy values only:**

> `0, "", null, undefined, NaN, false`
> 🧘‍♂️ Remember: **“ZEN-NF”**

**Examples:**

```js
!!0        // false
!!1        // true
!!""       // false
!!"Hello"  // true
!![]       // true
!!{}       // true
!!NaN      // false
```

**Mini Practice:**

```js
!!"0"       // true
!!"false"   // true
!![]        // true
!!{}        // true
!!NaN       // false
```

---

### 🧮 `typeof`

**⚡ Key Points:**

* `typeof functionName` → `"function"`
* `typeof functionName()` → gives the **type of return value**

**Example:**

```js
function test() {}
typeof test       // "function"
typeof test()     // "undefined" (because it returns nothing)
```

---

### 🧐 Nullish Coalescing (`??`)

**🧠 Trick:**

> `??` = only cares about **null or undefined**
> `||` = cares about **all falsy values**

**Examples:**

```js
null ?? "default"       // "default"
undefined ?? "default"  // "default"
0 ?? 100                 // 0
0 || 100                 // 100

console.log(0 || 100);  // 100   (because 0 is falsy)
console.log(0 ?? 100);  // 0     (because 0 is not null/undefined)
```

---

✅ With this small cheat sheet you can quickly remember:

* `+` vs `-`
* `!!` truth scanner
* All falsy values (ZEN-NF)
* `typeof`
* `??` vs `||`

---

## ⚡ Rule Recap - Logical Operators

* `&&` (AND):

  * if **1st is falsy → returns 1st**
  * if **1st is truthy → returns 2nd**

  * true && true; // returns true
  * true && false;// returns false
  * false && true; // returns false
  * false && false; // returns false

  * 0 && 10; // returns 0
  * 10 && 20; // returns 20 
  * 20 && 0; // returns 0

* How && works in JS:

  * If left side is true, it returns right side.
  * If left side is false, it returns false (renders nothing).

* `||` (OR):

  * if **1st is falsy → returns 2nd**
  * if **1st is truthy → returns 1st**

📌 Falsy values: `0, "", null, undefined, NaN, false`


## 📝 Example 1

```js
null || 10 || false
```

* `null` → falsy → move to next
* `10` → truthy → **stop here, return it**
  ✅ Output: `10`

---

## 📝 Example 2

```js
false || null || undefined
```

* `false` → falsy
* `null` → falsy
* `undefined` → falsy (last one)
* All are falsy → returns **last one**

✅ Output: `undefined`

---

## ⚡ Memory Trick

> `||` stops at the **first truthy** value,
> or gives the **last falsy** if nothing truthy exists.

# <><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><>

  Got it 👍 Let’s break down **JavaScript Promise Chaining** in the simplest way.

---

# 🔗 JavaScript – Promise Chaining

### ✅ What is it?

Promise chaining means using **`.then()` one after another**, where the **output of one Promise becomes the input of the next**.



# ----------------- 24/09/2025 -----------------
---

## 🔑 break down Promise.all vs Promise.allSettled in an interview-ready way.

* **`Promise.all`** → resolves only if all succeed; rejects on the first failure.
* **`Promise.allSettled`** → waits for all, and always resolves with an array of result statuses.

* **`Promise.allSettled` → "tell me everything"
* **`Promise.race` → "first to finish wins, good or bad"
* **`Promise.any` → "first success wins"

---


## 🔹 What is `setInterval`?

* A **JavaScript timer function**.
* Executes a given function **repeatedly** after a fixed time interval (in milliseconds).
* Keeps running until you **stop it** using `clearInterval`.

---

✅ Quick Mnemonic:

* `setTimeout` → "Do it **later** once"
* `setInterval` → "Do it **again and again** until told to stop"

---

# <><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><>


### **1. Cookies**

* **Part of the browser storage mechanism**.
* **Stores data in key–value pairs**.
* **Persistent or temporary:** can have expiry date; session cookies are deleted when the browser closes.
* **Storage limit:** \~4 KB per cookie.
* **Sent to server automatically** with every HTTP request (unlike LocalStorage/SessionStorage).
* **Accessible via JavaScript** unless marked `HttpOnly`.
* **Use Case:** Session management, authentication, user preferences, tracking.

---

### **2. LocalStorage**

* **Part of the Web Storage API.**
* **Stores data in key–value pairs** in the browser.
* **Persistent:** data remains even after closing and reopening the browser.
* **Storage limit:** \~5–10 MB per domain.
* **Data not sent to server automatically**.
* **Accessible via JavaScript.**
* **Use Case:** Storing large non-sensitive data like preferences, caching, offline storage.

---

### **3. SessionStorage**

* **Part of the Web Storage API.**
* **Stores data in key–value pairs** in the browser.
* **Temporary:** data is cleared when the browser tab closes.
* **Storage limit:** \~5–10 MB per domain.
* **Data not sent to server automatically.**
* **Accessible via JavaScript.**
* **Use Case:** Tab-specific or temporary session data, forms, wizards.

---

💡 **Quick Comparison Table**

| Feature        | Cookies             | LocalStorage       | SessionStorage    |
| -------------- | ------------------- | ------------------ | ----------------- |
| Size Limit     | \~4 KB              | \~5–10 MB          | \~5–10 MB         |
| Lifetime       | Expiry date         | Persistent         | Tab closes        |
| Sent to Server | ✅                   | ❌                  | ❌                 |
| JS Accessible  | ✅ (unless HttpOnly) | ✅                  | ✅                 |
| Use Case       | Session, auth       | Preferences, cache | Tab-specific data |

---

💡 **Mnemonic to remember BOM objects:**
```js
Window, Navigator, Screen, Location, History, Alert, Timer → WNSLHT
```


# ----------------- 25/09/2025 -----------------


Here’s a **quick interview-style definition** of each:

### 🔹 `Object.assign(target, ...sources)`

To copy properties and their values from one object to another object.


```js
const obj1 = {a:1}, obj2 = {b:2};
const result = Object.assign({}, obj1, obj2);
console.log(result); // {a:1, b:2}
```

---

### 🔹 `Object.entries(obj)`

Returns an **array of `[key, value]` pairs** from the object.

```js
const user = {id:1, name:"Mahendra"};
console.log(Object.entries(user)); 
// [["id",1], ["name","Mahendra"]]
```
---

### 🔹 `Object.values(obj)`

To get all **values of the object** in the array format.

```js
const user = {id:1, name:"Mahendra"};
console.log(Object.values(user)); 
// [1, "Mahendra"]
```
---

### 🔹 `Object.seal(obj)`

To get all **values of the object** in the array format.
To seal the object.

```js
const user = {id:1, name:"Mahendra"};
console.log(Object.values(user)); 
// [1, "Mahendra"]
```
# <><><><><><><><><><><><><><><><><><><><><><><><><><><><><><>

### 🔹 `keyup`
- Fires **when a key is released**.  
- Useful for **final values** (like in search inputs).  

### 🔹 `keydown`
- Fires **when a key is pressed down**.  
- Triggered for **all keys** (letters, numbers, function keys, Ctrl, Shift, etc.).  
- Fires **continuously if the key is held down**.  

# <><><><><><><><><><><><><><><><><><><><><><><><><><><><><><>

### 🔹 `event.preventDefault()`
```markdown
- This method **prevents the default action** associated with an event,  
  such as navigating to a link or submitting a form.
```
# <><><><><><><><><><><><><><><><><><><><><><><><><><><><><><>

# ----------------- 26/09/2025 -----------------

### ✅ Ways to Create an Empty Array in JavaScript

1. **Square brackets (preferred):**

   ```js
   let arr = [];
   ```
2. **Constructor:**

   ```js
   let arr = new Array(); // []
   let arr = new Array(5); // [ <5 empty items> ] ⚠️ not truly empty
   ```
3. **Array.of():**

   ```js
   let arr = Array.of();
   ```

👉 **Best practice:** use `[]` (clean & clear).

---

# <><><><><><><><><><><><><><><><><><><><><><><><><><><><><><>

# ----------------- 27/09/2025 -----------------

## **JavaScript Animation – Quick Review**

  **`requestAnimationFrame(callback)`**

  * Schedules `callback` to run **before next browser repaint**.
  * Used for **smooth DOM animations**.

  **`cancelAnimationFrame(id)`**

  * Stops a scheduled animation.

  **Example:**

  ```javascript
  let pos = 0;
  function animate() {
    if(pos < 350) {
      pos++;
      elem.style.left = pos + 'px';
      requestAnimationFrame(animate);
    }
  }
  requestAnimationFrame(animate);
  ```

  **Advantages over setInterval/setTimeout:**

  * Syncs with browser refresh → **smoother** (~60fps)
  * **Stops in inactive tabs** → more efficient
  * Better **timing accuracy**

---

# ----------------- 29/09/2025 -----------------

Perfect! Here’s a **ready-to-say 1-minute interview answer** for your `sendAutoEmail` example, explained clearly and simply:

---

### 🗣️ Spoken Answer (1 Minute)

*"This code is an example of **currying** and **closure** in JavaScript.

Currying means breaking a function into smaller functions that each take one argument at a time. Closure means that an inner function remembers variables from its outer function even after the outer function has finished executing.

In this example, `sendAutoEmail` is curried:

* First, I provide the recipient email — this returns a function waiting for the subject.
* Then I provide the subject — this returns a function waiting for the body.
* Finally, I provide the body, and the function prints the complete email with all the information.

Each step remembers the previous information because of closure.

A simple analogy is writing a letter: first you write the recipient, then the subject, then the message — each step remembers what you wrote earlier.

This approach is useful in real life when some data is available early and other data comes later, like sending emails, logging messages, or configuring APIs."*

---

💡 **Tip:**

* Speak slowly, highlight **currying** and **closure** clearly.
* You can optionally give a **one-line output example**:



