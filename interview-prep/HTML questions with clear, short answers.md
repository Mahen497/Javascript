Perfect 👍 Let’s go through **all 25 HTML questions with clear, short answers** — just like a revision sheet.
# 🏆 Master Web Design Interview Q\&A (HTML + CSS + Responsive + Optimization)

---

# 📝 HTML Interview Q\&A (Extended Set)

---

## 📌 Basics

**Q1. What are void (self-closing) elements in HTML? Give examples.**
👉 *Answer:* Elements without closing tags: `<img>`, `<br>`, `<hr>`, `<input>`, `<meta>`, `<link>`.

---

**Q2. Difference between HTML and XHTML?**
👉 *Answer:*

* HTML → forgiving, not strict with syntax.
* XHTML → stricter, requires proper nesting, lowercase tags, and closing of all elements.

---

**Q3. What is the difference between inline elements and block elements?**
👉 *Answer:*

* Inline → flow inside text (`<span>`, `<a>`).
* Block → start on new line, full width (`<div>`, `<p>`).

---

**Q4. What is the difference between `<strong>` and `<b>`?**
👉 *Answer:*

* `<strong>` → semantic (important text, accessibility).
* `<b>` → purely visual (bold style).

---

**Q5. What is the difference between `<em>` and `<i>`?**
👉 *Answer:*

* `<em>` → semantic emphasis (screen readers stress it).
* `<i>` → stylistic italic only.

---

## 📌 Forms & Inputs

**Q6. What’s the difference between `<input type="radio">` and `<input type="checkbox">`?**
👉 *Answer:*

* Radio → single selection in a group.
* Checkbox → multiple selections allowed.

---

**Q7. What is the purpose of the `label` tag in forms?**
👉 *Answer:* Associates text with input → improves accessibility and lets user click text to focus input.

---

**Q8. How does the `required` attribute work in forms?**
👉 *Answer:* Prevents form submission if input is empty → built-in HTML5 validation.

---

**Q9. What is the difference between GET and POST methods in forms?**
👉 *Answer:*

* GET → data in URL, visible, limited length, cached.
* POST → data in body, hidden, secure, no size limit.

---

**Q10. What is the difference between `<button>` and `<input type="submit">`?**
👉 *Answer:*

* `<button>` → flexible, can contain HTML inside.
* `<input type="submit">` → simpler, only submits form.

---

## 📌 Multimedia & Graphics

**Q11. Difference between `<img>`, `<picture>`, and `<figure>`?**
👉 *Answer:*

* `<img>` → single image.
* `<picture>` → responsive images with multiple sources.
* `<figure>` → semantic wrapper for image + caption.

---

**Q12. What’s the use of the `srcset` attribute in images?**
👉 *Answer:* Lets browser choose best image size/resolution based on device.

---

**Q13. What is the difference between `<audio>` and `<video>` tags?**
👉 *Answer:* `<audio>` → audio playback, `<video>` → video playback (supports controls, tracks).

---

**Q14. What’s the difference between `<canvas>` and `<svg>`?**
👉 *Answer:*

* `<canvas>` → bitmap-based, scripted graphics, not scalable.
* `<svg>` → vector-based, scalable, semantic shapes.

---

**Q15. How can you add subtitles or captions to a `<video>`?**
👉 *Answer:* Using `<track>` element inside `<video>`. Example:

```html
<track src="subs.vtt" kind="subtitles" srclang="en" label="English">
```

---

## 📌 Advanced HTML Concepts

**Q16. What is the difference between inline scripts and external scripts?**
👉 *Answer:*

* Inline → inside `<script>` in HTML file.
* External → linked via `<script src="file.js">`, better for caching & maintainability.

---

**Q17. What is the difference between `<link>` and `<a>`?**
👉 *Answer:*

* `<link>` → links resources (CSS, favicon).
* `<a>` → creates hyperlinks for navigation.

---

**Q18. What’s the use of the `defer` and `async` attributes in `<script>`?**
👉 *Answer:*

