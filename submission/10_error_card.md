# Error analysis card

## Zone × block

| zone | block | what | count |
|---|---|---|---:|
| center | B2 | MISSING | 16 |
| center | B2 | SPURIOUS | 8 |
| center | C0 | MISSING | 2 |
| center | C0 | SPURIOUS | 1 |
| edge | B2 | MISSING | 5 |
| edge | C0 | WRONG_CLASS | 1 |
| mid | B2 | MISSING | 12 |
| mid | B2 | SPURIOUS | 10 |
| mid | C0 | MISSING | 2 |

## Top defects
- MISSING: 37 (ví dụ frame adasind_019560.jpg)
- SPURIOUS: 19 (ví dụ frame adasind_019560.jpg)
- WRONG_CLASS: 1 (ví dụ frame adasind_019560.jpg)

## Phân tích của bạn

Hai bảng trên do `python3 lab11.py card` tính từ `findings.csv`; chạy lại lệnh sẽ cập nhật bảng và giữ nguyên mục này. Viết cho lỗi nổi bật nhất, dẫn frame/`object_ref`.

- Nguyên nhân khả dĩ (`why`) và vì sao bạn nghĩ vậy: Lỗi MISSING chiếm đa số (37 ca), nguyên nhân chính do vật thể ở rìa xa bị che khuất hoặc bị méo do hiệu ứng fisheye (E1_annotator_error và E4_model_domain).
- Cách sửa và ai nhận việc (`owner`): Chuyển cho annotator bổ sung các ô bbox sát viền theo đúng rule R01/R02 và AI team điều chỉnh threshold ghép cặp cho ảnh méo góc rộng.
- Bằng chứng (ảnh trong `screenshots/`, dòng findings, rule): Bằng chứng lưu tại screenshots/qa_evidence_1.png và dòng r3_diag trong findings.csv liên quan tới frame adasind_060000.jpg.
