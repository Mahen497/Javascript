Interview Question - 1
Great question 😃 This is a **classic JavaScript gotcha**! Let’s break it down step by step.

---

### 🔹 Code:

```js
console.log([] === []); // ?
console.log([] == []);  // ?
```

---

### 🔹 Explanation

1. In JavaScript, **arrays are objects**.
   When you create `[]`, it makes a **new object in memory**.

   ```js
   [] === []  
   ```

   👉 This compares **two different objects (different memory addresses)**.
   ✅ Result → `false`

---

2. Even with `==` (loose equality), JavaScript **doesn’t compare contents** of objects/arrays.
   It still checks if both references point to the **same object**.

   ```js
   [] == []  
   ```

   👉 Still two different objects.
   ✅ Result → `false`

---

### 🔹 Example to prove this

```js
let a = [];
let b = a;

console.log(a === b); // true (both point to same object)
```

But:

```js
let a = [];
let b = [];

console.log(a === b); // false (different objects)
```

---

### ✅ Key Takeaway

* `===` → compares **reference (memory address)** for objects/arrays.
* `==` → same behavior for objects/arrays (no deep comparison).
* To compare arrays by value, you need to **check their elements** manually or use helpers like:

```js
function arraysEqual(a, b) {
  return a.length === b.length && a.every((val, i) => val === b[i]);
}

console.log(arraysEqual([1,2], [1,2])); // true
console.log(arraysEqual([1,2], [2,1])); // false
```

--------------------------------------------------------
--------------------------------------------------------

Sure! Let’s break this step by step and explain why each method (`split`, `reverse`, `join`) is used, and what’s happening in your code.

---

### **Your code:**

```js
const revs = 'i am Mahendra';
const rs = revs.split(" ").reverse().join(" ");
console.log('fn:', rs);
```

---

### **Step 1: `split()`**

* **Purpose:** Convert a string into an **array** of smaller strings based on a separator.
* In your code:

```js
revs.split(" ")
```

* `" "` (space) is used as the separator.
* Original string: `'i am Mahendra'`
* After `split(" ")` → `['i', 'am', 'Mahendra']`

✅ Now we have an **array of words**, not a string.

---

### **Step 2: `reverse()`**

* **Purpose:** Reverse the **order of elements** in an array.
* Your array after `split`:

```js
['i', 'am', 'Mahendra']
```

* After `.reverse()` → `['Mahendra', 'am', 'i']`

✅ The array is reversed **word by word**.

---

### **Step 3: `join()`**

* **Purpose:** Convert an array **back into a string**, using a separator.
* Your code:

```js
.join(" ")
```

* Joins the reversed array using **space** between words.
* Resulting string: `'Mahendra am i'`

---

### **Step 4: `console.log` output**

```js
console.log('fn:', rs);
```

**Output:**

```
fn: Mahendra am i
```

---

### ✅ Summary of why methods are used:

| Method      | Why used here                                    |
| ----------- | ------------------------------------------------ |
| `split()`   | To break the string into an array of words       |
| `reverse()` | To reverse the order of words                    |
| `join()`    | To combine the reversed array back into a string |

---

### **Step 5: Function to reverse a string**

You can make a reusable function:

```js
function reverseString(str) {
  return str.split(" ").reverse().join(" ");
}

console.log(reverseString('i am Mahendra')); // Mahendra am i
```

* `str.split(" ")` → array of words
* `.reverse()` → reverse array
* `.join(" ")` → back to string

--------------------------------------------------------
--------------------------------------------------------

Ah! You want to **check if two arrays have the same elements**, not just if they point to the same reference. In JavaScript, `arr1 === arr2` **won’t work** because arrays are objects, and object equality checks **reference**, not content.

Here are some ways to check:

---

### **1️⃣ Using `every()` method**

```js
let arr1 = [100, 200, 300];
let arr2 = [100, 200, 300];

const isEqual = arr1.length === arr2.length && arr1.every((val, i) => val === arr2[i]);

console.log(isEqual); // true
```

**Explanation:**

* `arr1.length === arr2.length` ensures both arrays are the same size.
* `.every((val, i) => val === arr2[i])` checks each element one by one.

---

### **2️⃣ Using `JSON.stringify()`**

```js
const isEqual = JSON.stringify(arr1) === JSON.stringify(arr2);
console.log(isEqual); // true
```

**Explanation:**

* Converts arrays into strings and compares the string.
* Simple but only works for arrays with **primitive values**.

