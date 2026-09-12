# 02 — Group Problem Statement (Bản nộp nhóm)

> Làm chung 1 bản, mỗi thành viên copy vào repo cá nhân. Đi theo Phase 3 → 6 trong `01-worksheet.md`. Nhóm chỉ chọn candidate problem ở Phase 3, viết Problem Statement sau khi validate + vẽ workflow.

## Thành viên nhóm

| STT | Họ và tên | Mã học viên | Vai trò trong nhóm (VD: facilitator, workflow, research, writer) |
| --- | --- | --- | --- |
| 1 | Trần Long Khánh | 2A202602538 | facilitator |
| 2 | Nguyễn Đình Khang | 2A202602584 | workflow |
| 3 | Phạm Hồ Quang Dũng | 2A202602860 | workflow |
| 4 | Ngô Gia Quốc | 2A202602757 | research |
| 5 | Nguyễn Hải Đăng | 2A202602963 | research |

**Candidate problem nhóm chọn (1 câu):**
Sinh viên/AI Engineer làm multi-object tracking phải xem và đối chiếu hàng nghìn frame để tìm vị trí xảy ra ID switch trước khi sửa annotation; baseline tự báo cáo hiện tại là khoảng 50 phút cho một vòng QA và cần được bấm giờ lại trong pilot.

---

## Phase 3 — Group Convergence: từ 9-12 candidates về 1

### 3.1. Trình bày top 3 mỗi người (mỗi candidate 1-2 phút)

| # | Người đưa ra | Candidate problem | Người gặp vấn đề | Điểm nghẽn | Cảm nhận nhanh của nhóm |
| --- | --- | --- | --- | --- | --- |
| 1 | Nguyễn Đình Khang | Viết biên bản và tổng hợp kết luận cuộc họp thủ công | Thư ký/người ghi biên bản, trưởng nhóm, thành viên cuộc họp | Phải đọc/xem lại nội dung meeting rồi tự xác định thông tin quan trọng, decisions và action items. | Khá mạnh. Pain rõ, workflow rõ, AI phù hợp cho summarize/extract; cần human review để tránh sai owner/deadline. |
| 2 | Nguyễn Đình Khang | Kiểm tra email thường xuyên rồi tự note lịch vào Calendar | Sinh viên có nhiều môn/project/CLB; trưởng nhóm | Phải đọc từng email để xác định email nào chứa sự kiện rồi trích đúng ngày, giờ, địa điểm. | Pain thật nhưng cần challenge AI. Có thể giải quyết một phần bằng rule/filter + Calendar automation, AI chỉ cần cho email khó hiểu. |
| 3 | Nguyễn Đình Khang | Phải quay lại terminal nhiều lần khi build/train/test | Sinh viên AI/Software, developer, researcher | Polling terminal thủ công gây context switching và phải kiểm tra lại nhiều lần. | Có ích nhưng không AI-first. Notification/script giải quyết phần lớn; AI chỉ có giá trị khi job lỗi và cần giải thích log. |
| 4 | Ngô Gia Quốc | Tách video thành hàng nghìn frame rồi lọc frame không cần thiết | Sinh viên / AI Engineer làm Computer Vision | Phải kiểm tra và lọc frame trùng, mờ hoặc không cần thiết bằng tay. | Khá tốt và dễ đo. Tuy nhiên nên thử blur/similarity/FPS rule trước; AI chỉ cần khi tiêu chí “frame hữu ích” phức tạp. |
| 5 | Ngô Gia Quốc | Kiểm tra và sửa bounding box/annotation thủ công | Sinh viên / AI Engineer làm Computer Vision | Phải kiểm tra từng frame để tìm bounding box sai trước khi sửa. | Mạnh. Dataset lớn làm pain tăng nhanh; phù hợp mô hình AI flag box bất thường → human review. Metric cũng dễ đo. |
| 6 | Ngô Gia Quốc | Phát hiện và sửa ID switch giữa các frame | Sinh viên / AI Engineer làm Object Tracking | Phải tìm chính xác frame/đoạn video xảy ra ID switch bằng cách xem và đối chiếu nhiều frame. | Rất đáng thử nhưng khó hơn. Pain đặc thù, impact trực tiếp đến tracking; cần định nghĩa ground truth và tiêu chí ID-switch rõ. |
| 7 | Phạm Hồ Quang Dũng | Không tải được slide nên phải duyệt và chụp từng slide trước khi gửi AI tóm tắt | Sinh viên dùng AI + Notion để ghi chép | Duyệt thủ công slide quan trọng rồi screenshot từng slide; dễ mất thời gian và bỏ sót nội dung. | Pain rõ nhưng chưa phải AI problem. Nếu xin được file gốc/export hợp lệ thì vấn đề gần như biến mất. Nên ưu tiên process fix. |
| 8 | Phạm Hồ Quang Dũng | Việc cần làm nằm rải trên Discord, Gmail, Outlook và Zalo | Sinh viên nhận task từ nhiều nguồn | Không có một nơi capture thống nhất; đọc tin xong phải giữ task/deadline trong trí nhớ. | Problem thật, nhưng integration mới là nút thắt. Một inbox/process chung có thể tốt hơn AI; quyền truy cập Zalo/Discord cũng là rào cản. |
| 9 | Phạm Hồ Quang Dũng | Tự lên lịch hằng ngày và ước lượng thời gian công việc | Sinh viên tự quản lý lịch trình | Ước lượng thời gian hoàn toàn trong đầu, không có historical data nên lịch thường bị vỡ và phải xếp lại. | Nên process fix trước. Cần ghi task + actual duration để có dữ liệu; AI chưa thể estimate tốt nếu đầu vào hiện tại chưa tồn tại. |
| 10 | Nguyễn Hải Đăng | Debug Prompt Regression sau khi thay đổi system prompt | Intern / AI Engineer | Phải đọc và so sánh ngữ nghĩa 30+ output với ground truth bằng mắt; chiếm khoảng 90/120 phút. | Rất mạnh. AI-fit tốt vì exact-match không xử lý semantic equivalence tốt. Có metric rõ và impact trực tiếp đến release quality. |
| 11 | Nguyễn Hải Đăng | Chạy benchmark rồi tổng hợp Accuracy/Latency/Token Cost vào báo cáo | AI Engineer | Copy-paste và format metric từ log/MLflow/W&B vào Sheets thủ công. | Pain rõ nhưng không cần AI. Python + API/automation có thể giải quyết gần như hoàn toàn, nên không nên chọn làm AI solution. |
| 12 | Nguyễn Hải Đăng | Lọc hallucination/bad outputs từ production logs | AI Engineer, Domain Expert / QA | Phải đọc hàng trăm conversation log không cấu trúc rồi đánh giá hallucination/format thủ công. | Một trong các candidate mạnh nhất. AI phù hợp để pre-filter/rank risk; impact lớn. Cần giải quyết privacy và false-negative. |
| 13 | Trần Long Khánh | Setup môi trường và xử lý dependency conflict khi chuyển project AI | AI Engineer, thành viên team AI | Khó xác định package/version nào conflict và tổ hợp Python/CUDA/PyTorch/library nào tương thích. | Có pain nhưng phải challenge. Docker, lockfile và environment.yml đã giải quyết nhiều phần; AI nên tập trung vào diagnosis conflict chứ không phải cài env. |
| 14 | Trần Long Khánh | Xác định root cause khi project AI gặp lỗi | AI Engineer, developer/deployment engineer | Khó phân loại root cause và quyết định diagnostic step tiếp theo giữa code, library, CUDA/driver, hardware… | Rất tiềm năng. Đây là bài Agent/reasoning rõ, pain lớn; nhưng scope hiện rộng, nên thu hẹp vào Jetson/CUDA/TensorRT hoặc một environment cụ thể. |
| 15 | Trần Long Khánh | Review và kiểm chứng code do AI coding assistant sinh ra | AI Engineer, developer dùng AI coding assistant | Phải kiểm tra code AI có đúng requirement, architecture và environment thật hay không, rồi test và sửa nhiều vòng. | Mạnh nhưng đang rộng. Nên thu hẹp thành AI code review/test generation hoặc phát hiện assumption sai; nếu không scope sẽ quá lớn để prototype. |

