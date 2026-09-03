# Memo quyết định — Áp dụng AI cho trợ lý VLearn

Nhóm 333. Ngày 3 tháng 9 năm 2026. Memo này đi kèm file `dashboard/dashboard_hanh_dong_v2.xlsx`.

Thành viên: Nguyễn Hoàng Minh (2A202601764), Nguyễn Việt Hải (2A202601656), Trịnh Hải Đăng (2A202601602).

---

## 1. Bối cảnh và phạm vi

Nhóm em chọn trợ lý AI tích hợp trong nền tảng VLearn làm đối tượng chẩn đoán. Người dùng chính là learner đang theo học lab, cụ thể là những bạn đã bị kẹt ở bước cài đặt môi trường và phải tự xoay xở trong bảy ngày gần đây. Quy trình nhóm em xét gồm bốn bước nối nhau: learner nhận ra mình bị kẹt, learner hỏi trợ lý, learner kiểm chứng câu trả lời với tài liệu lab, rồi learner quyết định làm theo hay chuyển việc cho coach.

Triệu chứng nhóm em quan sát được là learner đã có trợ lý tích hợp sẵn nhưng vẫn rời nền tảng để mở Claude hoặc ChatGPT hỏi lại, và nhiều phiên làm lab bị kéo dài hoặc bỏ dở ngay ở bước cài đặt môi trường. Theo thang năm mức, trợ lý đang ở mức Usage, tức là learner tự dùng theo cách riêng, còn quy trình lab chưa ghi nhận bước hỏi trợ lý và chưa có ai chịu trách nhiệm cho chất lượng câu trả lời.

Nhóm em không xét việc rollout cho toàn khoá học, không xét việc để AI tự phán đoán đúng sai thay learner, và không xét các điểm kẹt khác ngoài lỗi cài đặt môi trường ở bước ba của bài lab đang chọn.

## 2. Nguyên nhân gốc và bằng chứng

Nhóm em chốt hai nguyên nhân gốc. Cả hai đều nằm ở độ tin cậy và quy trình, không phải ở chuyện learner chưa được đào tạo.

Nguyên nhân thứ nhất là độ tin cậy chưa được thiết kế trong lượt trả lời. Trợ lý gộp phần có trong tài liệu lab và phần tự suy đoán vào cùng một câu trả lời, không trích nguồn, không đánh dấu phần nằm ngoài tài liệu, và không có nút báo sai. Learner vì thế không phân biệt được, nên hoặc tin hết hoặc bỏ qua rồi tự xoay. Nhóm em xác định nguyên nhân này bằng trục Tin cậy trong năm câu hỏi chẩn đoán và bước Desire trong ADKAR. Bằng chứng là câu một learner nói lại nguyên văn khi nhóm em phỏng vấn: "Anh chụp cái slide lên hỏi, nó trả lời trơn tru, nhưng anh không biết chỗ nào lấy từ bài, chỗ nào nó tự nghĩ, nên anh buộc phải tin thôi." Ngoài ra, ba phiên nhóm em thử hỏi trợ lý đều cho câu trả lời không dẫn nguồn.

Nguyên nhân thứ hai là quy trình lab không có bước hỏi trợ lý và không có đường chuyển coach ít ma sát. Khi trợ lý không đủ căn cứ, learner không biết chuyển việc cho ai, nên tự dò tay từng dòng hoặc bỏ dở. Nhóm em xác định nguyên nhân này bằng trục Workflow trong năm câu hỏi và phần bàn giao giữa người và AI trong khung Mollick. Bằng chứng là một phiên làm lab nhóm em quan sát trực tiếp, trong đó learner mở trợ lý rồi vẫn quay lại dò tay, và trong quy trình không có bước nào nhắc gọi coach.

Triệu chứng learner rời nền tảng và phiên học bỏ dở là hệ quả của hai nguyên nhân trên, không phải là nguyên nhân.

## 3. Giải pháp đã chọn và lộ trình 30–60–90

Nhóm em cân nhắc ba cách chia việc giữa learner và trợ lý.

Option A đặt learner làm người giữ quyền. Trợ lý tìm trong tài liệu lab, tóm tắt bước learner đang vướng, và soạn câu trả lời nháp có trích dẫn từng ý. Learner đọc lại nguồn, đối chiếu với bài, rồi tự quyết định làm theo hay chuyển coach. Trợ lý chỉ tự động ở việc xác định learner đang ở bước nào và trích đúng đoạn hướng dẫn của bước đó.

Option B để trợ lý vừa trả lời vừa tự chấm câu trả lời của mình đáng tin đến đâu và khuyên learner có nên tin hay không.

Option C để trợ lý tự dán nhãn đúng hoặc sai cho cách làm của learner ở các câu hỏi lặp lại.

Nhóm em chọn Option A. Cách này xử lý trực tiếp hai nguyên nhân gốc. Trích dẫn từng ý và đánh dấu phần ngoài tài liệu sửa được chuyện learner không biết nên tin phần nào. Nút chuyển coach kèm nhãn "không đủ căn cứ" tạo ra đường bàn giao mà quy trình đang thiếu. Nhóm em loại Option B và Option C vì cả hai đẩy phần phán đoán sang cho trợ lý trong khi trợ lý chưa có tiêu chí kiểm tra rõ ràng.

