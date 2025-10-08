## 🔥 Top 7 Most Important React Hooks

### 1. **useState**

* Manages state in a functional component.
* ✅ Most used hook.

```jsx
const [count, setCount] = useState(0);
```

---

### 2. **useEffect**

* Handles side effects: fetching data, timers, subscriptions, etc.
* Replaces lifecycle methods (`componentDidMount`, `componentDidUpdate`, `componentWillUnmount`).

```jsx
useEffect(() => {
  console.log("Component mounted");
}, []);
```

---

### 3. **useContext**

* Accesses values from **Context API** without prop drilling.

```jsx
const value = useContext(MyContext);
```

---

### 4. **useRef**

* Stores mutable values that don’t trigger re-render.
* Also used to directly access DOM elements.

```jsx
const inputRef = useRef();
```

---

### 5. **useReducer**

* Alternative to `useState` for **complex state logic** (like Redux-style reducers).

```jsx
const [state, dispatch] = useReducer(reducer, initialState);
```

---

### 6. **useMemo**

* Optimizes performance by memoizing **expensive calculations**.

```jsx
const result = useMemo(() => compute(num), [num]);
```

---

### 7. **useCallback**

* Optimizes performance by memoizing **functions** (prevents unnecessary re-renders).

```jsx
const memoizedFn = useCallback(() => doSomething(), []);
```

---

✅ If you master just these 7 hooks, you can handle **90% of React interview questions + real-world scenarios**.

👉 Do you want me to make a **table cheatsheet (Hook → Purpose → Example)** so you can revise quickly before interviews?
