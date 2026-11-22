# Danh sách lớp v0 — Bùi Kim Trãi · G07

## DMS (ít nhất 6 lớp)

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng DMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | `face.eye_left` / `eye_right` | open / closed / unknown | Phát hiện tài xế buồn ngủ (mắt nhắm lâu) để cảnh báo tức thì | Có, trừ khi tròng kính bị đốm phản xạ LED che khuất |
| 2 | `face.gaze_zone` | road / mirror_l / mirror_r / mirror_c / cluster / center / lap / other | Phát hiện mất tập trung (xác định tài xế có nhìn đường hay nhìn xuống đùi, nhìn màn hình) | Có, qua hướng quay mặt và hướng nhìn của mắt |
| 3 | `face.glasses` | none / clear / sun / unknown | Nhận diện tài xế có đeo kính không để chỉnh thuật toán ước lượng mắt và vùng nhìn | Có (thấy rõ gọng kính và tròng kính) |
| 4 | `hand.on_wheel` | yes / no / unknown | Kiểm tra tài xế có đặt tay trên vô lăng không (Hands-On Detection) khi xe chạy tự lái | Có, thấy rõ bàn tay đặt trên vành vô lăng |
| 5 | `phone.state` | held / mounted / lap | Phát hiện tài xế sử dụng điện thoại khi đang lái xe để phát cảnh báo an toàn | Có, khi thấy cạnh máy hoặc màn hình |
| 6 | `person.seatbelt` | worn_correct / worn_incorrect / not_worn / unknown | Cảnh báo tài xế chưa thắt dây an toàn hoặc thắt sai quy cách trước khi xe chạy | Có, nhờ dải dây tối màu tương phản rõ trên áo |

## OMS (ít nhất 6 lớp)

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng OMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | `person.seat` | rear_left / rear_middle / rear_right | Nhận diện vị trí có người ngồi ghế sau để điều chỉnh điều hòa và nhắc thắt dây an toàn | Có, phân biệt rõ dáng người trên ghế |
| 2 | `child_seat` | seat, occupied | Nhận biết có ghế trẻ em trên xe để điều chỉnh lực bung túi khí phù hợp | Có, thấy cấu trúc khung ghế trẻ em |
| 3 | `infant_seat` | seat, facing | Kiểm tra nôi em bé có đặt đúng hướng quay về sau (rear-facing) không; tắt túi khí ghế trước | Có, thấy hình dáng nôi và hướng đặt quai |
| 4 | `object.type` | bag / box / cup / other | Phát hiện đồ vật bỏ quên khi rời xe hoặc vật rơi tự do gây nguy hiểm khi phanh gấp | Có, dựa trên hình khối đặc trưng của vật |
| 5 | `person.seatbelt` | worn_correct / not_worn / unknown | Kiểm tra hành khách hàng ghế sau đã cài dây an toàn đúng luật hay chưa | Nhìn thấy một phần, hạn chế nếu áo tối màu |
| 6 | `frame_meta.camera_blocked` | yes / no | Cảnh báo hệ thống khi camera cabin bị hành lý che khuất hoặc bị bẩn | Có, khung hình bị mất nét hoặc tối đen |

## 2 câu hỏi leo thang

1. **Câu hỏi:** Khi trong ghế trẻ em (`child_seat`) có đặt một vật dụng hoặc đồ chơi, quy định nên ưu tiên dùng thuộc tính `occupied = yes` của ghế hay bắt buộc phải vẽ thêm một bounding box `object` đè lên bên trong?
   * **Khung ví dụ:** `S01_rgb.png` (hàng ghế sau bên phải).
   * **Tạm gán và lý do:** Tạm thời gán box `child_seat` có thuộc tính `occupied = yes` theo hướng dẫn của giảng viên trên lớp, không vẽ thêm box `object` để tránh chồng lấn nhãn.

2. **Câu hỏi:** Đối với điện thoại gắn trên giá đỡ (`phone.state = mounted`), nếu giá đỡ kẹp che mất phần lớn thân máy và chỉ thấy một góc cạnh viền phản quang thì có được xem là đủ điều kiện vẽ box `phone` hay không?
   * **Khung ví dụ:** `D05.png`.
   * **Tạm gán và lý do:** Tạm thời vẽ box `phone` ôm phần máy thấy được và chọn `state = mounted` vì nhìn thấy rõ cạnh viền điện thoại gắn trên giá đỡ.
