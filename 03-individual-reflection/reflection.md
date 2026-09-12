# 03 — Individual Reflection

> Viết bằng lời của bạn (Phase 7 trong `01-worksheet.md`). Có thể dùng AI gợi ý câu hỏi tự soi, không dùng AI viết thay. 8-12 câu, có chuyện cụ thể.

## Thông tin cá nhân

- Họ và tên: Trần Long Khánh
- Mã học viên: 2A202602538
- Nhóm: Nhóm 5 thành viên (vai trò: facilitator)
- Candidate problem nhóm chọn: Sinh viên/AI Engineer làm multi-object tracking phải xem và đối chiếu hàng nghìn frame để tìm vị trí xảy ra ID switch trước khi sửa annotation, khiến một vòng QA có thể mất khoảng 50 phút hoặc kéo dài nhiều ngày với dataset lớn.

---

## 1. Tôi đã tham gia vào phần nào?

Ghi việc cụ thể + kết quả cụ thể. Không ghi chung chung kiểu "tham gia thảo luận".

| Hoạt động | Tôi đã làm gì? (việc cụ thể) | Kết quả / ảnh hưởng tới nhóm |
|---|---|---|
| Scan cá nhân | Tôi liệt kê 5 vấn đề trong công việc/học tập, sau đó phát triển 3 Problem Card về setup môi trường, xác định root cause và review code do AI sinh ra. | Bổ sung 3 candidate kỹ thuật cho nhóm, trong đó bài root-cause debugging được xem là tiềm năng nhưng cần thu hẹp scope. |
| Pitch Problem Card | Tôi pitch bài “Review và kiểm chứng code do AI sinh ra”, mô tả vòng lặp requirement → kiến trúc → AI code → review → test → sửa và nêu rủi ro khi giao AI build quá nhiều từ đầu. | Giúp nhóm nhìn rõ bottleneck nằm ở bước review/kiểm chứng assumption, không phải ở tốc độ sinh code. |
| Challenge bài của bạn khác | Tôi cùng nhóm đặt câu hỏi liệu rule theo IoU, quỹ đạo và mất–tái xuất hiện đã đủ cho bài ID switch hay chưa, đồng thời challenge việc dùng Agent tự sửa dữ liệu. | Nhóm thống nhất phải có rule-only baseline, human review và không cho hệ thống tự sửa/ghi đè annotation. |
| Gom trùng / cluster | Với vai trò facilitator, tôi hỗ trợ gom 15 candidate thành 4 cụm: quản lý thông tin, dataset/tracking QA, kiểm thử chất lượng AI, và vận hành/debug project AI. | Giúp nhóm so sánh các bài trên cùng tiêu chí và loại bớt những bài chủ yếu cần process fix hoặc automation. |
| Chọn candidate problem | Tôi điều phối shortlist và chấm điểm theo actor, workflow, evidence, impact, khả năng làm trong lab, mức phù hợp AI và hiểu biết domain. | Nhóm chọn #6 — phát hiện và sửa ID switch — với 34 điểm, cao hơn prompt regression và lọc hallucination. |
| Validation / research | Tôi cùng nhóm rà lại tín hiệu phỏng vấn, phân biệt self-report với bằng chứng đã kiểm chứng và đối chiếu các hướng SlowFast, CLIP-ReID, ByteTrack/BoT-SORT, TrackEval. | Nhóm thu hẹp mục tiêu thành phát hiện/xếp hạng đoạn nghi vấn để người kiểm tra, không xây tracker hoặc editor mới và không tự sửa ID. |
| Workflow nhóm | Tôi hỗ trợ chốt current workflow khoảng 50 phút/video và future workflow gồm rule tạo candidate, ReID chấm điểm, human review, sửa và đánh giá. | Bottleneck được xác định tại bước xem tuần tự và tua lại (~35 phút); mục tiêu tương lai là tối đa 15 phút/video. |
| Problem Statement | Tôi góp phần làm rõ actor, bottleneck, metric, boundary và điểm AI can thiệp; đồng thời yêu cầu đo trên cùng ground-truth subset. | Problem Statement v1 có các ngưỡng cụ thể: recall ≥90%, precision ≥70%, giảm median QA time ≥70% hoặc còn ≤15 phút/video. |
| Rule / Workflow / Agent | Tôi tham gia so sánh ba mức và ủng hộ Workflow kết hợp Rule + AI scoring + human review thay vì Agent. | Giải pháp giữ được chuỗi bước cố định, dễ audit, có thể tắt AI và vẫn bảo toàn dữ liệu gốc. |
| Decision | Tôi cùng nhóm kiểm tra mức sẵn sàng của dữ liệu, baseline, ground truth, rủi ro và người chịu trách nhiệm trước khi quyết định. | Nhóm chốt “Not Yet”: chỉ tiếp tục validation/pilot, chưa build workflow AI hoàn chỉnh khi bằng chứng còn thiếu. |

