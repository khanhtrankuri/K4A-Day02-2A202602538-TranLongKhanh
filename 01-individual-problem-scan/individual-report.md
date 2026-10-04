# 01 — Individual Problem Scan

> Điền theo Phase 1 + Phase 2 trong `01-worksheet.md`. Tự scan trước, dùng AI sau để phản biện. Không copy ví dụ Weekly Report.

## Thông tin cá nhân

- Họ và tên: Trần Long Khánh
- Mã học viên: 2A202602538
- Vai trò / bối cảnh (VD: sinh viên năm X, intern PM, ...): Sinh viên năm cuối, đang làm AI Engineer Intern
- Công việc hằng tuần (3-5 gạch đầu dòng để soi problem):
  - Train / fine-tune và đánh giá model Computer Vision (detection, tracking).
  - Convert và deploy model lên thiết bị edge (Jetson: TensorRT, GPU/DLA).
  - Setup môi trường, chuyển qua lại giữa nhiều project / máy (PC, server, Jetson).
  - Debug lỗi khi train, inference, convert model.
  - Dùng AI coding assistant để build feature / prototype mới rồi review lại code.

---

## Phase 1 — Scan 5+ problems (tối thiểu 5, khuyến khích 8-10)

**Cách điền:** mỗi dòng = việc gì + ai chịu + đo bằng gì. Cột `Dấu hiệu thật` bắt buộc có số: mất bao lâu (bấm giờ mấy lần), mấy lần/tuần, bao nhiêu người gặp, log/ticket/quote nào.

> Ghi chú trung thực: các con số dưới đây là **ước tính tự báo cáo** từ trải nghiệm 2-4 tuần gần nhất, chưa bấm giờ có hệ thống. Các dòng được chọn vào top 3 sẽ cần bấm giờ lại ít nhất 3 lần trước khi dùng làm baseline.

