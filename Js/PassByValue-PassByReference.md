### 📌 **Pass by Value vs. Pass by Reference in JavaScript**  

In JavaScript, **how data is passed** depends on whether it's a **primitive** or **non-primitive** type. Let’s break down the key differences with examples and common mistakes.

---

## ✅ **1. What is Pass by Value?**
When you pass a variable **by value**, a **copy** of the variable’s value is sent. Changes inside the function **do not** affect the original value.

### 🟢 **Example (Pass by Value – Primitives)**

```javascript
let a = 10;

function updateValue(x) {
  x = 20;  // Modifies the local copy
  console.log("Inside:", x); // 20
}

updateValue(a);
console.log("Outside:", a); // 10 (Original remains unchanged)
```

**Primitive types** (passed by **value**) in JavaScript:
- `Number`
- `String`
- `Boolean`
- `Undefined`
- `Null`
- `Symbol`
- `BigInt`

---

## ✅ **2. What is Pass by Reference?**
When you pass a variable **by reference**, the **address (reference)** of the object is shared. Changes inside the function **affect the original** object.

### When you pass data to the function, obj points to the same object in memory. Any changes to obj directly modify the original object.

### 🔵 **Example (Pass by Reference – Objects)**

```javascript
let user = { name: "Alice" };

function updateUser(obj) {
  obj.name = "Bob";  // Modifies the original object
  console.log("Inside:", obj.name); // Bob
}

updateUser(user);
console.log("Outside:", user.name); // Bob (Original is modified)
```

**Non-primitive types** (passed by **reference**) in JavaScript:
- `Object`
- `Array`
- `Function`
- `Map`, `Set`, etc.

---

## 🧐 **3. Deep Dive: Why the Difference Matters**

1. **Primitives** are stored directly in **stack memory**—copies are independent.
2. **Objects** are stored in **heap memory**—the reference (address) is passed.

---

## ⚠️ **4. Common Mistakes & Gotchas**

### ❌ **Mistake 1: Expecting Objects to be Passed by Value**
```javascript
let arr = [1, 2, 3];

function modifyArray(array) {
  array.push(4);  // Modifies the original array
}

modifyArray(arr);
console.log(arr); // [1, 2, 3, 4] (Changed!)
```

✅ **Solution:** To avoid modifying the original, **clone** the object:
```javascript
function modifyArray(array) {
  const newArray = [...array]; // Create a shallow copy
  newArray.push(4);
  return newArray;
}

const newArr = modifyArray(arr);
console.log(arr);    // [1, 2, 3] (Unchanged)
console.log(newArr); // [1, 2, 3, 4]
```

---

### ❌ **Mistake 2: Reassigning a Reference Won’t Change the Original**
```javascript
let obj = { value: 42 };

function reassign(objRef) {
  objRef = { value: 99 };  // New object assignment
}

reassign(obj);
console.log(obj.value); // 42 (Original unchanged)
```

✅ **Why?** Reassigning `objRef` only changes the local **copy** of the reference.

---

## 🔍 **5. How to Force Pass by Value for Objects**
If you **don’t** want to modify the original object, use:

1. **Shallow Copy** – `Object.assign()` or the spread operator:
```javascript
let obj = { a: 1 };
let newObj = { ...obj };
newObj.a = 99;

console.log(obj.a); // 1 (Unchanged)
```

2. **Deep Copy** – Use `structuredClone()` for complex nested objects:
```javascript
let nestedObj = { a: { b: 2 } };
let deepCopy = structuredClone(nestedObj);

deepCopy.a.b = 99;
console.log(nestedObj.a.b); // 2 (Original intact)
```

---

## 📚 **6. Summary: Key Differences**

| Feature               | Pass by Value              | Pass by Reference             |
|-----------------------|----------------------------|-------------------------------|
| **Data Type**         | Primitive (Number, String) | Non-Primitive (Object, Array) |
| **Memory**            | Stack (Copy of value)      | Heap (Reference to value)     |
| **Modification**      | Original is **unchanged**  | Original **can be changed**   |
| **Example**           | `let x = 10;`             | `let obj = { key: "value" };` |
| **Performance**       | Faster (small data)        | Slower (larger objects)       |
| **Prevention**        | No need – copies are safe  | Use `structuredClone()`       |

Would you like advanced tips or examples on **deep cloning** or **performance optimizations**? 🚀