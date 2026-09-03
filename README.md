# Day 28 · Track 01 — Dashboard Hành Động Cho Áp Dụng AI (v2)

> **Nhóm:** 333 · **Thời lượng:** 120 phút · **Mức:** Trung cấp
> Trạng thái file: **KHUNG — chưa điền nội dung.** Cấu trúc dựng theo §1–§2 của lab;
> sẽ rà lại với §3–§6 (đặc biệt §6.3 cho README và §6.4 cho memo) trước khi fill.

---

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

- **Sản phẩm AI:** _<điền>_
- **Nhóm người dùng chính:** _<điền>_
- **Quy trình trong phạm vi (2–4):** _<điền>_
- **Ngoài phạm vi:** _<điền>_
- **Mức độ hiện tại:** _<Usage / Pilot / Deployment / Adoption / Normalization>_

## 4. Nguyên nhân gốc (1–2, có căn cứ)

| # | Nguyên nhân gốc | Framework | Bằng chứng (≥1) |
|---|---|---|---|
| 1 | _<điền>_ | _<điền>_ | _<điền>_ |
| 2 | _<điền>_ | _<điền>_ | _<điền>_ |

## 5. Giải pháp + Lộ trình 30–60–90

| Giai đoạn | Mục tiêu | Owner | Dấu hiệu hoàn thành (cổng) |
|---|---|---|---|
| 0–30 | _<điền>_ | _<điền>_ | _<điền>_ |
| 31–60 | _<điền>_ | _<điền>_ | _<điền>_ |
| 61–90 | _<điền>_ | _<điền>_ | _<điền>_ |

## 6. Chỉ số chính

| Cấp | Chỉ số | Baseline | Target | Nguồn | Owner | Hành động khi xấu |
|---|---|---|---|---|---|---|
| Product | _<điền>_ | | | | | |
| Workflow | _<điền>_ | | | | | |

## 7. Thay đổi v1 → v2 (sau kiểm tra chéo)

1. _<điền>_
2. _<điền>_

## 8. Quyết định

**_<TIẾP TỤC / SỬA / DỪNG>_** — _<lý do 1 dòng>_. Chi tiết: [`memo/memo_quyet_dinh.md`](memo/memo_quyet_dinh.md).

---

## Checklist bằng chứng đầu ra (§2.3)

- [ ] Phạm vi đã khoá: 1 sản phẩm AI · 1 nhóm người dùng chính · 2–4 quy trình
- [ ] 1–2 nguyên nhân gốc có framework và ≥1 bằng chứng đi kèm
- [ ] Giải pháp + lộ trình 30–60–90 ngày có owner từng giai đoạn
- [ ] ≥1 product metric và ≥1 workflow metric — mỗi chỉ số đủ baseline, target, nguồn dữ liệu, người phụ trách, hành động khi chỉ số xấu
- [ ] ≥2 thay đổi so với bản v1 sau khi kiểm tra chéo
- [ ] Một quyết định rõ: tiếp tục / sửa / dừng