**Dấu tay rõ nhất của tôi trong artifact cuối (1-2 câu):**

```text
Dấu tay rõ nhất của tôi là vai trò facilitator trong quá trình đưa 15 candidate về một bài duy nhất và giữ cuộc thảo luận bám vào evidence, metric, boundary. Tôi cũng góp phần chốt rằng bài ID switch chỉ nên dùng Workflow có human-in-the-loop, không dùng Agent tự sửa annotation.
```

---

## 2. Bảng dùng AI (mỗi dòng 1 phase có dùng AI — 2 cột cuối bắt buộc)

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai / hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| Scan | Tôi dùng AI để phản biện 5 vấn đề ban đầu và gợi ý cách thu hẹp thành pain có actor, workflow, bottleneck. | AI giúp chỉ ra các ý quá rộng và đề xuất cách đo thời gian, số vòng thử-sai. | AI có xu hướng tự điền số liệu ước lượng như thể đã được đo và làm vấn đề nghe “đẹp” hơn thực tế. | Tôi giữ các số chưa đo ở trạng thái giả định, ghi rõ cần bấm giờ và không xem chúng là evidence. |
| Problem Card | Tôi dùng AI để kiểm tra độ đầy đủ của 3 card và gợi ý current/future workflow, metric, fallback. | AI giúp cấu trúc vấn đề setup, debug và review code thành các bước rõ ràng. | AI ban đầu làm scope “build project bằng AI” quá rộng và dễ nhảy thẳng sang giải pháp reviewer/agent. | Tôi chọn bottleneck cụ thể là review, test và kiểm chứng assumption; mọi lệnh hoặc thay đổi rủi ro vẫn phải do tôi kiểm tra. |
| Workflow | Tôi dùng AI để rà tính liên tục giữa input, output, actor, thời gian và handoff của từng bước. | AI giúp phát hiện bottleneck thực sự nằm ở tìm đoạn nghi vấn, không phải thao tác sửa ID. | AI có thể coi thời gian 50 phút và mục tiêu 15 phút là số đã được xác nhận. | Tôi ghi rõ đây là baseline tự báo cáo, yêu cầu bấm giờ ít nhất 5 video và so sánh trên cùng dữ liệu. |
| Research | Tôi dùng AI để gợi ý từ khóa và các hướng công cụ cần kiểm tra cho tracking, ReID và evaluation. | AI giúp mở rộng danh sách phương án để nhóm so sánh thay vì tự xây tất cả từ đầu. | AI có thể suy diễn rằng model tốt trên người/xe cũng sẽ tốt trên dữ liệu lợn hoặc gán sai vai trò cho TrackEval. | Tôi cùng nhóm chỉ giữ nguồn chính thức, xem ReID là một tín hiệu và dùng TrackEval để đánh giá chứ không gọi là giải pháp phát hiện. |
| Problem Statement | Tôi dùng AI phản biện các field còn mơ hồ trong bản v0. | AI chỉ ra rằng cần định nghĩa ground truth, frame bắt đầu switch, baseline và tiêu chí trước–sau. | AI dễ dùng cụm “AI phát hiện ID switch” quá chung và chưa nói rõ quyền hành động. | Tôi thu hẹp AI vào bước scoring/ranking sau rule và trước human review; bổ sung precision, recall, IDSW, boundary và rollback. |
| Rule / Workflow / Agent | Tôi dùng AI để lập luận ưu/nhược điểm của từng mức trên cùng bài toán. | AI giúp tách rõ rule cho kiểm tra cứng, model cho phần mơ hồ và người cho quyết định cuối. | AI dễ đề xuất Agent vì bài toán có nhiều bước và độ mơ hồ cao. | Tôi dựa vào đường xử lý cố định để hạ xuống Workflow; không cho hệ thống tự đổi config, tự sửa ID hay ghi đè file gốc. |
| Decision | Tôi dùng AI như người phản biện cho điều kiện Go/Not Yet/No-Go và tiêu chí dừng. | AI giúp liệt kê các lỗ hổng về evidence, baseline, data và ground truth. | AI có thể kết luận Go quá sớm chỉ vì workflow và metric đã được mô tả rõ trên giấy. | Tôi cùng nhóm chọn Not Yet, yêu cầu phỏng vấn thêm, bấm giờ, tạo ground truth review chéo và benchmark rule-only trước. |

