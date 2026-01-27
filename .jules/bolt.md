## 2024-05-22 - Asset Format Misleading
**Learning:** Images in `assets/images/` with `.png` extension are actually JPEG files (magic bytes `FF D8 FF`). This explains why they lack transparency and file sizes might be different than expected for PNGs.
**Action:** Do not attempt PNG-specific optimizations (like pngquant) without verifying file type first. Treat them as JPEGs for compression purposes.
