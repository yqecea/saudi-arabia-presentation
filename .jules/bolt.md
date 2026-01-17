## 2024-05-22 - Misleading Image Extensions
**Learning:** Image files in `assets/images` had `.png` extensions but were actually JPEGs (magic bytes `FF D8`). This caused initial scripts using PNG libraries to fail.
**Action:** Always verify image file headers (magic bytes) rather than relying solely on file extensions when processing binary assets.
