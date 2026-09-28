# Kế hoạch review từ lỗi quan sát được

Từ `findings.csv` và `zone_table.md`, chọn **hai lát cắt của bài ADASIND một camera** cần review trước. Bảng này
giải thích dữ liệu thật bạn vừa làm; nó không thay cho kế hoạch bốn camera giả lập ở `45_sampling_plan.csv`.

| Lát cắt / frame | Số ca và loại lỗi | Vì sao review trước | Bằng chứng cần giữ |
|---|---|---|---|
| adasind_060000.jpg | 16 ca MISSING | Lỗi bỏ sót vật thể tiệm cận H=40px ở rìa kính | Screenshot & XML reference |
| adasind_086220.jpg | 10 ca SPURIOUS | Model dự đoán nhầm các vệt tối ở mặt đường thành vehicle | HTML model comparison |

Giới hạn của kết luận từ ba frame ADASIND: Bộ 3 frame là mẫu nhỏ, chỉ phản ánh điều kiện ánh sáng ban ngày của 1 camera đơn, chưa đại diện cho các thời điểm ban đêm, mưa chói hoặc hệ 4 camera SVM toàn cảnh.

## Chuyển sang kế hoạch bốn camera giả lập

Cách soát độ phủ của 200 frame ở `45_sampling_plan.csv` (kể cả tránh đếm nhiều frame liền nhau trong cùng cảnh như nhiều ca độc lập), và vì sao kế hoạch đó chỉ giúp tìm ca cần soi, chưa đo được tỷ lệ lỗi: Lấy mẫu dải đều giữa 4 góc camera (front/rear/left/right) theo điều kiện bình thường và phức tạp. Việc chọn frame phân tán thời gian tránh đếm lặp trùng lặp một tình huống di chuyển, giúp phát hiện sớm các case biên mà không gây sai lệch thống kê tổng thể.
