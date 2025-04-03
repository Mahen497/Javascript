### **🔴 Callback Hell – Understanding `callback()`**  

In JavaScript, **`callback()` is simply a function that gets executed after another function completes**.  

Let's break it down using a **simple tea-making example**:  

---

### **❌ Callback Hell Example (Messy Code)**  
```js
function boilWater(callback) {
    setTimeout(() => {
        console.log("✅ Water boiled!");
        callback();  // Calling the next step
    }, 1000);
}

function addTeaLeaves(callback) {
    setTimeout(() => {
        console.log("✅ Added tea leaves!");
        callback();  // Calling the next step
    }, 1000);
}

function pourIntoCup(callback) {
    setTimeout(() => {
        console.log("✅ Poured tea into cup!");
        callback();  // Calling the next step
    }, 1000);
}

function drinkTea() {
    setTimeout(() => {
        console.log("😋 Enjoying the tea!");
    }, 1000);
}

// Nested Callbacks (Callback Hell)
boilWater(() => {  // Step 1
    addTeaLeaves(() => {  // Step 2
        pourIntoCup(() => {  // Step 3
            drinkTea();  // Step 4
        });
    });
});
```

---

### **🧐 What is `callback()` Doing?**
Each `callback()` **calls the next function in the sequence** when the current task is done.

#### **Step-by-step Breakdown:**
1️⃣ **`boilWater(callback)`**  
   - Starts boiling water.  
   - After **1 second**, prints `"✅ Water boiled!"`.  
   - Then, **calls the `callback()` function** → which is `addTeaLeaves()`.  

2️⃣ **`addTeaLeaves(callback)`**  
   - Starts adding tea leaves.  
   - After **1 second**, prints `"✅ Added tea leaves!"`.  
   - Then, **calls the `callback()` function** → which is `pourIntoCup()`.  

3️⃣ **`pourIntoCup(callback)`**  
   - Starts pouring tea into a cup.  
   - After **1 second**, prints `"✅ Poured tea into cup!"`.  
   - Then, **calls the `callback()` function** → which is `drinkTea()`.  

4️⃣ **`drinkTea()`**  
   - After **1 second**, prints `"😋 Enjoying the tea!"`.  
   - **No callback needed here** because this is the last step.

---

### **🔴 Problem with Callback Hell**
- Too **many nested functions**, making the code hard to read and manage.  
- If we need to add **more steps**, the indentation will keep increasing.  
- **Difficult to debug** errors in nested callbacks.  

---

### **🟢 Solution: Use Promises or Async/Await**
✅ Instead of **callback hell**, we can use **Promises** or **Async/Await** to clean up the code.  

Would you like a **Promise-based or Async/Await version** of this example? 😊