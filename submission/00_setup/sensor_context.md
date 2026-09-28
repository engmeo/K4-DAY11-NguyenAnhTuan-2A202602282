# Sensor context

- Rig: camera fisheye gắn trên phương tiện; tài liệu ADASIND không cung cấp chi tiết chính xác về loại/mounting của rig, nên chỉ ghi nhận theo quan sát từ ảnh.
- `ego_body`: nhìn thấy một phần thân/phần người của phương tiện ở vùng mép dưới và góc trái của các frame; các phần này được xem là `ego_body`, không gán nhãn đối tượng giao thông.
- Vùng kính (lens circle): ảnh có vùng nhìn fisheye hình tròn rõ rệt, với viền đen bao quanh phần lớn chu vi khung hình; phần viền này được xử lý bằng `ignore_region` với lý do `lens_border`.