Nhìn nhanh để chuẩn bị bước shortlist: các candidate nổi bật nhất hiện tại là #10 Prompt Regression, #12 Production Hallucination Filtering, #14 AI Root-cause Debugging, #6 ID Switch Detection, và #5 Annotation QA. Đây là các bài có cả pain rõ, workflow đo được và lý do dùng AI tương đối thuyết phục. Các bài #3, #7, #9, #11 lại là ví dụ tốt để chứng minh nhóm không cố dùng AI cho mọi vấn đề.

### 3.2. Gom trùng / cluster (gom 9-12 ý thành 3-4 cụm)

| Cluster | Candidates included | Pattern chung | Ghi chú |
| --- | --- | --- | --- |
| A — Họp, thông báo và quản lý việc | #1, #2, #7, #8, #9 | Thông tin nằm rải rác hoặc phải đọc, tóm tắt và chuyển thành task/lịch thủ công. | Nhiều bài có thể xử lý trước bằng process fix, rule hoặc tích hợp sẵn có; AI chỉ phù hợp ở bước trích xuất nội dung mơ hồ. |
| B — Dataset và tracking QA | #4, #5, #6 | Khối lượng frame lớn; người phải xem từng frame để lọc dữ liệu, kiểm tra annotation hoặc tính liên tục của ID. | Pain tăng theo số frame và đo được; #6 khó nhất vì cần suy luận xuyên nhiều frame, nhất là lúc che khuất/giao nhau. |
| C — Kiểm thử chất lượng hệ thống AI | #10, #12, #15 | Con người phải đọc output/code không cấu trúc để tìm lỗi ngữ nghĩa hoặc assumption sai. | AI phù hợp làm pre-filter/reviewer, nhưng luôn cần golden set, test hoặc người chịu trách nhiệm chốt. |
| D — Vận hành và debug project AI | #3, #11, #13, #14 | Theo dõi job, tổng hợp metric hoặc chẩn đoán lỗi môi trường/toolchain. | #3 và #11 chủ yếu là automation; #13 và #14 có giá trị reasoning nhưng scope rộng, khó làm pilot gọn. |

### 3.3. Shortlist (giữ 2-3 bài trả lời được 7 câu hỏi worksheet)

| Candidate | Vì sao vào shortlist (2-3 ý) | Rủi ro / điều chưa rõ |
| --- | --- | --- |
| #6 — Phát hiện và sửa ID switch giữa các frame | Actor và workflow cụ thể; bottleneck “tìm đúng frame bắt đầu switch” rõ. Tác động trực tiếp đến chất lượng tracking, có thể đo thời gian QA, precision/recall phát hiện và số IDSW. Nhóm có dữ liệu dự án tracking hành vi lợn để làm pilot nhỏ. | Hai cá thể giống nhau, giao nhau hoặc bị che khuất có thể làm rule/AI báo sai. Hiện mới có self-report từ một dự án, chưa có ground truth và validation độc lập. |
| #10 — Debug prompt regression | Mỗi lần kiểm thử có baseline 120 phút, trong đó khoảng 90 phút là đọc và so sánh 30+ output. Có golden cases, tiêu chí release và phương án LLM-as-a-Judge để thử nghiệm trong lab. | Judge có thể thiên lệch hoặc đồng ý sai; cần người review case FAIL và một tập case đã gán nhãn đủ tốt. Bài này ít gắn với chuyên môn CV chung của nhóm hơn #6. |
| #12 — Lọc hallucination/bad output từ production log | Pain lớn (3–4 giờ/tuần), input nhiều và không cấu trúc; AI có thể ưu tiên case rủi ro để con người review. Có thể đo coverage, recall trên sample và thời gian review. | Dữ liệu production nhạy cảm; hallucination theo domain khó có ground truth. False negative có thể khiến lỗi nghiêm trọng bị bỏ qua và dữ liệu thật khó đưa vào lab. |

### 3.4. Score để đồng thuận (chấm 1-5, ép nói rõ vì sao cho 5 / cho 3)

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| #6 — ID switch detection | 5 | 5 | 4 | 5 | 5 | 5 | 5 | 34 |
| #10 — Prompt regression | 5 | 5 | 4 | 5 | 5 | 5 | 4 | 33 |
| #12 — Production hallucination filtering | 5 | 5 | 4 | 5 | 4 | 4 | 4 | 31 |

**Candidate nhóm chọn (1 bài duy nhất):**

```
Phát hiện và sửa ID switch giữa các frame

```

**Vì sao chọn (4-5 câu):**

