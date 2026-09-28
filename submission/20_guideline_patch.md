# Guideline patch

- **Rule mới đề xuất:** Khi reference và model cùng có một đối tượng nhưng annotation thiếu, phải kiểm tra ảnh gốc trước khi rework; model mismatch một mình không đủ bằng chứng.
- **Áp dụng cho:** B4-mid, các object mismatch MISSING/SPURIOUS, đặc biệt vùng mid.
- **Vì sao luật hiện tại (`docs/02-rules-vi.md`) không đủ:** R01 quy định vật >=40 px phải có box nhưng chưa mô tả quy trình xử lý khi reference/model bất đồng với annotation.
- **`rules_version` mới:** v1.1.0
- **Hiệu lực từ:** round rework sau khi guideline patch được review.