---

### **3️⃣ Using a loop (manual way)**

```js
let isEqual = true;
if(arr1.length === arr2.length){
  for(let i=0; i<arr1.length; i++){
    if(arr1[i] !== arr2[i]){
      isEqual = false;
      break;
    }
  }
} else {
  isEqual = false;
}
console.log(isEqual); // true
```

**Explanation:** Checks each element manually.

---

✅ **Key point:** `[] === []` or `[100,200] === [100,200]` **always returns false** because they are different objects in memory.


--------------------------------------------------------
--------------------------------------------------------

To convert a **JavaScript object** into a **string**, you use `JSON.stringify()`.

### Example:

```js
const obj = {
  name: "Mahendra",
  age: 30,
  city: "Gujarat"
};

// Convert object to string
const objString = JSON.stringify(obj);

console.log(objString);
console.log(typeof objString);
```

**Output:**

```
{"name":"Mahendra","age":30,"city":"Gujarat"}
"string"
```

---

### **Explanation**

1. `JSON.stringify(obj)` → Converts a JS object into **JSON string format**.
2. The result can be stored, sent over network, or saved in localStorage.
3. Nested objects or arrays also get converted.

---

### **Optional: Pretty print**

You can make it more readable by adding indentation:

```js
const prettyString = JSON.stringify(obj, null, 2);
console.log(prettyString);
```

**Output:**

```json
{
  "name": "Mahendra",
  "age": 30,
  "city": "Gujarat"
}
```

--------------------------------------------------------
--------------------------------------------------------

Perfect! To **convert a string back into a JavaScript object**, you use `JSON.parse()`.

### Example:

```js
const objString = '{"name":"Mahendra","age":30,"city":"Gujarat"}';

// Convert string back to object
const obj = JSON.parse(objString);

console.log(obj);
console.log(typeof obj);
console.log(obj.name); // Access property
```

**Output:**

```
{ name: 'Mahendra', age: 30, city: 'Gujarat' }
"object"
Mahendra
```

---

### **Explanation**

1. `JSON.parse(objString)` → Converts a **JSON string** into a **JS object**.
2. Once converted, you can access its properties like a normal object (`obj.name`, `obj.age`).
3. Make sure the string is **valid JSON**, otherwise it will throw an error.

---

✅ **Tip:**

* `JSON.stringify()` → object → string
* `JSON.parse()` → string → object

This is very useful when storing objects in **localStorage**:

```js
localStorage.setItem("user", JSON.stringify(obj));
const storedUser = JSON.parse(localStorage.getItem("user"));
console.log(storedUser.name);
```

--------------------------------------------------------
--------------------------------------------------------

Ah! This is a **classic JavaScript type coercion case**. Let’s break it down step by step.

---

### Code:

```js
console.log(null == undefined);
```

### Output:

```
true
```

---

### **Explanation**

1. The `==` operator in JavaScript is the **loose equality operator**, meaning it does **type coercion** if the types are different.
2. `null` represents **“no value”** or **empty value**.
3. `undefined` represents a variable that has **been declared but not assigned a value**.
4. In JavaScript, the specification explicitly says:

> `null == undefined` → `true`

This is the **only case** where `==` returns true for **different types** without explicit conversion.

---

### Important Note:

* `null === undefined` → `false` ✅
  Because `===` is **strict equality**, which **does not do type coercion**. Types must match.

```js
console.log(null === undefined); // false
```

---

✅ **Summary Table for Loose Equality (`==`)**:

| Expression          | Result | Reason                             |
| ------------------- | ------ | ---------------------------------- |
| `null == undefined` | true   | Special JS rule                    |
| `null == 0`         | false  | No coercion with numbers           |
| `undefined == 0`    | false  | Same as above                      |
| `0 == "0"`          | true   | String `"0"` coerced to number `0` |


--------------------------------------------------------
--------------------------------------------------------

Here’s a short version to create an array of size 100:

```js
// 1. Empty array of size 100
let arr1 = new Array(100);

// 2. Array of 100 undefined elements
let arr2 = Array.from({ length: 100 });

// 3. Array of 100 elements filled with 0
let arr3 = new Array(100).fill(0);

// 4. Array of numbers 1 to 100
let arr4 = Array.from({ length: 100 }, (_, i) => i + 1);
```

* `arr1` → empty slots
* `arr2` → undefined values
* `arr3` → all 0
* `arr4` → 1 to 100

This is the concise way to create arrays of specific size.


