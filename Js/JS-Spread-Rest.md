### 📌 **Spread (`...`) vs. Rest (`...`) in JavaScript**

Both the **spread** and **rest** operators use the **three dots (`...`)** syntax, but their **purpose** and **behavior** are different. Here’s a clear breakdown:

---

### 🔥 **1. Spread Operator (`...`)**
The **spread** operator is used to **expand** or **unpack** elements from **arrays**, **objects**, or **iterables**.

#### ✅ **Use Cases of Spread:**

1. **Copying Arrays** (Avoiding mutations):
```javascript
const arr1 = [1, 2, 3];
const arr2 = [...arr1]; // Creates a new array
console.log(arr2); // [1, 2, 3]
```

2. **Merging Arrays**:
```javascript
const fruits = ["apple", "banana"];
const veggies = ["carrot", "spinach"];
const food = [...fruits, ...veggies];
console.log(food); // ["apple", "banana", "carrot", "spinach"]
```

3. **Spreading in Function Arguments**:
```javascript
function sum(a, b, c) {
  return a + b + c;
}
const nums = [1, 2, 3];
console.log(sum(...nums)); // 6
```

4. **Copying/Merging Objects**:
```javascript
const user = { name: "Alice", age: 25 };
const updatedUser = { ...user, location: "NYC" };
console.log(updatedUser); // { name: "Alice", age: 25, location: "NYC" }
```

---

### 🔥 **2. Rest Parameter (`...`)**
The **rest** operator is used to **collect** multiple elements into a **single array**.

#### ✅ **Use Cases of Rest:**

1. **Handling Variable Function Arguments**:
```javascript
function addNumbers(...nums) {
  return nums.reduce((sum, num) => sum + num, 0);
}
console.log(addNumbers(1, 2, 3, 4)); // 10
```

2. **Destructuring Arrays**:
```javascript
const [first, second, ...rest] = [1, 2, 3, 4, 5];
console.log(first); // 1
console.log(second); // 2
console.log(rest); // [3, 4, 5]
```

3. **Destructuring Objects**:
```javascript
const person = { name: "John", age: 30, city: "LA" };
const { name, ...otherDetails } = person;
console.log(name); // "John"
console.log(otherDetails); // { age: 30, city: "LA" }
```

---

### 📊 **Key Differences Between Spread & Rest:**

| Feature              | Spread (`...`)                         | Rest (`...`)                       |
|----------------------|----------------------------------------|------------------------------------|
| **Purpose**          | **Expands/Unpacks** items               | **Collects/Groups** items          |
| **Usage**            | Arrays, Objects, Function Calls         | Function Parameters, Destructuring |
| **Function Context** | Passes multiple arguments to functions  | Gathers multiple arguments as an array |
| **Example**          | `const copy = [...arr];`                | `function(...args) {}`             |

---

### 🎯 **Quick Rule to Remember:**
- **Spread** is for **expanding** (unpacking values).  
- **Rest** is for **gathering** (packing values together).

Would you like examples of **advanced use cases** or **common mistakes**? 😊