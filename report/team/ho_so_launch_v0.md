# Hồ sơ launch v0 · Trợ lý hoàn phí LogiX-VN · Gate 2a

Một trang. Cột trạng thái chỉ nhận: **Xong, có bằng chứng · Chưa · Giả lập**. Mục nào dựa trên cột `_simulated` ghi Giả lập. Người phụ trách là một vai trò, không ghi "cả đội". Gate 2a chỉ duyệt kế hoạch pilot: không viết như thể trợ lý đã được duyệt chạy chính thức (xem quy tắc 5 trong `README.md`).

Nhóm: RealCua · Lớp: L3A

| Mục | Con số chính | Trạng thái | Người phụ trách |
| --- | --- | --- | --- |
| 1 · Chi phí mỗi việc thành công | 4.472 đ/việc [simulated], gấp 16,3 lần hoá đơn token + tool chia số yêu cầu (274,7 đ); phạm vi noi_dia + hang_nang 3.414 đ, cộng cố định 4.599 đ ở 45.000 yêu cầu/tháng [simulated] | Giả lập | PM trợ lý hoàn phí |
| 2 · Ba yếu tố nhạy nhất | 1. Số ca làm lại ±51,8% · 2. Tỉ lệ xem lại ±40,7% · 3. Lương nhân viên +23,1%; giá token chỉ +5,6% khi gấp đôi [simulated] | Giả lập | PM trợ lý hoàn phí |
| 3 · So với nhân viên tự làm | Cả hệ thống 5.865 đ/yêu cầu = 0,49× của 12.000 đ (đã cộng 222 ca nhân viên làm thay); quoc_te 1,88×, doi_tac 0,85×; xem lại 100% thì 0,98× đến 1,03× [simulated] | Giả lập | Giám đốc vận hành |
| 4 · Chỉ số chính, chỉ số dùng, chỉ số an toàn | Trong đợt chạy thử: chính 82,83% (994/1.200) · bỏ qua gợi ý 27,12% (48/177) · mở lại 7 ngày 4,25% (51/1.200); 11 event đều có trace_id | Xong, có bằng chứng | Trưởng nhóm CSKH |
| 5 · Bảng lỗi và cách khắc phục | Đồng thuận 18/20 = 90%; 5 loại: người dùng 4, hệ thống 5, ngữ cảnh 4, giới hạn 4, ngầm 3; lỗi nặng nhất là ca 7 (báo đã hoàn khi sổ cái 503) và ca 20 (hoàn trùng) | Xong, có bằng chứng | Kỹ sư trưởng agent |
| 6 · Pilot plan | Chia theo nhân viên 20 + 20, phân tầng theo depot; mde 6 điểm (859/nhóm, ≥ 299 yêu cầu mỗi nhân viên, DE 6,96); power chỉ 0,64 nếu tác động thật là 5 điểm; 3 luật dừng; quyết định 2027-01-11 | Xong, có bằng chứng | Giám đốc vận hành |
| 7 · Rủi ro kinh tế | Làm lại gấp đôi → 6.787 đ; xem lại 100% → 11.743 đ = 0,98×; khối lượng còn một nửa → cố định +2.370 đ/việc [simulated] | Giả lập | PM trợ lý hoàn phí |

**Đề xuất:** **Go có điều kiện**, cho pilot chỉ gồm noi_dia + hang_nang (0,22× và 0,69× [simulated]), không gồm quoc_te và doi_tac.

- Sửa khoá chống trùng (ca 20) và chỉ báo "đã hoàn" khi sổ cái trả ok (ca 7), đối soát mỗi giờ ngưỡng 0 ca. Phụ trách: Kỹ sư trưởng agent. Kiểm tra: 2026-12-04, trước ngày bắt đầu.
- Giám đốc vận hành ký chấp nhận mde 6 điểm (power 0,64 nếu tác động thật chỉ 5 điểm). Phụ trách: Giám đốc vận hành. Kiểm tra: 2026-12-04.
- Bật đủ 11 event có trace_id; thay phút simulated bằng phút đo thật sau tuần 1 và tính lại cps. Phụ trách: PM trợ lý hoàn phí. Kiểm tra: 2026-12-14.
- Có kế hoạch giảm xem lại theo bậc, vì xem lại 100% thì không tiết kiệm (0,98×, B4); mục tiêu mỗi lần xem lại ≤ 5 phút. Phụ trách: Trưởng nhóm CSKH. Kiểm tra: 2026-12-21, cuối bước rollout 0.25.