> Nếu phase nào không dùng AI, ghi `Không dùng` và vì sao tự làm.

---

## 3. Reflection câu hỏi mở

Chọn 3-4 câu trong 6 câu dưới để viết thành đoạn 8-12 câu (không trả lời bullet 1 dòng):
- Tôi học được gì khi nghe top 3 problems của các bạn khác?
- Nhóm có lúc nào bị solution-first, đòi làm Agent cho ngầu không?
- Tôi có thay đổi ý kiến sau khi bị challenge không, vì sao đổi?
- Tôi đóng góp gì thật sự vào artifact cuối, phần nào có dấu tay của tôi?
- Điều khó nhất khi viết Problem Statement là gì, metric hay boundary?
- Nếu làm lại, tôi sẽ challenge nhóm mạnh hơn ở điểm nào?

**Reflection:**

```text
Khi nghe các top problems của các bạn, tôi nhận ra một pain có thật chưa chắc đã là một bài toán cần AI; nhiều việc như theo dõi terminal, tổng hợp metric hay tải slide có thể được xử lý tốt hơn bằng notification, script hoặc thay đổi quy trình. Ban đầu tôi thiên về bài review code do AI sinh ra vì nó gần với trải nghiệm của mình, nhưng khi bị challenge tôi thấy scope của bài này còn quá rộng và khó tạo một pilot có ground truth trong thời gian ngắn. Vì vậy, tôi đồng ý chuyển sang bài ID switch vì actor, workflow và bottleneck “tìm đúng frame bắt đầu lỗi” cụ thể hơn, đồng thời nhóm có dữ liệu tracking để thử nghiệm. Với vai trò facilitator, đóng góp chính của tôi là giúp nhóm gom 15 candidate thành 4 cụm, đưa 3 bài vào shortlist và giữ việc chấm điểm dựa trên cùng một bộ tiêu chí. Điều khó nhất khi viết Problem Statement là không biến các con số ước lượng thành bằng chứng; baseline 50 phút và mục tiêu 15 phút chỉ có ý nghĩa khi được bấm giờ trên cùng tập video. Tôi cũng học được rằng boundary quan trọng không kém metric: AI chỉ nên xếp hạng đoạn nghi vấn, còn người phải xem bằng chứng trước–sau và quyết định có sửa ID hay không. Nhóm từng có thể bị cuốn vào ý tưởng Agent vì bài toán vừa mơ hồ vừa nhiều bước, nhưng chuỗi xử lý thực tế vẫn cố định nên Workflow kết hợp rule, ReID và human review là mức phù hợp hơn. Quyết định “Not Yet” giúp tôi hiểu rằng mô tả giải pháp hợp lý chưa đủ để bắt đầu build khi chưa có ground truth, validation độc lập và rule baseline. Nếu làm lại, tôi sẽ challenge sớm hơn về nguồn gốc từng con số, yêu cầu ghi quote và bấm giờ ngay từ đầu thay vì hoàn thiện workflow rồi mới quay lại kiểm tra evidence. Tôi cũng sẽ yêu cầu nhóm benchmark rule-only trước, vì nếu rule đã đạt recall và thời gian mục tiêu thì thêm AI chỉ làm tăng chi phí và rủi ro mà không tạo thêm giá trị.
```

---

## 4. Tự kiểm cuối bài (check trước khi nộp repo)

- [x] [12đ] Cá nhân có 5+ problems + top 3 Problem Cards
- [x] [12đ] Tôi đã pitch rõ + challenge nhóm đúng trọng tâm (ghi ở bảng mục 1)
- [x] Nhóm có nhật ký hội tụ từ candidates về 1 bài
- [x] [15đ] Nhóm có workflow trước/sau
- [x] [20đ] Nhóm có PS v0/v1 với metric + boundary rõ
- [x] [15đ] Nhóm có so sánh No AI / Rule / Workflow / Agent
- [x] [10đ] Nhóm có Go / Not Yet / No-Go + lý do rõ
- [x] [10đ] Reflection này có vai trò thật + AI giúp/sai ở đâu + điều học được + nếu làm lại đổi gì
- [x] [6đ] Tôi tự giải thích được mạch problem → workflow → metric → boundary → độ phù hợp AI

