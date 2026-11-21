# Báo cáo cá nhân — NguyenPhuNam-2A202603501

## 1. Thông tin thành viên

- Họ tên: Nguyễn Phú Nam
- MSSV: 2A202603501
- Email: 145128129+Manny402@users.noreply.github.com
- GitHub: [Manny402](https://github.com/Manny402)
- Vai trong nhóm: Người viết code (nhiệm vụ A, B), nhóm trưởng

## 2. Phần việc phụ trách

- Nhóm trưởng: chia vai, theo dõi tiến độ theo năm checkpoint.
- Viết code nhiệm vụ A và B trong `src/lab13.py`.

## 3. Đóng góp cụ thể

- Viết ba hàm A1 theo công thức E[số lần chạy] = (1 − (1 − p)^k) ÷ p; ba phép thử in ĐẠT (1,20 · 1,25 · 1,25).
- Viết `mo_hinh`: tử số cộng token + tool của mọi lần chạy (kể cả lỗi) và phút xem lại, làm lại; mẫu số là 978 việc thành công → 4.472 đ [simulated].
- Tách theo `loai` (A3), thêm bảng tỉ lệ ok theo lần thử để chỉ ra quoc_te chạy lại không giúp (30,0% → 11,4% → 2,2%).
- A4: cộng cố định 40 triệu/tháng → 4.599 đ = 0,38× ở 45.000 yêu cầu/tháng [simulated].
- B1–B4: 9 kịch bản, cặp (+46,3%), giới hạn chạy (2 lần rẻ nhất cho công ty), xem lại 100% (0,98×) [simulated].

## 4. Bằng chứng

- `src/lab13.py`: hàm A1, `mo_hinh`, `in_bang_a2`, `in_bang_a3`, `in_bang_a4`, `KICH_BAN_B1`, `in_bang_b`.
- Commit `feat(cost): implement cost-per-success model and sensitivity scenarios`.

## 5. Công cụ AI đã dùng

- Dùng Claude để hỏi lại cách lọc runs theo `request_id` khi giới hạn số lần chạy và soát lỗi cú pháp pandas.
- Tự kiểm tra: ba phép thử A1 phải ĐẠT; so từng số A2, A3, B1 với bảng đối chiếu trong hướng dẫn (lệch < 2%); kiểm tra kịch bản “giảm một nửa” bằng đúng nửa mức tăng của “gấp đôi”.

## 6. Tự đánh giá

- Hiểu vì sao tử số tính cả lần chạy lỗi còn mẫu số chỉ đếm việc thành công, và vì sao giới hạn rẻ nhất cho công ty (2 lần) khác giới hạn cho cps thấp nhất (1 lần).
- Cần cải thiện: tách code in bảng và code tính toán rõ hơn để dễ kiểm thử.
