# Đề xuất gold set theo camera — tình huống giả lập

| camera_id | Hard case cần chọn | Vì sao dễ sai | Annotation space / calibration cần giữ | Cách review trước khi ghi là gold |
|---|---|---|---|---|
| front | distortion và object nhỏ | Box dễ lệch hình học | tọa độ ảnh gốc và calibration | peer review + kiểm tra R01/R02 |
| rear | object bị che/khuất | dễ nhầm occluded/truncated | ảnh gốc + attribute | kiểm tra ảnh gốc trước khi freeze |
| left | seam/cross-camera | có nguy cơ duplicate | boundary/seam evidence | review cả hai phía trước khi ghép |
| right | lens/edge distortion | dễ đặt box sai ở rìa | lens_border + ảnh gốc | kiểm tra R08/R09 |

- Khi nào cần refresh gold set (đổi camera, calibration hoặc rule): Khi calibration, rule hoặc phân bố dữ liệu thay đổi đủ để reference hiện tại không còn đại diện.
- Một ca seam/cross-camera cần policy và evidence trước khi ghép hai box: Phải xác định đó là cùng một object qua evidence hình ảnh và policy seam; không ghép chỉ vì hai box gần nhau.
- Vì sao peer agreement hoặc quality report trên ảnh một camera chưa chứng minh gold set đúng cho cả bốn camera: Vì mỗi camera có góc nhìn, distortion và seam khác nhau; agreement trên một camera không đại diện tự động cho ba camera còn lại.