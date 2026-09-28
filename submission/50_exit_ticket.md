# Exit ticket

Đọc `docs/10-svm360-reading-vi.md` trước khi trả lời câu 1–2. Các câu về zone, `why`, rework, parking và sampling
đã nằm trong file tương ứng nên không hỏi lại ở đây.

1. Một vật ở vùng seam giữa hai camera thật xuất hiện với hai box khác nhau: đó là lỗi `DUPLICATE` hay cần một quy
   tắc riêng? Vì sao? Đây cần một quy tắc riêng (Cross-camera Seam Policy) chứ không chỉ đơn thuần là DUPLICATE đơn lẻ trên 1 camera. Vì mỗi camera có hệ tọa độ 2D riêng và góc nhìn fisheye biến dạng khác nhau; việc quyết định 2 box 2D ở 2 camera có thuộc về cùng 1 vật thể 3D trong không gian hay không phụ thuộc vào đồng bộ thời gian và ma trận hiệu chuẩn camera (extrinsic calibration).
2. Một vật đi qua nhiều frame trên cùng camera: khi nào giữ cùng track ID, khi nào thêm keyframe hoặc trạng thái
   Outside? Nêu bằng chứng sẽ cần trước khi nối track qua hai camera. Giữ cùng Track ID khi đối tượng di chuyển liên tục và không bị khuất hoàn toàn quá số frame quy định. Thêm keyframe khi đối tượng thay đổi hướng/kích thước mạnh, và gắn trạng thái Outside khi đối tượng ra khỏi tầm nhìn hoàn toàn. Bằng chứng cần trước khi nối track qua 2 camera là: timestamp trùng khớp, ma trận biến đổi tọa độ 3D và vector hướng di chuyển (velocity vector) tương thích.
3. Nhìn lại cả buổi: một chỗ bạn tin nhãn mình đúng nhưng reference hoặc người soát nghĩ khác (dẫn frame/`object_ref`),
   bạn đã xử lý thế nào, và nếu làm lại slice này bạn sẽ đổi gì trong cách làm? Tại frame adasind_060000.jpg đối tượng L1, nhãn ban đầu vẽ sát theo bóng mờ vật thể, nhưng QA cho rằng là SPURIOUS. Nhóm đã xem lại ảnh đối chiếu gốc và quy tắc R01 để thống nhất giữ nhãn với ly do occluded=true và ghi vào decision log. Nếu làm lại, nhóm sẽ soát kỹ các vật ở rìa trước khi lock để giảm bớt số ca cần phân xử ở P4.
