# Phiếu chấm hội đồng Gate 2a

Nhóm số n chấm nhóm số n + 1; nhóm cuối chấm nhóm 1. Chấm theo bằng chứng trong hồ sơ, không theo cách trình bày: một đề xuất No-go có lý do bằng số được điểm cao hơn một đề xuất Go bỏ qua con số bất lợi.

- Nhóm chấm (hội đồng): RealCua (L3A)
- Nhóm được chấm: KKK (L3A) · repo `tuancui0/K5-L3A-DAY13-KKK-LaunchEconomics`

| Tiêu chí | 0 điểm | 5 điểm | 10 điểm | Điểm | Lý do (có số) |
| --- | --- | --- | --- | ---: | --- |
| Đề xuất khớp bằng chứng | Mâu thuẫn với số của chính nhóm | Khớp nhưng bỏ qua một con số bất lợi | Khớp, nêu cả con số bất lợi và cách xử lý | 10 | Khớp 0,49× [simulated]; tự nêu power 0,64 và xem lại 100% = 1,03×, mỗi số có điều kiện xử lý |
| Số giả lập và phạm vi | Không nhãn; phạm vi "mọi yêu cầu" | Có nhãn hoặc có thu hẹp phạm vi | Nhãn ở mọi số giả lập; phạm vi thu hẹp có lý do bằng số | 10 | Mọi số giả lập có nhãn; chỉ giữ noi_dia + hang_nang (0,22×, 0,69×), loại quoc_te (1,88×) và doi_tac (0,85×) |
| Pilot ra được quyết định | Không đối chứng hoặc thiếu cỡ mẫu | Đủ cỡ mẫu, luật dừng chung chung | Tách được tác động, đủ mẫu, luật dừng có ngưỡng, thời hạn, người có quyền dừng | 10 | Ngẫu nhiên theo nhân viên 20 + 20; đủ mẫu cho MDE 6 điểm (859/nhóm); 4 luật dừng có ngưỡng, thời hạn, người dừng |
| **Tổng** | | | | **30 / 30** | |

**Quyết định của hội đồng:** Go có điều kiện

**Lý do:** Khớp số, không giấu con số bất lợi (power 0,64; 1,03× [simulated]); pilot có 20 cụm mỗi nhóm. Cần theo dõi: lịch sát (điều kiện hạn 22/11, bắt đầu 23/11) và event `input_validation_failed` chưa có trong danh sách event.

**Một câu hỏi cho đội trình:** Vì sao nhóm chia pilot theo nhân viên mà không chia theo depot, dù chia theo depot dễ triển khai hơn?

**Câu trả lời của đội trình (ghi lại tại buổi):** Chia theo depot chỉ được 6 depot mỗi nhóm, nên cỡ mẫu hiệu dụng tối đa là 6 / 0,02 = 300, quá xa mức 859 cần cho chênh lệch 6 điểm. Số cụm cũng chỉ có 6, dưới mức tối thiểu 20. Chia theo nhân viên thì được 20 cụm mỗi nhóm, và với ít nhất 299 yêu cầu mỗi người thì đạt 859 hiệu dụng mỗi nhóm.
