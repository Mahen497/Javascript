# **🚀 Hoisting in JavaScript (Easy Explanation)**  

## **🔹 What is Hoisting?**  
Hoisting is **JavaScript's default behavior** of **moving function and variable declarations to the top of their scope** **before execution**.  

### **Think of it as JS "lifting" the declarations to the top before running the code.**  

---

## **🔹 Example 1: Hoisting with `var`**  
```js
console.log(name);  // Output: undefined
var name = "John";
console.log(name);  // Output: John
```
### **🧐 Why is `undefined` printed first?**  
- JavaScript **moves** (hoists) `var name;` **to the top** before execution.  
- But only the **declaration** is hoisted, **not the value**.  

Internally, JS reads it as:
```js
var name;  // Declaration hoisted to the top
console.log(name); // undefined (no value yet)
name = "John";  // Now value is assigned
console.log(name); // John
```

---

## **🔹 Example 2: Hoisting with `let` and `const`**
```js
console.log(age);  // ❌ ReferenceError: Cannot access 'age' before initialization
let age = 25;
console.log(age);  // ✅ Works fine
```
### **❓ Why does `let` cause an error?**  
- `let` and `const` are **hoisted but not initialized**.
- They are stored in the **Temporal Dead Zone (TDZ)** until assigned a value.

---

## **🔹 Example 3: Hoisting with Functions**  
### **✅ Function Declarations (Hoisted)**
```js
sayHello();  // ✅ Works fine, Output: Hello!

function sayHello() {
    console.log("Hello!");
}
```
- **Function declarations** are fully hoisted, so we can call them **before** they are defined.

---

### **❌ Function Expressions (NOT Hoisted)**
```js
greet();  // ❌ TypeError: greet is not a function

var greet = function () {
    console.log("Hi!");
};
```
- `greet` is declared as `var`, so it is **hoisted as undefined**.
- When we try to call it **before assignment**, it **throws an error**.

---

## **🔹 Hoisting Summary Table**
| **Type** | **Hoisted?** | **Initialized?** | **Usable Before Declaration?** |
|----------|------------|--------------|----------------------------|
| `var` | ✅ Yes | ❌ Undefined | ⚠️ Yes, but returns `undefined` |
| `let` | ✅ Yes | ❌ No (TDZ) | ❌ No (ReferenceError) |
| `const` | ✅ Yes | ❌ No (TDZ) | ❌ No (ReferenceError) |
| Function Declaration | ✅ Yes | ✅ Yes | ✅ Yes (Can call before definition) |
| Function Expression (`var`) | ✅ Yes | ❌ Undefined | ❌ No (TypeError) |

---

## **🎯 Key Takeaways**
✔ **JavaScript moves function and variable declarations to the top before execution**.  
✔ `var` is hoisted **but initialized as `undefined`**.  
✔ `let` and `const` are hoisted **but stay in the "Temporal Dead Zone" (TDZ)**.  
✔ Function **declarations are fully hoisted**, but function **expressions are not**.

### **🚀 Best Practice:**  
👉 **Always declare variables at the top** to avoid confusion.  
👉 **Use `let` and `const` instead of `var`** to prevent unintended hoisting issues.  

---

Hope this makes hoisting super easy! 😊 Let me know if you need more examples. 🚀