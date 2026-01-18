## 2024-05-23 - Fake PNGs Discovered
**Learning:** The project contained images labeled as `.png` that were actually JPEGs. This is a confusing anti-pattern that can mislead optimization tools and developers.
**Action:** Always verify image headers before assuming file type based on extension. Use Python or similar to inspect magic bytes if CLI tools are missing.
