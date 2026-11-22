# Tự đánh giá — Bùi Kim Trãi · G07

## 1. Tự rà soát 4 cảnh

| Ảnh | Đối tượng | Loại lỗi | Ghi chú | Đã sửa? |
|---|---|---|---|---|
| D02.png | `person` | `ok` | Dây an toàn nhìn rõ dải vắt chéo, gán worn_correct | Có |
| D04.png | `face13` | `flag` | Mắt phải dưới đốm phản quang và mắt trái trong bóng tối ban đầu thiếu cờ occluded/outside | Đã sửa |
| S01_rgb.png | `child_seat` | `box` | Box ghế trẻ em cần ôm trọn toàn bộ thân ghế, không chừa mép ngoài | Đã sửa |
| S02_ir.png | `child_seat` | `seat_flip` | Ban đầu để mặc định seat=driver, sau khi rà soát đã chỉnh lại thành rear_right theo xe | Đã sửa |

## 2. Lỗi mình lặp lại nhiều nhất hôm nay

* **Lỗi:** Quên đổi thuộc tính vị trí ghế (`seat`) từ giá trị mặc định `driver` sang các ghế sau (`rear_left`, `rear_right`, `rear_middle`) trên các ảnh OMS (SVIRO), và nhầm lẫn trái/phải theo góc nhìn ảnh thay vì theo chiều xe.
* **Vì sao mình mắc:** Khi tạo bounding box mới, phần mềm CVAT tự động điền thuộc tính đầu tiên là `driver`. Do quán tính thao tác nhanh nên không mở tab DETAILS để chỉnh lại ngay. Ngoài ra góc nhìn camera chiếu từ trước ra sau khiến bên trái ảnh thực tế lại là bên phải của xe.
* **Lần sau tránh bằng cách:** Áp dụng nguyên tắc "nói to tên ghế theo xe trước khi vẽ box"; ngay khi kéo xong hình hộp lập tức mở bảng thuộc tính chọn đúng ghế; thường xuyên chạy script `cabin_check.py` để bắt các cảnh báo `seat=driver` sớm.

## 3. Ghi chú về disagreement_log

* Ở ảnh `S04_ir.png`, đối với nhãn nôi em bé `infant_seat`, bạn mình chọn `facing = rear` trong khi mình chọn `front`. Sau khi thảo luận và tra cứu tiêu chuẩn an toàn xe hơi, nôi trẻ sơ sinh luôn bắt buộc lắp quay mặt về phía sau xe (`rear-facing`) để bảo vệ vùng đầu và cổ của bé khi phanh gấp. Đồng thời ở ảnh `S03_ir.png` và `S03_rgb.png`, mình cũng tiếp thu góp ý của bạn và chỉnh lại nhãn `object.type` từ `other` sang `cup` cho đồ vật có hình dáng cốc nước, sau đó xuất ra bản cập nhật `export_final_v2.zip`. Mình học được rằng khi gán nhãn dữ liệu cabin xe hơi, hiểu biết về an toàn xe thực tế giúp đưa ra quyết định nhãn chuẩn xác hơn nhiều so với việc chỉ nhìn cảm tính.
