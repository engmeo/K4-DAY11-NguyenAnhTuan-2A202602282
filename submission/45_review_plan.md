# Kế hoạch review từ lỗi quan sát được

Từ `findings.csv` và `zone_table.md`, chọn **hai lát cắt của bài ADASIND một camera** cần review trước. Bảng này
giải thích dữ liệu thật bạn vừa làm; nó không thay cho kế hoạch bốn camera giả lập ở `45_sampling_plan.csv`.

| Lát cắt / frame | Số ca và loại lỗi | Vì sao review trước | Bằng chứng cần giữ |
|---|---|---|---|
| B4-mid / adasind_261480.jpg | 3 mismatch: L2 SPURIOUS, R2 MISSING, R7 MISSING | Có nhiều mismatch trong cùng frame và cần phân biệt annotation lỗi với reference/model mismatch | ảnh gốc, QA overlay, findings.csv |
| B4-mid / adasind_265065.jpg | 3 MISSING: R4, R5, R7 | Reference có object nhưng annotation thiếu; cần kiểm tra theo R01 trước khi rework | ảnh gốc, compare.md, findings.csv |


Giới hạn của kết luận từ ba frame ADASIND: đây chỉ là slice ba frame, không đủ để suy ra tỷ lệ lỗi cho toàn bộ ADASIND.


## Chuyển sang kế hoạch bốn camera giả lập

Cách soát độ phủ của 200 frame ở `45_sampling_plan.csv` (kể cả tránh đếm nhiều frame liền nhau trong cùng cảnh
như nhiều ca độc lập), và vì sao kế hoạch đó chỉ giúp tìm ca cần soi, chưa đo được tỷ lệ lỗi:  phân bổ frame cho cả `normal` và `hard` của bốn camera, sau đó ưu tiên kiểm tra các frame có seam, distortion, object nhỏ/che khuất và khác biệt giữa các nguồn. Kế hoạch chỉ giúp tìm ca cần soi, chưa đo được tỷ lệ lỗi thật.