| # | Lăng kính (Lặp lại / Tốn thời gian / AI có thể tốt hơn / Pain từ người khác) | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu thật (số + bằng chứng) |
|---|---|---|---|---|
| 1 | Lặp lại / Tốn thời gian | Setup môi trường: mỗi lần chuyển project phải check lại version Python, CUDA, PyTorch, library; env không kiểm soát kỹ thì phải cài lại library hoặc xóa env làm lại. | Tôi, AI Engineer trong team | Khoảng 1-2 lần/tuần; một lần setup suôn sẻ ~20-30 phút, lần bị conflict ~45-120 phút. Tháng gần nhất phải xóa và tạo lại env khoảng 3 lần. |
| 2 | Lặp lại / Tốn thời gian | Fix bug khi build/deploy project AI: khó biết lỗi do code, torch, CUDA/driver hay phần cứng. | Tôi, AI Engineer, đồng nghiệp | Ví dụ thật: tìm nguyên nhân vì sao model chạy trên DLA của Jetson chậm hơn GPU mất ~2 buổi làm việc. Lỗi thường mất 30-180 phút/lỗi, khoảng 2-3 lỗi khó/tuần. |
| 3 | Tốn thời gian | Di chuyển nhiều giữa nhà, trường và nơi làm việc. | Tôi, đồng nghiệp | 40-60 km/ngày, ~2 giờ di chuyển/ngày, khoảng 4-5 ngày/tuần. (Pain thật nhưng không phải bài toán AI — giữ để đối chứng.) |
| 4 | Tốn thời gian | Dành nhiều thời gian buổi tối để chơi game, làm giảm thời gian tự học. | Tôi | 2-4 giờ/ngày. (Vấn đề thói quen cá nhân, giải bằng process fix, không phải AI.) |
| 5 | AI có thể tốt hơn / Tốn thời gian / Lặp lại | Build sản phẩm mới bằng AI coding assistant nhưng phải tự thiết kế kiến trúc, giám sát và kiểm chứng code AI sinh ra. | Tôi, đồng nghiệp dùng AI coding | Mỗi feature ~60-180 phút, trong đó review + test + sửa assumption sai chiếm ~50%; thường cần 3-5 vòng prompt → sửa trước khi chạy đúng. |
| 6 | Lặp lại / Tốn thời gian | Convert model sang ONNX/TensorRT cho Jetson: thử nhiều tổ hợp opset, precision (FP16/INT8), batch size rồi benchmark lại bằng tay. | Tôi, AI Engineer làm deploy | Mỗi model ~1-3 giờ, thường phải thử 3-6 cấu hình; kết quả benchmark ghi rời rạc trong terminal/notes. |
| 7 | Tốn thời gian / AI có thể tốt hơn | So sánh kết quả nhiều lần train: mở log/TensorBoard từng run, copy mAP/loss sang bảng để chọn checkpoint. | Tôi, team AI | ~30-45 phút mỗi lần so sánh, 2-3 lần/tuần; từng chọn nhầm checkpoint 1 lần vì copy sai cột. (Có thể giải bằng script/MLflow trước khi nghĩ đến AI.) |
| 8 | Pain từ người khác | Đồng nghiệp/thành viên mới hỏi lại cách chạy project vì README không cập nhật theo code. | Đồng nghiệp, thành viên mới, tôi (người trả lời) | Khoảng 3-5 câu hỏi/tuần dạng "chạy file nào", "cần version gì"; mỗi lần mất 10-20 phút giải thích hoặc ngồi setup cùng. |
| 9 | Pain từ người khác / Tốn thời gian | Kiểm tra annotation (bounding box, ID tracking) của dataset do người khác gán nhãn trước khi train. | Tôi, người gán nhãn, team AI | Dataset vài nghìn frame, kiểm tra thủ công mất vài giờ mỗi đợt; lỗi annotation phát hiện muộn làm phải train lại. (Trùng hướng với candidate #5, #6 của nhóm.) |
| 10 | Tốn thời gian / AI có thể tốt hơn | Đọc paper/repo mới để tìm kiến trúc hoặc kỹ thuật phù hợp cho bài toán đang làm. | Tôi | ~3-5 giờ/tuần; nhiều paper đọc xong mới biết không phù hợp phần cứng edge (Jetson) hoặc không có code. |

> Gợi ý tự soi: tuần trước mất nhiều thời gian nhất vào việc gì? Việc gì hay trì hoãn? Người khác hay hỏi lại câu gì? Workflow nào ai cũng biết là chậm?

**AI đã dùng ở Phase 1 (nếu có):**
- Prompt đã hỏi: "Đây là danh sách việc tôi làm hằng tuần với vai trò AI Engineer Intern. Hãy chỉ ra problem nào quá chung chung, problem nào không phải pain thật, và tôi cần đo gì để có dấu hiệu thật cho từng problem."
- Ý dùng được: AI chỉ ra bài "fix bug" và "build bằng AI" còn quá rộng, gợi ý thu hẹp vào một bước cụ thể (xác định root cause, review/kiểm chứng code); gợi ý thêm lăng kính "pain từ người khác" (câu hỏi lặp lại của đồng nghiệp, chất lượng annotation); nhắc phải ghi số đo (phút/lần, lần/tuần) thay vì "mất nhiều thời gian".
- Ý bỏ vì không phải pain thật: AI gợi ý "viết email/báo cáo tuần" và "lên lịch họp" nhưng tôi gần như không làm việc này nên bỏ. Problem #3 (di chuyển) và #4 (chơi game) giữ lại để đối chứng nhưng ghi rõ không phải bài toán AI.

**Self-check Phase 1:**
- [x] Đủ 5+ dòng, mỗi dòng có actor + số đo cụ thể (10 dòng)
- [x] Dùng ít nhất 3/4 lăng kính (dùng đủ 4/4: Lặp lại, Tốn thời gian, AI có thể tốt hơn, Pain từ người khác)
- [x] Không có dòng chung chung kiểu "mất nhiều thời gian"

---

## Phase 2 — Top 3 Problem Cards

### 2.1. Chọn top 3

Giữ bài nào: actor cụ thể, workflow vẽ được 3-7 bước, bottleneck ở 1 bước, impact đo được. Loại bài quá rộng.

| Rank | Problem (copy từ bảng scan) | Vì sao chọn (2-3 ý) | Điều còn chưa chắc |
|---|---|---|---|
| 1 |Setup môi trường. Mỗi lần chuyển project đều phải check version, library,.. | Workflow rất rõ: tạo env → cài dependency → kiểm tra CUDA/PyTorch/library → chạy project → phát hiện conflict → sửa/cài lại. Bottleneck nằm ở bước phát hiện dependency/version conflict. Có thể đo bằng thời gian setup, số lần lỗi, số lần phải recreate env. | Chưa có số liệu thật: trung bình setup một project mất bao lâu, bao nhiêu lần/tuần, bao nhiêu lần phải xóa env làm lại. |
| 2 | Fix bug. Khi build một project, việc dính bug là điều hết sức bình thường, nhưng khi fix thường mất rất nhiều thời gian, nguyên nhân có thể do code, phần cứng, thư viện,... | Pain xảy ra thường xuyên với AI Engineer. Workflow có thể vẽ: gặp lỗi → đọc log → xác định nhóm nguyên nhân → kiểm tra code/library/hardware → thử fix → rerun. Bottleneck rõ nhất là xác định root cause từ log và môi trường. Impact đo được bằng thời gian debug/lỗi và số lần thử trước khi fix được. | Hiện problem còn hơi rộng. Nên thu hẹp thành ví dụ: “Mất nhiều thời gian xác định root cause của lỗi khi deploy/train AI trên Jetson” thay vì toàn bộ mọi loại bug. |
| 3 | Build từ đầu một sản phẩm, nhưng phải ngồi kiểm soát AI, thiết kế kiến trúc cho AI làm, kiểm chứng code. | Đây là workflow thực tế khi dùng AI coding: mô tả yêu cầu → thiết kế kiến trúc → giao AI code → review → test → sửa prompt/code → tích hợp. Bottleneck có thể nằm ở review và kiểm chứng code AI sinh ra. Có khả năng đo bằng thời gian review, số vòng sửa, số bug của code do AI sinh ra. | Problem hiện quá rộng và chưa có bằng chứng số. Cần thu hẹp thành một bước cụ thể, ví dụ “Review và kiểm chứng code do AI sinh ra tốn nhiều thời gian”. |

### 2.2. Problem Cards chi tiết (lặp lại cho cả 3 cards)

---

#### Problem Card #1 — [Setup và quản lý môi trường cho project AI]

```text
Problem 1 câu:
Mỗi khi chuyển sang một project AI mới, tôi mất nhiều thời gian để tạo môi trường, kiểm tra version và xử lý xung đột giữa Python, CUDA, PyTorch và các thư viện.

Actor:
Tôi, AI Engineer, đồng nghiệp trong team AI.

Thời điểm / bối cảnh:
Khi bắt đầu project mới, clone project cũ sang máy khác, chuyển từ PC sang Jetson/server hoặc quay lại một project sau thời gian dài.

Current workflow 3-7 bước:
1. Clone project và đọc README/requirements.
2. Tạo Conda/venv mới.
3. Cài Python và các thư viện cần thiết.
4. Kiểm tra CUDA, PyTorch, driver và dependency.
5. Chạy thử project.
6. Nếu lỗi, tìm package/version xung đột.
7. Gỡ/cài lại package hoặc xóa env và tạo lại từ đầu.

Bottleneck:
Xác định chính xác package/version nào đang gây conflict và tìm được tổ hợp version tương thích.

Impact:
- Có thể mất từ vài chục phút đến vài giờ cho một lần setup lỗi.
- Khi phải tạo lại environment, toàn bộ thời gian cài đặt trước đó bị mất.
- Làm chậm việc bắt đầu coding/training/inference.
- Có thể ảnh hưởng cả đồng nghiệp nếu project không có environment reproducible.

Success metric:
- Giảm thời gian setup environment ít nhất 50%.
- Giảm số lần phải recreate environment.
- ≥ 80% dependency conflict được xác định đúng ngay trong lần phân tích đầu.
- Project có thể chạy được sau tối đa 1-2 vòng chỉnh dependency.

Non-AI alternative:
- Dùng Docker.
- Lock dependency bằng requirements.txt / environment.yml / poetry.lock.
- Viết script setup tự động.
- Chuẩn hóa base environment theo từng loại project.

AI hypothesis:
AI có thể đọc requirements, environment hiện tại, CUDA/Python/PyTorch version và error log để phát hiện conflict, đề xuất phiên bản tương thích và sinh command sửa environment.

Quick gut:

[ ] No AI / process fix
[ ] Rule
[x] Workflow
[ ] Agent
[ ] Chưa biết

Draft workflow Card #1

CURRENT STATE — khoảng 45-120 phút
(ước tính ban đầu, cần bấm giờ ít nhất 3 lần để xác nhận)

[1 Clone + đọc dependency: 10']
        ↓
[2 Tạo env + install: 15-30']
        ↓
[3 Chạy thử: 5']
        ↓
[4 Debug dependency/version: 20-60']  <-- BOTTLENECK
        ↓
[5 Reinstall / recreate env: 15-30']

FUTURE STATE — mục tiêu 20-40 phút

[1 Clone project + scan dependency: 5']
        ↓
[2 Tool tự collect Python/CUDA/GPU/package: 2']
        ↓
[3 AI phân tích compatibility + sinh fix plan: 3-5']
        ↓
[4 Human review command: 3']  <-- HUMAN BOUNDARY
        ↓
[5 Auto install + validation: 10-25']

Fallback:
Nếu AI đề xuất version sai thì không tự động thay đổi environment.
Hệ thống chỉ đưa command đề xuất + lý do + khả năng rollback.
Engineer review trước khi execute.

```
---

#### Problem Card #2 — [Xác định root cause khi project AI gặp lỗi]

```text
Problem 1 câu:
Khi project AI gặp lỗi, tôi mất nhiều thời gian để xác định lỗi đến từ code, library, CUDA/driver, phần cứng hay cấu hình hệ thống.

Actor:
Tôi, AI Engineer, đồng nghiệp phát triển/deploy AI.

Thời điểm / bối cảnh:
Trong lúc training, inference, convert model, TensorRT deployment hoặc chạy model trên Jetson/server.

Current workflow 3-7 bước:
1. Chạy chương trình và gặp lỗi.
2. Đọc traceback/log.
3. Search error trên Google/GitHub/Stack Overflow/documentation.
4. Đặt giả thuyết: code, library, driver, CUDA, hardware...
5. Chạy các command kiểm tra từng giả thuyết.
6. Thay config/package/code rồi chạy lại.
7. Lặp lại đến khi tìm được root cause.

Bottleneck:
Phân loại đúng root cause ngay từ đầu và biết cần kiểm tra thông tin nào tiếp theo.

Impact:
- Một lỗi khó có thể mất từ hàng chục phút đến nhiều giờ.
- Có nhiều vòng thử-sai không tạo ra thông tin mới.
- Engineer phải đọc log dài và tìm kiếm ở nhiều nguồn khác nhau.
- Ví dụ thực tế: cần tìm nguyên nhân vì sao workload trên Jetson/DLA chậm hơn GPU hoặc không thực sự chạy trên DLA.

Success metric:
- Giảm thời gian xác định root cause ≥ 40%.
- Giảm số vòng thử-sai trước khi xác định đúng nguyên nhân.
- Top-3 nguyên nhân AI đề xuất chứa root cause thật ≥ 80% trường hợp.
- Mỗi recommendation phải đi kèm command kiểm chứng.

Non-AI alternative:
- Tạo troubleshooting checklist.
- Chuẩn hóa logging.
- Viết script collect system information.
- Xây internal wiki chứa các lỗi đã gặp.

AI hypothesis:
AI có thể kết hợp traceback, log, hardware info, version library và lịch sử lỗi để phân loại nguyên nhân, xếp hạng hypothesis và đề xuất command kiểm chứng theo thứ tự.

Quick gut:

[ ] No AI / process fix
[ ] Rule
[ ] Workflow
[x] Agent
[ ] Chưa biết

Draft workflow Card #2

CURRENT STATE — khoảng 30-180+ phút
(cần log thời gian của ít nhất 3-5 bug để xác nhận)

[1 Gặp error: 1']
        ↓
[2 Đọc log: 10-20']
        ↓
[3 Search web/docs: 15-40']
        ↓
[4 Đặt hypothesis + thử fix: 20-90+']  <-- BOTTLENECK
        ↓
[5 Rerun]
        ↺ nếu lỗi tiếp tục thì quay lại bước 2-4

FUTURE STATE — mục tiêu 15-60 phút

[1 Error + log]
        ↓
[2 Auto collect system/package/hardware info: 1-2']
        ↓
[3 AI tạo ranked root-cause hypotheses: 2-5']
        ↓
[4 AI đưa diagnostic commands]
        ↓
[5 Human review + chạy command: 5-15']  <-- HUMAN BOUNDARY
        ↓
[6 AI cập nhật hypothesis → đề xuất fix]

Fallback:
Nếu confidence thấp hoặc nguyên nhân liên quan hardware/driver nguy hiểm,
AI chỉ đưa checklist kiểm tra và không tự động thay đổi hệ thống.
Engineer quyết định thao tác cuối cùng.
```

---

#### Problem Card #3 — [Review và kiểm chứng code do AI sinh ra]

```text
Problem 1 câu:
Khi dùng AI để build project mới, tôi vẫn mất nhiều thời gian thiết kế kiến trúc, kiểm tra code AI sinh ra, chạy test và sửa các lỗi hoặc assumption sai.

Actor:
Tôi, AI Engineer, developer dùng AI coding assistant.

Thời điểm / bối cảnh:
Khi bắt đầu project mới hoặc giao một feature tương đối lớn cho AI coding assistant.

Current workflow 3-7 bước:
1. Xác định yêu cầu của feature/project.
2. Thiết kế kiến trúc và chia task.
3. Prompt AI tạo code.
4. Đọc và review code AI sinh ra.
5. Chạy test/build/inference.
6. Phát hiện bug hoặc thiết kế sai.
7. Sửa prompt/code và lặp lại.

Bottleneck:
Review và xác minh code AI sinh ra có thực sự đúng với requirement, architecture và environment thực tế hay không.

Impact:
- Phải dành nhiều thời gian giám sát thay vì chỉ giao task cho AI.
- Code có thể chạy được nhưng logic sai hoặc không phù hợp architecture.
- Với AI/ML project, lỗi còn có thể liên quan tensor shape, device, library version, dataset hoặc GPU.
- Một feature lớn có thể cần nhiều vòng prompt → code → test → fix.

Success metric:
- Giảm ≥ 40% thời gian review code AI.
- Giảm số vòng prompt-sửa trước khi feature pass test.
- ≥ 90% code thay đổi phải có test hoặc validation tương ứng.
- Không merge code khi critical test chưa pass.

Non-AI alternative:
- Coding guideline rõ ràng.
- CI/CD.
- Unit test/integration test.
- Static analysis/linter/type checking.
- Chia task nhỏ trước khi giao AI.

AI hypothesis:
Một AI reviewer độc lập có thể đọc requirement + architecture + git diff, sinh test, kiểm tra assumption và đánh dấu đoạn code có rủi ro trước khi con người review.

Quick gut:

[ ] No AI / process fix
[ ] Rule
[x] Workflow
[ ] Agent
[ ] Chưa biết

Draft workflow Card #3

CURRENT STATE — khoảng 60-180+ phút / feature
(cần đo thực tế trên 3 feature)

[1 Viết requirement: 10-20']
        ↓
[2 Thiết kế architecture/task: 15-30']
        ↓
[3 AI generate code: 5-15']
        ↓
[4 Review + test + tìm assumption sai: 30-90+']  <-- BOTTLENECK
        ↓
[5 Prompt/fix lại]
        ↺ có thể lặp nhiều vòng

FUTURE STATE — mục tiêu 30-90 phút

[1 Requirement + acceptance criteria: 10']
        ↓
[2 AI coding]
        ↓
[3 AI reviewer sinh test + inspect diff: 5-15']
        ↓
[4 CI chạy validation]
        ↓
[5 Human review phần flagged/high-risk: 15-30']  <-- HUMAN BOUNDARY

Fallback:
Nếu AI reviewer và coding agent cùng cho kết quả sai,
CI/test vẫn là gate bắt buộc.
Không tự động merge khi test fail hoặc confidence thấp.
```

---

### 2.3. Card muốn pitch nhất (chuẩn bị 2 phút)

**Card tôi muốn pitch nhất:**

```
Problem Card #3: Review và kiểm chứng code do AI sinh ra

```

**Vì sao (2-3 câu: workflow gì, số đo gì, impact gì):**

```text
Workflow: viết requirement → thiết kế kiến trúc → prompt AI sinh code → review → chạy test/build/inference → sửa prompt/code, lặp nhiều vòng. Khi build model từ đầu, prompt phải chứa kiến trúc model và những gì mình đã nghiên cứu để AI có baseline tốt.
Số đo (ước tính, cần đo trên 3 feature): mỗi feature ~60-180 phút, trong đó bước review + test + tìm assumption sai chiếm ~50%, thường 3-5 vòng sửa.
Impact: bottleneck không nằm ở tốc độ AI sinh code mà ở việc con người kiểm chứng code có đúng requirement, kiến trúc và môi trường thật (tensor shape, device, version library) hay không; code "chạy được" nhưng sai logic có thể lọt vào project.
```

**Pitch 2 phút (bản nói):**

```text
Tôi là AI Engineer Intern, thường dùng AI coding assistant để build feature/model mới.
AI viết code rất nhanh, nhưng tôi vẫn mất khoảng một nửa thời gian của mỗi feature để đọc, chạy test và tìm các assumption sai mà AI tự đặt ra.
Điểm nghẽn nằm ở một bước: kiểm chứng code AI sinh ra trước khi tích hợp.
Nếu giảm được ≥40% thời gian review và giữ quy tắc "không merge khi critical test fail", tôi có nhiều thời gian hơn cho thiết kế kiến trúc.
Câu hỏi tôi chưa chắc: bài này có thật sự cần AI reviewer, hay chỉ cần test + CI + chia task nhỏ hơn là đủ?
```

**Câu hỏi tôi muốn nhóm challenge (1-2 câu hỏi đúng chỗ yếu):**

```text
- Nếu đã có unit test, CI và linter, phần nào của việc review còn lại thật sự cần AI? Hay đây chỉ là process fix (chia task nhỏ, viết acceptance criteria trước)?
- Kiến trúc tôi thiết kế cho AI làm đã đúng và hiệu quả chưa, và làm sao có ground truth để đo "AI reviewer bắt đúng lỗi" khi mỗi feature/project lại khác nhau?
```

**AI phản biện Card (nếu có):**
- Điểm yếu AI chỉ ra: Problem ban đầu ("build sản phẩm từ đầu bằng AI") quá rộng và đang solution-first; nếu không kiểm soát kỹ từng bước thì khả năng fail khá cao. Ngoài ra chưa có số đo thật và chưa so sánh với phương án không dùng AI (CI, test, linter).
- Tôi sửa gì: Thu hẹp card về đúng một bottleneck là "review và kiểm chứng code AI sinh ra"; bổ sung non-AI alternative và đặt CI/test làm gate bắt buộc; áp dụng nguyên tắc khi AI chạy xong từng bước thì tôi check code, check thuật toán trước khi để AI chạy bước tiếp theo.

**Kết quả sau khi nhóm challenge:**
- Nhóm nhận xét card #3 mạnh nhưng scope còn rộng, khó tạo pilot có ground truth trong thời gian lab; card #2 (root cause) tiềm năng nhưng cần thu hẹp vào Jetson/CUDA/TensorRT.
- Tôi đồng ý chuyển sang candidate #6 (phát hiện ID switch) của nhóm vì actor, workflow và bottleneck cụ thể hơn và nhóm có dữ liệu tracking để thử. Chi tiết ở `02-group-problem-statement/group-report.md`.

### Self-check nộp phần 01
- [x] Có 5+ problems (10 problems) + top 3 Cards đủ field
- [x] Mỗi Card có workflow trước/sau + bottleneck + metric + fallback
- [x] Đã chọn 1 card pitch + câu hỏi challenge
