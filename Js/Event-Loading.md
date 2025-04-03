### **🔹 What is Event Loading in JavaScript?**  

Event loading refers to how JavaScript handles the loading of **events** (like `click`, `DOMContentLoaded`, or `load`) and executes them at the right time.

---

## **🔸 1. `DOMContentLoaded` (Fires When HTML is Loaded)**
- This event triggers **when the HTML document is fully parsed**, but before images, stylesheets, and sub-resources are loaded.  
- Useful when you want to run JavaScript **as soon as the DOM is ready**.

### **Example: Using `DOMContentLoaded`**
```js
document.addEventListener("DOMContentLoaded", function () {
    console.log("DOM fully loaded and parsed!");
});
```
✅ **Best for:** Running scripts that modify HTML elements **before the page fully loads**.  

---

## **🔸 2. `load` (Fires After Everything is Loaded)**
- The `load` event triggers when the **entire page (including images, styles, and scripts) is fully loaded**.  
- Useful when waiting for large assets (like images or videos) to load.

### **Example: Using `window.onload`**
```js
window.onload = function () {
    console.log("Entire page including images and styles has loaded!");
};
```
✅ **Best for:** Running scripts **after everything (including images, CSS) is loaded**.  

---

## **🔸 3. `beforeunload` (Triggers Before Page Unloads)**
- This event fires **before the user leaves the page** (e.g., closing the tab or navigating away).
- Often used to **show warnings** if the user is about to lose unsaved changes.

### **Example: Using `beforeunload`**
```js
window.addEventListener("beforeunload", function (event) {
    event.preventDefault();
    event.returnValue = ""; // Show a confirmation dialog
});
```
✅ **Best for:** Warning users about **unsaved changes** before leaving the page.  

---

## **🔹 Summary Table**
| Event | When It Fires | Best Use Case |
|-------|-------------|--------------|
| `DOMContentLoaded` | When the HTML is fully loaded (before images, CSS) | Running JS as soon as DOM is ready |
| `load` | When everything (including images, CSS) is loaded | Running scripts that need full resources |
| `beforeunload` | When the user is about to leave the page | Warning users about unsaved changes |

---

### **🚀 Need more real-world examples? Let me know!** 😃