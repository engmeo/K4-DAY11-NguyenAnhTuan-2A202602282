# Zone table (slice của bạn)

Lệnh `python3 lab11.py model` tự ghi bảng số (cùng cách đếm với `r1_craft/compare.md` và `model_compare.md`); chạy lại lệnh sẽ cập nhật bảng và giữ nguyên phần nhận xét. Bạn chỉ viết mục Nhận xét.

| Zone | n_ref | L missing | L spurious | M missing (`LR_noM` + `R_only`) | M thừa (`LM_noR` + `M_only`) | Lỗi L chính (`what`) |
|---|---:|---:|---:|---:|---:|---|
| center | 4 | 2 | 0 | 1 | 4 | MISSING (2) |
| mid | 13 | 4 | 1 | 3 | 7 | MISSING (4) |
| edge | 0 | 0 | 0 | 0 | 1 | — |

## Nhận xét

- Zone mid gây nhiễu nhiều nhất cho cả L và M: có 4 L missing, 1 L spurious, 3 M missing và 7 M thừa; center đứng sau với 2 L missing và 4 M thừa. Edge không có reference nên khó đánh giá mismatch.
- Khả năng chính là vùng mid có nhiều đối tượng và biến dạng fisheye hơn, làm tăng khó khăn khi đặt/ghép box; tuy nhiên slice chỉ có ba frame nên chưa đủ bằng chứng để kết luận nguyên nhân tổng quát cho toàn bộ dữ liệu.
