# Thành viên và phân vai — Day11 SVM 360 Fisheye

## 1. Thông tin nhóm

- Khóa/lớp: K4
- Tên nhóm: NhomsG
- Repo Public: https://github.com/DungTien04/K4-DAY11-Nguyen-Tien-Dung-2A202602207
- Máy giữ hồ sơ chính / người quản lý: Nguyễn Tiến Dũng
- Slice chung lấy từ mode.json: B2-mid
- Tên định danh vai A dùng cho --self: an
- Kênh trao đổi nội bộ: Zalo / Teams
- Đại diện nộp (vai C): Nguyễn Tiến Dũng - 2A202602207
- Commit chốt bài: HEAD

## 2. Ba vai chính

| Vai | Họ và tên | MSSV | Tên định danh trong mode | Trách nhiệm | Bằng chứng đóng góp |
|---|---|---|---|---|---|
| A · Gán nhãn | Nguyễn Tiến Dũng | 2A202602207 | an | Parking/C0/slice, self-QC, lock, rework | submission/r1_craft/annotations.xml, lock.txt |
| B · QA độc lập | Vũ Tuấn Hiệp | 2A202602208 | binh | Review trước reference, finding QA, kiểm lại ca sửa | submission/r2_qa/qa_review.md |
| C · Chẩn đoán & điều phối | Nguyễn Văn G | 2A202602209 | chi | Báo cáo, phân xử, kế hoạch, tích hợp, check và nộp | submission/r3_diag/model_compare.md, manifest.json |

## 3. Bàn giao theo pha

| Mốc | Người giao → nhận | File / commit / mã khóa | Người nhận đã kiểm gì? | Trạng thái / vướng mắc |
|---|---|---|---|---|
| P0 · Chốt môi trường và vai | C → A, B | mode.json, B2-mid | Đã kiểm slice chung | Hoàn thành |
| P2 · Khóa bản đầu | A → B, C | XML, lock.txt, 7E7E-3FE9 | Đã kiểm bản khóa | Hoàn thành |
| P3 · Chốt QA mù | B → C, A | qa_review.md, qa_overlay.html | Đã kiểm review độc lập | Hoàn thành |
| P4 · Quyết định sửa | C → A, B | findings.csv, decision_log.csv | Đã đối chiếu bằng chứng | Hoàn thành |
| P5 · Kiểm bản sửa | A → B → C | annotations-v2.xml, delta.md | Đã kiểm bản rework | Hoàn thành |
| P6 · Chốt nộp | A, B → C | manifest.json | Đã check exit 0 | Hoàn thành |

## 4. Bất đồng và phối hợp

- Một ca đã phân xử: adasind_060000.jpg / L1 / R01; ý kiến A gắn nhãn chi tiết, B nghi ngờ SPURIOUS; thống nhất giữ nhãn với lý do occluded=true.
- Ca còn mở: Không có.
- Đóng góp của A/B/C vào kế hoạch và exit ticket: Cả 3 cùng hoàn thiện 45_sampling_plan.csv, 46_gold_set_plan.md và 50_exit_ticket.md.
- Thay đổi phân công nếu có: Không thay đổi.

## 5. Xác nhận trước khi nộp

- [x] A xác nhận nhãn và export đúng phiên bản: Nguyễn Tiến Dũng / r1_craft annotations.xml
- [x] B xác nhận đã QA độc lập trước reference và kiểm lại ca sửa: Vũ Tuấn Hiệp / r2_qa qa_review.md
- [x] C xác nhận báo cáo đúng bản khóa, các file đầy đủ và check exit 0: Nguyễn Văn G / manifest.json
- [x] manifest.json tại commit chốt có failed_gates rỗng.
- [x] Repo nhóm Public, ảnh và các bằng chứng mở được.
- [x] C đã push và gửi link repo nhóm + commit qua kênh lớp công bố.
