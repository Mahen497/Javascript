A **callback function** is a function that is **passed as an argument** to another function and is **executed later**, usually after a specific task is completed.

---

### 📌 **Why Use Callback Functions?**
1. **Asynchronous operations** – Handle tasks like fetching data, reading files, or making API calls.  
2. **Code reusability** – Pass different functions to customize behavior.  
3. **Event handling** – React to user actions like clicks or keypresses.  

---

### 📊 **Basic Example of a Callback Function**
```javascript
// A function that takes a callback
function greet(name, callback) {
  console.log("Hello, " + name);
  callback(); // Execute the callback function
}

// Callback function
function sayGoodbye() {
  console.log("Goodbye!");
}

// Call with the callback
greet("Alice", sayGoodbye);
```

👉 **Output:**  
```
Hello, Alice  
Goodbye!
```

---

### 📌 **Callbacks in Asynchronous Code (e.g., `setTimeout`)**
```javascript
setTimeout(function() {
  console.log("This runs after 2 seconds!");
}, 2000);
```

👉 **Explanation:**  
- `setTimeout` takes a **function** (callback) and a **delay** (in milliseconds).  
- The callback is executed **after** the delay.

---

### 📌 **Example: Callback in Array Methods**
```javascript
const numbers = [1, 2, 3, 4];

// Using a callback with forEach
numbers.forEach(function(number) {
  console.log(number * 2);
});
```

👉 **Output:**  
```
2  
4  
6  
8
```

---

### 📌 **Named vs. Anonymous Callbacks**
1. **Anonymous Function (Inline Callback)**  
   ```javascript
   numbers.forEach(function(num) {
     console.log(num);
   });
   ```

2. **Named Function (Reusable Callback)**  
   ```javascript
   function print(num) {
     console.log(num);
   }
   numbers.forEach(print);
   ```

---

### 📌 **When to Use Callback Functions?**
- **Handling asynchronous tasks** – API calls, file reading, timers.  
- **Event listeners** – Clicks, form submissions.  
- **Customizable functions** – Allow behavior to be adjusted.  

Would you like more examples or dive into **promises** and **async/await**? 🚀