```text
Bài #6 thuyết phục nhóm vì actor, workflow và bottleneck đều khá rõ. Người làm tracking không quá vất vả ở thao tác đổi ID; phần mất công thật sự là lần theo đúng frame đầu tiên nơi identity bị gán nhầm. Video càng dài, lỗi càng dễ kéo sang các frame sau và làm ảnh hưởng annotation lẫn metric tracking. Nhóm có dataset tracking hành vi lợn để làm một pilot nhỏ trong lab, đồng thời có thể đặt Rule, Workflow và Agent lên cùng một bàn cân. Tuy nhiên, AI ở đây chỉ được xếp hạng đoạn nghi vấn; người vẫn là người xác nhận và sửa ID. Vì evidence hiện mới đến từ một thành viên, đây vẫn là giả thuyết ưu tiên cần kiểm tra thêm, chưa phải kết luận đã chứng minh.
```

**Vì sao KHÔNG chọn các candidate còn lại (mỗi bài 2-3 câu):**

```text
#10 Prompt regression không được chọn vì đã có golden test và batch output khá có cấu trúc; một workflow evaluator là khả thi nhưng domain này chủ yếu do một thành viên nắm, trong khi nhóm có dữ liệu CV thuận tiện hơn để cùng kiểm chứng. Đây vẫn là phương án dự phòng tốt nếu pilot ID switch không tạo được ground truth.

#12 Production hallucination filtering không được chọn vì cần truy cập log thật, xử lý privacy và xây tiêu chí factuality theo domain. False negative khó phát hiện và hậu quả cao hơn, nên không phù hợp bằng #6 cho một lab ngắn với dữ liệu có thể cô lập.
```

**Disagreement (nếu có — ai lo gì, chốt ra sao):**

```text
Một số thành viên lo rằng rule dựa trên thay đổi ID/IoU đã đủ và AI có thể nhầm khi các con vật giống nhau hoặc che khuất nhau. Nhóm chốt không xây Agent tự sửa; trước hết sẽ benchmark rule baseline với workflow kết hợp đặc trưng chuyển động/ngoại hình và human review. Chỉ tiếp tục nếu pilot cho thấy workflow tăng recall hoặc giảm thời gian rõ rệt mà không làm tăng lỗi sửa sai.
```

---

## Phase 4 — Quick Validation + Research

### 4.1. Quick validation (ít nhất 1 cách: interview 2-3 người hoặc survey 5-10 người)

