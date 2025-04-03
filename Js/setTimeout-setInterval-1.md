## **⏳ `setTimeout()` vs `setInterval()` in JavaScript**
Both `setTimeout()` and `setInterval()` are used to schedule code execution **after a delay** in JavaScript, but they work differently.

---

## **🔹 1. `setTimeout()` - Run Code After a Delay**
- Runs **only once** after a given time.
- **Syntax**:
  ```js
  setTimeout(callback, delay);
  ```
- **Example:**
  ```js
  setTimeout(() => {
      console.log("Hello after 2 seconds!");
  }, 2000);
  ```
  - After **2 seconds**, `"Hello after 2 seconds!"` is logged.
  - It runs **only once**.

---

## **🔹 2. `setInterval()` - Repeat Code Every Interval**
- Runs **repeatedly** at a fixed interval.
- **Syntax**:
  ```js
  setInterval(callback, interval);
  ```
- **Example:**
  ```js
  setInterval(() => {
      console.log("Hello every 3 seconds!");
  }, 3000);
  ```
  - Logs `"Hello every 3 seconds!"` **every** 3 seconds **forever**.

---

## **🔹 3. Stopping `setTimeout()` and `setInterval()`**
### **✅ `clearTimeout()` - Cancel a Scheduled `setTimeout()`**
```js
let timeoutID = setTimeout(() => {
    console.log("This will not run!");
}, 3000);

clearTimeout(timeoutID); // Cancels the timeout
```
- The `"This will not run!"` **never appears** because we stopped it.

---

### **✅ `clearInterval()` - Stop a Repeating `setInterval()`**
```js
let count = 0;
let intervalID = setInterval(() => {
    count++;
    console.log("Running... " + count);
    if (count === 5) {
        clearInterval(intervalID); // Stops after 5 times
        console.log("Stopped!");
    }
}, 1000);
```
- Runs `"Running..."` **5 times**, then stops.

---

## **🔹 4. Real-World Use Cases**
| **Scenario** | **Use `setTimeout()` or `setInterval()`?** |
|-------------|----------------------------------|
| Show a message **once after a delay** | `setTimeout()` |
| Auto-refresh data every **5 seconds** | `setInterval()` |
| Stop a repeating function **after 10 times** | `setInterval()` + `clearInterval()` |
| Delay execution of a function | `setTimeout()` |

---

## **🎯 Summary**
| Function | Runs | Stops with |
|----------|------|------------|
| `setTimeout(func, delay)` | **Once** after delay | `clearTimeout()` |
| `setInterval(func, interval)` | **Repeatedly** at interval | `clearInterval()` |

Both are essential for **timing-based** operations in JavaScript. Let me know if you need more examples! 🚀😊