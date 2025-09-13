# 📝 Web Design Interview Q\&A (Direct, No Scenario)

---

## 🖥 HTML

**Q1. What is the difference between inline, block, and inline-block elements?**
👉 *Answer:*

* Inline → only takes width of content (`<span>`, `<a>`).
* Block → takes full width, starts on new line (`<div>`, `<p>`).
* Inline-block → behaves inline but allows block properties like width/height.

---

**Q2. Why is the `alt` attribute important for images?**
👉 *Answer:*

* Improves accessibility (screen readers).
* Displays fallback text if image fails.
* Helps SEO (search engines read `alt`).

---

**Q3. Can you explain the difference between `<section>`, `<article>`, and `<div>`?**
👉 *Answer:*

* `<section>` → groups related content (thematic).
* `<article>` → self-contained content (blog post, news).
* `<div>` → generic container with no semantic meaning.

---

**Q4. What are meta tags and why are they used?**
👉 *Answer:*
Meta tags provide metadata (description, keywords, viewport) for browsers & search engines. Example: `<meta name="description" content="SEO text">`.

---

**Q5. What’s the difference between `id` and `class` attributes?**
👉 *Answer:*

* `id` → unique, used once per page (`#id`).
* `class` → reusable, used multiple times (`.class`).

---

## 🎨 CSS

**Q6. What are pseudo-classes and pseudo-elements? Give examples.**
👉 *Answer:*

* Pseudo-class → defines state (`:hover`, `:focus`).
* Pseudo-element → targets part of element (`::before`, `::after`).

---

**Q7. Explain the difference between relative, absolute, fixed, and sticky positioning.**
👉 *Answer:*

* Relative → positioned relative to itself.
* Absolute → positioned relative to nearest positioned parent.
* Fixed → relative to viewport, doesn’t scroll.
* Sticky → behaves relative until a scroll threshold is reached.

---

**Q8. How do CSS specificity rules work?**
👉 *Answer:*
Priority order: inline styles > IDs > classes/pseudo-classes/attributes > elements. More specific = higher priority.

---

**Q9. What’s the difference between `em`, `rem`, `%`, and `px` units?**
👉 *Answer:*

* `em` → relative to parent font-size.
* `rem` → relative to root (`html`) font-size.
* `%` → relative to parent element.
* `px` → fixed unit.

---

**Q10. What are CSS variables (custom properties), and why would you use them?**
👉 *Answer:*
CSS variables store reusable values:

```css
:root { --main-color: #333; }  
h1 { color: var(--main-color); }
```

Used for consistency, easy theme changes, maintainability.

---

## 📱 Responsive Design

**Q11. What is the difference between responsive design and adaptive design?**
👉 *Answer:*

* Responsive → fluid, adjusts using flexible grids & media queries.
* Adaptive → fixed layouts for specific breakpoints.

---

**Q12. Explain the concept of a mobile-first approach.**
👉 *Answer:*
Start designing for smallest screen → then scale up with media queries (`min-width`). Ensures better performance & usability.

---

**Q13. How do you use `minmax()` in CSS Grid?**
👉 *Answer:*
`grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));` → sets flexible columns, min 200px wide, max fills space.

---

**Q14. What are media queries, and how do they work?**
👉 *Answer:*
Media queries apply CSS based on device width, height, orientation. Example:

```css
@media (max-width: 768px) { body { font-size: 14px; } }
```

---

**Q15. What are container queries in CSS, and how are they different from media queries?**
👉 *Answer:*

* Media queries → based on viewport size.
* Container queries → based on parent container size (new CSS feature).

---

## ⚡ Performance & Optimization

**Q16. What are Core Web Vitals, and why are they important?**
👉 *Answer:*
Google metrics for user experience:

