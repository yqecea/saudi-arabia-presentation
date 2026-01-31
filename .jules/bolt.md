## 2024-05-22 - Static Image Optimization Patterns
**Learning:** In static HTML environments (no build step), explicit `width` and `height` attributes on `<img>` tags are critical for preventing Cumulative Layout Shift (CLS), even when CSS handles responsive sizing (e.g., `width: 100%`). Browsers need the aspect ratio before CSS loads.
**Action:** Always manually verify `width`/`height` attributes on static sites. Use `fetchpriority="high"` for the LCP element (hero image) and `loading="lazy"` for all others to maximize main-thread availability.