* `async` → loads script in parallel, executes immediately (not order guaranteed).
* `defer` → loads in parallel, executes after HTML parsing (order preserved).

---

**Q19. Difference between localStorage, sessionStorage, and cookies?**
👉 *Answer:*

* localStorage → persistent, no expiry, client-side only.
* sessionStorage → temporary, cleared when tab closes.
* cookies → small data, can be sent to server.

---

**Q20. What’s the difference between `<noscript>` and `<script>`?**
👉 *Answer:*

* `<script>` → runs JS.
* `<noscript>` → fallback content when JS is disabled.

---

## 📌 Accessibility & SEO

**Q21. What is the difference between `alt`, `title`, and `aria-label` attributes?**
👉 *Answer:*

* `alt` → describes images for accessibility.
* `title` → tooltip text on hover.
* `aria-label` → accessibility for screen readers.

---

**Q22. What is the difference between `<nav>` and `<ul>` for navigation?**
👉 *Answer:*

* `<nav>` → semantic container for navigation links.
* `<ul>` → unordered list of items (used inside nav).

---

**Q23. What are landmark roles in HTML (e.g., `<main>`, `<aside>`)?**
👉 *Answer:* Special semantic regions to improve accessibility → `<header>`, `<main>`, `<aside>`, `<footer>`, `<nav>`.

---

**Q24. Why is heading order (`<h1>` to `<h6>`) important?**
👉 *Answer:* Defines document structure, improves SEO, helps screen readers navigate content hierarchy.

---

**Q25. What is the difference between canonical and alternate links in SEO?**
👉 *Answer:*

* Canonical → tells search engines which page is the “main/original” version.
* Alternate → specifies language/region variations of a page.

---


## 📌 Section 1: HTML (Structure & Semantics)

**Q26. What are void elements in HTML?**
👉 Elements without closing tags, e.g. `<img>`, `<br>`, `<hr>`, `<input>`.

**Q27. Difference between HTML and XHTML?**
👉 HTML is flexible; XHTML is strict (lowercase tags, proper nesting, all tags closed).

**Q28. Difference between inline and block elements?**
👉 Inline (e.g., `<span>`, `<a>`) doesn’t start new line; Block (e.g., `<div>`, `<p>`) takes full width.

**Q29. Difference between `<strong>` vs `<b>` and `<em>` vs `<i>`?**
👉 `<strong>` / `<em>` → semantic (importance/emphasis).
👉 `<b>` / `<i>` → purely visual (bold/italic).

**Q30. Difference between `<canvas>` and `<svg>`?**
👉 Canvas = bitmap, scripted, not scalable. SVG = vector, semantic, scalable.

**Q31. What are semantic elements in HTML5?**
👉 `<header>`, `<nav>`, `<main>`, `<aside>`, `<footer>`, `<section>`, `<article>`. Improve SEO & accessibility.

**Q31. What is the difference between `alt`, `title`, and `aria-label`?**
👉 `alt` → image description. `title` → tooltip. `aria-label` → accessibility text.

---

## 📌 Section 2: CSS (Styling & Layout)

**Q32. What is the difference between relative, absolute, fixed, and sticky positioning?**
👉

* Relative → positioned relative to itself.
* Absolute → relative to nearest positioned ancestor.
* Fixed → relative to viewport (stays on scroll).
* Sticky → toggles between relative & fixed (based on scroll).

**Q33. Difference between inline, internal, and external CSS?**
👉 Inline = inside element (`style=""`), Internal = in `<style>` tag, External = in `.css` file.

**Q34. Explain z-index.**
👉 Controls stacking order of elements. Higher z-index = element appears on top. Works only on positioned elements.

**Q35. Difference between rem, em, %, px, vh, vw units?**
👉

* `px` → fixed pixels.
* `em` → relative to parent font-size.
* `rem` → relative to root font-size.
* `%` → relative to parent element.
* `vh/vw` → relative to viewport height/width.