--------------------------------------------------------
--------------------------------------------------------

It seems you meant **`Object.freeze()`** in JavaScript. Here's a clear explanation:

---

### **`Object.freeze(obj)`**

* **Purpose:** Prevents modifications to an object.
* Once an object is frozen:

  1. You **cannot add new properties**.
  2. You **cannot delete existing properties**.
  3. You **cannot modify property values**.
* However, **nested objects are not frozen** unless you recursively freeze them.

---

### **Example:**

```js
const user = {
  name: "Mahendra",
  age: 30
};

Object.freeze(user);

user.name = "Amit"; // ❌ won't change
user.city = "Ahmedabad"; // ❌ won't add
delete user.age; // ❌ won't delete

console.log(user);
// Output: { name: "Mahendra", age: 30 }
```

---

### **Important Notes:**

* `Object.freeze()` only works on **objects**, not on primitive values.
* To make nested objects immutable, you need to **deep freeze**.


--------------------------------------------------------
--------------------------------------------------------

Ah! This is a classic **object reference problem** in JavaScript.

Right now:

```js
const a = { age: 23 };
const b = a;  // b points to the same object as a
b.age = 100;

console.log(a.age); // 100
console.log(b.age); // 100
```

✅ **Why:** Objects are **reference types**, so `b = a` does **not** create a new object. Both `a` and `b` point to the same memory location.

---

### **How to make `a` and `b` independent objects**

#### **1. Using Object.assign**

```js
const a = { age: 23 };
const b = Object.assign({}, a); // shallow copy

b.age = 100;

console.log(a.age); // 23
console.log(b.age); // 100
```

#### **2. Using Spread Operator**

```js
const a = { age: 23 };
const b = { ...a }; // shallow copy

b.age = 100;

console.log(a.age); // 23
console.log(b.age); // 100
```

#### **3. Using JSON (deep copy)**

```js
const a = { age: 23 };
const b = JSON.parse(JSON.stringify(a)); // deep copy

b.age = 100;

console.log(a.age); // 23
console.log(b.age); // 100
```

> Note: JSON method works for nested objects but fails for functions, undefined, or special objects like `Date`.


--------------------------------------------------------
--------------------------------------------------------

Perfect! For modern JavaScript, the best way to safely copy objects—including nested objects—is using **structured cloning** or libraries like **Lodash**, but we can do it natively with `structuredClone` (available in modern browsers and Node.js).

### **Example using `structuredClone`**

```js
const a = { 
  age: 23, 
  details: { city: "Mumbai", skills: ["HTML", "CSS"] } 
};

const b = structuredClone(a); // deep copy

b.age = 100;
b.details.city = "Delhi";

console.log(a.age); // 23
console.log(a.details.city); // "Mumbai"
console.log(b.age); // 100
console.log(b.details.city); // "Delhi"
```

✅ **Why this works:**

* `structuredClone` creates a **deep copy**, so nested objects are also independent.
* Any changes to `b` won’t affect `a` at all.


--------------------------------------------------------
--------------------------------------------------------

Sure! Let’s break this down **step by step** in a simple and clear way. I’ll explain **Promise chaining**, **Promises**, and the **difference between `map` and `forEach`** with examples.

---

## **1️⃣ Promises in JavaScript**

A **Promise** is an object representing the eventual completion or failure of an asynchronous operation. It has three states:

* **Pending** → initial state, not fulfilled or rejected
* **Fulfilled** → operation completed successfully
* **Rejected** → operation failed

**Basic Example:**

```js
const promise = new Promise((resolve, reject) => {
  let success = true;
  if(success){
    resolve('Task completed');
  } else {
    reject('Task failed');
  }
});

promise
  .then((result) => console.log(result))   // runs if resolved
  .catch((err) => console.log(err));      // runs if rejected
```

**Output:**

```
Task completed
```

---

## **2️⃣ Promise Chaining**

**Promise chaining** allows you to perform multiple asynchronous tasks in sequence. Each `.then()` returns a new promise, so you can chain multiple operations.

**Example:**

```js
new Promise((resolve, reject) => {
  resolve(5);
})
.then((num) => {
  console.log(num); // 5
  return num * 2;
})
.then((num) => {
  console.log(num); // 10
  return num + 3;
})
.then((num) => {
  console.log(num); // 13
});
```

* Each `.then()` gets the value returned by the previous `.then()`.
* This is cleaner than nested callbacks.

---

## **3️⃣ Arrays with `map` vs `forEach`**

