# Đối chiếu chất lượng cục bộ — rectangle

Teaching reference, không phải gold set đã phê duyệt; không có điểm đạt tự động.
Nguồn: export r1_craft đã khóa SHA256 `b31cd18c42fd0d8aa5c04ff0d0be4fa1671894102683602bb136667f6daf92d4`; slice `B4-mid`.
Ghép hình học greedy một-một theo IoU ≥ 0.50, rồi so class; H ≥ 40 px.
Box trái nằm chủ yếu trong ignore_region reference không tính. Polygon, polyline, track không được chấm.
Đây là phép tính offline của lab, không phải báo cáo hay kết quả tương đương CVAT Premium.

Frame được tính: adasind_249480.jpg, adasind_261480.jpg, adasind_265065.jpg. Frame thiếu trong export: không.
TP=11; FP=1; FN=6; số lần đối chiếu=18; mean IoU của TP=0.863.

| Chỉ số | Micro | Macro | Nhãn thấp nhất |
|---|---:|---:|---:|
| accuracy | 0.611 | 0.922 | 0.722 |
| precision | 0.917 | 0.733 | 0.000 |
| recall | 0.647 | 0.760 | 0.000 |
| jaccard | 0.611 | 0.693 | 0.000 |
| dice | 0.759 | 0.738 | 0.000 |

| Nhãn | TP | FP | FN | Accuracy | Precision | Recall | Jaccard | Dice |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Bike | 0 | 0 | 5 | 0.722 | 0.000 | 0.000 | 0.000 | 0.000 |
| Car | 2 | 1 | 0 | 0.944 | 0.667 | 1.000 | 0.667 | 0.800 |
| Pedestrian | 4 | 0 | 1 | 0.944 | 1.000 | 0.800 | 0.800 | 0.889 |
| ThreeWheeler | 3 | 0 | 0 | 1.000 | 1.000 | 1.000 | 1.000 | 1.000 |
| Truck | 2 | 0 | 0 | 1.000 | 1.000 | 1.000 | 1.000 | 1.000 |

| Frame | TP | FP | FN | Accuracy | Precision | Recall |
|---|---:|---:|---:|---:|---:|---:|
| adasind_249480.jpg | 1 | 0 | 1 | 0.500 | 1.000 | 0.500 |
| adasind_261480.jpg | 5 | 1 | 2 | 0.625 | 0.833 | 0.714 |
| adasind_265065.jpg | 5 | 0 | 3 | 0.625 | 1.000 | 0.625 |

Confusion matrix: hàng = teaching reference; cột = export đã khóa.
`<missing>` là thiếu box; `<extra>` là box thừa. Xem `local_quality_confusion.csv`.

| Reference \ Export | Bike | Car | Pedestrian | ThreeWheeler | Truck | <missing> |
|---|---:|---:|---:|---:|---:|---:|
| Bike | 0 | 0 | 0 | 0 | 0 | 5 |
| Car | 0 | 2 | 0 | 0 | 0 | 0 |
| Pedestrian | 0 | 0 | 4 | 0 | 0 | 1 |
| ThreeWheeler | 0 | 0 | 0 | 3 | 0 | 0 |
| Truck | 0 | 0 | 0 | 0 | 2 | 0 |
| <extra> | 0 | 1 | 0 | 0 | 0 | 0 |

Chi tiết xung đột trong `local_quality_conflicts.csv`; dữ liệu máy đọc trong `local_quality.json`.
Mismatching label đóng góp một FP cho class vẽ và một FN cho class reference; attribute khác được báo riêng.
Micro accuracy đếm mỗi cặp ghép sai class là một lần đối chiếu; Jaccard đếm cả FP và FN.
Macro/worst bỏ nhãn không xuất hiện ở cả hai phía; chỉ số không có mẫu là N/A.
