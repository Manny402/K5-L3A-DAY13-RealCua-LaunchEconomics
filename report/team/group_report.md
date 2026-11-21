# Báo cáo nhóm

Báo cáo ngắn, tối đa 2 trang. Số liệu chi tiết nằm trong các file hồ sơ; ở đây chỉ dẫn lại con số chính.

## 1. Thông tin nhóm

- Tên nhóm: RealCua
- Lớp: L3A
- Thành viên: xem `TEAM.md` (Nguyễn Phú Nam, Nguyễn Hoàng, Trương Hoàng Tùng, Trịnh Thanh Tùng)

## 2. Mục tiêu và cách tiếp cận

Dựng hồ sơ launch v0 cho trợ lý hoàn phí LogiX-VN để trả lời bốn câu hỏi: có đáng chạy không, nhân viên có dùng không, khi hỏng thì sao, pilot thiết kế thế nào để ra được quyết định. Nhóm viết một file `src/lab13.py` tính mọi con số từ hai file CSV, rồi chép số sang hồ sơ; mỗi con số từ cột `_simulated` đều có nhãn simulated. Vai được chia theo bốn vai của lab; hai người cùng viết code (A–B và D) để ít nhất hai người tự tính được chi phí.

## 3. Giải pháp

- **A · Chi phí** ([bang_chi_phi.md](bang_chi_phi.md)): ba hàm A1 qua 3 phép thử (1,20 · 1,25 · 1,25); `mo_hinh` cộng token + tool của mọi lần chạy, kể cả lần lỗi, cộng phút xem lại và làm lại, chia cho số việc thành công; tách theo `loai`; cộng chi phí cố định cho phạm vi noi_dia + hang_nang.
- **B · Độ nhạy** ([bang_chi_phi.md](bang_chi_phi.md)): gọi lại `mo_hinh` cho 9 kịch bản, một cặp, giới hạn 1–3 lần chạy (tính cả chi phí hệ thống) và kịch bản xem lại 100%.
- **C · Lỗi** ([bang_loi.md](bang_loi.md)): hai người gắn nhãn độc lập 20 ca theo năm loại Google PAIR, so nhãn, viết quy tắc cho ca lệch, bảng khắc phục 5 ca.
- **D · Pilot** ([pilot_plan.yaml](pilot_plan.yaml)): tính đủ năm câu D1 trước, rồi chọn chia theo nhân viên 20 + 20; tính tỉ lệ mở lại hiện tại trước khi đặt luật an toàn.
- **E · Chỉ số và hồ sơ** ([chi_so.md](chi_so.md), [ho_so_launch_v0.md](ho_so_launch_v0.md)): tính thử ba chỉ số, 11 event có `trace_id`, 4 dòng rủi ro kinh tế lấy số từ bảng độ nhạy.

## 4. Kết quả

- Chi phí mỗi việc thành công **4.472 đ** [simulated], gấp 16,3 lần hoá đơn chia số yêu cầu; làm lại chiếm 51,8% tổng chi phí [simulated].
- Cả hệ thống 5.865 đ/yêu cầu = **0,49×** của 12.000 đ [simulated]; quoc_te 1,88× nên bị loại khỏi phạm vi.
- Yếu tố nhạy nhất: số ca làm lại (+51,8%), tỉ lệ xem lại (+40,7%), lương (+23,1%) [simulated]. Giới hạn 2 lần chạy rẻ nhất cho công ty (6.901.220 đ) [simulated].
- Đồng thuận gắn nhãn 18/20 = 90%.
- Pilot: chia theo nhân viên 20 + 20, mde 6 điểm (859/nhóm, m ≥ 299), power 0,64 nếu tác động thật là 5 điểm.
- Đề xuất: **Go có điều kiện** cho pilot noi_dia + hang_nang.
- Kết quả duyệt chéo từ hội đồng: chưa có (phần duyệt chéo chưa thực hiện).

## 5. Khó khăn và cách xử lý

- Kiểm tra `yaml.safe_load(open(...))` trên Windows báo `UnicodeDecodeError` vì Python mặc định đọc bằng cp1252. Cách xử lý: chạy với `PYTHONUTF8=1` (hoặc `open(..., encoding='utf-8')`); file đọc được, có 3 luật dừng.
- Ban đầu nhóm định so 4.472 đ trực tiếp với 12.000 đ (0,37×). Đọc lại hướng dẫn thì thấy con số này chưa tính 222 ca nhân viên làm thay, nên nhóm chuyển sang dùng chi phí cả hệ thống (0,49×).
- Hai ca gắn nhãn lệch (8, 13) đều ở ranh giới "Hệ thống" với loại khác. Nhóm thống nhất theo nguyên nhân gốc và ghi quy tắc vào `bang_loi.md`.

## 6. Tổng hợp đóng góp

Chi tiết đóng góp của từng thành viên nằm trong `TEAM.md`.

## 7. Hạn chế và hướng cải thiện

- Chi phí xem lại và làm lại dựa trên phút giả lập; cần thay bằng phút đo thật từ event `staff_review_decision` và `staff_rework_completed` sau tuần 1 pilot.
- Với 40 nhân viên, pilot không thấy được mức chênh 5 điểm; nếu có thể, kéo dài thời gian để mỗi nhân viên xử lý nhiều yêu cầu hơn, hoặc mời thêm depot.
- Đợt chạy thử không có đối chứng, nên chỉ số 82,83% chưa nói được gì về tác động của trợ lý.

## 8. Tài liệu tham khảo

- Erol và cộng sự, *Cost-of-Pass: An Economic Framework for Evaluating Language Models*, arXiv:2504.13359.
- Google PAIR, *People + AI Guidebook*, chương "Errors + Graceful Failure".
- Tài liệu statsmodels, `NormalIndPower`, `proportion_effectsize`.
- Tài liệu lab: `docs/du_lieu_va_cong_thuc.md`, `docs/Lab13_Huong_dan_chi_tiet_buoi_chieu.md`.