| Nguồn | Số người / mẫu | Tín hiệu xác nhận (kèm quote nguyên văn) | Tín hiệu phản bác | Nhóm sửa problem thế nào |
| --- | ---: | --- | --- | --- |
| Interview | Chưa thực hiện | Kịch bản phỏng vấn ở mục 4.1a; cần thu tối thiểu 2 quote nguyên văn từ AI Engineer/annotator ngoài data owner. | Chưa có dữ liệu. | Chưa dùng để thay đổi Problem Statement. |
| Survey / poll (evidence thứ cấp) | 1 user study công bố: 7 người xử lý 30 video camera trap | [User study về tagging video động vật](https://doi.org/10.1002/wlb3.01539) cho 7 người xử lý 30 video: quy trình bán tự động mất 768 ± 83 giây, so với 3.111 ± 269 giây khi làm tay (xấp xỉ nhanh hơn 4 lần); điểm dễ thực hiện lần lượt là 7,4 ± 0,9 và 2,0 ± 0,3 trên thang 1–10. | Khác domain: camera trap, không phải QA ID switch cho video lợn. Các số trên không thể dùng làm baseline hoặc cam kết ROI của nhóm. | Dùng như bằng chứng thứ cấp cho pitch: video review/annotation có pain về thời gian và UX. Trước khi Go, nhóm vẫn chạy script ở mục 4.1a với 5–10 phản hồi hoặc 2 interview + bấm giờ trên video lợn. |
| Log / ticket / review (nếu có) | 1 self-report của data owner | Data owner báo rằng phần tốn thời gian nằm ở việc tìm đúng frame bắt đầu bị đổi ID và phải tua lại nhiều lần. Đây là tóm tắt do nhóm ghi lại, chưa phải quote nguyên văn đã được người nói xác nhận. | Với video ngắn hoặc ít đối tượng, kiểm tra thủ công vẫn có thể chấp nhận được; một self-report chưa đủ để suy ra pain hay ROI cho toàn bộ AI Engineer/annotator. | Thu hẹp actor sang người QA video dài, nhiều đối tượng, có overlap/occlusion; giữ quyết định Not Yet và yêu cầu thêm interview/bấm giờ trước khi build. |

**Insight sau validation (1-2 câu — pain thật nằm ở đâu):**

```text
Điểm đau lớn nhất không nằm ở thao tác sửa ID. Nó nằm ở việc phải xem và tua qua rất nhiều frame để tìm đúng lúc lỗi bắt đầu, nhất là khi các đối tượng giao nhau hoặc che khuất nhau. Vì vậy, hướng hợp lý hơn là đánh dấu những đoạn đáng nghi để người dùng kiểm tra nhanh, thay vì để hệ thống tự sửa hoàn toàn.
```

Bằng chứng đính kèm (nếu có): `02-group-problem-statement-survey.png`, `02-group-problem-statement-interview-notes.md` — chưa có; bổ sung sau khi chạy survey/interview.

### 4.1a. Survey / interview script cần chạy trước khi Go

> Đây là kịch bản thu thập dữ liệu, chưa phải kết quả survey. Nhóm cần lưu câu trả lời gốc và chỉ trích quote khi người trả lời đồng ý.

1. Bạn làm vai trò gì (AI Engineer, annotator, researcher) và thường QA bao nhiêu video/frame hoặc bao nhiêu đối tượng mỗi tuần?
2. Hãy chọn một video QA gần nhất: từ lúc mở output đến lúc lưu annotation, bạn mất bao nhiêu phút? Ước lượng riêng thời gian tìm/tua lại đoạn nghi vấn và thời gian sửa ID.
3. ID switch thường xuất hiện trong tình huống nào: giao nhau, che khuất, mất detection/tái xuất hiện, hay ngoại hình gần giống? Có thể mô tả một case cụ thể không?
4. Hiện bạn dùng rule, tracker hoặc tool nào để flag bất thường? Phần nào đã đủ tốt và phần nào vẫn phải xem tay?
5. Nếu tool chỉ xếp hạng các đoạn nghi vấn (không tự sửa), bạn cần recall/precision hoặc số candidate ở mức nào để nó thực sự tiết kiệm thời gian? Bạn lo rủi ro nào nhất?

**Cách tổng hợp:** lấy tối thiểu 2 interview độc lập hoặc 5–10 survey responses; ghi median phút QA/video, median tỷ trọng thời gian tìm đoạn lỗi, số người gặp overlap/occlusion và 1 quote phản bác. Không dùng câu trả lời này để suy diễn sang domain khác.

### 4.2. Research giải pháp đã có (ít nhất 2-3 tools/patterns + 1-2 link kiểm được)

| Nguồn / tool / case | Link | Họ giải quyết bước nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
| --- | --- | --- | --- | --- | --- |
| Survey học thuật về MOT | [Multiple Object Tracking in Deep Learning Approaches: A Survey](https://www.mdpi.com/2079-9292/10/19/2406) | Tổng quan các phương pháp MOT, benchmark và đánh giá; nêu che khuất và biến đổi ngoại hình/chuyển động là các thách thức cho việc duy trì track. | Nguồn học thuật kiểm được, giúp kiểm tra rằng bối cảnh giao nhau/che khuất của nhóm là khó khăn đã được nghiên cứu trong MOT. | Phần tóm tắt không khẳng định riêng ID switch là vấn đề trung tâm, không đo thời gian QA annotation và không chứng minh hiệu quả trên video lợn. Không được suy diễn benchmark thành ROI trong pilot. | Dùng nguồn này để giải thích vì sao các đoạn che khuất đáng được ưu tiên review; ID switch vẫn là định nghĩa lỗi vận hành mà nhóm phải gán nhãn và đo trong pilot. |
| Systematic review về MOT trong chăn nuôi | [Multiobject tracking in livestock](https://www.sciencedirect.com/science/article/pii/S1751731125000862) | Tổng quan MOT cho gia súc; tập trung vào việc duy trì identity trong video dài, khi có che khuất, ngoại hình tương tự và chuyển động không tuyến tính. | Review theo PRISMA trên 111 bài báo giai đoạn 2019–2025, nên khớp trực tiếp hơn với bối cảnh tracking lợn của nhóm. | Đây là evidence về khó khăn kỹ thuật của domain, không phải survey người dùng; không cho biết annotator mất bao lâu để QA hoặc hệ thống nào có ROI tốt nhất. | Dùng để bảo vệ lý do chọn candidate trong pitch, nhưng vẫn phải chạy interview/bấm giờ với người QA trước khi Go. |
| Nghiên cứu có survey người dùng về xử lý video động vật | [Improving manual tagging of camera-trap videos for wildlife studies](https://doi.org/10.1002/wlb3.01539) | So sánh quy trình gắn nhãn thủ công với công cụ hỗ trợ trực quan; có survey trải nghiệm sau tác vụ với 7 người xử lý 30 video. | Mục Results của full text báo quy trình bán tự động mất 768 ± 83 giây, so với 3.111 ± 269 giây làm tay; điểm dễ thực hiện là 7,4 ± 0,9 so với 2,0 ± 0,3 trên thang 1–10. Đây là bằng chứng gần với pain “xem video + gắn nhãn” hơn survey MOT thuần kỹ thuật. | Domain là camera trap động vật hoang dã và công cụ tagging, không phải QA ID switch cho đàn lợn. Cỡ mẫu, tác vụ và thiết kế công cụ khác nên không được lấy tỷ lệ 4× làm cam kết ROI của nhóm. | Dùng trong pitch như một case cho thấy workflow hỗ trợ người dùng có thể giảm tải video-review; pilot của nhóm vẫn cần bấm giờ trên chính video lợn và đo lỗi ID. |
| SlowFast (PySlowFast) | [Repository chính thức](https://github.com/facebookresearch/SlowFast) | Mã hóa thông tin không gian–thời gian của một đoạn video; có thể dùng đặc trưng chuyển động quanh thời điểm hai track giao nhau hoặc bị che khuất để hỗ trợ chấm điểm đoạn nghi vấn. | Khai thác nhiều frame thay vì đánh giá từng ảnh độc lập; repository cung cấp các video backbone, model zoo và công cụ train/evaluation. | SlowFast được thiết kế chủ yếu cho video classification/action detection, không trực tiếp phát hiện hay sửa ID switch. Muốn áp dụng phải tạo clip/tube theo từng đối tượng, có dữ liệu huấn luyện đúng domain và tốn compute; vì vậy quá nặng cho baseline đầu tiên. | Không chọn SlowFast làm lõi của MVP. Chỉ thử temporal feature khi rule + appearance embedding không phân biệt được các case che khuất/giao nhau. |
| CLIP-ReID | [Mã nguồn chính thức của bài báo](https://github.com/Syliz517/CLIP-ReID) | Trích xuất embedding ngoại hình cho từng crop đối tượng; so similarity của cùng track trước và sau một điểm nghi vấn để phát hiện khả năng hai identity đã bị tráo. | Phù hợp trực tiếp hơn với bài toán so khớp identity; có pipeline train/test và checkpoint cho các benchmark person/vehicle ReID. Có thể kết hợp với vị trí, IoU và lịch sử chuyển động để xếp hạng candidate. | Checkpoint công bố chủ yếu được huấn luyện trên người và phương tiện, không phải lợn; ngoại hình các cá thể gần giống và góc nhìn/ánh sáng thay đổi có thể làm similarity sai. Cần kiểm tra transfer learning hoặc fine-tune trên dữ liệu dự án, không được dùng metric benchmark của repository làm bằng chứng cho domain này. | Dùng embedding như một tín hiệu, không dùng làm quyết định duy nhất. Pilot phải so sánh rule-only với rule + ReID và giữ human review trước mọi lần sửa ID. |
| Ultralytics Multi-Object Tracking (ByteTrack/BoT-SORT và ReID) | [Tài liệu chính thức](https://docs.ultralytics.com/modes/track/) | Chạy detector + tracker để gán và duy trì ID qua các frame; hỗ trợ đổi tracker, chỉnh các ngưỡng association và bật ReID ở tracker phù hợp. | Tạo baseline nhanh, trả về bounding box/track ID và cho phép thử motion-only với phương án có appearance/ReID mà không phải tự xây toàn bộ tracker. | Đây là giải pháp tạo track hoặc giảm ID switch từ đầu, không phải công cụ QA tự động tìm và sửa lỗi trong annotation đã có. Kết quả phụ thuộc detector, cấu hình, mức che khuất và đặc điểm video. | Chạy ít nhất ByteTrack và BoT-SORT/ReID trên cùng video để tạo baseline. Tận dụng output/confidence làm input cho hàng đợi review, nhưng không tự ghi đè annotation. |
| CVAT — annotation editor | [Tài liệu Track mode](https://docs.cvat.ai/docs/annotation/manual-annotation/modes/) | Mở video/track, xem frame trước–sau và sửa annotation trong editor hiện có; Track mode hỗ trợ thao tác theo chuỗi frame. | Công cụ annotation có sẵn cho video và track; phù hợp làm nơi human review/sửa nên không cần xây editor mới cho pilot. | CVAT không tự phát hiện ID switch theo workflow của nhóm; interpolation/annotation có thể vẫn lan lỗi nếu người dùng không phát hiện kịp. | Dùng CVAT làm human-review surface và giữ file gốc/version; nhóm chỉ xây lớp rule/AI để xếp hạng candidate, không thay editor. |
| ByteTrack — paper gốc | [ECCV 2022 paper](https://arxiv.org/abs/2110.06864) | Liên kết low-score detection với tracklet để giảm object missing/fragmented trajectory, vốn hay xuất hiện khi bị che khuất. | Là baseline tracking rõ ràng và paper gốc báo cải thiện IDF1 trên benchmark; phù hợp để so sánh tracker/config trước khi xây thêm QA workflow. | Benchmark và đối tượng huấn luyện khác với video lợn; paper không giải quyết bước người đi tìm, review và sửa ID switch trong annotation có sẵn. | Nếu ByteTrack/tuning đã đạt recall và thời gian mục tiêu trên pilot thì dừng ở Rule/tracker baseline, không thêm AI scoring chỉ để “có AI”. |
| TrackEval | [Repository chính thức](https://github.com/JonathonLuiten/TrackEval) | So sánh output tracking với ground truth và tính các metric HOTA, CLEAR, Identity, trong đó có số ID switch (`IDSW`). | Cung cấp thước đo định lượng và hỗ trợ định dạng MOTChallenge; phù hợp để so sánh current workflow, rule-only và workflow có ReID trên cùng một ground-truth subset. | Chỉ đánh giá được khi có ground truth đáng tin cậy; không tự xác định annotation nào đúng và không sửa ID. Metric tốt trên subset nhỏ cũng chưa chứng minh hệ thống tổng quát cho toàn bộ dataset. | Dùng TrackEval làm lớp đánh giá, không gọi nó là giải pháp phát hiện. Hai người phải review chéo ground truth trước khi dùng IDSW/IDF1 để kết luận. |

**Research takeaway (2-3 câu — nên build gì / không build gì):**

```text
Research MOT xác nhận che khuất và biến đổi ngoại hình/chuyển động làm việc duy trì track khó hơn; còn ID switch là lỗi vận hành mà nhóm cần tự định nghĩa và đo trên pilot. Các study annotation/video-review chỉ là evidence thứ cấp, không thể thay cho pain hoặc ROI trên video lợn. Hướng nên thử là workflow QA nhỏ: rule dùng IoU, quỹ đạo và sự kiện mất–tái xuất hiện để tạo candidate; CLIP-ReID hoặc ReID chỉ hỗ trợ chấm điểm ngoại hình; người dùng mở candidate trong CVAT để xem và quyết định sửa. SlowFast chưa phù hợp MVP; nếu ByteTrack hoặc rule đã đạt ngưỡng, nhóm sẽ không thêm AI scoring chỉ để bài trông “AI hơn”.
```

> Lưu ý: không dùng số liệu AI đưa nếu không verify được link chính thức. Ghi rõ giả định chưa chắc.

---

## Phase 5 — Workflow + Problem Statement

### 5.1. Current workflow bản nhóm

Dán workflow hoặc link file: `02-group-problem-statement-workflow.png/pdf/md`

```text
[1 Chạy tracker/xuất annotation: ~5' - AI Engineer] → [2 Mở video và track: ~3'] → [3 Xuất hiện giao nhau/che khuất hoặc mất–tái xuất hiện detection] → [4 Xem tuần tự để tìm đoạn có vấn đề: ~25' - bottleneck] → [5 Tua lại và đối chiếu trước/sau: ~10'] → [6 Xác nhận frame bắt đầu switch: ~3'] → [7 Sửa ID + lưu file: ~4'] → [8 Kiểm tra metric/QA lại: chưa đo]

Tổng baseline tạm: ~50 phút/video hoặc một vòng QA, chưa gồm bước kiểm tra metric/QA lại ở bước 8. Thời gian từng bước là phân bổ ước lượng từ problem card, cần bấm giờ lại trong pilot.
```

| Bước | Actor | Input | Output | Thời gian / tần suất | Ghi chú (handoff? bottleneck?) |
| --- | --- | --- | --- | --- | --- |
| 1 | AI Engineer / sinh viên CV | Video, detector/tracker, config | File track gồm frame, ID, bounding box | ~5 phút/mỗi video hoặc mỗi vòng QA | Máy chạy tracker; thời gian chưa gồm inference dài nếu video lớn. |
| 2 | Cùng actor | Video overlay + annotation | Phiên review đã mở | ~3 phút/vòng | Handoff từ output máy sang người. |
| 3 | Tracker + bối cảnh video | Các track đang chạy | Giao nhau, che khuất, mất detection hoặc tái xuất hiện | Xảy ra theo nội dung video | Bước gặp vấn đề: đây là trigger làm identity có thể bị gán nhầm; người chưa chắc nhận ra ngay. |
| 4 | Cùng actor | Chuỗi frame có ID | Các thời điểm “có vẻ bất thường” trong trí nhớ/ghi chú | ~25 phút/vòng | Bottleneck: phải xem tuần tự để tìm ra bước 3; dễ mỏi mắt và bỏ sót. |
| 5 | Cùng actor | Đoạn nghi vấn | So sánh identity trước/sau giao nhau, che khuất | ~10 phút/vòng | Tua đi/tua lại nhiều lần; các cá thể giống nhau làm kết luận khó. |
| 6 | Cùng actor | Đoạn đã đối chiếu | Timestamp/frame bắt đầu ID switch | ~3 phút/case | Human quyết định đây là switch thật hay chỉ mất detection/tái xuất hiện. |
| 7 | Cùng actor / annotator | Track sai đã xác nhận | Track ID đã sửa và lưu | ~4 phút/case | Có thể phải sửa một dải frame sau điểm switch. |
| 8 | Cùng actor | Annotation đã lưu | Metric/spot-check sau sửa | Chưa được thực hiện ổn định; chỉ chạy trong pilot | Đây là guardrail dự kiến, chưa thuộc baseline current workflow nên không tính vào 5 bước thủ công. |

**Bottleneck chính (2-3 câu):**

```text
Sự cố thật sự xuất hiện ở bước 3, khi các đối tượng giao nhau, bị che khuất hoặc mất rồi tái xuất hiện; lúc đó tracker có thể gán nhầm identity. Bottleneck nằm ở bước 4–5: người phải xem toàn bộ chuỗi và tua lại để tìm một số ít đoạn có sự cố đó, chứ không phải ở thao tác sửa ID. Với video khoảng 1.800 frame, phần lớn thời gian được dùng để loại các frame bình thường; lỗi sau che khuất còn có thể lan sang nhiều frame và khó nhận biết bằng mắt.
```

### 5.2. Future workflow bản nhóm

Phải nhìn ra 5 thứ: bước nào máy (Rule), bước nào AI, bước nào người, boundary ở đâu, fallback khi AI sai.

```text
[1 Parse track + rule kiểm tra trùng ID/nhảy vị trí: ~1' - máy] → [2 Tạo candidate window quanh giao nhau, che khuất, ID mất/tái xuất hiện: ~2' - workflow] → [3 AI/appearance model chấm điểm cặp identity: ~3'] → [4 Xếp hạng và mở đúng cửa sổ nghi vấn: ~1' - máy] → [5 Human review trước/sau: ~6' - boundary] → [6 Người sửa ID đã xác nhận: ~2'] → [7 Chạy TrackEval trên subset có ground truth + spot-check: ~1']

Fallback: nếu model lỗi, confidence thấp hoặc pilot cho recall không đạt ngưỡng, tắt bước AI và dùng danh sách candidate từ rule; người quay lại review toàn video theo cách cũ. Không tự sửa ID và luôn giữ bản annotation gốc để rollback.
```

**Before/after impact:**

| Metric | Trước | Sau kỳ vọng | Cách đo |
| --- | ---: | ---: | --- |
| Tổng thời gian | ~50 phút/video hoặc vòng QA (self-report, chưa bấm giờ độc lập) | ≤15 phút trên cùng video/subset | Bấm giờ từ lúc mở output đến lúc lưu bản sửa; chạy tối thiểu 5 video cho mỗi phương án. |
| Số bước | 8 | 7 | Đếm các bước có input/output riêng trong sơ đồ. |
| Số bước thủ công | 5 bước (2, 4–7) | 2 bước (review và sửa) | Đếm thao tác người làm trong current workflow; bước 3 là sự kiện do tracker/bối cảnh video tạo ra, không tính là bước thủ công. Bước 8 là guardrail chưa có quy trình độc lập ổn định nên không tính vào baseline. |
| Bottleneck chính | Xem tuần tự và tua lại để tìm sự cố ở bước giao nhau/che khuất (~35 phút) | Review top-k cửa sổ nghi vấn (~6 phút mục tiêu) | Log số cửa sổ, phút review và tỷ lệ thời gian dành cho đoạn không có lỗi. |
| Risk mới | Mỏi mắt, bỏ sót ID switch | False negative bỏ sót switch; false positive làm tăng review; appearance model nhầm cá thể giống nhau | Trên ground truth pilot, đo recall, precision và số lần người sửa nhầm do gợi ý; spot-check ngẫu nhiên phần không bị flag. |

### 5.3. Problem Statement v0 (mỗi field 2-3 câu)

| Field | Nội dung |
| --- | --- |
| **Actor** | Sinh viên/AI Engineer làm multi-object tracking và chịu trách nhiệm QA annotation hoặc output tracker trên video nhiều cá thể. Họ có quyền xem, sửa và xuất track ID. |
| **Workflow** | Sau khi chạy tracker, trong video có thể xảy ra giao nhau, che khuất hoặc mất–tái xuất hiện detection làm identity có nguy cơ bị gán nhầm. Người mở video overlay, xem tuần tự để tìm đoạn đó, tua lại frame trước/sau, xác nhận frame bắt đầu switch rồi sửa và lưu annotation. Việc này lặp lại cho mỗi video hoặc mỗi vòng QA dataset. |
| **Bottleneck** | Sự cố xuất hiện ở các đoạn giao nhau, che khuất hoặc mất–tái xuất hiện, nhưng người phải tìm đúng đoạn và frame đầu tiên bằng mắt; riêng xem tuần tự và đối chiếu đang được ước lượng khoảng 35/50 phút mỗi vòng. Ngoại hình gần giống khiến lỗi dễ bị bỏ sót hoặc xác định nhầm. |
| **Impact** | Một ID sai có thể kéo dài qua nhiều frame, làm giảm chất lượng ground truth/tracker và khiến metric association không phản ánh đúng. Quy mô thời gian QA trên dataset lớn chưa có validation độc lập; nhóm không dùng claim này để dự báo ROI. |
| **Success Metric** | Trên cùng tập video có ground truth: giảm median thời gian QA từ baseline bấm giờ xuống ≤30% (mục tiêu tham khảo 50→15 phút), recall phát hiện ID switch ≥90%, precision ≥70%, và không tăng số IDSW sau khi người sửa. Báo cả số lượng mẫu và khoảng dao động, không chỉ báo trung bình. |
| **Boundary** | Hệ thống chỉ flag/xếp hạng cửa sổ nghi vấn và đưa bằng chứng trước/sau; con người xác nhận và thực hiện sửa. Không tự đổi ID, không thay detector/tracker production, không kết luận hiệu quả ngoài domain/video pilot. |

**Câu hỏi AI phản biện v0 (nếu có):**

- Field nào mơ hồ: “AI phát hiện ID switch” chưa nói có ground truth hay không, switch được định nghĩa theo frame liền trước hay lần xuất hiện gần nhất, và baseline 50 phút mới chỉ là self-report.
- Tôi sửa gì: Thu hẹp intervention thành candidate ranking + human review; yêu cầu subset gán nhãn frame bắt đầu switch, thêm precision/recall/IDSW và bấm giờ trên cùng video trước–sau.

---

## Phase 6 — Rule / Workflow / Agent + Decision

### 6.0. Ma trận độ phù hợp (suy nghĩ nhanh, không thay quyết định cuối)

- Độ mơ hồ: [ ] Thấp (có đúng/sai rõ) / [x] Cao (nhiều cách trả lời vẫn OK) — Vì sao: nếu không có ground truth, hai cá thể giống nhau sau che khuất có thể được nối theo nhiều cách hợp lý; cần xem cả chuyển động, ngoại hình và lịch sử track.
- Độ phức tạp: [ ] Thấp (1-2 bước) / [x] Cao (3+ bước/nguồn, phụ thuộc nhau) — Vì sao: phải parse track, tạo candidate, so khớp qua nhiều frame, xếp hạng, cho người xác nhận, sửa và đánh giá lại.

**Bài toán nhóm nằm ở ô nào:**

```text
Ô “độ mơ hồ cao – độ phức tạp cao”. Đây là tín hiệu để cân nhắc Agent, nhưng không tự động đồng nghĩa phải chọn Agent.
```

**Vì sao (2-3 câu):**

```text
Việc xác định identity qua giao nhau/che khuất cần nhiều tín hiệu và các bước phụ thuộc nhau, nên rule đơn lẻ khó bao phủ mọi case. Tuy nhiên đường đi xử lý vẫn cố định và human review là gate bắt buộc; vì vậy một Workflow có AI ở bước scoring phù hợp hơn Agent tự lập kế hoạch.
```

### 6.1. So sánh Rule / Workflow / Agent (so trên cùng 1 bài)

| Mức | Phương án cho bài toán nhóm | Khi nào đủ | Rủi ro | Chọn? (Dùng cho bước nào?) |
| --- | --- | --- | --- | --- |
| **Rule** | Flag duplicate ID trong cùng frame, bbox nhảy xa/tốc độ bất thường, track mất rồi ID mới xuất hiện gần vị trí cũ, hoặc hai track giao nhau. | Đủ làm baseline và đủ dùng nếu đạt recall ≥90% với lượng false positive người review được trong ≤15 phút/video. | Threshold phụ thuộc cảnh; dễ bỏ sót switch “mượt” và báo nhầm khi vật di chuyển nhanh/che khuất. | Có, dùng ở bước parse, kiểm tra cứng và tạo candidate window. |
| **Workflow** | Chuỗi cố định: rule tạo candidate → appearance/ReID chấm điểm → xếp hạng → người xác nhận/sửa → TrackEval/spot-check. | Đủ khi input/output mỗi bước rõ, không cần hệ thống tự đổi chiến lược và người luôn là gate trước thay đổi dữ liệu. | Model có thể tạo false negative/positive; tích hợp định dạng annotation và calibration confidence cần công sức. | Chọn mức chính, dùng cho toàn bộ quy trình triage và human-in-the-loop. |
| **Agent** | Tự chọn tool/model, điều chỉnh ngưỡng, mở editor và đề xuất hoặc thực hiện chuỗi sửa theo từng video. | Chỉ đáng dùng nếu nhiều loại dữ liệu/tool buộc phải lập kế hoạch động và workflow cố định đã chứng minh không đủ. | Khó audit, hành động sai có thể làm hỏng hàng loạt ID; tốn thời gian/chi phí và vượt scope pilot. | Không chọn; không giao quyền tự sửa annotation hay tự thay config. |

**5 câu hỏi chốt (trả lời câu đầy đủ):**

1. Rule có thể tạo phần lớn candidate rõ như duplicate ID, nhảy vị trí hoặc mất/tái xuất hiện, nhưng hiện chưa có ground truth để khẳng định giải được 70–80% case; đây là giả thuyết phải benchmark trước.
2. Các bước chính đi theo một đường cố định; chỉ rẽ nhánh ở human review: xác nhận switch thì sửa, không phải switch thì dismiss, confidence thấp thì mở rộng cửa sổ hoặc review thủ công.
3. Không cần Agent tự lập kế hoạch hay tự gọi tool, vì thứ tự xử lý, input/output và quyền quyết định đều xác định trước; orchestration bằng script/workflow là đủ.
4. AI Engineer/annotator phát hiện sai đầu tiên khi xem đoạn trước–sau trong CVAT; mục tiêu xử lý mỗi candidate trong 1–2 phút, còn case không kết luận được sẽ gắn “uncertain” và chuyển review chéo thay vì tự sửa.
5. Có thể hạ từ Agent xuống Workflow và nhóm chọn hạ như vậy; sau pilot, nếu rule một mình đạt recall/time target thì tiếp tục hạ xuống Rule để giảm rủi ro và chi phí.

**Mức chọn:**

```text
Workflow (kết hợp Rule + AI scoring + human review)
```

**Vì sao chọn (3-4 câu):**

```text
Quy trình có nhiều bước nhưng thứ tự ổn định, nên Workflow đủ để nối parser, rule, appearance/ReID scoring, hàng đợi review và bước đánh giá. AI chỉ xử lý phần mơ hồ là so khớp identity/xếp hạng rủi ro; rule xử lý kiểm tra cứng và người chịu trách nhiệm xác nhận/sửa. Thiết kế này dễ đo từng bước, audit được và có thể tắt AI mà không làm mất dữ liệu gốc.
```

**Vì sao không chọn mức đơn giản hơn (2-3 câu):**

```text
Rule đơn thuần có thể bắt các bất thường hình học rõ nhưng có nguy cơ bỏ sót switch khi quỹ đạo vẫn liên tục sau giao nhau hoặc che khuất. Vì các cá thể có thể rất giống nhau, cần thử thêm tín hiệu appearance/temporal để xếp hạng; nếu pilot chứng minh rule đã đạt ngưỡng thì nhóm sẽ bỏ bước AI và dùng phương án đơn giản hơn.
```

### 6.2. Problem Statement v1 (v0 sửa chặt hơn + 3 field cuối)

| Field | Nội dung |
| --- | --- |
| **Actor** | Sinh viên/AI Engineer làm multi-object tracking, trực tiếp QA và sửa track ID cho video nhiều cá thể (pilot: dữ liệu tracking hành vi lợn). |
| **Workflow** | Chạy tracker/xuất annotation → khi có giao nhau, che khuất hoặc mất–tái xuất hiện detection thì rule tạo candidate window → appearance/ReID chấm điểm → xếp hạng → người xem frame trước/sau → người sửa ID → đánh giá/spot-check. Workflow chạy cho mỗi video hoặc mỗi vòng QA dataset. |
| **Bottleneck** | Sự cố có thể phát sinh lúc giao nhau, che khuất hoặc mất–tái xuất hiện detection; người hiện phải xem tuần tự và tua lại hàng nghìn frame để tìm frame đầu tiên bị đổi identity. Ước lượng hiện tại là ~35/50 phút ở hai bước tìm và đối chiếu; cá thể gần giống nhau làm việc xác định càng khó. |
| **Impact** | Switch không được sửa có thể lan qua nhiều frame, làm sai annotation và giảm chất lượng association của tracker. Quy mô thời gian QA trên dataset lớn chưa có validation độc lập nên chưa dùng để dự báo ROI. |
| **Success Metric** | Trên cùng ground-truth subset: median QA time giảm ≥70% hoặc còn ≤15 phút/video; recall phát hiện switch ≥90%; precision ≥70%; số IDSW sau human-approved correction không tăng. Đồng thời ghi số candidate/video và tỷ lệ case “uncertain”. |
| **Boundary** (làm / không làm) | Làm: phát hiện/xếp hạng đoạn nghi vấn, hiển thị bằng chứng và hỗ trợ người review. Không làm: tự đổi ID, tự ghi đè file gốc, xây editor mới, thay tracker production hoặc khái quát ngoài domain pilot. |
| **AI intervention point** (can thiệp sau bước nào, trước bước nào) | Sau khi rule đã parse track và tạo cửa sổ ứng viên, trước khi người mở đoạn để xác nhận. AI chỉ chấm similarity/risk và sắp thứ tự, không có quyền sửa. |
| **Mức chọn** (Rule / Workflow / Agent + 1 câu vì sao) | Workflow: nhiều bước cố định cần phối hợp rule, AI và người, nhưng không cần năng lực tự lập kế hoạch/hành động của Agent. |
| **Rủi ro & người thật kiểm tra** (rủi ro lớn nhất + ai kiểm tra bằng cách nào) | Rủi ro lớn nhất là false negative khiến switch bị bỏ qua hoặc false positive dẫn tới sửa nhầm. AI Engineer/annotator xem tối thiểu một cửa sổ trước–sau, chỉ sửa khi đủ bằng chứng; QA thứ hai spot-check ngẫu nhiên vùng không bị flag và TrackEval đo trên subset có ground truth. |

### 6.3. Final decision

| Câu hỏi | Yes / Not Yet / No | Ghi chú (câu đầy đủ) |
| --- | --- | --- |
| Actor + workflow rõ chưa? | Yes | Actor là người làm tracking/annotation QA; input, output, bottleneck và human boundary đã được mô tả theo từng bước. |
| Baseline + metric đo được chưa? | Not Yet | Có baseline tự báo cáo ~50 phút và mục tiêu ~15 phút, nhưng chưa bấm giờ trên nhiều video; precision/recall/IDSW chưa có ground truth pilot. |
| Data/input đủ dùng chưa? | Not Yet | Có dữ liệu dự án làm điểm xuất phát nhưng chưa thống kê số video dùng được, chưa khóa format và chưa tạo subset có frame bắt đầu switch được review chéo. |
| AI sai, hậu quả chấp nhận được không? | Yes, có điều kiện | Chấp nhận được nếu AI chỉ đề xuất, file gốc bất biến và người xác nhận trước khi sửa; không chấp nhận auto-correction hoặc bỏ spot-check vùng không bị flag. |
| Có người review/owner không? | Yes | Ngô Gia Quốc là domain/data owner cho pilot; một thành viên khác phải review chéo nhãn ground truth và sample không bị flag. |
| Có cách non-AI đơn giản hơn không? | Yes | Rule theo duplicate ID, IoU/quỹ đạo, mất–tái xuất hiện là baseline bắt buộc; nếu đạt ngưỡng thì không dùng AI. |

**Decision cuối cùng: Not Yet**

Nhóm chưa build workflow AI hoàn chỉnh ở thời điểm này; chỉ tiếp tục bước validation và chuẩn bị pilot.

**Lý do (3-4 câu dựa trên bằng chứng):**

```text
Problem và workflow đủ hẹp để làm pilot, đồng thời nguồn chính thức xác nhận có công cụ tracking, annotation và metric sẵn để không phải xây lại từ đầu. Tuy nhiên evidence pain hiện mới là self-report của một thành viên; chưa có interview/survey độc lập, baseline bấm giờ hay ground truth ID-switch được review chéo. Vì vậy nhóm chỉ Go cho bước chuẩn bị/validation, chưa Go cho việc build workflow AI hoàn chỉnh. Quyết định sẽ chuyển sang Go nếu dữ liệu pilot đủ và rule baseline chưa đạt mục tiêu nhưng AI-assisted workflow tạo cải thiện đo được.
```

**Nếu Go — pilot nhỏ nhất (data nào, chạy tay ra sao, đo 3 số nào):**

```text
Khi đủ điều kiện Go: chọn 5 video đại diện, tạo ground-truth subset gồm các cửa sổ có/không có switch và giữ nguyên annotation gốc. Chạy tay ba phương án trên cùng dữ liệu: review toàn video, rule-only, rồi rule + appearance/ReID ranking + human review. Đo ba số chính: (1) median phút QA/video, (2) recall phát hiện ID switch, (3) precision của candidate; dùng IDSW sau sửa và số sửa nhầm làm guardrail.
```

**Nếu Not Yet — cần validate gì trước:**

```text
Phỏng vấn ít nhất 2 AI Engineer/annotator khác và lưu quote nguyên văn; bấm giờ current workflow trên tối thiểu 5 video; thống kê số frame, số switch và tình huống che khuất. Sau đó hai người gán nhãn chéo frame bắt đầu switch trên một subset, giải quyết bất đồng để tạo ground truth, rồi benchmark rule-only trước khi thêm AI.
```

**Nếu No-Go — làm gì thay AI:**

```text
Không áp dụng vì quyết định hiện tại là Not Yet. Nếu pilot dẫn tới No-Go, dùng rule để ưu tiên một số đoạn rõ ràng và tiếp tục human review trong CVAT, hoặc thử đổi/tune tracker như ByteTrack/BoT-SORT thay vì xây AI QA riêng.
```

**Exit / rollback (khi nào dừng AI, quay về cách cũ):**

```text
Dừng bước AI và quay về rule-only hoặc review thủ công nếu recall trên ground truth <90%, thời gian median không giảm ít nhất 30%, số candidate false positive làm review vượt baseline, hoặc xuất hiện bất kỳ lần tự động sửa/ghi đè dữ liệu ngoài boundary. Luôn version file annotation, giữ bản gốc chỉ đọc và rollback bằng cách bỏ file sửa của lần chạy; không sửa chồng lên ground truth.
```

---

### Self-check nộp phần 02 (nhóm)

- [x] Có nhật ký hội tụ 9-12 → 1 (cluster + shortlist + score)
- [ ] Có validation (quote thật) + research (link kiểm được) — research link đã kiểm được và self-report đã ghi theo dạng tóm tắt, nhưng còn thiếu quote nguyên văn đã được data owner xác nhận hoặc interview/survey độc lập.
- [x] Có workflow trước/sau đủ thời gian, handoff, bottleneck, boundary, fallback
- [x] Có PS v0 → v1, metric có trước/sau + cách đo, boundary có làm/không làm
- [x] Có so sánh Rule/Workflow/Agent + Decision Go/Not Yet/No-Go có lý do
