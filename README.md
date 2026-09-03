# Day 28 · Track 01 — Dashboard Hành Động Cho Áp Dụng AI (v2)

> **Nhóm:** 333 · **Thời lượng:** 120 phút · **Mức:** Trung cấp
> Trạng thái file: **Đã điền — bản v2, sau kiểm tra chéo.**

---

## 0. Thành viên nhóm

| Họ tên | MSSV | Phần phụ trách | Góp ý đã đưa cho nhóm bạn |
|---|---|---|---|
| _<điền>_ | _<điền>_ | _<điền>_ | _<điền>_ |
| _<điền>_ | _<điền>_ | _<điền>_ | _<điền>_ |

> Ghi rõ nhóm bạn đã phản biện chéo ở chặng 3. Bảng này bắt buộc theo §6.3 của bài lab — chưa có tên/MSSV thật nên để nguyên placeholder, cần điền trước khi nộp.

## 1. Bài này giải quyết gì

Đã mua công cụ AI nhưng công việc vẫn như cũ: nhân viên dùng thử vài lần rồi quay lại
cách cũ, quản lý thấy số lượt dùng nhưng chưa thấy giá trị. Repo này đi từ triệu chứng
đó xuống nguyên nhân gốc, thiết kế lại workflow, rồi ra một Dashboard Hành Động đủ rõ
để trả lời: **tiếp tục / sửa / dừng**.

Nguyên tắc: *Sử dụng nhiều ≠ đã áp dụng.* Ứng dụng thật bắt đầu khi **công việc**,
**trách nhiệm** và **cách kiểm soát** đã thay đổi.

## 2. Cấu trúc repo

```
Day28_Track01_333/
├── README.md                          ← file này (xem §6.3 của lab)
├── dashboard/
│   └── dashboard_hanh_dong_v2.xlsx     ← bản v2, sau kiểm tra chéo
├── memo/
│   └── memo_quyet_dinh.md              ← memo quyết định, 5 phần (xem §6.4)
└── v1/
    └── dashboard_hanh_dong_v1.xlsx     ← bản trước phản biện, để đối chiếu
```

Các sheet trong workbook dashboard:

| Sheet | Nội dung |
|---|---|
| `0_Huong_dan` | Cách dùng workbook |
| `1_Pham_vi` | 1 sản phẩm AI · 1 nhóm người dùng · 2–4 quy trình · triệu chứng · mức độ hiện tại |
| `2_Chan_doan` | 5 câu hỏi chẩn đoán · Gartner-Lite · Mollick · ADKAR |
| `3_Nguyen_nhan_goc` | 1–2 nguyên nhân gốc + framework + ≥1 bằng chứng |
| `4_Workflow_ASIS_TOBE` | AS-IS / TO-BE + nguồn kiểm chứng + owner + xử lý khi AI sai |
| `5_Lo_trinh_30_60_90` | 3 cổng quyết định dựa trên bằng chứng, có owner + dấu hiệu hoàn thành |
| `6_Chi_so` | ≥1 product metric + ≥1 workflow metric, đủ baseline/target/nguồn/owner/hành động |
| `7_Quyet_dinh` | tiếp tục / sửa / dừng (chi tiết ở `memo/`) |
| `8_Thay_doi_v1_v2` | *(chỉ v2)* ≥2 thay đổi sau kiểm tra chéo |

## 3. Phạm vi đã khoá

- **Sản phẩm AI:** VLearn — trợ lý hỗ trợ learner khi làm bài lab
- **Nhóm người dùng chính:** Learner đang học lab, đã từng bị kẹt và phải tự xoay xở trong 7 ngày gần đây
- **Quy trình trong phạm vi (2–4):** Gặp điểm kẹt → hỏi trợ lý → kiểm chứng câu trả lời → quyết định đi tiếp hoặc chuyển coach
- **Ngoài phạm vi:** Rollout toàn khoá học; để AI tự phán đoán đúng/sai thay learner; các điểm kẹt khác ngoài lỗi cài đặt môi trường ở bước 3 của bài lab đang chọn
- **Mức độ hiện tại:** Usage — learner đã dùng AI tutor tích hợp sẵn nhưng vẫn phải rời nền tảng để tự kiểm chứng; chưa bước vào Pilot có kiểm soát

## 4. Nguyên nhân gốc (1–2, có căn cứ)

| # | Nguyên nhân gốc | Framework | Bằng chứng (≥1) |
|---|---|---|---|
| 1 | Độ tin cậy không được thiết kế trong lượt trả lời — learner không biết ý nào có nguồn, ý nào không | 5 câu hỏi chẩn đoán (trục Tin cậy) | Learner: "Anh chụp slide lên... anh buộc phải tin thôi" — không kiểm chứng được nên buộc phải tin |
| 2 | Workflow không có đường bàn giao ít ma sát sang coach khi AI không đủ căn cứ | 5 câu hỏi chẩn đoán (trục Workflow) + Mollick (bàn giao người–AI) | Learner rời nền tảng đi hỏi AI ngoài (Claude/ChatGPT) dù đã thử AI tutor tích hợp trước |

