# Đề xuất gold set theo camera — tình huống giả lập

**Đầu bài:** 50.000 frame từ bốn camera SVM, ngân sách chọn 200 frame để review/gold. Đây là tình huống trên slide,
**không phải** 50.000 frame có trong repo. Phân bổ đúng 200 ở `45_sampling_plan.csv` cho bốn camera, mỗi camera có
normal và hard slice. “Gold set” ở đây là **kế hoạch tạo** reference sau kiểm chứng, không phải teaching reference
ADASIND hoặc nhãn bạn vừa vẽ. Nếu cần, dùng `notebooks/day11-svm360-colab.ipynb` để thử tổng phân bổ; notebook
không làm thay phần lý do.

| camera_id | Hard case cần chọn | Vì sao dễ sai | Annotation space / calibration cần giữ | Cách review trước khi gọi là gold |
|---|---|---|---|---|
| front | Đèn pha chói, xe rẽ cắt ngang | Biến dạng fisheye ánh sáng chói | Giữ nguyên gốc 2D image coordinates & intrinsic fisheye calib | 2 QA review độc lập mù, consensus >95% IoU |
| rear | Bụi bẩn đọng kính, điểm mù đùi | Che khuất nặng bởi cản sau xe | Giữ vùng polygon ignore cho vết bẩn kính | Cross-check với cảm biến siêu âm / radar |
| left | Xe máy chen ngang sát sườn | Méo mép kính fisheye cực đại | Bắt buộc vẽ sát viền thực tế, không nắn thẳng | Dual-annotator review + Senior Editor sign-off |
| right | Chơi đêm, ánh sáng đèn đường mờ | Tỷ lệ tương phản cực thấp | Đánh dấu thuộc tính occluded & truncated rõ ràng | Review trên ảnh tăng cường độ sáng (contrast boosted) |

- Khi nào cần refresh gold set (đổi camera, calibration hoặc rule): Refresh lại gold set khi hệ thống thay đổi vị trí gá đặt camera (rig change), thay đổi thông số hiệu chuẩn ống kính fisheye hoặc cập nhật phiên bản guideline nhãn mới (major version).
- Một ca seam/cross-camera cần policy và evidence trước khi ghép hai box: Cần chính sách đồng bộ thời gian (timestamp synchronization) chính xác đến từng millisecond và phép biến đổi tọa độ không gian 3D trước khi quyết định merge 2 bbox từ 2 camera đè vùng seam.
- Vì sao peer agreement hoặc quality report trên ảnh một camera chưa chứng minh gold set đúng cho cả bốn camera: Đánh giá trên 1 camera đơn lẻ không đo lường được các lỗi do méo viền ở vùng giao thoa (seam zone), hiện tượng chuyển giao đối tượng (tracking handover) và sự khác biệt về đặc tính phơi sáng giữa các góc camera khác nhau.
