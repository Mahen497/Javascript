## 🔹 1. **Core Topics They Expect**

### ✅ Cross-Browser Compatibility

* Be ready to talk about:

  * **CSS Resets / Normalize.css** (handling browser default styles).
  * **Vendor prefixes** (`-webkit-`, `-moz-`, `-ms-`, etc.).
  * **Feature detection** with `@supports` in CSS or `Modernizr`.
  * **Progressive enhancement**: build for basic support, then add advanced features.

👉 Example Q: *How do you ensure a website looks consistent across browsers?*
✔️ Answer: *By using CSS resets, vendor prefixes, testing in major browsers (Chrome, Safari, Firefox, Edge), and applying progressive enhancement and graceful degradation techniques.*

---

### ✅ Web Accessibility (a11y)

* **Semantic HTML** (`<nav>`, `<header>`, `<main>`, `<button>` instead of `<div>` everywhere).
* **ARIA attributes** (`aria-label`, `aria-hidden`, `role`).
* **Keyboard navigation** (tab, enter, space).
* **Contrast & readability** (use tools like Lighthouse or Axe).
* **Alt text** for images, captions for videos.

👉 Example Q: *How would you make a carousel accessible?*
✔️ Answer: *By providing keyboard navigation (left/right arrows), proper ARIA roles (`role="region"`, `aria-live`), and visible focus indicators.*

---

### ✅ CSS Animation Libraries

* Know popular ones: **Animate.css**, **GSAP (GreenSock)**, **Framer Motion (React)**.
* Benefits:

  * Prebuilt animations (fadeIn, bounce, slide).
  * Better performance (GSAP uses `requestAnimationFrame`).
  * Can animate SVG, canvas, and DOM.

👉 Example Q: *Difference between CSS animations and JS libraries like GSAP?*
✔️ Answer: *CSS animations are simpler and browser-optimized but limited. GSAP allows complex timelines, chaining, and fine control over easing and performance.*

---

### ✅ Canvas & Visual Effects

* **Canvas basics**:

  * `getContext("2d")`
  * Drawing shapes (`fillRect`, `arc`, `stroke`).
  * Animating with `requestAnimationFrame`.
* **Use cases**: game-like animations, particle effects, charts, image manipulation.

👉 Example Q: *When would you choose Canvas over CSS animations?*
✔️ Answer: *When rendering pixel-based graphics, real-time animations, or effects like particles and games where DOM elements aren’t efficient.*

---

## 🔹 2. **Hands-On Code Prep**

### Carousel / Slider (vanilla JS)

```html
<div class="carousel">
  <div class="slide active">Slide 1</div>
  <div class="slide">Slide 2</div>
  <div class="slide">Slide 3</div>
</div>
<button id="next">Next</button>
```

```js
const slides = document.querySelectorAll(".slide");
let index = 0;
document.getElementById("next").onclick = () => {
  slides[index].classList.remove("active");
  index = (index + 1) % slides.length;
  slides[index].classList.add("active");
};
```

### CSS Animation Example

```css
@keyframes bounce {
  0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
  40% { transform: translateY(-30px); }
  60% { transform: translateY(-15px); }
}
button:hover {
  animation: bounce 1s;
}
```

### Canvas Animation Example

```html
<canvas id="myCanvas" width="400" height="200"></canvas>
<script>
const c = document.getElementById("myCanvas");
const ctx = c.getContext("2d");
let x = 0;

function draw() {
  ctx.clearRect(0,0,400,200);
  ctx.beginPath();
  ctx.arc(x,100,20,0,Math.PI*2);
  ctx.fillStyle = "blue";
  ctx.fill();
  x += 2;
  if (x > 400) x = 0;
  requestAnimationFrame(draw);
}
draw();
</script>
```

---

## 🔹 3. **Likely Interview Questions**

* **Theory**:

  * What’s the difference between `transform` and `translate` in CSS?
  * How do you optimize animations for performance?
  * Difference between `<canvas>` and `<svg>`?
  * How do you make animations accessible for people with motion sensitivity?
* **Practical**:

  * Build a simple slider without a library.
  * Animate a button on hover (bounce or pulse effect).
  * Draw a circle with canvas and make it move.

---

## 🔹 4. **Final Tips**

* Prepare a **portfolio/demo** (CodePen/GitHub) with:

  * A working carousel
  * A GSAP/Animate.css animation
  * A small canvas effect (particle or bouncing ball)
* Emphasize:

  * **Performance** (avoid layout thrashing, use `transform` & `opacity`).
  * **Accessibility** (keyboard navigation + ARIA).
  * **Cross-browser testing** (Chrome, Firefox, Safari, Edge).

