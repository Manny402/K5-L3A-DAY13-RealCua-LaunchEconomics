# Đặc tả chỉ số, event và rủi ro kinh tế · Nhiệm vụ E1, E2

Số tính bằng `src/lab13.py` (hàm `in_chi_so`, `in_bang_b`). Mọi con số từ cột `_simulated` ghi nhãn `simulated`.

## E1 · Đặc tả chỉ số

| Loại | Chỉ số | Công thức | Tính thử trên 1.200 yêu cầu |
| --- | --- | --- | --- |
| Chính (kết quả) | % yêu cầu đóng trong 24 giờ và không mở lại trong 7 ngày | `dong_trong_24h` bằng 1 và `mo_lai_trong_7_ngay` bằng 0, chia tổng số yêu cầu | 82,83% (994/1.200) |
| Dùng | Tỉ lệ bỏ qua gợi ý | `quyet_dinh_xem_lai` là `sua` hoặc `bo`, chia số yêu cầu được xem lại | 27,12% (48/177: 41 sửa, 7 bỏ) |
| An toàn | Tỉ lệ lỗi lọt đến khách | `mo_lai_trong_7_ngay` bằng 1, chia tổng số yêu cầu | 4,25% (51/1.200); phạm vi noi_dia + hang_nang 3,97% |
| Dùng | Nhóm tự đề xuất: % yêu cầu của nhóm trợ lý được mở bằng trợ lý | Số yêu cầu có `agent_suggestion_shown` ÷ số `refund_request_created` của nhóm arm = tro_ly, theo tuần | Không cần tính |
| An toàn | Nhóm tự đề xuất: % đơn hoàn sai tiền qua kiểm tra mẫu hằng tuần (bắt lỗi ngầm như ca 5, 17) | Số đơn trong `audit_sample_checked` có `so_tien_da_hoan` ≠ `so_tien_dung` ÷ 100 đơn mẫu mỗi tuần | Không cần tính |

Chỉ số chính trong đợt chạy thử là 82,83%. Con số này không so trực tiếp được với baseline 0,70, vì đợt chạy thử không có nhóm đối chứng.

## Danh sách event

Mỗi event có `trace_id` để nối với trace của agent.

| Event | Ai tạo | Thuộc tính chính | Thời điểm |
| --- | --- | --- | --- |
| `refund_request_created` | App khách | request_id, loai, so_tien, depot, arm, trace_id | Khi khách gửi yêu cầu |
| `agent_run_completed` | Agent | attempt, tokens_in, tokens_out, tool_calls, status, trace_id | Sau mỗi lần chạy, kể cả lần lỗi |
| `agent_suggestion_shown` | Giao diện nhân viên | staff_id, so_tien_de_xuat, trace_id | Khi gợi ý hiện ra cho nhân viên |
| `staff_review_decision` | Nhân viên | quyet_dinh (giu/sua/bo), phut_xem_lai đo thật, staff_id, trace_id | Khi bấm gửi, sửa hoặc bỏ |
| `staff_rework_completed` | Nhân viên | phut_lam_lai đo thật, ly_do, staff_id, trace_id | Khi làm lại xong |
| `refund_ledger_write` | Dịch vụ sổ cái | idempotency_key, so_tien, ket_qua, trace_id | Khi ghi hoàn tiền vào sổ cái |
| `handoff_to_staff` | Agent | reason (thieu_du_lieu, ngoai_pham_vi, het_lan_chay), tom_tat, trace_id | Khi chuyển nhân viên |
| `input_validation_failed` | Agent | kieu_ma_nhap, truong_loi, trace_id | Khi đầu vào của khách không hợp lệ |
| `ticket_closed` | Hệ thống ticket | closed_at, trace_id | Khi yêu cầu đóng |
| `ticket_reopened` | Khách | reopened_at, reason, trace_id | Khi khách mở lại |
| `audit_sample_checked` | Kế toán | so_tien_da_hoan, so_tien_dung, phien_ban_bang_gia, trace_id | Hằng tuần, 100 đơn mẫu |

**Kiểm tra chéo:** mỗi chỉ số E1 tính được từ event nào.

- Chính: `refund_request_created` (mẫu số) + `ticket_closed` (đóng trong 24 giờ) + `ticket_reopened` (không mở lại trong 7 ngày).
- Dùng (bỏ qua gợi ý): `staff_review_decision` với quyet_dinh sua hoặc bo ÷ tổng `staff_review_decision`.
- An toàn (lỗi lọt đến khách): `ticket_reopened` trong 7 ngày ÷ `refund_request_created`.
- Dùng (tự đề xuất): `agent_suggestion_shown` ÷ `refund_request_created` lọc arm = tro_ly.
- An toàn (tự đề xuất): `audit_sample_checked`.
- Chi phí mỗi việc thành công đo thật: `agent_run_completed` (token, tool) + `staff_review_decision` và `staff_rework_completed` (phút thật thay cột simulated) ÷ số yêu cầu thành công.

## E2 · Rủi ro kinh tế

Số lấy từ bảng độ nhạy trong `bang_chi_phi.md`.

| Rủi ro | Tác động đã tính | Dấu hiệu theo dõi | Hành động | Người phụ trách |
| --- | --- | --- | --- | --- |
| Số ca làm lại tăng gấp đôi | +51,8%, cps lên 6.787 đ [simulated] | Tỉ lệ làm lại theo tuần > 7% (đợt chạy thử: 4,9% trong phạm vi) | Thu hẹp về noi_dia, rà 20 trace làm lại gần nhất | PM trợ lý hoàn phí |
| Phải xem lại 100% kéo dài | 11.743 đ = 0,98× (12.415 đ = 1,03× nếu làm lại 15,3 phút như dữ liệu) [simulated] | % yêu cầu được xem lại còn > 50% cuối bước rollout 0.25; phút xem lại trung vị > 5 phút | Giảm xem lại theo bậc khi tỉ lệ sửa + bỏ < 15% | Trưởng nhóm CSKH |
| Lương nhân viên tăng | +23,1% khi lương tăng 25%, cps lên 5.506 đ [simulated] | Đơn giá phút nhân viên trong bảng lương quý | Cập nhật mô hình, giữ điều kiện cps < 0,5× của 12.000 đ | PM trợ lý hoàn phí |
| Khối lượng thấp hơn dự kiến | Cố định 40 triệu/tháng: +1.185 đ/việc ở 45.000 yêu cầu/tháng, +2.370 đ/việc nếu còn một nửa (5.784 đ = 0,48×) [simulated] | Số việc thành công theo tuần < 50% kế hoạch | Không mở rộng pilot, xem lại hợp đồng chi phí cố định | Giám đốc vận hành |
