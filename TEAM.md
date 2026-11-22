# TEAM — Ngày 12

Mã bộ ảnh: **G07** · Hình thức: cá nhân

| Họ tên | MSSV | Đã gán đủ 22 ảnh? | Review chéo với (peer diff) | Số dòng disagreement đã xử lý |
|---|---|---|---|---|
| Bùi Kim Trãi | 2A202603176 | có | Nguyễn Ngọc Đức (ducnn059) | 44 |

Ca hai bạn vẫn không thống nhất và đã hỏi coach (ghi tên ảnh + đối tượng):

- Ảnh `S01_ir.png` / `S01_rgb.png` (đối tượng `child_seat`): Hai bạn bất đồng về việc thuộc tính `occupied` nên ghi `yes` hay ghi `unknown` và vẽ thêm box `object`. Đã hỏi coach và thống nhất thực hiện theo hướng dẫn cập nhật của lớp là cho phép `occupied = yes`.

## Cá nhân

Mỗi người một mục, 1–2 dòng mỗi ý.

### BuiKimTrai-2A202603176
- Phần mình làm: Tự gán toàn bộ 22 ảnh cốt lõi trên CVAT cá nhân; xuất dữ liệu và chạy kiểm tra `cabin_check.py` đạt 0 lỗi 0 cảnh báo; thực hiện so sánh diff với bạn Nguyễn Ngọc Đức và phân tích, xử lý 44 dòng bất đồng trong file `disagreement_log.csv`.
- Điều mình học được hôm nay: Hiểu rõ cơ chế chiếu sáng của camera cận hồng ngoại NIR 940nm trong buồng lái; nắm vững quy tắc hệ quy chiếu không gian (trái/phải theo cơ thể người lái, vị trí ghế theo chiều tiến của xe dù camera nhìn ngược hoặc xoay 90°).
