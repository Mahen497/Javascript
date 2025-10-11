Perfect 👍 — since your **E-Commerce README** already documents features and structure, we’ll add a **dedicated “Pagination” section** that clearly explains both types:

* Simple Pagination
* Advanced Pagination with Ellipsis Subset

Here’s how you can integrate it smoothly into your README 👇

---

## 🧩 Pagination

The project includes **two types of pagination systems** used for displaying products efficiently in the product grid.

### 1. Simple Pagination

A basic pagination system that:

* Divides products into pages based on the selected number of items per page.
* Provides **Next**, **Previous**, and direct **page number buttons**.
* Updates the visible products dynamically using React’s state management.

**Key Features:**

* Allows selecting the number of items per page (5, 10, 15, etc.).
* Automatically resets to the first page when product data changes.
* Disables navigation buttons appropriately at first/last pages.

**Code Example:**

```jsx
const [currentPage, setCurrentPage] = useState(1);
const [itemsPerPage, setItemsPerPage] = useState(5);

const totalPages = Math.ceil(products.length / itemsPerPage);
const indexOfLastItem = currentPage * itemsPerPage;
const indexOfFirstItem = indexOfLastItem - itemsPerPage;
const currentItems = products.slice(indexOfFirstItem, indexOfLastItem);
```

---

### 2. Advanced Pagination (Subset with Ellipsis Logic)

To improve UX for large datasets (e.g., 50+ pages),
the app also demonstrates **subset pagination with ellipsis** (`...`) for a cleaner layout.

**Example:**

```
1 ... 5 6 7 ... 20
```

**Logic:**

* Always shows the **first and last pages**.
* Shows only a **subset** of pages around the current page.
* Collapses hidden ranges with ellipses (`...`).
* Clicking ellipsis-adjacent numbers reveals new subsets dynamically.

**Benefits:**

* Cleaner and more readable pagination bar.
* Avoids overwhelming the user with too many buttons.
* Uses memoization (`useMemo`) for performance optimization.

**Code Snippet:**

```jsx
const pageNumbers = useMemo(() => {
  const pages = [];
  const maxVisible = 3;

  if (totalPages <= 7) {
    return Array.from({ length: totalPages }, (_, i) => i + 1);
  }

  if (currentPage <= 4) {
    pages.push(1, 2, 3, 4, 5, '...', totalPages);
  } else if (currentPage >= totalPages - 3) {
    pages.push(1, '...', totalPages - 4, totalPages - 3, totalPages - 2, totalPages - 1, totalPages);
  } else {
    pages.push(1, '...', currentPage - 1, currentPage, currentPage + 1, '...', totalPages);
  }

  return pages;
}, [currentPage, totalPages]);
```

**UI Example:**

```jsx
<nav className="pagination">
  <button onClick={goToPrevPage} disabled={currentPage === 1}>Previous</button>
  {pageNumbers.map((page, index) => (
    page === '...'
      ? <span key={index}>...</span>
      : <button
          key={page}
          className={currentPage === page ? 'active' : ''}
          onClick={() => goToSpecificPage(page)}
        >
          {page}
        </button>
  ))}
  <button onClick={goToNextPage} disabled={currentPage === totalPages}>Next</button>
</nav>
```

---

### ⚙️ Pagination Enhancements

* Supports **changing items per page** dynamically.
* Uses `useEffect` to reset the current page when data or filter changes.
* Includes performance optimization using `useMemo`.
* Keeps logic modular — you can reuse pagination across other components like Orders or Products.

---

### 📂 Related File

```
src/components/ProductsGrid.jsx
```

This file contains both pagination implementations (basic and advanced ellipsis version).

---