## 5. Giải pháp + Lộ trình 30–60–90

| Giai đoạn | Mục tiêu | Owner | Dấu hiệu hoàn thành (cổng) |
|---|---|---|---|
| 0–30 | Chứng minh vấn đề: vẽ AS-IS/TO-BE, khoá tài liệu pilot, chỉ định data owner, ghi baseline tuần 1 | Product owner + data owner | Có log workflow, mẫu câu hỏi và baseline. Nếu không lấy được dữ liệu thì sửa instrumentation trước khi mở rộng |
| 31–60 | Chứng minh chất lượng: bật trích nguồn, QA mẫu hàng tuần, thêm chuyển coach, hỗ trợ learner tại workflow | QA owner + lab coach | Tỷ lệ câu trả lời có nguồn và tỷ lệ hoàn thành không phải làm lại đạt mục tiêu nhóm. Nếu xấu, tăng QA và thu hẹp phạm vi |
| 61–90 | Quyết định mở rộng: so với baseline, chốt owner vận hành, kiểm tra quyền truy cập và consent, review chi phí | Product owner + governance owner | Chỉ mở rộng khi chất lượng, hành vi và giá trị cùng đạt ngưỡng. Nếu không, sửa hoặc dừng pilot |

## 6. Chỉ số chính

| Cấp | Chỉ số | Baseline | Target | Nguồn | Owner | Hành động khi xấu |
|---|---|---|---|---|---|---|
| Product | Mức dùng theo workflow (lượt mở trợ giúp / lượt kẹt) | Đo tuần 1 | Tăng so với baseline, do nhóm xác nhận | Log workflow | Trưởng nhóm lab | Quan sát điểm ma sát, không chỉ gửi thông báo tăng dùng |
| Product | Chất lượng / tin cậy (tỷ lệ ý có nguồn đúng, nhãn ngoài tài liệu đúng) | Đo mẫu QA | Đạt ngưỡng do QA owner xác nhận trước pilot | Phiếu QA mẫu + log nguồn | QA owner | Tăng cỡ mẫu, thu hẹp nguồn hoặc dừng rollout |
| Workflow | Thời gian / năng suất (từ lúc mở trợ giúp đến lúc đi tiếp hoặc chuyển coach) | Đo hiện trạng | Giảm so với baseline, không tính thời gian chờ coach là tiết kiệm | Log tác vụ | Chủ quy trình | Xem lại cách bàn giao và độ dài câu trả lời |
| Workflow | Hành vi làm lại (quay lại bước cũ hoặc hỏi lại cùng điểm) | Đo hiện trạng | Giảm so với baseline | Log phiên học | Product owner | Kiểm tra câu trả lời và hướng dẫn kiểm chứng |
| Workflow | Kết quả nghiệp vụ (tỷ lệ hoàn thành bước lab) | Baseline tuần 1 | Tăng mà không làm tăng lỗi bài tập | Hệ thống lab / bài nộp | Chủ nghiệp vụ | So sánh nhóm, điều chỉnh hoặc dừng |
| Workflow | Rủi ro / bàn giao (tỷ lệ câu hỏi không neo được, tỷ lệ chuyển coach thành công) | Ghi hiện trạng | Có ngưỡng cảnh báo được nhóm xác nhận | Log lỗi và Support Queue | AI owner + coach | Bổ sung fallback, không để learner bị kẹt im lặng |

## 7. Thay đổi v1 → v2 (sau kiểm tra chéo)

1. **Chỉ số:** Dashboard v1 chỉ đo lượt mở trợ giúp và thời gian tiết kiệm tự khai (activity metric, không dẫn tới quyết định gì). v2 bổ sung chỉ số hành vi (tỷ lệ làm lại), chất lượng/tin cậy (tỷ lệ có nguồn) và rủi ro/bàn giao (tỷ lệ chuyển coach thành công), đồng thời bỏ chỉ số thời gian tiết kiệm tự khai.
2. **Giải pháp / chia việc:** Workflow TO-BE ở v1 chỉ thêm bước "hỏi AI" mà chưa nói rõ ai chịu trách nhiệm kết quả cuối khi AI không chắc. v2 thêm rõ nguồn kiểm chứng, người chịu trách nhiệm (lab coach) và cách xử lý khi AI không chắc chắn (gắn nhãn → chuyển coach), theo đúng nguyên tắc chia việc của Mollick.
3. **Nguyên nhân gốc:** Nguyên nhân gốc ở v1 còn gần triệu chứng ("learner chưa quen dùng tutor tích hợp"). Sau khi chạy lại 5 câu hỏi chẩn đoán + ADKAR, v2 chốt lại nguyên nhân là thiếu trích nguồn (Tin cậy) và thiếu đường chuyển coach (Workflow).
4. **Lộ trình:** Giai đoạn 31–60 và 61–90 ở v1 chưa có owner và dấu hiệu hoàn thành, dễ biến thành lịch cứng. v2 gắn owner cho từng giai đoạn và định nghĩa cổng bằng ngưỡng chỉ số, không phải mốc thời gian.