### **`forEach`**

* Executes a function for **each element** of an array.
* **Does not return** anything (`undefined`).
* Usually used for **side effects** (like logging or DOM updates).

```js
let arr = [1, 2, 3];
arr.forEach((num) => {
  console.log(num * 2);
});
```

**Output:**

```
2
4
6
```

> Notice: `arr.forEach()` **does not create a new array**.

---

### **`map`**

* Executes a function for **each element** and **returns a new array**.
* Original array remains unchanged.

```js
let arr = [1, 2, 3];
let doubled = arr.map((num) => num * 2);
console.log(doubled);
```

**Output:**

```
[2, 4, 6]
```

**Key difference:**

| Feature        | `forEach`    | `map`                          |
| -------------- | ------------ | ------------------------------ |
| Returns value  | undefined    | new array                      |
| Purpose        | Side effects | Transformation                 |
| Original array | Not changed  | Not changed, returns new array |

---

## **4️⃣ Sparse Array Example**

```js
let arr = [,,,];
console.log(arr);        // [ <3 empty items> ]
console.log(arr.length); // 3
```

* `[,,,]` creates a **sparse array** of length 3.
* The positions are empty, not `undefined`.
* `forEach` **skips empty elements**, but `map` **creates new array with `undefined` for empty slots**.

```js
arr.forEach((v, i) => console.log(i)); // prints nothing
arr.map((v, i) => i);                  // [undefined, undefined, undefined]
```

---

✅ **Summary:**

* **Promises** → handle async tasks.
* **Promise chaining** → sequence async tasks.
* **forEach** → iterate, no return.
* **map** → iterate and create new array.
* Sparse arrays behave differently for `map` and `forEach`.

--------------------------------------------------------
--------------------------------------------------------

Perfect! Here’s a **full 1️⃣–5️⃣0️⃣ short guide** covering everything you’ve asked today, **copy-paste friendly**, with small examples where needed:

---

### **1️⃣ Undefined in JS**

* Variable declared but not assigned → `undefined`

```js
let a;
console.log(a); // undefined
```

### **2️⃣ null vs undefined**

* `undefined` = variable exists but no value.
* `null` = explicitly empty.

```js
let a;       // undefined
let b = null;
console.log(a == null); // true
```

### **3️⃣ Arrays Comparison**

* Arrays are **reference types** → two arrays never equal directly.

```js
console.log([] === []); // false
```

### **4️⃣ Array.every()**

* Checks all elements pass a test.

```js
let a=[1,2], b=[1,2];
console.log(a.every((v,i)=>v===b[i])); // true
```

### **5️⃣ Reverse String**

```js
let s = "hello";
console.log(s.split("").reverse().join("")); // olleh
```

### **6️⃣ split() method**

* Splits string into array by separator.

```js
"i am".split(" "); // ["i", "am"]
```

### **7️⃣ join() method**

* Joins array into string.

```js
["i","am"].join(" "); // "i am"
```

### **8️⃣ Comparing Arrays**

* To check arrays content equality, use `every()`.

```js
arr1=[1,2]; arr2=[1,2];
arr1.every((v,i)=>v===arr2[i]); // true
```

### **9️⃣ JSON to String**

* Use `JSON.stringify()`.

```js
JSON.stringify({a:1}); // '{"a":1}'
```

### **🔟 JSON to Object**

* Use `JSON.parse()`.

```js
JSON.parse('{"a":1}'); // {a:1}
```

### **1️⃣1️⃣ null == undefined**

* True because both represent “no value” loosely.

```js
null == undefined; // true
```

### **1️⃣2️⃣ Create array of size 100**

```js
let arr = new Array(100);
```

### **1️⃣3️⃣ Object.freeze()**

* Makes object **immutable**.

```js
const obj={a:1}; Object.freeze(obj);
obj.a=10; // won't change
```

### **1️⃣4️⃣ Copy object without reference**

* Use **spread operator**.

```js
let a={x:1}, b={...a};
b.x=100;
console.log(a.x); // 1
```

### **1️⃣5️⃣ em vs i**

* `<em>` = emphasis (semantic)
* `<i>` = italic (styling)

### **1️⃣6️⃣ strong vs b**

* `<strong>` = important text (semantic)
* `<b>` = bold (styling only)

### **1️⃣7️⃣ progress & meter**

```html
<progress value="30" max="100"></progress>
<meter value="0.6">60%</meter>
```

