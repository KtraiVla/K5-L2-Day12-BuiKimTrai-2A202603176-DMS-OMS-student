# TEAM — Ngày 12

Mã bộ ảnh: **G07** · Hình thức: cá nhân

| Họ tên | MSSV | Đã gán đủ 22 ảnh? | Review chéo với (peer diff) | Số dòng disagreement đã xử lý |
|---|---|---|---|---|
| Bùi Kim Trãi | 2A202603176 | có | Nguyễn Ngọc Đức (ducnn059) | 44 |

Trường hợp chưa thống nhất và đã hỏi coach (ghi tên ảnh + đối tượng):

- Ảnh `S01_ir.png` / `S01_rgb.png` (đối tượng `child_seat`): Mình và bạn Đức phân vân chỗ thuộc tính `occupied` nên để `yes` hay để `unknown` và vẽ thêm box `object`. Sau khi hỏi coach thì thống nhất chọn `occupied = yes` theo hướng dẫn cập nhật của lớp.

## Cá nhân

### BuiKimTrai-2A202603176
- Phần mình làm: Tự gán đủ 22 ảnh cốt lõi trên CVAT cá nhân; xuất dữ liệu và chạy kiểm tra đạt 0 lỗi 0 cảnh báo; so sánh diff với bạn Nguyễn Ngọc Đức và cùng thảo luận xử lý 44 dòng bất đồng trong file `disagreement_log.csv`.
- Điều mình học được hôm nay: Hiểu rõ cơ chế chiếu sáng của camera cận hồng ngoại NIR 940nm; nắm chắc quy tắc hệ quy chiếu không gian (trái/phải tính theo người lái, vị trí ghế theo chiều tiến của xe dù camera nhìn ngược hoặc xoay 90°).