Workflow mới của nhóm em nêu rõ ba thứ. Nguồn kiểm chứng là bộ tài liệu lab bản mới nhất do data owner giữ. Người chịu trách nhiệm là learner cho phần tự làm và coach cho phần chuyển giao. Cách xử lý khi trợ lý không chắc là trợ lý tự gắn nhãn "không đủ căn cứ", ẩn nút làm theo và hiện nút chuyển coach, sau đó coach nhận trong hàng chờ và phản hồi trong khung giờ hỗ trợ.

Lộ trình 30–60–90 của nhóm em là ba cổng quyết định, không phải một lịch cố định.

Trong 30 ngày đầu, nhóm em chứng minh vấn đề có thật và lấy số liệu nền. Nhóm em vẽ AS-IS và TO-BE, khoá bộ tài liệu lab dùng cho pilot, chỉ định data owner, và ghi baseline tuần đầu cho thời gian xử lý một điểm kẹt, tỷ lệ phiên bỏ dở và tỷ lệ rời nền tảng. Người phụ trách giai đoạn này là product owner của trợ lý cùng data owner. Cổng mở khi nhóm em có log quy trình, có mẫu câu hỏi thật và có baseline. Nếu chưa lấy được số liệu, nhóm em sửa cách ghi log trước, chưa chuyển sang giai đoạn hai.

Từ ngày 31 đến ngày 60, nhóm em chứng minh chất lượng câu trả lời và đường bàn giao. Nhóm em bật trích nguồn và nhãn phần ngoài tài liệu, chấm QA trên mẫu phiên thật hàng tuần, thêm nút chuyển coach và hàng chờ, và thêm hướng dẫn ngắn trong màn hình trợ lý. Người phụ trách là người phụ trách QA cùng lab coach. Cổng mở khi tỷ lệ câu trả lời trích nguồn đúng và tỷ lệ learner hoàn thành bước lab mà không phải làm lại đạt mức nhóm em đặt. Nếu số liệu xấu, nhóm em tăng cỡ mẫu QA và thu hẹp bộ tài liệu.

Từ ngày 61 đến ngày 90, nhóm em quyết định có mở rộng hay không. Nhóm em so kết quả với baseline, chốt người vận hành thường trực, kiểm tra quyền truy cập và phần learner đồng ý ghi log, và xem lại chi phí. Người phụ trách là product owner cùng người phụ trách governance. Nhóm em chỉ mở sang bài lab hoặc nhóm learner khác khi chất lượng, hành vi và kết quả bước lab cùng đạt ngưỡng. Nếu không đạt, nhóm em sửa hoặc dừng pilot.

## 4. Quyết định: TIẾP TỤC

Nhóm em quyết định tiếp tục. Nhóm em chạy pilot Option A trong một nhóm learner và một bài lab, kèm điều kiện bổ sung đường chuyển coach cho các câu trả lời không có căn cứ trong tài liệu. Nhóm em chưa mở rộng sang bài lab khác vì Gartner-Lite cho thấy Readiness và Absorption còn thiếu.

Nhóm em dựa vào các bằng chứng sau. Ba phiên thử nghiệm độc lập đều nghiêng về Option A. Hai nguyên nhân gốc đều có cách xử lý cụ thể trong Option A. Chỉ số dẫn đường cho quyết định là tỷ lệ câu trả lời trích nguồn đúng và thời gian xử lý một điểm kẹt, chứ không phải số lượt dùng.

Sau khi kiểm tra chéo với nhóm Đức Sơn, nhóm em sửa bốn điểm so với bản v1.

1. Nhóm em tách riêng ba option và ghi rõ ở Option A learner là người kiểm chứng và quyết định, trợ lý chỉ tìm và tóm tắt. Bản v1 mô tả Option C lẫn với Option B.
2. Nhóm em thêm vào dashboard các chỉ số chất lượng trích nguồn, hành vi làm lại, kết quả bước lab và rủi ro bàn giao, mỗi chỉ số ghi rõ hành động khi số liệu xấu. Bản v1 nghiêng về số lượt dùng và thời gian tiết kiệm do learner tự khai.
3. Nhóm em thêm bảng ba phiên thử nghiệm làm bằng chứng cho việc chọn Option A, kèm ghi chú về giới hạn của bằng chứng.
4. Nhóm em loại phiên thử thứ ba khỏi mọi kết luận về Option C, vì phiên đó không theo đúng kịch bản phỏng vấn và mô tả sai cơ chế Option C. Nhóm em chỉ giữ lại phần phiên đó nói về Option A.

## 5. Bước tiếp theo

| Việc cần làm | Người phụ trách | Hạn | Chỉ số theo dõi |
| --- | --- | --- | --- |
| Chốt data owner cho bộ tài liệu lab | Trưởng nhóm lab | Trong tuần này | Có tên người phụ trách và lịch cập nhật |
| Dựng cách ghi log quy trình và đo baseline tuần đầu | Product owner trợ lý | Trước khi bật pilot | Thời gian xử lý một điểm kẹt, tỷ lệ phiên bỏ dở |
| Bật trích nguồn và nhãn phần ngoài tài liệu | Product owner trợ lý | Trong 30 ngày đầu | Tỷ lệ câu trả lời có trích dẫn |
| Thêm nút chuyển coach và hàng chờ hỗ trợ | Product owner trợ lý cùng lab coach | Giai đoạn 31 đến 60 ngày | Tỷ lệ chuyển coach xử lý trong khung giờ hỗ trợ |
| Chấm QA mẫu hàng tuần trên phiên thật | Người phụ trách QA | Từ ngày 31 | Tỷ lệ trích nguồn đúng, tỷ lệ hoàn thành bước lab không phải làm lại |
