# Phiếu chấm hội đồng Gate 2a

Nhóm số n chấm nhóm số n + 1; nhóm cuối chấm nhóm 1. Chấm theo bằng chứng trong hồ sơ, không theo cách trình bày: một đề xuất No-go có lý do bằng số được điểm cao hơn một đề xuất Go bỏ qua con số bất lợi.

- Nhóm chấm (hội đồng): RealCua (L3A)
- Nhóm được chấm: KKK (L3A) · repo `tuancui0/K5-L3A-DAY13-KKK-LaunchEconomics`

| Tiêu chí | 0 điểm | 5 điểm | 10 điểm | Điểm | Lý do (có số) |
| --- | --- | --- | --- | ---: | --- |
| Đề xuất khớp bằng chứng | Mâu thuẫn với số của chính nhóm | Khớp nhưng bỏ qua một con số bất lợi | Khớp, nêu cả con số bất lợi và cách xử lý | 10 | Go có điều kiện khớp với 0,49× cả hệ thống và 4.599 đ (0,38×) trong phạm vi [simulated]; tự nêu cả hai con số bất lợi: power 0,64 nếu tác động thật là 5 điểm (điều kiện Giám đốc vận hành ký) và xem lại 100% tốn 12.415 đ = 1,03× (điều kiện giảm xem lại theo bậc) |
| Số giả lập và phạm vi | Không nhãn; phạm vi "mọi yêu cầu" | Có nhãn hoặc có thu hẹp phạm vi | Nhãn ở mọi số giả lập; phạm vi thu hẹp có lý do bằng số | 10 | Mọi số từ cột `_simulated` trong hồ sơ, `bang_chi_phi.md`, `chi_so.md` và `scope` đều có nhãn; phạm vi thu hẹp về noi_dia + hang_nang (0,22×, 0,69×), loại quoc_te (1,88×, thành công 27,3%) và doi_tac (0,85×). Góp ý nhỏ: `simulated_inputs` chỉ liệt kê tên cột, chưa liệt kê các con số đã dùng |
| Pilot ra được quyết định | Không đối chứng hoặc thiếu cỡ mẫu | Đủ cỡ mẫu, luật dừng chung chung | Tách được tác động, đủ mẫu, luật dừng có ngưỡng, thời hạn, người có quyền dừng | 10 | Chia ngẫu nhiên theo nhân viên 20 + 20, phân tầng theo depot, seed ghi trước, đối chứng cùng thời gian; đủ mẫu cho MDE 6 điểm (859 hiệu dụng, m ≥ 299, ước tính ~430 yêu cầu/người trong 14 ngày); 4 luật dừng đủ NẾU – TRONG – THÌ – KHÔNG THÌ, có ngưỡng (1 ca hoàn trùng, 6% hoặc +2 điểm, 8.000 đ, 70% nhân viên), thời hạn và người có quyền dừng |
| **Tổng** | | | | **30 / 30** | |

**Quyết định của hội đồng:** Go có điều kiện

**Lý do:** Đề xuất khớp với số của chính nhóm và không giấu con số bất lợi nào (power 0,64; xem lại 100% là 1,03× [simulated]). Pilot tách được tác động với 20 cụm mỗi nhóm, ngưỡng an toàn đặt theo tỉ lệ mở lại hiện tại 3,97–4,25% nên không dừng oan ngay tuần đầu. Hai điểm cần theo dõi: (1) lịch rất sát, hai điều kiện hạn 22/11 trong khi pilot bắt đầu 23/11; (2) bảng khắc phục dùng event `input_validation_failed` (ca 9) nhưng event này chưa có trong danh sách event của `chi_so.md`, nên cách phát hiện cho ca 9 chưa đo được.

**Một câu hỏi cho đội trình:** Vì sao nhóm chia pilot theo nhân viên mà không chia theo depot, dù chia theo depot dễ triển khai hơn?

**Câu trả lời của đội trình (ghi lại tại buổi):** Chia theo depot chỉ được 6 depot mỗi nhóm, nên cỡ mẫu hiệu dụng tối đa là 6 / 0,02 = 300, quá xa mức 859 cần cho chênh lệch 6 điểm. Số cụm cũng chỉ có 6, dưới mức tối thiểu 20. Chia theo nhân viên thì được 20 cụm mỗi nhóm, và với ít nhất 299 yêu cầu mỗi người thì đạt 859 hiệu dụng mỗi nhóm.