* LCP (Largest Contentful Paint) → load speed.
  <img src="/assets/img1.jpg" alt="Hero" loading="eager" fetchpriority="high" />
  fetchpriority="high" further hints the browser that this image is critical for the page.
  Together, loading="eager" + fetchpriority="high" ensures your hero image appears fast.

  💡 Rule of thumb:
    Eager → above-the-fold, critical images (hero, banners, LCP image).
    Lazy → below-the-fold, non-critical images (gallery, sliders, thumbnails).

  “Above-the-fold” means the part of the page you see without scrolling.
  “Below-the-fold” is the part you have to scroll to reach.

  ✅ So basically:

    Omitting loading → browser decides automatically.
    Using loading="eager" → forces immediate load, which is good for hero/banner/LCP images.
    Using loading="lazy" → delays loading until the image is near viewport, saving bandwidth.

    ┌───────────────────────────────┐
    │          Above-the-fold       │ ← visible immediately
    │  Hero Banner / First Slide    │
    │  loading="eager" + fetchpriority="high"
    └───────────────────────────────┘
          ↑ loads immediately

    ┌───────────────────────────────┐
    │       Below-the-fold          │ ← you have to scroll to see
    │  Slide 2 / Slide 3 / Images   │
    │  loading="lazy"
    └───────────────────────────────┘
          ↑ loads when near viewport

* FID/TBT (First Input Delay/Blocking Time) → interactivity.
* CLS (Cumulative Layout Shift) → visual stability.

Important for SEO & usability.

---

**Q17. What is lazy loading, and how do you implement it?**
👉 *Answer:*
Delays loading of non-critical images until needed. Example:

```html
<img src="placeholder.jpg" data-src="image.jpg" loading="lazy">
```

---

**Q18. How does using a CDN improve performance?**
👉 *Answer:*
CDN delivers files from nearest server → reduces latency, speeds up load, improves availability.

---

**Q19. What’s the difference between inline CSS, external CSS, and inline styles in terms of performance?**
👉 *Answer:*

* Inline styles → highest specificity, bad for maintainability.
* Internal `<style>` → inside HTML, blocks rendering.
* External CSS → cached, better performance & maintainability.

---

**Q20. How would you reduce render-blocking resources in a web page?**
👉 *Answer:*

* Minify & combine CSS/JS.
* Use `defer`/`async` on scripts.
* Inline critical CSS.
* Load non-essential styles later.

---

## 🧑‍💻 General Web Design

**Q21. What’s the difference between UX and UI in web design?**
👉 *Answer:*

* UX → user experience (usability, flow).
* UI → user interface (visual design, aesthetics).

---

**Q22. How do you ensure accessibility (a11y) in your web designs?**
👉 *Answer:*

* Use semantic HTML.
* Proper `alt` text.
* Color contrast ratio (≥4.5).
* Keyboard navigation.
* ARIA roles where needed.

---

**Q23. What is progressive enhancement?**
👉 *Answer:*
Start with simple, accessible HTML → add CSS & JS enhancements for advanced browsers. Ensures core functionality works everywhere.

---

**Q24. Explain the difference between absolute units and relative units in CSS.**
👉 *Answer:*

* Absolute → fixed size (`px`, `cm`, `in`).
* Relative → adjusts with context (`em`, `rem`, `%`, `vw`).

---

**Q25. What is the difference between a static, dynamic, and responsive website?**
👉 *Answer:*

* Static → fixed content, HTML/CSS only.
* Dynamic → content generated by server (PHP, CMS).
* Responsive → adapts to screen sizes using CSS.

Got it 👍 Mahendra. Let’s extend the **Q\&A set** with more **HTML, CSS, Responsive, and Optimization** questions + clear answers (short + useful for interviews). I’ll also explain **`@media only`** at the end.

---

## 🔹 More HTML Questions

**Q1. What is the difference between `localStorage`, `sessionStorage`, and `cookies`?**

* `localStorage`: Stores data with no expiry, per domain.
* `sessionStorage`: Stores data until browser tab closes.
* `cookies`: Small data (4KB), sent with every request, supports expiry + server access.

**Q2. Difference between `<link>` and `<a>`?**

* `<link>`: Defines relationship with external resource (CSS, favicon).
* `<a>`: Creates a clickable hyperlink.

**Q3. What is the purpose of the `<noscript>` tag?**

