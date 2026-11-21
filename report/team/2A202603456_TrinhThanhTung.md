# Báo cáo cá nhân — TrinhThanhTung-2A202603456

## 1. Thông tin thành viên

- Họ tên: Trịnh Thanh Tùng
- MSSV: 2A202603456
- Email: 26ai.tungtt2@vinuni.edu.vn
- GitHub: [TgTrh06](https://github.com/TgTrh06)
- Vai trong nhóm: Người gắn nhãn 2, kiêm giữ hồ sơ

## 2. Phần việc phụ trách

- Gắn nhãn độc lập 20 ca (CP3), tính đồng thuận, viết quy tắc ca lệch.
- Giữ hồ sơ: `ho_so_launch_v0.md`, `group_report.md`, chuẩn bị `phieu_cham.md`.
- Điền `report/team/ho_so_launch_v0.md` từ đầu buổi (bảy mục hồ sơ launch).

## 3. Đóng góp cụ thể

- Gắn nhãn độc lập 20 ca; so nhãn, đồng thuận 18/20 = 90%; viết quy tắc phân biệt cho ca 8 (Hệ thống, không phải Ngầm) và ca 13 (Giới hạn, không phải Hệ thống).
- Điền hồ sơ launch v0 dần từ đầu buổi: bảy mục, mỗi mục có con số, trạng thái, vai trò phụ trách.
- Đề xuất Go có điều kiện cho noi_dia + hang_nang, 4 điều kiện kèm người phụ trách và ngày kiểm tra; nêu rõ con số bất lợi (power 0,64, xem lại 100% là 0,98×).
- Viết báo cáo nhóm tổng hợp kết quả A–E vào `group_report.md`; chuẩn bị phiếu chấm trong `phieu_cham.md` (phần duyệt chéo chưa thực hiện trong buổi lab).

## 4. Bằng chứng

- `report/team/bang_loi.md` (cột nhãn người 2, đồng thuận, quy tắc), `report/team/ho_so_launch_v0.md`, `report/team/group_report.md`, `report/team/phieu_cham.md`.
- Commit `docs(labels): add label set 2, agreement rate and rules for cases 8 and 13`, `docs(launch): add launch dossier v0 and group report`.

## 5. Công cụ AI đã dùng

- Dùng Claude để hỏi lại định nghĩa năm loại lỗi Google PAIR trước khi gắn nhãn (không dùng AI để gắn nhãn); soát câu chữ hồ sơ (mỗi câu có số, không vượt ba dòng).
- Tự kiểm tra: đếm lại từng ca đồng thuận và bất đồng để xác nhận 18/20; grep toàn bộ `report/team` để chắc không có từ bị cấm theo quy tắc 5; mọi số giả lập trong hồ sơ có nhãn simulated; đề xuất là một trong ba lựa chọn.

## 6. Tự đánh giá

- Hiểu tại sao tỉ lệ đồng thuận cần được tính trước khi nhóm trao đổi, để đảm bảo hai bộ nhãn thực sự độc lập; hiểu vì sao chỉ được viết "chỉ số trong đợt chạy thử là 82,83%" chứ không viết "trợ lý đã nâng chỉ số".
- Cần cải thiện: điền hồ sơ launch và chốt danh sách điều kiện Go sớm hơn để cả nhóm cùng rà trước khi viết đề xuất Go/No-go.
