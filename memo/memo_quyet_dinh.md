# Memo Quyết Định — Áp Dụng AI

> **Nhóm:** 333 · **Ngày:** 2026-09-03 · Đi kèm `dashboard/dashboard_hanh_dong_v2.xlsx`
> Trạng thái: **ĐÃ ĐIỀN — bản v2, sau kiểm tra chéo.**

---

## 1. Bối cảnh & phạm vi

- **Sản phẩm AI:** VLearn — trợ lý hỗ trợ learner khi làm bài lab
- **Nhóm người dùng chính:** Learner đang học lab, đã từng bị kẹt và phải tự xoay xở trong 7 ngày gần đây
- **Quy trình trong phạm vi (2–4):** Gặp điểm kẹt (bước 3 – cài đặt môi trường) → hỏi trợ lý AI tutor tích hợp → kiểm chứng câu trả lời → quyết định đi tiếp hoặc chuyển coach
- **Triệu chứng quan sát được:** Learner đã dùng thử AI tutor tích hợp nhưng vẫn rời nền tảng để hỏi AI ngoài (Claude/ChatGPT) hoặc đồng đội; tự nhận "buộc phải tin thôi" vì không kiểm chứng được câu trả lời
- **Mức độ hiện tại:** Usage — công cụ đã được dùng thử nhưng chưa bước vào Pilot có kiểm soát

## 2. Nguyên nhân gốc & bằng chứng

| # | Nguyên nhân gốc (phân biệt với triệu chứng) | Framework xác định | Bằng chứng (≥1, cụ thể) |
|---|---|---|---|
| 1 | Độ tin cậy không được thiết kế trong lượt trả lời — learner không biết ý nào có nguồn, ý nào không | 5 câu hỏi chẩn đoán (trục Tin cậy) + ADKAR (Desire) | Phỏng vấn learner: "Anh chụp slide lên... anh buộc phải tin thôi" — không kiểm chứng được nên buộc phải tin |
| 2 | Workflow không có đường bàn giao ít ma sát sang coach khi AI không đủ căn cứ | 5 câu hỏi chẩn đoán (trục Workflow) + Mollick (bàn giao người–AI) | Quan sát: learner rời nền tảng đi hỏi AI ngoài dù đã thử AI tutor tích hợp trước |

> Triệu chứng ("ít người dùng lại") ≠ nguyên nhân. Ở đây nguyên nhân nằm ở độ tin cậy của câu trả lời và ở chỗ workflow thiếu bước bàn giao khi AI không chắc — không phải vì learner "chưa quen dùng công cụ".

## 3. Giải pháp đã chọn & lộ trình 30–60–90

- **Giải pháp khớp nguyên nhân:** Không mở lớp đào tạo. Thiết kế lại workflow tra cứu để mỗi câu trả lời có nguồn + ngày cập nhật, và có đường chuyển coach khi AI gắn nhãn "không đủ căn cứ".
- **Workflow TO-BE nêu rõ 3 thứ:**
  - **Nguồn kiểm chứng:** tài liệu bài lab bước 3, có owner và lịch cập nhật
  - **Người chịu trách nhiệm kết quả cuối:** lab coach trực pilot
  - **Cách xử lý khi AI không chắc chắn:** AI tự gắn nhãn "không đủ căn cứ" → chuyển coach trong ca trực

| Giai đoạn | Mục tiêu | Hành động chính | Owner | Dấu hiệu hoàn thành (cổng) |
|---|---|---|---|---|
| 0–30 | Chứng minh vấn đề | Vẽ AS-IS/TO-BE, khoá tài liệu pilot, chỉ định data owner, ghi baseline tuần 1 | Product owner + data owner | Có log workflow, mẫu câu hỏi và baseline; nếu không lấy được dữ liệu thì sửa instrumentation trước khi sang giai đoạn 2 |
| 31–60 | Chứng minh chất lượng | Bật trích nguồn, QA mẫu hàng tuần, thêm chuyển coach, hỗ trợ learner tại workflow | QA owner + lab coach | Tỷ lệ câu trả lời có nguồn và tỷ lệ hoàn thành không làm lại đạt mục tiêu nhóm; nếu xấu thì tăng QA và thu hẹp phạm vi |
| 61–90 | Quyết định mở rộng | So kết quả với baseline, chốt owner vận hành, kiểm tra quyền truy cập/consent, review chi phí | Product owner + governance owner | Chỉ mở rộng khi chất lượng, hành vi và giá trị cùng đạt ngưỡng; nếu không thì sửa hoặc dừng pilot |

## 4. Quyết định: TIẾP TỤC / SỬA / DỪNG

- **Quyết định:** **TIẾP TỤC** — pilot trong một nhóm, một bài lab; bổ sung fallback chuyển coach cho câu trả lời không có căn cứ; chưa rollout rộng.
- **Dựa trên bằng chứng nào:** Tỷ lệ câu trả lời có nguồn kiểm chứng (chỉ số Product, tầng 4) và tỷ lệ hoàn thành không cần làm lại (chỉ số Workflow, tầng 3–4) trong `dashboard/dashboard_hanh_dong_v2.xlsx` — cả hai đều là decision metric, không chỉ dựa vào lượt dùng.
- **≥2 thay đổi so với v1 sau kiểm tra chéo:**
  1. Dashboard v1 chỉ đo lượt mở trợ giúp và thời gian tiết kiệm tự khai (activity metric, không dẫn tới quyết định gì). Sau phản biện, v2 bổ sung chỉ số hành vi (tỷ lệ làm lại), chất lượng/tin cậy (tỷ lệ có nguồn) và rủi ro/bàn giao (tỷ lệ chuyển coach thành công), đồng thời bỏ chỉ số thời gian tiết kiệm tự khai.
  2. Workflow TO-BE ở v1 chỉ thêm bước "hỏi AI" mà chưa nói rõ ai chịu trách nhiệm kết quả cuối khi AI không chắc. Sau phản biện, v2 thêm rõ nguồn kiểm chứng, người chịu trách nhiệm (lab coach) và cách xử lý khi AI không chắc chắn (gắn nhãn → chuyển coach).

## 5. Bước tiếp theo

| Việc | Owner | Hạn | Chỉ số theo dõi |
|---|---|---|---|
| Gắn trích nguồn + ngày cập nhật vào mọi câu trả lời của AI tutor | QA owner | Ngày 30 | Tỷ lệ câu trả lời có nguồn kiểm chứng |
| Dựng đường chuyển coach khi AI gắn nhãn "không đủ căn cứ" | Lab coach | Ngày 30 | Tỷ lệ chuyển coach thành công |
| Đo baseline thời gian xử lý và tỷ lệ hoàn thành bước lab | Data owner | Tuần 1 | Thời gian / năng suất, kết quả nghiệp vụ |
