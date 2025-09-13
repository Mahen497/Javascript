## 🔹 What is `undefined` in JavaScript?

* `undefined` is a **special primitive value** in JavaScript.
* It simply means: **“no value has been assigned yet.”**

---

## 🔹 When do we get `undefined`?

1. **Variable declared but not assigned**

   ```js
   let name;
   console.log(name); // undefined
   ```

2. **Function without a return value**

   ```js
   function sayHello() {
     console.log("Hello");
   }
   let result = sayHello();
   console.log(result); // undefined (no return)
   ```

3. **Accessing a property that doesn’t exist**

   ```js
   let person = { name: "Amit" };
   console.log(person.age); // undefined (age not defined)
   ```

4. **Array element not present**

   ```js
   let arr = [10, 20];
   console.log(arr[5]); // undefined
   ```

5. **Function parameter not passed**

   ```js
   function greet(msg) {
     console.log(msg);
   }
   greet(); // undefined (no argument passed)
   ```

---

## 🔹 Difference between `null` and `undefined`

* `undefined` → JS itself gives this when something is not assigned.
* `null` → You explicitly set it when you want to say **“no value.”**

```js
let a;
console.log(a); // undefined (not assigned)

let b = null;
console.log(b); // null (assigned intentionally)
```

---

👉 Think of `undefined` as **“JavaScript hasn’t filled it yet.”**
👉 Think of `null` as **“I have emptied it myself.”**

---

Do you want me to also show you **real-world mistakes where `undefined` causes bugs** (like in APIs or forms) and how to avoid them?
