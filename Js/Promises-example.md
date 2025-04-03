### **🟢 Using Promises (Cleaner & Readable) – Code Explanation**  

Instead of using **nested callbacks**, we can use **Promises** to avoid "Callback Hell" and make the code **more readable**.  

---

### **🔹 Promise Version of Tea Making Process**
```js
function boilWater() {
    return new Promise((resolve) => {
        setTimeout(() => {
            console.log("✅ Water boiled!");
            resolve();  // Mark the task as done
        }, 1000);
    });
}

function addTeaLeaves() {
    return new Promise((resolve) => {
        setTimeout(() => {
            console.log("✅ Added tea leaves!");
            resolve();  // Mark the task as done
        }, 1000);
    });
}

function pourIntoCup() {
    return new Promise((resolve) => {
        setTimeout(() => {
            console.log("✅ Poured tea into cup!");
            resolve();  // Mark the task as done
        }, 1000);
    });
}

function drinkTea() {
    return new Promise((resolve) => {
        setTimeout(() => {
            console.log("😋 Enjoying the tea!");
            resolve();  // Mark the task as done
        }, 1000);
    });
}

// Chaining Promises to avoid Callback Hell
boilWater()
    .then(() => addTeaLeaves())
    .then(() => pourIntoCup())
    .then(() => drinkTea())
    .then(() => console.log("🎉 Tea making process finished!"));
```

---

### **🧐 Step-by-Step Code Explanation**  

#### **1️⃣ Creating a Promise in Each Function**
Each function **returns a Promise**. A **Promise** is an object that represents a task that will be completed in the future.

```js
function boilWater() {
    return new Promise((resolve) => {
        setTimeout(() => {
            console.log("✅ Water boiled!");
            resolve();  // Tells JavaScript the task is complete
        }, 1000);
    });
}
```
- **`return new Promise(...)`** → Creates a Promise that runs the task inside.
- **Inside `setTimeout()`**, we perform the action (`console.log()`).
- **`resolve()`** → This tells JavaScript that the Promise has been **successfully completed**.

The same pattern is used in **`addTeaLeaves()`, `pourIntoCup()`, and `drinkTea()`**.

---

#### **2️⃣ Using `.then()` to Chain Promises**
Instead of nesting functions inside each other, we use **`.then()`** to handle each step **one after another**.

```js
boilWater()
    .then(() => addTeaLeaves())  // After boiling water, add tea leaves
    .then(() => pourIntoCup())   // Then pour into cup
    .then(() => drinkTea())      // Then drink the tea
    .then(() => console.log("🎉 Tea making process finished!"));
```
✅ Each **`.then()`** waits for the previous Promise to finish before executing the next step.  

---

### **🔎 How Does Promise Chaining Work?**
| Step | Function | Time Taken | What Happens? |
|------|---------|------------|---------------|
| 1️⃣ | `boilWater()` | 1 second | Prints `"✅ Water boiled!"` and **resolves the Promise** |
| 2️⃣ | `addTeaLeaves()` | 1 second | Prints `"✅ Added tea leaves!"` and **resolves the Promise** |
| 3️⃣ | `pourIntoCup()` | 1 second | Prints `"✅ Poured tea into cup!"` and **resolves the Promise** |
| 4️⃣ | `drinkTea()` | 1 second | Prints `"😋 Enjoying the tea!"` and **resolves the Promise** |
| ✅ | Last `.then()` | Instant | Prints `"🎉 Tea making process finished!"` |

---

### **🔴 Why is This Better Than Callback Hell?**
| **Callback Hell ❌** | **Promise Chaining ✅** |
|----------------------|----------------------|
| Hard to read 😵 | Easy to read 📖 |
| Too many nested functions 🔄 | Flat & structured code 📌 |
| Difficult to debug 🛑 | Errors are easier to catch 🕵️‍♂️ |

---

### **✨ Bonus: What If Something Goes Wrong? (Error Handling)**
With Promises, we can **catch errors easily** using `.catch()`.

```js
boilWater()
    .then(() => addTeaLeaves())
    .then(() => pourIntoCup())
    .then(() => drinkTea())
    .then(() => console.log("🎉 Tea making process finished!"))
    .catch((error) => console.log("❌ Error:", error));
```
✅ If any function **fails**, `.catch()` will **handle the error** and prevent the app from crashing.

---

### **🚀 Final Thoughts**
✔ **Promises make async code clean & readable.**  
✔ **Promise chaining eliminates Callback Hell.**  
✔ **Error handling is easier with `.catch()`.**  

🚀 **But wait… Async/Await is even better!** Would you like an **even simpler version** using `async/await`? 😃