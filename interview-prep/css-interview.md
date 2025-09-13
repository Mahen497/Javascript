1. First Contentful Paint (FCP) – 1.2s
	👉 Definition: Time it takes for the browser to render the first piece of content (text, image, SVG, canvas).

	✅ How to improve further:
		Optimize critical CSS (inline above-the-fold CSS).
		Compress images (WebP/AVIF).
		Use font-display: swap for custom fonts.

----------------------------------------------------------------
2. Largest Contentful Paint (LCP) – 2.0s
	👉 Definition: Time it takes for the largest visible element (like hero image/banner text) to fully render.

	✅ How to improve further:
		Optimize banner image → use WebP format, resize properly.
		Use lazy loading for below-the-fold images (we already added this).
		Serve images via CDN for faster delivery.
	

----------------------------------------------------------------

3. Total Blocking Time (TBT) – 380ms
	👉 Definition: Measures how much time the main thread was blocked by long JavaScript tasks (anything >50ms).

	✅ Fixes:
		Minimize JavaScript execution (don’t load big scripts in <head>).
		Split JS into smaller chunks (code-splitting).
		Use defer or async on <script> tags.
		Remove unused JS (e.g., no jQuery if not needed).

----------------------------------------------------------------

4. Cumulative Layout Shift (CLS) – 0.114
	👉 Definition: Measures how much elements move around while the page is loading.

	✅ Fixes:
		Always define width & height (or aspect-ratio) for images/videos so space is reserved.
		Don’t insert ads or banners dynamically without reserving space.
		Use font-display: swap → prevents text shifting when custom fonts load.

----------------------------------------------------------------

5. Optimize JS (TBT fix)
	Right now, your JS has placeholder logic (loading image swap).
	It might block rendering if written inefficiently.

	✅ Rewrite as:

	document.addEventListener("DOMContentLoaded", () => {
	  document.querySelectorAll("img[data-src]").forEach(img => {
	    img.src = img.dataset.src;  // load real image
	    img.onload = () => img.classList.add("loaded"); // fade-in effect
	  });
	});


	👉 Why better?

	Runs after DOM is parsed (no blocking).

	Async image replacement.

----------------------------------------------------------------