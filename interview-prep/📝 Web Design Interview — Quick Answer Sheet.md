# 📝 Web Design Interview — Quick Answer Sheet (Mahendra Patil)
⚡️ This is the **last-minute revision sheet** – read once before your interview for quick recall.

## 🔹 Technical

* **Semantic HTML** → improves accessibility, SEO, maintainability. Use `<header>`, `<main>`, etc.
* **Responsive design** → mobile-first, CSS Grid/Flexbox, test on devices, simplify tables for mobile.
* **Optimization** → lazy load, WebP images, inline critical CSS, preload fonts, reduce CLS.
* **Flexbox vs Grid** → Flexbox = 1D (nav bars), Grid = 2D (page layouts).
* **Debug tools** → Chrome DevTools, Lighthouse, WebPageTest, BrowserStack.

---

## 🔹 Design Scenarios

* **E-commerce priorities** → clear hierarchy + fast load + brand consistency.
* **High bounce rate (mobile)** → check analytics, optimize LCP, fix readability, compress images.
* **Dashboard design** → show KPIs first, use charts, collapsible panels, maintain accessibility.
* **Mobile issue** → test in emulators/devices, replace fixed px with %, rem, fr.
* **3-column layout (no Bootstrap)** → `grid-template-columns: repeat(auto-fit, minmax(250px,1fr));`.

---

## 🔹 Behavioral

* **Challenging project** → dashboard with big data → fixed via lazy loading + caching → load time cut by half.
* **Team disagreements** → resolve with data proof (Lighthouse, analytics), propose alternatives.
* **Client wants heavy feature** → explain trade-offs, show numbers, suggest balanced solution.
* **Stay updated** → Smashing Magazine, CSS-Tricks, MDN, experimenting with new CSS (container queries, Tailwind).
* **Ownership example** → fixed payment page bug before launch → coordinated QA → smooth delivery.

---

Perfect 👍 Here’s your **Web Design Interview Quick Revision Sheet** (one-page style, short bullet answers only):

---

# 📘 Web Design Interview – Quick Revision Sheet

### 🔹 HTML

* Inline = no new line, Block = new line, Inline-block = inline + width/height
* `alt` attribute = accessibility + SEO + fallback text
* `<section>` = thematic group, `<article>` = self-contained, `<div>` = generic
* Meta tags = SEO (description, keywords), viewport, charset
* `id` = unique, `class` = reusable
* Semantic tags improve SEO + accessibility
* HTML5 new tags: `<header>`, `<footer>`, `<section>`, `<article>`, `<nav>`
* `<!DOCTYPE html>` = declare HTML5, prevents quirks mode
* `<iframe>` = embed external content
* `<canvas>` = raster (dynamic drawing), `<svg>` = vector (scalable)

---

### 🔹 CSS

* Pseudo-class (`:hover`), Pseudo-element (`::before`)
* Position: Relative (offset), Absolute (to ancestor), Fixed (viewport), Sticky (hybrid)
* Specificity: Inline > ID > Class/Attr/Pseudo > Tag
* Units: `em` (relative parent), `rem` (root), `px` (fixed), `%` (relative)
* CSS variables: `--main-color` (reusable)
* Flexbox = 1D layout, Grid = 2D layout
* `z-index` = stacking order (needs position)
* Transition = smooth state change, Animation = keyframes
* Responsive images = `srcset` + `sizes`
* Critical CSS = inline above-the-fold

---

### 🔹 Responsive Design

* Responsive = fluid, Adaptive = fixed breakpoints
* Mobile-first = start small, scale up
* Media queries = style per screen size
* Container queries = style per parent container size
* CSS Grid `minmax()` = flexible size ranges

---

### 🔹 Optimization

* Core Web Vitals:

  * **FCP** = First content paint
  * **LCP** = Largest content paint
  * **CLS** = Layout shift
  * **TBT** = Blocking time
  * **Speed Index** = Perceived load speed
* Lazy loading = load on scroll
* CDN = fast global delivery
* Reduce render-blocking = `async/defer` JS, preload CSS
* Minify + compress images/code

---

### 🔹 General / Professional

* UX = overall experience, UI = look/feel
* Accessibility = alt text, ARIA roles, keyboard nav
* Progressive enhancement = basic first, enhance later
* Static = HTML only, Dynamic = server/db, Responsive = adapts layout
* Wireframing tools = Figma, XD, Sketch

---


