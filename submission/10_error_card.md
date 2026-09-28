# Error analysis card

## Zone × block

| zone | block | what | count |
|---|---|---|---:|
| center | B4 | MISSING | 3 |
| center | B4 | SPURIOUS | 4 |
| edge | B4 | SPURIOUS | 1 |
| mid | B4 | MISSING | 6 |
| mid | B4 | SPURIOUS | 8 |

## Top defects
- SPURIOUS: 13 (ví dụ frame adasind_249480.jpg)
- MISSING: 9 (ví dụ frame adasind_249480.jpg)

## Phân tích của bạn

Hai bảng trên do `python3 lab11.py card` tính từ `findings.csv`; chạy lại lệnh sẽ cập nhật bảng và giữ nguyên mục này. Viết cho lỗi nổi bật nhất, dẫn frame/`object_ref`.

- Nguyên nhân khả dĩ (`why`) và vì sao bạn nghĩ vậy: Các mismatch MISSING/SPURIOUS tập trung ở vùng `mid`; một số case reference+model cùng có box nhưng annotation thiếu, nên ưu tiên kiểm tra lại annotation trên ảnh gốc. Các `M_only` không được coi là lỗi annotation chỉ từ model.
- Cách sửa và ai nhận việc (`owner`): Với case xác nhận annotation thiếu theo ảnh gốc thì `annotator` rework; với mismatch chưa đủ bằng chứng thì `qa` xác minh trước.
- Bằng chứng (ảnh trong `screenshots/`, dòng findings, rule): `submission/findings.csv`, `submission/r3_diag/model_compare.md`, `submission/r3_diag/zone_table.md`; kiểm tra theo R01 và ảnh gốc.
