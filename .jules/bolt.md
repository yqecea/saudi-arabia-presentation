## 2024-05-22 - Deceptive File Extensions
**Learning:** The images in `assets/images/` are named with `.png` extensions but are actually JPEG files (magic bytes `FF D8 FF E0`).
**Action:** When optimizing images in this codebase, do not assume file type based on extension. Use tools or header inspection to verify. Do not rely on extension-based tools that might fail on mismatch.
