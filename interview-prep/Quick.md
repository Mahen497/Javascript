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
```

---

✅ With this small cheat sheet you can quickly remember:

* `+` vs `-`
* `!!` truth scanner
* All falsy values (ZEN-NF)
* `typeof`
* `??` vs `||`

---

## ⚡ Rule Recap

* `&&` (AND):

  * if **1st is falsy → returns 1st**
  * if **1st is truthy → returns 2nd**

* `||` (OR):

  * if **1st is truthy → returns 1st**
  * if **1st is falsy → returns 2nd**

📌 Falsy values: `0, "", null, undefined, NaN, false`

