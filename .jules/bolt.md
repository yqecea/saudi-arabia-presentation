## 2024-05-22 - Misleading File Extensions
**Learning:** Files in `assets/images/` are named with `.png` extensions but are actually JPEG files (start with `\xff\xd8`).
**Action:** When optimizing or resizing images, always check file headers rather than relying on extensions. Tools or browsers might handle it, but it can lead to confusion during optimization (e.g., choosing compression settings).
