## 2026-01-28 - Misleading Image Extensions
**Learning:** The images in `assets/images/` have `.png` extensions but are actually JPEGs (magic bytes `FF D8 FF`).
**Action:** Always verify file headers when performing image optimizations or format conversions, rather than relying on file extensions. This avoids attempting transparency optimizations on files that don't support it.