* Provides fallback content if JavaScript is disabled in the browser.

**Q4. Explain difference between `async` and `defer` in `<script>`.**

* `async`: Loads JS file asynchronously, executes immediately (may block order).
* `defer`: Loads JS in parallel, executes **after HTML parsing** in order.

**Q5. What is the difference between HTML Collections vs NodeList?**

* HTMLCollection: Live, auto-updated (`document.forms`).
* NodeList: Static (unless queried with `childNodes`).

---

## 🔹 More CSS Questions

**Q6. Difference between relative, absolute, fixed, and sticky positioning?**

* Relative: Moves based on its normal position.
* Absolute: Moves relative to nearest positioned ancestor.
* Fixed: Stays fixed to viewport.
* Sticky: Hybrid → scrolls until threshold then sticks.

**Q7. What is the difference between inline CSS, internal CSS, and external CSS?**

* Inline: Inside tag (`<h1 style="color:red;">`).
* Internal: Inside `<style>` in `<head>`.
* External: Separate `.css` file linked via `<link>`.

**Q8. Difference between `opacity:0`, `visibility:hidden`, and `display:none`?**

* `opacity:0`: Element invisible but clickable (takes space).
* `visibility:hidden`: Invisible, but space reserved.
* `display:none`: Element removed from layout.

**Q9. What are pseudo-elements and give examples?**

* Add style to part of an element: `::before`, `::after`, `::first-letter`.

**Q10. Difference between relative units (`em`, `rem`, `%`) and absolute (`px`)?**

* `em`: Relative to parent font size.
* `rem`: Relative to root (html) font size.
* `%`: Relative to parent element dimension.
* `px`: Fixed size.

---

## 🔹 Responsive / Optimization Questions

**Q11. What is a responsive image in HTML?**

* Use `<img srcset="small.jpg 480w, medium.jpg 768w, large.jpg 1200w" sizes="(max-width:768px) 100vw, 50vw" src="default.jpg">`
* Browser chooses best image size.

**Q12. What is critical CSS and why is it important?**

* Inline above-the-fold CSS in `<head>` to speed up first render.

**Q13. What is lazy loading and how to implement in HTML?**

* Load images/videos only when needed: `<img src="img.jpg" loading="lazy">`.

**Q14. Difference between mobile-first and desktop-first design?**

* Mobile-first: Start with small screens → scale up with `min-width`.
* Desktop-first: Start with large screens → scale down with `max-width`.

---

## 🔹 General Professional Questions

**Q15. Difference between progressive enhancement and graceful degradation?**

* Progressive enhancement: Start simple, add advanced features.
* Graceful degradation: Build full-featured, ensure fallback for old browsers.

**Q16. What are Web Accessibility (a11y) best practices?**

* Use semantic HTML, alt text, ARIA roles, keyboard navigation, color contrast.

**Q17. What is the difference between UX and UI?**

* UX = Experience (journey).
* UI = Interface (look & feel).

---

## 🔹 Special Explanation: `@media only` in CSS

👉 **Syntax Example:**

```css
@media only screen and (max-width: 768px) {
  body {
    background: lightblue;
  }
}
```

✔ **`only`** is a keyword used to **filter older browsers** that do not understand media queries.

* `@media screen and (max-width:768px)` = works everywhere (old + new browsers).
* `@media only screen and (max-width:768px)` = ignores old browsers that don’t support media queries.

⚡ In modern practice → `only` is optional, since almost all browsers support media queries.

---

Got it Mahendra 👍 Thanks for catching that.
Let me now create a **fresh extended set** — not repeats — focusing only on **new advanced HTML/CSS questions with answers**, including **media queries (`only` keyword explained in depth)**.

---

# 🔹 Extended Web Design Interview Q\&A (Fresh – No Repeats)

---

### **HTML – New Questions**

**Q1. Difference between `<figure>` and `<img>`?**

* `<img>`: Displays image only.
* `<figure>`: Semantic container for image + caption (`<figcaption>`).

**Q2. What is the difference between `<section>`, `<article>`, and `<div>`?**