**Q36. Difference between relative length and absolute length units in CSS?**
👉 Absolute (px, pt) = fixed. Relative (em, rem, %, vw, vh) = flexible, responsive.

**Q37. Difference between CSS Grid and Flexbox?**
👉 Flexbox → one-dimensional (row/column).
👉 Grid → two-dimensional (rows & columns).

**Q37. What are pseudo-classes and pseudo-elements?**
👉 Pseudo-classes → state selectors (`:hover`, `:focus`).
👉 Pseudo-elements → specific parts of element (`::before`, `::after`).

---

## 📌 Section 3: Responsive Design

**Q39. What is mobile-first design?**
👉 Designing for smaller screens first, then scaling up with media queries.

**Q40. How do you make images responsive?**
👉 Using `max-width: 100%; height: auto; object-fit: cover;`

**Q41. Difference between `em`, `rem`, and percentages in responsive design?**
👉 `em` depends on parent, `rem` depends on root, `%` depends on container.

**Q42. How do media queries work?**
👉 CSS rules apply only if conditions are met, e.g.:

```css
@media (max-width: 768px) {
  body { font-size: 14px; }
}
```

**Q43. What is the difference between responsive, adaptive, and fluid design?**
👉

* Responsive → adjusts dynamically with CSS/media queries.
* Adaptive → fixed breakpoints with different layouts.
* Fluid → uses %/relative units to scale automatically.

---

## 📌 Section 4: Optimization & Performance

**Q43. Explain FCP, LCP, TBT, CLS in Core Web Vitals.**
👉

* FCP (First Contentful Paint) → time when first text/image is painted.
* LCP (Largest Contentful Paint) → time when main content loads.
* TBT (Total Blocking Time) → time JS blocks main thread.
* CLS (Cumulative Layout Shift) → visual stability (unexpected layout shift).

**Q44. How to optimize images for performance?**
👉 Use WebP/AVIF, responsive images (`srcset`), lazy loading (`loading="lazy"`), compression.

**Q45. How to reduce render-blocking resources?**
👉 Minify CSS/JS, use `async` or `defer` for scripts, preload critical CSS.

**Q46. How to improve page speed in CSS & HTML?**
👉 Minification, remove unused CSS/JS, use CDN, cache assets, responsive images, reduce DOM size.

**Q47. What is lazy loading?**
👉 Defers loading of non-critical resources (like images/videos) until they’re visible in viewport.

**Q48. Difference between `async` and `defer` in `<script>`?**
👉 `async` loads in parallel & executes immediately.
👉 `defer` loads in parallel & executes after DOM parsing.

---

## 📌 Section 5: Professional & Practical

**Q49. How do you ensure cross-browser compatibility?**
👉 Use CSS resets, test in major browsers, avoid experimental features, use Autoprefixer for vendor prefixes.

**Q50. How do you handle accessibility in web design?**
👉 Semantic HTML, alt text for images, ARIA roles, keyboard navigation, color contrast check.

**Q51. What steps do you follow when converting Figma designs to HTML/CSS?**
👉 Analyze layout → semantic structure → mobile-first → pixel-perfect CSS → test responsiveness → optimize assets.

**Q52. How do you handle version control in projects?**
👉 Git for tracking changes, branching strategy, pull requests, code reviews.

**Q53. Tell me about one project you are proud of (Ecommerce, Dashboard, Landing Page)?**
👉 *(You would give a personal experience answer here)* Example: “I optimized an ecommerce website where LCP reduced from 5.2s to 2.1s by optimizing images and using critical CSS.”

**Q54. specificity**
👉 CSS specificity is the algorithm used by browsers to determine which style declarations should be applied to an element when multiple rules target the same element. 
Specificity is calculated based on a hierarchy of selector types, often represented as a four-part score (A, B, C, D):
  -Inline Styles (A)
  -ID Selectors (B):
  -Class Selectors, Attribute Selectors, and Pseudo-classes (C):
  -Element Selectors and Pseudo-elements (D):




