## 2025-01-23 - Image Optimization & Log Management
**Learning:** When adding explicit `width` and `height` attributes for CLS optimization, ensure the aspect ratio matches the intrinsic image or that CSS handles the display ratio (e.g., `object-fit: cover`). Also, generated log files like `server.log` from background processes must be excluded or deleted before submission to avoid polluting the repo.
**Action:** Always verify image dimensions and check for generated artifacts before committing.
