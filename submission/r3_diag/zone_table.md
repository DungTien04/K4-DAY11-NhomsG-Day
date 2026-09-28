# Zone table (slice của bạn)

Lệnh `python3 lab11.py model` tự ghi bảng số (cùng cách đếm với `r1_craft/compare.md` và `model_compare.md`); chạy lại lệnh sẽ cập nhật bảng và giữ nguyên phần nhận xét. Bạn chỉ viết mục Nhận xét.

| Zone | n_ref | L missing | L spurious | M missing (`LR_noM` + `R_only`) | M thừa (`LM_noR` + `M_only`) | Lỗi L chính (`what`) |
|---|---:|---:|---:|---:|---:|---|
| center | 9 | 7 | 0 | 5 | 8 | MISSING (7) |
| mid | 8 | 6 | 0 | 4 | 10 | MISSING (6) |
| edge | 3 | 2 | 0 | 2 | 0 | MISSING (2) |

## Nhận xét

- Zone người (L) và model (M) bỏ sót (missing) nhiều nhất là vùng `center` (7 ca L missing, 5 ca M missing) và `mid` (6 ca L missing, 4 ca M missing).
- Nguyên nhân chủ yếu do độ biến dạng cao của ống kính fisheye ở rìa, các đối tượng bị che khuất một phần hoặc kích thước tiệm cận ngưỡng H=40px, dẫn đến việc model phát hiện thừa (M thừa) ở trung tâm và bỏ sót ở vùng biên. Giới hạn của 3 frame là chưa đại diện đầy đủ cho toàn bộ góc quay 360 độ.