### **1️⃣8️⃣ Empty/self-closing elements**

* `<br>`, `<img>`, `<input>` → no closing tag needed.

### **1️⃣9️⃣ Marquee tag**

* Scrolls text.

```html
<marquee scrollamount="10">Hello</marquee>
```

### **2️⃣0️⃣ Description list in CSS**

```html
<dl><dt>Term</dt><dd>Definition</dd></dl>
```

### **2️⃣1️⃣ Text shadow**

```css
text-shadow: 2px 2px 4px #000;
```

### **2️⃣2️⃣ Image reflection**

* CSS reflection: `-webkit-box-reflect`.

### **2️⃣3️⃣ CSS box model**

* Content → padding → border → margin

### **2️⃣4️⃣ Map vs forEach**

* `map` returns new array, `forEach` returns undefined.

```js
[1,2].map(n=>n*2); // [2,4]
[1,2].forEach(n=>n*2); // undefined
```

### **2️⃣5️⃣ Promise chaining**

```js
Promise.resolve(1)
  .then(x=>x+1)
  .then(x=>console.log(x)); // 2
```

### **2️⃣6️⃣ Closures**

* Function remembering outer scope.

```js
function outer(){ let a=1; return ()=>a; }
let f = outer();
console.log(f()); // 1
```

### **2️⃣7️⃣ Mouse move custom cursor**

```js
document.addEventListener('mousemove', e=>{
  cursor.style.top=e.clientY+'px';
  cursor.style.left=e.clientX+'px';
});
```

### **2️⃣8️⃣ Cursor hover effect**

* Change size on hover using `mouseover`/`mouseleave`.

### **2️⃣9️⃣ Mouse wheel scroll slider**

```js
document.addEventListener('wheel', e=>{
  if(e.deltaY>0) moveNext(); else movePrev();
});
```

### **3️⃣0️⃣ Touch swipe for mobile slider**

```js
slider.addEventListener('touchstart', e=>touchStart=e.touches[0].clientX);
slider.addEventListener('touchend', e=>{ if(touchEnd<touchStart) moveNext(); });
```

### **3️⃣1️⃣ CSS vh issue in mobile**

* Use `--vh` to fix viewport height problem.

### **3️⃣2️⃣ JS random number**

```js
Math.floor(Math.random()*(10-5+1))+5;
```

### **3️⃣3️⃣ Array equality check**

* Use `every` or `JSON.stringify`.

### **3️⃣4️⃣ Assign new array**

```js
let arr = Array(100).fill(0);
```

### **3️⃣5️⃣ Reversing words**

```js
"i am me".split(" ").reverse().join(" "); // "me am i"
```

### **3️⃣6️⃣ Difference map vs forEach**

* `map` → new array, `forEach` → undefined.

### **3️⃣7️⃣ `undefined` vs `null` comparison**

* `undefined==null` → true
* `undefined===null` → false

### **3️⃣8️⃣ Object.assign vs spread**

* Copy object without reference.

### **3️⃣9️⃣ Promise chaining example**

```js
Promise.resolve(1).then(x=>x+1).then(x=>x*2); // 4
```

### **4️⃣0️⃣ Self closing tags**

* `<img>`, `<input>`, `<br>`

### **4️⃣1️⃣ HTML vertical banner text**

* Use `position:absolute; top:50%; transform:translateY(-50%)`

### **4️⃣2️⃣ Section with 3 blocks**

* Use `flex` or `grid`, each block: image + heading + text.

### **4️⃣3️⃣ Split section left & right**

* Right → image, left → heading + paragraph

```css
display:flex;
```

### **4️⃣4️⃣ Responsive design**

* Use `%`, `vw`, `vh`, media queries

### **4️⃣5️⃣ Optimize website**

* Minify CSS/JS, optimize images, lazy load images, use proper semantic tags

### **4️⃣6️⃣ Console.log(\[]==\[])**

* false → different object references

### **4️⃣7️⃣ Object.freeze example**

```js
const a={x:1}; Object.freeze(a); a.x=2; // a.x still 1
```

### **4️⃣8️⃣ Cursor random size on hover**

* Change cursor width & height using JS `Math.random()`

### **4️⃣9️⃣ JS closure example**

* Function remembers outer variable even after outer scope finished

### **5️⃣0️⃣ Convert JSON to string & back**

```js
let obj={a:1}; let str=JSON.stringify(obj);
let newObj=JSON.parse(str);
```

--------------------------------------------------------
--------------------------------------------------------


