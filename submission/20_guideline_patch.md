# Guideline patch

- **Rule mới đề xuất:** R12_edge_occlusion - Bắt buộc gắn thuộc tính occluded=true cho mọi vật thể ở vùng rìa góc rộng (edge zone) bị cắt quá 30% bởi lens border.
- **Áp dụng cho:** Tất cả các class đối tượng ở vùng edge zone và rìa kính fisheye.
- **Vì sao luật hiện tại (`docs/02-rules-vi.md`) không đủ:** Luật hiện tại chỉ định nghĩa truncated chung chung cho biên ảnh, chưa làm rõ quy tắc gán nhãn cho vật thể vừa bị biến dạng fisheye vừa bị viền đen lens border cắt ngang.
- **`rules_version` mới:** v1.1.0
- **Hiệu lực từ:** r3_diag và rework round
