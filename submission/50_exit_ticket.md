# Exit ticket

Đọc `docs/10-svm360-reading-vi.md` trước khi trả lời câu 1–2. Các câu về zone, `why`, rework, parking và sampling
đã nằm trong file tương ứng nên không hỏi lại ở đây.

1. Một vật ở vùng seam giữa hai camera xuất hiện với hai box khác nhau: không nên tự động gọi là `DUPLICATE`; cần áp dụng quy tắc seam/cross-camera và kiểm tra evidence trước khi quyết định đó là cùng một object hay hai quan sát khác nhau.

2. Một vật đi qua nhiều frame trên cùng camera: giữ cùng track ID khi vẫn là cùng object và track liên tục; thêm keyframe khi hình học thay đổi cần mô tả lại. Khi object rời khỏi vùng quan sát thì chuyển trạng thái Outside/kết thúc track theo quy ước của bài. Không nối track qua hai camera nếu chưa có bằng chứng và policy cho phép.

3. Với trường hợp bản thân tin annotation đúng nhưng reference/reviewer khác: đối chiếu frame, object_ref, rule và ảnh gốc; không sửa chỉ vì reference khác. Nếu evidence chưa đủ thì ghi unresolved/escalate và nêu rõ cần kiểm tra gì. Nếu làm lại slice này, sẽ giữ evidence ảnh gốc và ghi rõ lý do cho từng quyết định.
