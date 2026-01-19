## 2025-05-22 - Static Asset Dimensions
**Learning:** All images in `assets/images/` are 1024x1024 pixels, despite some appearing to be landscape content in context (e.g., hero backgrounds). This implies AI-generated assets where aspect ratio matches resolution.
**Action:** When adding `width` and `height` attributes for CLS prevention in this specific project, safely default to 1024x1024 for existing assets, but verify any new assets added in the future.
