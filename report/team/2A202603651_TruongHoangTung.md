# Báo cáo cá nhân — TruongHoangTung-2A202603651

## 1. Thông tin thành viên

- Họ tên: Trương Hoàng Tùng
- MSSV: 2A202603651
- Email: 186200067+Dobit25@users.noreply.github.com
- GitHub: [Dobit25](https://github.com/Dobit25)
- Vai trong nhóm: Người gắn nhãn 1

## 2. Phần việc phụ trách

- Theo dõi điều kiện “Xong khi” của từng checkpoint.
- Gắn nhãn độc lập 20 ca (CP3), viết bảng khắc phục.
- Viết `chi_so.md` (E1, E2).

## 3. Đóng góp cụ thể

- Gắn nhãn độc lập 20 ca trong 8 phút, không trao đổi; lệch với người gắn nhãn 2 ở ca 8 và ca 13.
- Viết bảng khắc phục 5 ca (9, 7, 18, 4, 17), mỗi dòng có event, ngưỡng, tần suất và một vai trò phụ trách.
- Viết `in_chi_so` trong `src/lab13.py`: chính 82,83% (994/1.200), bỏ qua gợi ý 27,12% (48/177), mở lại 4,25% (51/1.200).
- Đề xuất thêm chỉ số dùng (% yêu cầu mở bằng trợ lý) và chỉ số an toàn (% đơn sai tiền qua kiểm tra mẫu); 11 event có `trace_id`; 4 dòng rủi ro kinh tế lấy số từ bảng độ nhạy.

## 4. Bằng chứng

- `report/team/bang_loi.md` (cột nhãn người 1, bảng khắc phục), `report/team/chi_so.md`, `src/lab13.py` (`in_chi_so`).
- Commit `docs(errors): add independent labels, agreement rate and remediation table`, `feat(metrics): compute E1 metrics and add event list and economic risks`.

## 5. Công cụ AI đã dùng

- Dùng Claude để hỏi lại định nghĩa năm loại lỗi Google PAIR trước khi gắn nhãn (không dùng để gắn nhãn).
- Tự kiểm tra: mỗi chỉ số E1 đều chỉ ra được event dùng để tính; số trong bảng rủi ro khớp với `bang_chi_phi.md`.

## 6. Tự đánh giá

- Hiểu khác nhau giữa lỗi hệ thống (đã lộ ra) và lỗi ngầm (chỉ phát hiện qua kiểm tra mẫu).
- Cần cải thiện: đọc kỹ phạm vi trợ lý trước khi gắn nhãn các ca ngoài phạm vi.
