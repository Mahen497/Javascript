## 🔹 What are Hooks?

Hooks are **functions** that let you use React features (like state, lifecycle methods, context) inside **functional components**.
Before hooks (React < 16.8), we had to use **class components** to manage state and lifecycle. Hooks made functional components more powerful.

---

## 🔹 Commonly Used Hooks

### 1. **useState**

* Lets you add state to a functional component.

```jsx
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0); 

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increase</button>
    </div>
  );
}
```

---

### 2. **useEffect**

* Runs side effects (like fetching data, subscriptions, DOM updates).

```jsx
import { useEffect, useState } from "react";

function Example() {
  const [data, setData] = useState([]);

  useEffect(() => {
    fetch("https://jsonplaceholder.typicode.com/posts")
      .then(res => res.json())
      .then(json => setData(json));
  }, []); // [] → runs only once (like componentDidMount)

  return <div>{data.length} Posts Loaded</div>;
}
```

---

### 3. **useContext**

* Lets you use **context API** directly in components (no need for `Consumer`).

```jsx
const ThemeContext = React.createContext("light");

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Toolbar />
    </ThemeContext.Provider>
  );
}

function Toolbar() {
  const theme = React.useContext(ThemeContext);
  return <p>Theme is {theme}</p>;
}
```

---

### 4. **useRef**

* Creates a **mutable reference** that persists between renders (like `document.getElementById` alternative).

```jsx
function InputFocus() {
  const inputRef = React.useRef();

  const focusInput = () => {
    inputRef.current.focus();
  };

  return (
    <div>
      <input ref={inputRef} />
      <button onClick={focusInput}>Focus Input</button>
    </div>
  );
}
```

---

### 5. **useReducer**

* Alternative to `useState`, useful for complex state logic.

```jsx
function reducer(state, action) {
  switch (action.type) {
    case "increment":
      return { count: state.count + 1 };
    case "decrement":
      return { count: state.count - 1 };
    default:
      return state;
  }
}

function Counter() {
  const [state, dispatch] = React.useReducer(reducer, { count: 0 });

  return (
    <div>
      <p>{state.count}</p>
      <button onClick={() => dispatch({ type: "increment" })}>+</button>
      <button onClick={() => dispatch({ type: "decrement" })}>-</button>
    </div>
  );
}
```

---

### 6. **useMemo**

* Caches (memoizes) expensive calculations.

```jsx
function ExpensiveCalc({ num }) {
  const result = React.useMemo(() => {
    console.log("Calculating...");
    return num * 2;
  }, [num]);

  return <p>Result: {result}</p>;
}
```

---

### 7. **useCallback**

* Memoizes functions so they are not recreated unnecessarily (helps with performance).

```jsx
function App() {
  const [count, setCount] = React.useState(0);

  const increment = React.useCallback(() => {
    setCount(prev => prev + 1);
  }, []);

  return <button onClick={increment}>Count: {count}</button>;
}
```

---

### 8. **Custom Hooks**

* You can create your own hooks by reusing logic.

```jsx
function useWindowWidth() {
  const [width, setWidth] = React.useState(window.innerWidth);

  React.useEffect(() => {
    const handleResize = () => setWidth(window.innerWidth);
    window.addEventListener("resize", handleResize);
    return () => window.removeEventListener("resize", handleResize);
  }, []);

  return width;
}

function App() {
  const width = useWindowWidth();
  return <p>Window width: {width}</p>;
}
```

---

👉 There are more hooks (`useLayoutEffect`, `useImperativeHandle`, etc.), but these are the **most important**.

---