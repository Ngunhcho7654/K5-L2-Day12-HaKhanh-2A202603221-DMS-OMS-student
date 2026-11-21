# Tự đánh giá — HaKhanh (2A202603221)

## 1. Tự rà soát 4 cảnh

Nghỉ tay 1 phút, mở lại bài của mình, chọn 4 ảnh (2 S##, 2 D##), đọc như người lạ.

Loại lỗi: `seat_flip`, `wrong_class`, `guess`, `box`, `missing`, `extra`, `lr_flip` (trái/phải mặt), `flag` (thiếu cờ điểm), `ok`.

| Ảnh | Đối tượng | Loại lỗi | Ghi chú | Đã sửa? |
|---|---|---|---|---|
| S01_rgb | frame_meta | guess | Ban đầu gán `light` khác `unknown` trên ảnh SVIRO dựng bằng máy tính | Đã sửa về `light = unknown` |
| S03_rgb | child_seat / frame_meta | wrong_class | Đã sửa `frame_meta.light = unknown`; còn thuộc tính `child_seat.occupied = yes` (cần kiểm tra lại theo guideline chỉ dùng `no`/`unknown`) | Đã sửa `light`; `occupied` cần rà lại trên CVAT |
| D01 | person, face, face13, hand | ok | Đủ 13 điểm `face13`, 2 tay trái/phải đúng theo người lái, đủ `frame_meta` | OK |
| D06 | hand | lr_flip | Ban đầu gán nhầm cả 2 bàn tay tài xế (`whose=driver`) cùng `side=left` | Đã sửa thành 1 `left`, 1 `right` |

## 2. Lỗi mình lặp lại nhiều nhất hôm nay

Lỗi: Gán `frame_meta.light` khác `unknown` trên các ảnh SVIRO `_rgb` và chọn nhầm `child_seat.occupied = yes`.

Vì sao mình mắc: Nhìn ảnh `_rgb` thấy sáng nên chọn theo cảm quan mà quên ảnh SVIRO là ảnh dựng (`light = unknown`); chọn `occupied = yes` theo trực quan mà chưa bám sát giới hạn giá trị `no`/`unknown` của guideline.

Lần sau tránh bằng cách: Đặt tag `frame_meta` theo đúng quy tắc ngay từ đầu trước khi vẽ box, kiểm tra lại bảng thuộc tính hợp lệ ở `GUIDE.md` §4.1–§4.8 và chạy `cabin_check.py` sớm ở từng checkpoint.

## 3. Ghi chú về disagreement_log

Ghi chú: Trong buổi học chưa tìm được bạn cùng mã bộ ảnh để review chéo (`diff`) nên chưa có file `disagreement_log.csv`. Đã tự rà soát lại bộ 22 ảnh cốt lõi theo `GUIDE.md` và tự kiểm bằng `cabin_check.py`; sẽ bổ sung review chéo nếu được ghép cặp sau.
