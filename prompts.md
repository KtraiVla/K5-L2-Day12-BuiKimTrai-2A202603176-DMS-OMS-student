# Khai báo dùng AI — Bùi Kim Trãi · 2A202603176

| # | Công cụ | Bạn hỏi gì (tóm tắt) | Bạn dùng kết quả thế nào | Bạn có kiểm lại không? Bằng gì? |
|---|---|---|---|---|
| 1 | ChatGPT | Hỏi cách xử lý lỗi khi chạy script `cabin_check.py` báo thiếu file `export_final.zip` do CVAT xuất thành 2 job riêng | Dùng lệnh Python gộp các ảnh từ job 22 (OMS) và job 23 (DMS) vào chung 1 file XML để ra đủ 22 ảnh cho `export_final.zip` | Có, kiểm tra lại bằng lệnh `python -m zipfile -l export_final.zip` thấy chỉ có file `annotations.xml` không kèm ảnh |
| 2 | ChatGPT | Hỏi nguyên nhân các lỗi ERROR về `child_seat occupied` và cảnh báo `seat=driver` trên ảnh SVIRO | Hiểu quy định thuộc tính và cập nhật lại file `cabin_schema.py` cho phép `occupied = yes` theo hướng dẫn của giảng viên trên lớp | Có, chạy lại script `cabin_check.py` kiểm tra kết quả báo 0 lỗi, 0 cảnh báo |
| 3 | ChatGPT | Nhờ giải thích các thuật ngữ vùng nhìn (gaze_zone) và quy tắc đặt cờ cho các điểm mốc mắt face13 khi bị đốm LED che | Điền các cột verdict, guideline_rule và action trong file `disagreement_log.csv` chuẩn theo tài liệu GUIDE | Có, đối chiếu lại trực tiếp với mục 4.4, 4.5 và 4.7 trong tài liệu `GUIDE.md` |
| 4 | ChatGPT | Tham khảo ý tưởng về các chức năng thực tế của hệ thống DMS và OMS để hoàn thiện bảng danh sách lớp | Chọn lọc và viết lại các ứng dụng của từng nhãn vào file `class_list_v0.md` cho phù hợp với bài học | Có, tự soát lại bảng nhãn và slide bài giảng số 54 |
