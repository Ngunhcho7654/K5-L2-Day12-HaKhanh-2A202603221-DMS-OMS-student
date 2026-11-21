# Khai báo dùng AI — HaKhanh (2A202603221)

Nhắc lại: không đưa ảnh cabin hay ảnh tài xế (kể cả ảnh chụp màn hình) cho bất kỳ công cụ AI nào.

| # | Công cụ | Bạn hỏi gì (tóm tắt) | Bạn dùng kết quả thế nào | Bạn có kiểm lại không? Bằng gì? |
|---|---|---|---|---|
| 1 | Antigravity | Hỏi định dạng export CVAT và vị trí đặt file export / `annotations.xml` | Export định dạng `CVAT for images 1.1` (bỏ chọn `Save images`) và đặt file `.zip` tại thư mục gốc của repo | Có, kiểm bằng `python -m zipfile -l` và đối chiếu `CHECKPOINTS.md`, `SUBMISSION.md` |
| 2 | Antigravity | Hỏi cách chạy `scripts/cabin_check.py` cho checkpoint và `export_final.zip`, cách lấy log bước tiếp theo | Chạy các lệnh `cabin_check.py check` để xuất `check_cpA.txt`, `check_cpB.txt`, `check_final.txt` | Có, xem trực tiếp output lệnh và các file `check_*.txt` |
| 3 | Antigravity | Nhờ tạo khung `self_review.md` (kèm ghi chú chưa tìm được người review chéo) và hỗ trợ git commit/push các file cần thiết | Tạo `self_review.md`, `prompts.md` và push lên GitHub (không kèm ảnh) | Có, kiểm tra lại nội dung file và `git status` / `git log` |
