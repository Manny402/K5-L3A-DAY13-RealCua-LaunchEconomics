# Báo cáo cá nhân — NguyenHoang-2A202603447

## 1. Thông tin thành viên

- Họ tên: Nguyễn Hoàng
- MSSV: 2A202603447
- Email: 185824992+gauronaldo@users.noreply.github.com
- GitHub: [gauronaldo](https://github.com/gauronaldo)
- Vai trong nhóm: Người kiểm số; người viết code nhiệm vụ D

## 2. Phần việc phụ trách

- Kiểm số và điền `bang_chi_phi.md` (A, B).
- Viết code D1 trong `src/lab13.py` và điền `pilot_plan.yaml`.

## 3. Đóng góp cụ thể

- Tính tay tool = 5.600 × 15 = 84.000 đ và cps = 4.373.585 ÷ 978 = 4.472 đ, khớp với output.
- Tính tay chi phí so với nhân viên tự làm: (4.373.585 + 222 × 12.000) ÷ 1.200 = 5.865 đ = 0,49× [simulated].
- Viết `co_mau`, `he_so_thiet_ke`, `in_bang_d`: a) 1.251 · b) DE 2,48, 42 người/nhóm · c) trần 1.000 · d) trần 300 · e) m ≥ 299; đối chiếu statsmodels (1.250; power 0,64).
- Tính tỉ lệ mở lại hiện tại 4,25% trước khi đặt luật an toàn (chênh +2 điểm so với đối chứng, trần 6%).
- Điền `pilot_plan.yaml`: chia theo nhân viên 20 + 20, mde 0,06, ba luật dừng đủ bốn vế, `simulated_inputs`.

## 4. Bằng chứng

- `report/team/bang_chi_phi.md`, `src/lab13.py` (`co_mau`, `he_so_thiet_ke`, `in_bang_d`), `report/team/pilot_plan.yaml`.
- Commit `docs(cost): fill A-B cost and sensitivity tables`, `feat(pilot): compute D1 sample sizes and complete pilot_plan.yaml`.

## 5. Công cụ AI đã dùng

- Dùng Claude để giải thích hệ số thiết kế và cách giải bất phương trình câu e.
- Tự kiểm tra: giải tay câu e (2,82m ≥ 841,82 → m ≥ 299); so công thức z với `NormalIndPower`; chạy `yaml.safe_load` và grep để chắc không còn dấu `?`.

## 6. Tự đánh giá

- Hiểu vì sao số cụm quyết định cỡ mẫu hiệu dụng (luôn < c ÷ ICC) chứ không phải tổng số yêu cầu.
- Cần cải thiện: ghi lại các bước tính tay ngay trong lúc làm thay vì bổ sung sau.
