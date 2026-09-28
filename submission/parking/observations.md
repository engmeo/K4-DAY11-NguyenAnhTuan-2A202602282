# Quan sát vạch ô đỗ

- Hai vạch `parking_line` đã vẽ (mô tả vị trí trong ảnh): Hai vạch sơn trắng chéo ở khu vực phía trước ảnh, dùng để phân chia các ô đỗ xe.
- Một vạch/dấu sơn hoặc biên **không** vẽ, và vì sao: Các đường/vạch khác ở xa hoặc không xác định rõ là vạch phân chia ô đỗ nên không gán `parking_line`.
- Polygon `free_space` dừng ở đâu; có phần bị che nào không: Polygon dừng trong vùng mặt đường trống có thể quan sát được; không kéo qua các vật thể hoặc phần bị che khuất.
- Ca chưa chắc cần hỏi người soát (nếu không có, ghi “không có”): không có