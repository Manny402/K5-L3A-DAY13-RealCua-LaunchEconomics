# Team

## Thông tin nhóm

- Tên nhóm: RealCua
- Lớp: L3A
- Repo nhóm: `K5-L3A-DAY13-RealCua-LaunchEconomics` (xem [SUBMISSION.md](SUBMISSION.md))
- URL repo, nhánh nộp, commit chốt: https://github.com/Manny402/K5-L3A-DAY13-RealCua-LaunchEconomics · nhánh `main` · commit chốt: commit cuối trên `main` trước deadline

## Thành viên

| STT | Họ tên | MSSV | Email | GitHub | Vai trò |
| --: | ------ | ---- | ----- | ------ | ------- |
|   1 | Nguyễn Phú Nam (nhóm trưởng) | 2A202603501 | 145128129+Manny402@users.noreply.github.com | [Manny402](https://github.com/Manny402) | Người viết code (nhiệm vụ A, B) |
|   2 | Nguyễn Hoàng | 2A202603447 | 185824992+gauronaldo@users.noreply.github.com | [gauronaldo](https://github.com/gauronaldo) | Người kiểm số; người viết code nhiệm vụ D |
|   3 | Trương Hoàng Tùng | 2A202603651 | 186200067+Dobit25@users.noreply.github.com | [Dobit25](https://github.com/Dobit25) | Người gắn nhãn 1 |
|   4 | Trịnh Thanh Tùng | 2A202603456 | 129481785+TgTrh06@users.noreply.github.com | [TgTrh06](https://github.com/TgTrh06) | Người gắn nhãn 2, kiêm giữ hồ sơ |

Bốn vai của lab:

- **Người viết code:** viết và chạy `src/lab13.py`.
- **Người kiểm số:** tính tay một con số để đối chiếu, điền bảng.
- **Người gắn nhãn 1:** đọc đề, theo dõi điều kiện "Xong khi"; gắn nhãn 20 ca độc lập ở CP3.
- **Người gắn nhãn 2, kiêm giữ hồ sơ:** điền `report/team/ho_so_launch_v0.md` từ đầu buổi; gắn nhãn 20 ca độc lập ở CP3.

Nam viết code nhiệm vụ A, B; Hoàng viết code nhiệm vụ D, để ít nhất hai người trong nhóm tự tay tính được chi phí.

## Cá nhân

Báo cáo riêng của từng thành viên:

- [report/team/2A202603501_NguyenPhuNam.md](report/team/2A202603501_NguyenPhuNam.md)
- [report/team/2A202603447_NguyenHoang.md](report/team/2A202603447_NguyenHoang.md)
- [report/team/2A202603651_TruongHoangTung.md](report/team/2A202603651_TruongHoangTung.md)
- [report/team/2A202603456_TrinhThanhTung.md](report/team/2A202603456_TrinhThanhTung.md)

## NguyenPhuNam-2A202603501

### Phần việc phụ trách

- Nhóm trưởng; người viết code nhiệm vụ A, B.

### Đóng góp cụ thể

- Viết ba hàm A1 (`so_lan_chay_ky_vong`, `ti_le_thanh_cong`, `he_so_chi_phi_moi_viec_thanh_cong`), qua ba phép thử 1,20 · 1,25 · 1,25.
- Viết `mo_hinh` (A2), tách theo `loai` và bảng tỉ lệ ok theo lần thử (A3), cộng chi phí cố định (A4).
- Viết 9 kịch bản B1, kịch bản cặp B2, giới hạn chạy B3, xem lại 100% B4.

### Bằng chứng

- `src/lab13.py`: các hàm A1, `mo_hinh`, `in_bang_a2`, `in_bang_a3`, `in_bang_a4`, `in_bang_b`; commit `feat(cost)…`.

## NguyenHoang-2A202603447

### Phần việc phụ trách

- Người kiểm số (nhiệm vụ A, B); người viết code nhiệm vụ D1; điền `pilot_plan.yaml`.

### Đóng góp cụ thể

- Tính tay tool = 5.600 × 15 = 84.000 đ và cps = 4.373.585 ÷ 978 = 4.472 đ để đối chiếu; điền bảng A1–A4, B1–B4 trong `bang_chi_phi.md`.
- Viết `co_mau`, `he_so_thiet_ke`, `in_bang_d` (năm câu D1, kiểm tra bằng statsmodels, power 0,64; tỉ lệ mở lại hiện tại 4,25%).
- Điền `pilot_plan.yaml`: D1, D2, đánh đổi, ba luật dừng, `simulated_inputs`.

### Bằng chứng

- `report/team/bang_chi_phi.md`, `src/lab13.py` (phần D1), `report/team/pilot_plan.yaml`.

## TruongHoangTung-2A202603651

### Phần việc phụ trách

- Người gắn nhãn 1 (CP3); viết `chi_so.md` (E1, E2).

### Đóng góp cụ thể

- Gắn nhãn độc lập 20 ca (bộ nhãn 1); viết bảng khắc phục 5 ca, mỗi loại một ca.
- Viết hàm `in_chi_so` tính thử ba chỉ số (82,83% · 27,12% · 4,25%); đề xuất thêm hai chỉ số; danh sách 11 event có `trace_id`; 4 dòng rủi ro kinh tế.

### Bằng chứng

- `report/team/bang_loi.md` (cột nhãn người 1, bảng khắc phục), `report/team/chi_so.md`, `src/lab13.py` (hàm `in_chi_so`).

## TrinhThanhTung-2A202603456

### Phần việc phụ trách

- Người gắn nhãn 2 (CP3), kiêm giữ hồ sơ; viết `ho_so_launch_v0.md`, `group_report.md`; chuẩn bị `phieu_cham.md`.

### Đóng góp cụ thể

- Gắn nhãn độc lập 20 ca (bộ nhãn 2), tính tỉ lệ đồng thuận 18/20 = 90%, viết quy tắc cho ca 8 và ca 13.
- Điền hồ sơ launch v0 bảy mục và đề xuất Go có điều kiện kèm 4 điều kiện, người phụ trách, ngày kiểm tra.
- Viết báo cáo nhóm; chuẩn bị phiếu chấm (phần duyệt chéo chưa thực hiện).

### Bằng chứng

- `report/team/bang_loi.md` (cột nhãn người 2, đồng thuận, quy tắc), `report/team/ho_so_launch_v0.md`, `report/team/group_report.md`, `report/team/phieu_cham.md`.