* `<section>`: Groups related content with a heading.
* `<article>`: Self-contained content (e.g., blog post, news item).
* `<div>`: Generic container with no semantic meaning.

**Q3. What is a semantic element? Give 5 examples.**

* Elements with meaning for both developers & browsers.
* Examples: `<header>`, `<footer>`, `<main>`, `<aside>`, `<nav>`.

**Q4. What is the difference between `<dl>`, `<dt>`, and `<dd>`?**

* `<dl>`: Definition list.
* `<dt>`: Term.
* `<dd>`: Description.

**Q5. What’s the difference between `id` and `class` attributes?**

* `id`: Unique, used once per page.
* `class`: Reusable, applied to multiple elements.

---

### **CSS – New Questions**

**Q6. Difference between relative units (`em`, `rem`, `%`, `vh`, `vw`)**

* `em`: Relative to parent font size.
* `rem`: Relative to root (`html`).
* `%`: Relative to parent element.
* `vh`: % of viewport height.
* `vw`: % of viewport width.

**Q7. What is the difference between inline-block and block elements?**

* Block: Occupies full width, starts new line.
* Inline-block: Flows inline but can set width/height.

**Q8. Difference between CSS Grid and Flexbox?**

* Grid: 2D (rows + columns).
* Flexbox: 1D (row OR column).
* Use Grid for layouts, Flexbox for alignment.

**Q9. Difference between relative and absolute length units?**

* Absolute: Fixed (px, in, cm).
* Relative: Depends on parent/viewport (%, em, rem, vh, vw).

**Q10. What’s the difference between `z-index` and stacking context?**

* `z-index`: Controls layer order.
* Stacking context: A new layer group created by positioned elements, opacity, etc.

---

### **Responsive Design & Media Queries**

**Q11. What is the difference between `@media screen`, `@media print`, and `@media speech`?**

* `screen`: For monitors, tablets, phones.
* `print`: For printed documents / print preview.
* `speech`: For screen readers.

**Q12. What is `@media only` in CSS?**

```css
@media only screen and (max-width: 768px) {
  body { font-size: 14px; }
}
```

* `only`: Prevents older browsers (that don’t support media queries) from applying styles.
* Modern browsers → optional.
* Example:

  * `@media screen` → may apply wrongly in old browsers.
  * `@media only screen` → applies **only if media queries supported**.

**Q13. Example: Mobile-first media query vs Desktop-first media query.**

* **Mobile-first:**

```css
/* Base: mobile */
body { font-size: 14px; }

/* Larger screens */
@media (min-width: 768px) { body { font-size: 16px; } }
```

* **Desktop-first:**

```css
/* Base: desktop */
body { font-size: 16px; }

/* Smaller screens */
@media (max-width: 768px) { body { font-size: 14px; } }
```

---

### **Optimization / Performance**

**Q14. Difference between inline SVG and SVG as an image?**

* Inline SVG: Can be styled with CSS, animated.
* `<img src="icon.svg">`: Treated as static image.

**Q15. What is preloading vs prefetching?**

* Preload: Load resource early for current page.
* Prefetch: Load resource for next navigation.

**Q16. Why use `srcset` and `sizes` in `<img>`?**

* Helps browser choose best image size → improves performance.

---

### **Professional / Best Practices**

**Q17. What’s the difference between responsive and adaptive design?**

* Responsive: Fluid layout adjusts to any screen.
* Adaptive: Predefined layouts for specific breakpoints.

**Q18. What is FOUC (Flash of Unstyled Content)? How to prevent it?**

* Page loads without CSS briefly.
* Fix: Inline critical CSS, use `rel="preload"` for stylesheets.

**Q19. What is difference between external CSS file vs CSS-in-JS (React/Angular)?**

* External CSS: Traditional, browser cached.
* CSS-in-JS: Scoped styles, dynamic in apps.

**Q20. Why should semantic HTML be preferred over `<div>`-based layouts?**

* Better SEO.
* Accessibility.
* Cleaner code structure.

---



