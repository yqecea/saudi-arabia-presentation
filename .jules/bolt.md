## 2024-05-23 - Static Site Image Optimization
**Learning:** For static sites without a build step, `loading="lazy"` and `fetchpriority="high"` are the highest ROI optimizations.
**Action:** Always check `index.html` for LCP candidates and apply `fetchpriority="high"` while lazy loading everything else.