> Đối chiếu trực tiếp tại `v1/dashboard_hanh_dong_v1.xlsx` (sheet `6_Chi_so`, `4_Workflow_ASIS_TOBE`, `5_Lo_trinh_30_60_90`) so với `dashboard/dashboard_hanh_dong_v2.xlsx`.

## 8. Quyết định

**TIẾP TỤC** — pilot Option A trong một nhóm, một bài lab; bổ sung fallback chuyển coach cho câu trả lời không có căn cứ; chưa rollout rộng. Chi tiết: [`memo/memo_quyet_dinh.md`](memo/memo_quyet_dinh.md).

---

## Checklist bằng chứng đầu ra (§2.3)

- [x] Phạm vi đã khoá: 1 sản phẩm AI · 1 nhóm người dùng chính · 2–4 quy trình
- [x] 1–2 nguyên nhân gốc có framework và ≥1 bằng chứng đi kèm
- [x] Giải pháp + lộ trình 30–60–90 ngày có owner từng giai đoạn
- [x] ≥1 product metric và ≥1 workflow metric — mỗi chỉ số đủ baseline, target, nguồn dữ liệu, người phụ trách, hành động khi chỉ số xấu
- [x] ≥2 thay đổi so với bản v1 sau khi kiểm tra chéo
- [x] Một quyết định rõ: tiếp tục / sửa / dừng

---

## Phụ lục — Dashboard hành động v2 (bản đầy đủ)

§6 ở trên là bản rút gọn cho README. Bảng dưới đây là bản dashboard v2 gốc, đầy đủ 5 tầng đo (sử dụng → hành vi → năng suất → chất lượng/tin cậy → giá trị), khớp với `dashboard/dashboard_hanh_dong_v2.xlsx`:

| Chỉ số | Mốc đầu | Mục tiêu pilot | Nguồn dữ liệu | Phụ trách | Khi chỉ số xấu |
| --- | --- | --- | --- | --- | --- |
| Mức dùng theo workflow | Đo tuần 1: số lượt mở trợ giúp / số lượt kẹt | Tăng so với baseline, do nhóm xác nhận | Log workflow | Trưởng nhóm lab | Quan sát điểm ma sát, không chỉ gửi thông báo tăng dùng |
| Thời gian / năng suất | Thời gian từ lúc mở trợ giúp đến lúc đi tiếp hoặc chuyển coach | Giảm so với baseline, không tính thời gian chờ coach là tiết kiệm | Log tác vụ | Chủ quy trình | Xem lại cách bàn giao và độ dài câu trả lời |
| Hành vi làm lại | Tỷ lệ quay lại bước cũ hoặc hỏi lại cùng điểm | Giảm so với baseline | Log phiên học | Product owner | Kiểm tra câu trả lời và hướng dẫn kiểm chứng |
| Chất lượng / tin cậy | QA mẫu: tỷ lệ ý có nguồn đúng và nhãn ngoài tài liệu đúng | Đạt ngưỡng do QA owner xác nhận trước pilot | Phiếu QA mẫu + log nguồn | QA owner | Tăng cỡ mẫu, thu hẹp nguồn hoặc dừng rollout |
| Kết quả nghiệp vụ | Tỷ lệ hoàn thành bước lab, baseline tuần 1 | Tăng mà không làm tăng lỗi bài tập | Hệ thống lab / bài nộp | Chủ nghiệp vụ | So sánh nhóm, điều chỉnh hoặc dừng |
| Rủi ro / bàn giao | Tỷ lệ câu hỏi không neo được và tỷ lệ chuyển coach thành công | Có ngưỡng cảnh báo được nhóm xác nhận | Log lỗi và Support Queue | AI owner + coach | Bổ sung fallback, không để learner bị kẹt im lặng |

Các chỉ số sử dụng chỉ là tín hiệu chẩn đoán. Quyết định mở rộng phải dựa vào chất lượng, hành vi, năng suất và kết quả workflow — không dùng số tài khoản, số câu hỏi hay thời gian tiết kiệm tự khai làm căn cứ duy nhất.
